# Include & Joins

## Includes In Rails:

N + 1 queries occur when a group of records are loaded from the database in an inefficient way, along with any records associated with them.

We have two tables employee and forms

Forms belongs to employee and employees has many forms

Employee.all.map { |employee| employee.forms }.flatten

The SQL for this command looks like:

> SELECT `employees`.* FROM `employees` ORDER BY `employees`.`id`

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` = 1

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` = 2

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` = 3

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` = 4

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` = 5

There are 6 total hits to the database being made.

Rails provides an [ActiveRecord method called :includes](https://apidock.com/rails/ActiveRecord/QueryMethods/includes) which loads associated records in advance and limits the number of SQL queries made to the database. This technique is known as "eager loading" and in many cases will improve performance by a significant amount.

Depending on what your query is, :includes will use either the ActiveRecord method :preload or :eager_load.

## **Pre_load with Includes**
In most cases :includes will default to use the [method :preload](https://apidock.com/rails/ActiveRecord/QueryMethods/preload) which will fire 2 queries:

1. Load all records tied to the leading model
2. Load records associated with the leading model based off the foreign key on the associated model or the leading model

So, if we introduced :preload to our query we would produce only 2 SQL selects where forms would be loaded, based off the foreign key Form#employee_id.

Employee.preload(:forms).map { |employee| employee.forms }.flatten

> SELECT `employees`.* FROM `employees`

> SELECT `forms`.* FROM `forms` WHERE `forms`.`employee_id` IN (1, 2, 3, 4, 5)

The SQL for this example would look the exact same if we were to replace :preload with :includes.

Employee.includes(:forms).map { |employee| employee.forms }.flatten

## **Eagerload with Includes**

:includes will default to use :preload unless you reference the association being loaded in a subsequent clause, such as :where or :order. When constructing a query this way, you also need to explicitly reference the eager loaded model.

Employee.includes(:forms).where('forms.kind = "health"').references(:forms)

In this case, :includes will use the [method :eager_load](https://apidock.com/rails/v4.2.7/ActiveRecord/QueryMethods/eager_load) which will produce 1 query that uses left outer joins to build an intermediary table which is then used to construct the model output.

> SELECT `employees`.`id` AS t0_r0, `employees`.`name` AS t0_r1, `forms`.`id` AS t1_r0, `forms`.`employee_id` AS t1_r1, `forms`.`kind` AS t1_r2 LEFT OUTER JOIN `forms` ON `forms`.`employee_id` = `employees`.`id` WHERE (forms.kind = "health")

If the query were reversed, where forms were loaded first and we wanted to efficiently load the employee association, we can still use :includes. The query will load employees based off the collection of Employee#ids, which is referenced from Form#employee_id.

Form.includes(:employee)

> SELECT `forms`.* FROM `forms`

> SELECT `employees`.* FROM `employees` WHERE `employees`.`id` IN (1, 2, 3, 4, 5)

## EAGER LOADER WITH NESTED ATTRIBUTES

Yes. Here are a few examples of different scenarios you could use if the Form model was modified to have additional associations such as has_one: :signer and has_one: issuer, which has_one: :address.

Employee.includes(forms: :issuer)

Employee.includes(forms: { issuer: :address })

Employee.includes(forms: [{ issuer: :address }, :signer])

:includes will improve the performance significantly when a :preload is invoked, but has the opposite effect for :eager_load in most cases. :eager_load constructs a complex query to gather information about the associations being loaded, thus it makes sense that this option would be slower.ss

## **Joins in Rails**

If we have one more field with employee where employee have active field and wants form for that employee who are activated we create join query

Employee.where(status: "active")

But what if we want to load all active employees who belong to forma that are verified? Without joins, you would write something like this:

active_employees = Employee.where(status: "active")

active_employees.select **do** |employee|

employee.form.verified?

end

This isn’t great because it triggers an N + 1 query since it is looking in the database for a company record for each employee in the loop. I ran a similar query in a MySQL database containing 62 employee records and 3 forms records. This unoptimized query took about 1 second to run on average.

We can easily improve the code above by using :joins.

Employee.where(status: "active").joins(:forms).where(forms: { verified: true })

Running this optimized query in the same database described from above took about 0.5 seconds on average.

Employee.where(status: "active").joins(:company)

We would be loading all active employees who belong to a company. If an employee is not associated with a company, then they would not be returned. This is because [:joins performs a SQL inner join by default](https://apidock.com/rails/ActiveRecord/QueryMethods/joins).

Adding the clause where(companies: { verified: true }) scopes companies so that only employee’s with verified companies are returned. Note that this section of the query uses companies as a keyword since it is referring to the *table name*. The SQL output would look like this:

**SELECT** `employees`.* **FROM** `employees` **INNER JOIN** `forms` **ON** `form`.`id` = `employee`.`forn_id’ **WHERE** `employees`.`status` = 'active' **AND** `form`.`verified` = 1

Joins with associationEmployee.joins(forms: [:issuer])

## **When to use :includes or Joins**

includes is a method in ActiveRecord used to preload data in order to avoid N + 1 queries. Use :joins when you solely need to filter data based on associated tables and use :includes if you need to reference data in associated tables later on. For example, we’d want to use :includes if we were to load all active employees for forms that are verified and then print each employee’s name and their form.
