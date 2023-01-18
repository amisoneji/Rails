## 1)ORM:

- [Object Relational Mapping](https://en.wikipedia.org/wiki/Object-relational_mapping), commonly referred to as its abbreviation ORM, is a technique that connects the rich objects of an application to tables in a relational database management system. Using ORM, the properties and relationships of the objects in an application can be easily stored and retrieved from a database without writing SQL statements directly and with less overall database access code.
- An ORM provides a mapping layer between how a database handles its data and how an object-oriented application handles its data. It maps database tables to classes, database table rows to objects, and database tables columns to object attributes. Active Record mainly carries out the mapping process for you. While using Active Record, you have to no longer deal with database constructs like tables, rows or columns. Your application only deals with classes, attributes and objects.

## **Active Record Basics**

- **Active Record Classes and Objects**

Each table in a database is generally represented by a class that extends Active Record base class. By extending Active Record base classes, model objects inherit a lot of functionalities.While using Active Records, you don't have to set up any database connections. It manages all the database connections for an application. It adds attributes to your class for each of the columns in the database.

- **Active Record naming conventions**

Active Record uses the CoC (convention over configuration) principle. On following naming convention, you can take advantage of many dynamic features of Active Record without any configuration.

## **2) Explain what [Rack](https://www.jetbrains.com/help/ruby/rake.html#:~:text=Rake%20is%20a%20popular%20task,backup%20databases%2C%20and%20so%20on.) means in Ruby on Rails.**

Rake is a popular task runner for Ruby and Rails applications. For example, Rails provides the predefined Rake tasks for creating databases, running migrations, and performing tests. You can also create custom task to automate specific actions - run code analysis tools, backup databases, and so on.

Rake also makes a few things easier, like finding files that match a certain pattern & that have been modified recently

- **Rake** is a task runner.
- **Rack** helps Ruby servers & frameworks work together.

[https://lh4.googleusercontent.com/0PPCdqj8yoisLhOJoS5HbIZyHi4h28ZXmqhC9l61zp6ZNjxxDrQq0sMFLpg6TgGaDdRkc3T20q1KUqScuMNYVNQmQ0mk1wejNpUNj6QtjiBw0HDRFOVBP3uh7LrdHY7PTzXHVbfgkTE_P0kkG9QxrLPfCUDta-yyFZ85ZseLBy0-ApERU27df6WPUGIAfw](https://lh4.googleusercontent.com/0PPCdqj8yoisLhOJoS5HbIZyHi4h28ZXmqhC9l61zp6ZNjxxDrQq0sMFLpg6TgGaDdRkc3T20q1KUqScuMNYVNQmQ0mk1wejNpUNj6QtjiBw0HDRFOVBP3uh7LrdHY7PTzXHVbfgkTE_P0kkG9QxrLPfCUDta-yyFZ85ZseLBy0-ApERU27df6WPUGIAfw)

## **3) Explain what Ruby on Rails is.**

[https://www.clariontech.com/blog/what-is-ruby-on-rails-a-brief-walk-through](https://www.clariontech.com/blog/what-is-ruby-on-rails-a-brief-walk-through)

**4)What is meant by “[Rails Migration](https://stackify.com/rails-migration-a-complete-guide/#:~:text=A%20Rails%20migration%20is%20a,app%20to%20a%20new%20platform.)”?**

A Rails migration is a tool for changing an application’s database schema. Instead of managing SQL scripts, you define database changes in a domain-specific language (DSL). The code is database-independent, so you can easily move your app to a new platform. You can roll migrations back, and manage them alongside your application source code.

Migrations keep your database schema changes with your application code. They’re written in Ruby and versioned with the rest of your app. Sure, you can (and should) version your SQL files, but do they belong in the same place? Not everyone feels the same way about that question. But it’s not an issue with Rails.

Migrations are additive. Each one represents a new version of your database schema. Rails applications can evolve, and publishing a new migration with a new release of your application isn’t unusual.

As we’ll see in the example below, Active Record uses migrations to update your app’s schema in *schema.rb.* This file is what Rails uses to deploy your application to a new database. So using migrations makes it possible for you to deploy your app to new platforms. You can develop on one database and deploy to another, or deploy to a new database platform in production

## **5)What does the subdirectory *app/controllers* do?**

## **6)Explain what *load* does in Ruby on Rails.**

The load method simply reads and parses other files into your code every time a script is executed.

Another commonly used method is require. It reads the file from the file system, parses it, saves to the memory and runs it in a given place. What does it mean? Simply, even if you change the required file when the script is running, those changes won't be applied - Ruby will use the file from memory, not from the file system.

In most cases you’ll use require, but there are some cases when load is useful, for example, when your module changes frequently you may want to pick up those changes in classes that load this module.

- require reads and parses files only once, when they were referenced for the first time.
- load reads and parses files every time you call load.

## **7) include vs extend?**

[LINK](https://prograils.com/ruby-methods-differences-load-require-include-extend)

## **8)What is a helper in Ruby on Rails?**

A helper is a [method](https://www.rubyguides.com/2019/06/ruby-method-definition/) that is (mostly) used in your Rails views and sometimes with controllers to share reusable code. Rails comes with a set of built-in helper methods.

One of these built-in helpers is time_ago_in_words.

## **9)Outline three components of Rails.**

[https://www.careerride.com/view/what-are-the-different-components-of-rails-ruby-on-rails-2426.aspx](https://www.careerride.com/view/what-are-the-different-components-of-rails-ruby-on-rails-2426.aspx)

## **10) Explain what “scaffolding” is.**

Scaffolding in Ruby on Rails refers to the **auto-generation** of a set of a model, views, and a controller usually used for a single database table.

## **11)]Explain which symbols developers use to define variables, global variables, and class variables**.

## **Local variables**

A local variable name starts with a lowercase letter or underscore (_). It is only accessible or have its scope within the block of its initialization. Once the code block completes, variable has no scope.

When uninitialized local variables are called, they are interpreted as call to a method that has no arguments.

## **Class variables**

A class variable name starts with @@ sign. They need to be initialized before use. A class variable belongs to the whole class and can be accessible from anywhere inside the class. If the value will be changed at one instance, it will be changed at every instance.

A class variable is shared by all the descendents of the class. An uninitialized class variable will result in an error.

## **Instance variables**

An instance variable name starts with a @ sign. It belongs to one instance of the class and can be accessed from any instance of the class within a method. They only have limited access to a particular instance of a class.

They don't need to be initialize. An uninitialized instance variable will have a nil value.

**Global variables**

A global variable name starts with a $ sign. Its scope is globally, means it can be accessed from any where in a program.

An uninitialized global variable will have a nil value. It is advised not to use them as they make programs cryptic and complex.

There are a number of predefined global variables in Ruby.

## **12)What are the benefits of using Ruby on Rails?**

[LINK](https://aristeksystems.com/blog/why-use-ruby-on-rails-for-your-project/)

## **13)What is gem?**

A gem in Ruby programming language is a software package in which Ruby applications or libraries can be distributed in a single format.

We can use that method. But sometimes, if the code seems more general than the project-specific code, it should be converted to a gem so that it can be reused and shared with multiple projects. This will ultimately help you to maintain a clean line of code as well as will reduce the duplication of the code.

## **14)What is a plugin in Ruby on Rails?zz**

**Gem**

Gem is a packaged ruby application using the packaging system defined by RubyGems.

Rails itself is a Gem.

Rails gem is installed in jruby-1.0\lib\ruby\gems\1.8\gems\rails-1.2.3 as:DIR bin

DIR builtin

68,465 CHANGELOG

DIR configs

DIR dispatches

DIR doc

DIR environments

307 fresh_rakefile

DIR helpers

DIR html

DIR lib

1,072 MIT-LICENSE

11,969 Rakefile

The lib directory contains all the gem source code.We can install,upgrade and query the gem version.If one uses a tool like my GemInstaller, one can easily automate the installation and loading of RubyGems with a single simple config file.

Gem installed for Ruby interpreter can be used system-wide by that interpreter.

Gem may be published as a plugin.

Can also be vendored in vendor/gems.

**Plugin**

Plugin is an extension of Rails Framework.

Can not be upgraded by using a command. To upgrade one have to uninstall and then install upgraded version.

Has to be hooked into rails application. (has to have init.rb)

Have an install.rb file.

\]

Plugin cannot be published as a Gem.

Can only be used application wide.

Goldspike plugin is installed in vendor\plugins\rails-integration directory of the application as:

7,089 build.xml

1,141 LICENSE.txt

DIR plugins

6,675 pom.xml

1,447 README

DIR samples

plugins/goldspike directory consists of

24 init.rb

25 install.rb

DIR lib

549 Rakefile

536 README

DIR tasks

DIR test

The lib directory contains all the plugin source code.

**Gem vs Plugins**

Rails had a way of loading plugins from the vendor/plugins/ directory. This will most likely deprecate as Rails has added support for bundling gems with the project in the vendor/gems/ directory. The gem versions of rspec are the ones that are intended for everyday use. One should go with those

unless you are supporting a Rails application in the 1.2.x family or earlier.

It often becomes quicker to check-in and check-out of a repository using Gems as you are not including the library in your actual application. There are often lesser problems using Plugins related to incompatibility arising concerning software versions among the distributed team.

General rule of thumb is to make Rails-specific functionality a plugin while making more general Ruby libraries into gems.

**Engine**

An Engine in rails terminology is actually a sub application of a web-application. For instance, something like a blog, a forum, or simple authentication: these are not full-blown applications, but pages/views/controllers/models that can be added to any rails application.

In rails2 this would be done using a plugin. Now since rails3 an engine can be packaged in a gem.

A gem: is a generic library, which can be easily installed, which are version-managed, have dependencies and such.

An engine: is a sub-application of a Rails application, and since Rails 3 these are distributed as a gem (which is awesome!).

So when will you use one or the other:

create a gem if you want to share ruby-functionality

create an engine (and package it in a gem) if you have parts of your rails application that can be used more generally.

**The basic difference is a gem is something that needs to be installed on the system running your Rails application, whereas a plugin is deployed along with your application. More specifically, plugins live in vendor/plugins whereas gems need to be install using rake gem install gem_name.**

## **15)What is the difference between nil and false in Ruby?**

null means no data value but memory is still allocated for null. false is a boolean, it is simply not true.

" false is false, 0 is an integer, and nil is no value.

true is true, 1 is an integer, and nil is no value

Numbers, strings, and all other values evaluate to true.

nil evaluates to false. However, nil is not strictly equal to false, because false is a boolean datatype while nil has no datatype."

Credits: [https://www.sololearn.com/Profile/1221076/?ref=app](https://www.sololearn.com/Profile/1221076/?ref=app)

" The differences of the methods nil and false are:

- nil cannot be a value, where as a false can be a value
- A method returns true or false in case of a predicate, other wise nil is returned.
- false is a boolean data type, where as nil is not.
- nil is an object for NilClass, where as false is an object of for FalseClass
- False is a boolean datatype

Nil is not a data type."

## **16)Explain what *delete* does in Ruby on Rails.**

The **delete()** is an inbuilt method in [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) which deletes the given object from the set and returns the self object. In case the object is not present, it returns self only.

As you can see, using destroy also removes a given id (or ids) from a table. However, an object is instantiated first, therefore all [callbacks](https://medium.com/@david.chase4/the-art-of-the-callback-bc95f8d453c9) and filters are fired off before the object is “deleted”. Because of the extra callbacks and validations performed before the object is “deleted”, this method is less efficient than ActiveRecord#delete, but it allows cleanup methods and other actions to be run. Essentially, this finds the given id, creates a new object from the attributes, and then calls destroy on it (performing any dependencies and callbacks).

When responding to this question, candidates shouldn’t get confused between ***delete*** and ***destroy***. They should be able to explain that ***delete*** deletes a record, whereas ***destroy*** both deletes a record and executes any callbacks on the model.

## **17)Describe what destructive methods are?**

The difference is simply that flatten returns a copy of the array (a new array that is flattened) and flatten! does the modification "in place" or "destructively." The term destructive means that it modifies the original array. This is useful for when you know what you want your end result to be and don't mind if the original structure gets changed.

As @padde pointed out, it will consume less memory as well to perform something destructively since the structure could be large and copying will be expensive.

However, if you want to keep your original structure it is best to use the method and make a copy.

## 18)What is a filter in Ruby on Rails?

Rails filters are methods that run before or after a controller's action method is executed. They are helpful when you want to ensure that a given block of code runs with whatever action method is called.

Rails before filters are executed before the code in action controller is executed. The before filters are defined at the top of a controller class that calls them. To set it up, you need to call before_filter method.

- **Public:** These methods are accessible from any external class or method that uses the same class in which they are defined.
- **Protected:** These methods are accessible only within the class in which they are defined and in the classes that inherit from the class in which they are defined.
- **Private:** These methods are only accessible within the class in which they are defined.

## 

## **19)Explain what observers are in Ruby on Rails.**

Observers register themselves in the model class they observe, since it is the class that notifies them of events when they occur. As a side-effect, when an observer is loaded its corresponding model class is loaded.

Up to (and including) [Rails](https://api.rubyonrails.org/v3.2.16/classes/Rails.html) 2.0.2 observers were instantiated between plugins and application initializers. Now observers are loaded after application initializers, so observed models can make use of extensions.

If by any chance you are using observed models in the initialization you can still load their observers by calling ModelObserver.instance before. Observers are singletons and that call instantiates and registers them.

*The observer pattern is used when you are building a system where the state of one object effects the state of other objects.*

- ***Push vs Pull***

In the default implementation, the notification sent to the observer doesn’t specify which of the Subjects attributes has changed. To find out which attribute has changed, the Observer has to check the Subjects attributes, this is the ***pull*** method.

Another approach would be the ***push*** method where the notification includes other attributes which provide the Observer with additional information like the examples below.

## **20) what are call backes in ruby and rails?**

## Callbacks are methods that get called at certain moments of an object's life cycle. With callbacks it is possible to write code that will run whenever an Active Record object is created, saved, updated, deleted, validated, or loaded from the database.

### **[Creating an Object](https://guides.rubyonrails.org/active_record_callbacks.html#creating-an-object)**

- [before_validation](https://api.rubyonrails.org/v7.0.3/classes/ActiveModel/Validations/Callbacks/ClassMethods.html#method-i-before_validation)
- [after_validation](https://api.rubyonrails.org/v7.0.3/classes/ActiveModel/Validations/Callbacks/ClassMethods.html#method-i-after_validation)
- [before_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-before_save)
- [around_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-around_save)
- [before_create](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-before_create)
- [around_create](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-around_create)
- [after_create](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-after_create)
- [after_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-after_save)
- [after_commit](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_commit) / [after_rollback](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_rollback)

### **[3.2 Updating an Object](https://guides.rubyonrails.org/active_record_callbacks.html#updating-an-object)**

- [before_validation](https://api.rubyonrails.org/v7.0.3/classes/ActiveModel/Validations/Callbacks/ClassMethods.html#method-i-before_validation)
- [after_validation](https://api.rubyonrails.org/v7.0.3/classes/ActiveModel/Validations/Callbacks/ClassMethods.html#method-i-after_validation)
- [before_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-before_save)
- [around_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-around_save)
- [before_update](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-before_update)
- [around_update](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-around_update)
- [after_update](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-after_update)
- [after_save](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-after_save)
- [after_commit](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_commit) / [after_rollback](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_rollback)

### **[3.3 Destroying an Object](https://guides.rubyonrails.org/active_record_callbacks.html#destroying-an-object)**

- [before_destroy](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-before_destroy)
- [around_destroy](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-around_destroy)
- [after_destroy](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Callbacks/ClassMethods.html#method-i-after_destroy)
- [after_commit](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_commit) / [after_rollback](https://api.rubyonrails.org/v7.0.3/classes/ActiveRecord/Transactions/ClassMethods.html#method-i-after_rollback)

after_save runs both on create and update, but always *after* the more specific callbacks after_create and after_update, no matter the order in which the macro calls were executed.

## **19)Explain what harnesses are.?**

[LINK](https://www.rubydoc.info/gems/harness/0.2.8)

## **21)What are fixtures in Ruby on Rails?**

Fixtures are data that you can feed into your unit testing. They are automatically created whenever rails generates the corresponding tests for your controllers and models. They are only used for your tests and cannot actually be accessed when running the application.

By default, Rails provides two fixtures named 'one' and 'two' every time. You can change them as you so please, Also, the data that goes into the fixtures is made when you pass in the keys for the database columns you want when using the generator. In the the first example were you used rails g model Post title:string... you created a model called Post and passed in two keys: :title and :text

## **22)Explain what a symbol is in Ruby on Rails.**

**Symbol** is the most basic Ruby object we can create. It's just a name and an internal ID. Since a given symbol name refers to the same object throughout a Ruby program, Symbols are useful and more efficient than strings. Two strings with the same contents are two different objects, but for any given name, there is only one Symbol object. This can save both time and memory.

**Using symbols not only saves time when doing comparisons, but also saves memory, because they are only stored once.**

Ruby Symbols are immutable (can't be changed), which makes looking something up much easier

Using symbols not only saves time when doing comparisons, but also saves memory, because they are only stored once.

Symbols in Ruby are basically "immutable strings" .. that means that they can not be changed, and it implies that the same symbol when referenced many times throughout your source code, is always stored as the same entity, e.g. has the same object id.

**Strings on the other hand are mutable**, they can be changed anytime. This implies that Ruby needs to store each string you mention throughout your source code in it's separate entity, e.g. if you have a string "name" multiple times mentioned in your source code, Ruby needs to store these all in separate String objects, because they might change later on (that's the nature of a Ruby string).

If you use a string as a Hash key, Ruby needs to evaluate the string and look at it's contents (and compute a hash function on that) and compare the result against the (hashed) values of the keys which are already stored in the Hash.

If you use a symbol as a Hash key, it's implicit that it's immutable, so Ruby can basically just do a comparison of the (hash function of the) object-id against the (hashed) object-ids of keys which are already stored in the Hash. (much faster)

**Downside:** Each symbol consumes a slot in the Ruby interpreter's symbol-table, which is never released. Symbols are never garbage-collected. So a corner-case is when you have a large number of symbols (e.g. auto-generated ones). In that case you should evaluate how this affects the size of your Ruby interpreter.

**Notes:**

If you do string comparisons, Ruby can compare symbols just by comparing their object ids, without having to evaluate them. That's much faster than comparing strings, which need to be evaluated.

If you access a hash, Ruby always applies a hash-function to compute a "hash-key" from whatever key you use. You can imagine something like an MD5-hash. And then Ruby compares those "hashed keys" against each other.

Every time you use a string in your code, a new instance is created - string creation is slower than referencing a symbol.

Starting with Ruby 2.1, when you use frozen strings, Ruby will use the same string object. This avoids having to create new copies of the same string, and they are stored in a space that is garbage collected.

## **23)Explain what a proc is.?**

A Proc object is an encapsulation of a block of code, which can be stored in a local variable, passed to a method or another [Proc](https://ruby-doc.org/core-2.6/Proc.html), and can be called. [Proc](https://ruby-doc.org/core-2.6/Proc.html) is an essential concept in Ruby and a core of its functional programming features.

Procs are coming in two flavors: lambda and non-lambda (regular procs). Differences are:

- In lambdas, return means exit from this lambda;
- In regular procs, return means exit from embracing method (and will throw LocalJumpError if invoked outside the method);
- In lambdas, arguments are treated in the same way as in methods: strict, with ArgumentError for mismatching argument number, and no additional argument processing;
- Regular procs accept arguments more generously: missing arguments are filled with nil, single [Array](https://ruby-doc.org/core-2.6/Array.html) arguments are deconstructed if the proc has multiple arguments, and there is no error raised on extra arguments.
- 

def test_return

-> { return 3 }.call  	# just returns from lambda into method body

proc { return 4 }.call	# returns from method

return 5

End

test_return # => 4, return from proc

## **24)What is a Gemfile in Ruby on Rails?**

A Gemfile is a file we create which is used for **describing gem dependencies for Ruby programs**. A gem is a collection of Ruby code that we can extract into a “collection” which we can call later. It lets you specify which gems you want to use, and which versions of these gems to use.

## **25)Count vs size:**

1) In rails count is a ActiveRecord method, therefore count can be applied on model name directly as:

> User.count

(1.4ms)  SELECT COUNT(*) FROM "users"

=> 1

But size is not ActiveRecord method therefore it will throw an error

> User.size

"NoMethodError".

2) Size in rails can be used with ActiveRecord array (ie. size is Array method)

> User.all.size

(1.2ms)  SELECT COUNT(*) FROM "users"

=> 1

3) count will always fire ActiveRecord query. but size will not fire ActiveRecord query, only if record or ActiveRecord array is already loaded (executed) as:

> d=User.all

User Load (18.1ms)  SELECT "users".* FROM "users"

=> #<ActiveRecord::Relation [#<User id: 1, email: "fasf@f.df", name: "mano", dob: "2017-02-16", address: "fasfafasf", created_at: "2017-02-12 08:16:12", updated_at: "2017-02-12 09:34:07", online: false>]

If "addresses" is an association which it looks like, then they are different but they should return the same result.

#count is provided by ActiveRecord and will execute something like "select count(*) from addresses where user_id = ".

In the other cases, #addresses will build an array containing actual model objects and #size and #length are provided by the Array class or maybe Enumerable.

So #count is probably faster, because the counting happens in the database. Not much good if you actually need the addresses tho :)

## **26)[what is the difference between link_to, redirect_to, and render?](https://stackoverflow.com/questions/17236122/what-is-the-difference-between-link-to-redirect-to-and-render)**

**render :index** says, ‘combine the data I've prepared (@books = Book.all) with the books/index.html.erb view template to generate a complete HTML document, then send that back to the client.’

**redirect_to @book** says, ‘tell the client to start the whole process over again, issuing a new GET request to url_for(@book).

If you omit both, the action will render a template with the same name as the action itself. In other words, you only need to call render explicitly when the view template you want doesn’t match the action you’re rendering it from.

Note that not every controller action has a corresponding view template. Generally, #create, #update, and #destroy (which are all routed to non-GET HTTP requests) attempt to make some change to the database and then either redirect_to some resource (if it succeeded) or re-render the form that preceded it, along with any errors (if it failed).

"redirect_to" will cause the browser to make a new request, whereas "render" renders the specified view for the current request. It is important to use redirect_to after mutating the database or application state. Otherwise, if the user refreshes the page, the browser will make the same request, and the mutation will be repeated.

As for "link_to", the link_to helper renders a link with its first argument as the link's text and its second argument as the link's destination. If we pass a model object as the second argument, link_to will call the appropriate path helper to convert the object to a path. For example, if we pass an article, link_to will call article_path.

## **27)Explain what is Interpolation in Ruby?**

#{variable}

## **28) Tell me about getters and setters in Ruby**

**Ans:**

A getter allows accessing an instance variable. A setter allows setting an instance variable.

It’s possible to manually define getter and setter methods.

But Ruby provides three accessor methods that do the same thing and are cleaner: attr_reader (getter), attr_writer (setter), and attr_accessor (setter and getter).

**29)What is the meaning of “skinny controllers, skinny models”?**

As a codebase grows, fat models get out of hand, start doing too many things and become unmanageable. Models should handle persistence without being bloated with logic.

Models can be made skinnier by keeping the single responsibility principle in mind and moving logic out of models, and into other design patterns like service objects.

## **29) What is a PORO?**

**Ans:**

PORO stands for “Plain Old Ruby Object”.

Although almost everything in Ruby is an object, ActiveRecord tends to use a lot of complex objects. So, the term PORO is typically to stress a small, simple object used to support business logic.

## **30) Does Ruby allow multiple inheritances?**

**Ans:**

Ruby does not allow inheriting from more than one parent class, but it does allow module mixins with include and extend.

## **31)What frameworks have you used for backgrounding jobs?**

**Ans:**

- Delayed::Job: Easy to set up and use. Queues are stored in a database table. If the same database is used for Delayed::Job and production, then a large number of jobs could turn the database into a bottleneck.
- Sidekiq: Uses Redis to queue jobs. Redis is an in-memory data store so it’s very fast. Sidekiq adds complexity to infrastructure because Redis needs to be added.
- Sucker Punch: Runs as a Ruby process and keeps all jobs in memory. Jobs are lost if the process crashes. Not recommended for critical tasks.

## **32)What is Rack?**

Ans: Rack is an API sitting between the web server and Rails. It allows plugging in and swapping frameworks like Rails with Sinatra, or web servers like Unicorn with Puma.

## **33) What is content_for for?**

**Ans:**

It allows defining and rendering content in views. This is useful for defining content in one place and rendering it in many.

<div>

<h1> This is the wrapper!</h1>

<%= yield :my_content %>

</div>

<% content_for :my_content do %>

This is the content.

<% end %>

**Result:**

<div>

<h1> This is the wrapper!</h1>

This is the content.

</div>

## **34) What is the difference between Hash and JSON?**

**Ans:**

Hash is a Ruby class, a collection of key/value pairs that allows accessing values by keys.

JSON is a string in a specific format for sending data.

## **35) What is Spring?**

**Ans:**

Spring is an application preloader. It keeps the application running in the background so booting is not required any time you run a migration or rake task.

Developers use [Spring](https://www.testgorilla.com/test-library/programming-skills-tests/spring-test/) as a preloader for applications to speed up development. They can use it to keep the app running in the background when running tests, rake tasks, or migrations. With Spring, developers don’t have to restart the server when they make changes.

## **36). What is the asset pipeline?**

**Ans:**

It’s a framework that prepares JavaScript and CSS for the browser.

## **37) What is the splat operator?**

**Ans:**

Splat is used when you don’t want to specify the number of arguments passed to a method in advance. Ruby has two splat operators, the single splat and double splat.

The single splat works as you’d expect:

The double splat is like the single splat but it takes key/values as arguments.

## **38) What’s a scope?**

**Ans:**

A scope is ActiveRecord query logic that you can define inside a model and call elsewhere.

Defining a scope can be useful rather than duplicating the same logic in many places in the app.

## **39)What is Initializers in Ruby on Rails?**

An initializer is **any file of ruby code stored under /config/initializers in your application**. You can use initializers to hold configuration settings that should be made after all of the frameworks and plugins are loaded.

## **40) Explain what ActiveJob is.?**

Active Job is a framework for declaring jobs and making them run on a variety of queuing backends. These jobs can be everything from regularly scheduled clean-ups, to billing charges, to mailings. Anything that can be chopped up into small units of work and run in parallel, really.

The main point is to ensure that all Rails apps will have a job infrastructure in place. We can then have framework features and other gems build on top of that, without having to worry about API differences between various job runners such as Delayed Job and Resque. Picking your queuing backend becomes more of an operational concern, then. And you'll be able to switch between them without having to rewrite your jobs.

- Delayed::Job: Easy to set up and use. Queues are stored in a database table. If the same database is used for Delayed::Job and production, then a large number of jobs could turn the database into a bottleneck.
- Sidekiq: Uses Redis to queue jobs. Redis is an in-memory data store so it’s very fast. Sidekiq adds complexity to infrastructure because Redis needs to be added.
- Sucker Punch: Runs as a Ruby process and keeps all jobs in memory. Jobs are lost if the process crashes. Not recommended for critical tasks.

## **41)Explain what Strong Parameters are.?**

Strong Parameters is a feature of Rails that prevents assigning request parameters to objects unless they have been explicitly permitted. It has its own DSL (Domain Specific Language, or in other words, a predefined syntax it understands), that allows you to indicate what parameters should be allowed. It also lets you indicate if each parameter should be a hash, array or scalar (i.e. integer, string, etc.), as well as some other functionality that is not relevant for this post.

## **42)Does Ruby support single inheritance?**

Ruby supports only *single class inheritance*, it does not support multiple class inheritance but it supports *mixins*.

**Key terms in Inheritance:**

**Super class:** The class whose characteristics are inherited is known as a *superclass* or *base class* or *parent class*.

**Sub class:** The class which is derived from another class is known as a *subclass* or *derived class* or *child class*. You can also add its own objects, methods in addition to base class methods and objects, etc.

## **43)Give an example of a filter in Ruby on Rails.**

Before_action,after_actions

## **44)Explain what dynamic finders are.**

## Options for Finders

You can use following option along with **find** function.

- **:order => 'name DESC'** Use this option to sort the result in ascending or descending order.
- **:offset => 20** Starts fetching records from offset 20.
- **:limit => 20** Returns only 20 records.
- **:group => 'name'** This is equivalent to sql fragment GROUP BY.
- **:joins => LEFT JOIN ...'** Additional LEFT JOIN (rarely used).
- **:include => [:account, :friends]** This is LEFT OUTER JOIN with these model.
- **:select => [:name, :address]** Use this instead of SELECT * FROM.
- **:readonly => true** Use this to make objects write protected.
- Person.find_by_user_name(user_name)
- Person.find_all_by_last_name(last_name)

## **45)How would you use two databases for one application?**

[https://medium.com/@shilpikayal/dual-database-connection-in-rails-76ca42e276a7](https://medium.com/@shilpikayal/dual-database-connection-in-rails-76ca42e276a7)

## **46) Explain what a Rails engine is.?**

Rails::Engine allows you to wrap a specific [Rails](https://api.rubyonrails.org/classes/Rails/Rails.html) application or subset of functionality and share it with other applications or within a larger packaged application. Every [Rails::Application](https://api.rubyonrails.org/classes/Rails/Application.html) is just an engine, which allows for simple feature and application sharing.

Any Rails::Engine is also a [Rails::Railtie](https://api.rubyonrails.org/classes/Rails/Railtie.html), so the same methods (like rake_tasks and generators) and configuration options that are available in railties can also be used in engines.

## **47)Is Ruby a flexible language? Why, or why not?**

## **48)Explain whether instance methods are private or public.**

**Private methods:** are methods defined under the private keyword. Private methods can only be used within the class definition; they’re for internal usage. The only way to have external access to a private method is to call it within a public method. Also, private methods can not be called with an explicit receiver, the receiver is always implicitly *self.* Think of private methods as internal helper methods.

- Both Python and Rails are cross-platform, making it convenient for the teams where they might use Linux or Windows.
- Python and Ruby are advanced scripting languages, which means their programs are not ought to be assembled.
- They support **object-oriented programming (OOP)**.
- Rails and Python can be used for building web applications that are scalable, portable and database-driven.
- A [GNU Debugger](https://sourceware.org/gdb/current/onlinedocs/gdb.html) (GDB) technique is presented in each language.
- Both are obtainable through Lambda functions at Amazon Web Services.
- Ruby, Python are both vigorously typed, which states that you can employ a variable without presenting it first.
- They possess clean syntax and are effortlessly readable.

## **49)How is Ruby on Rails different from Python?**

[https://learn.onemonth.com/ruby-vs-python/#:~:text=The%20Ruby%20on%20Rails%20web,their%20approaches%20to%20solving%20problems.](https://learn.onemonth.com/ruby-vs-python/#:~:text=The%20Ruby%20on%20Rails%20web,their%20approaches%20to%20solving%20problems.)

## **50)What is a closure in Ruby on Rails?**

In Ruby, closure is a function or a block of code with variables that are bound to the environment that the closure is called. Or in other words, closure can be treated like a variable that can be assigned to another variable or can be pass to any function as an argument.

- A closure block can be defined in one scope and can be called in a different scope.
- Closure always remember the variable within its scope at the creation time and when its called it can access the variable even if they are not in the current scope i.e *closure* retain its knowledge of it lexical environment at the time of defining.
- In Ruby, **Blocks**, **procs**, **lambdas** are clousers.

## **51)Explain the difference between *#equal* and *#==* ?**

[https://medium.com/@khalidh64/difference-between-eql-equal-in-ruby-2ffa7f073532](https://medium.com/@khalidh64/difference-between-eql-equal-in-ruby-2ffa7f073532)

## **52)Explain the difference between *Array#each* and *Array#map*.**

Array#each executes the given block for each element of the array, then returns the array itself.

Array#map also executes the given block for each element of the array, but returns a new array whose values are the return values of each iteration of the block.

## **53)Explain the difference between *raise*/*rescue* and *throw*/*catch.***

catch/throw are not the same as raise/rescue. catch/throw allows you to quickly exit blocks back to a point where a catch is defined for a specific symbol, raise rescue is the real exception handling stuff involving the Exception object.

## **54) Outline the types of associations models can have in Ruby on Rails.**

Candidates may respond to this Ruby on Rails interview question by mentioning that they use associations to create connections between models in a Rails application. They may then explain that Active Record supports three main types of associations:

- **One-to-one**: A relationship in which one object is linked to only one other object
- **One-to-many**: A relationship in which one object can be related to many other objects
- **Many-to-many**: A relationship in which an instance of the first type of object is linked to one or more instances of a second type of object, and an instance of a second type of object is linked to one or more instances of the first type of object

## **55) Difference between Include and joins**

Consider this scenario:

- A User has_many comments and a comment belongs_to a User.
- The User model has the following attributes: Name(string), Age(integer). The Comment model has the following attributes:Content, user_id. For a comment a user_id can be null.

## **Joins:**

**:joins performs a inner join between two tables. Thus**

Comment.joins(:user)

#=> <ActiveRecord::Relation [#<Comment id: 1, content: "Hi I am Aaditi.This is my first   comment!", user_id: 1, created_at: "2014-11-12 18:29:24", updated_at: "2014-11-12 18:29:24">,

#<Comment id: 2, content: "Hi I am Ankita.This is my first comment!", user_id: 2, created_at: "2014-11-12 18:29:29", updated_at: "2014-11-12 18:29:29">,

#<Comment id: 3, content: "Hi I am John.This is my first comment!", user_id: 3, created_at: "2014-11-12 18:30:25", updated_at: "2014-11-12 18:30:25">]>

will fetch **all records where user_id (of comments table) is equal to user.id (users table).** Thus if you do

Comment.joins(:user).where("comments.user_id is null")

#=> <ActiveRecord::Relation []>

You will get a empty array as shown.

Moreover joins does not load the joined table in memory. Thus if you do

comment_1 = Comment.joins(:user).first

comment_1.user.age

#=>←[1m←[36mUser Load (0.0ms)←[0m  ←[1mSELECT "users".* FROM "users" WHERE "users"."id" = ? ORDER BY "users"."id" ASC LIMIT 1←[0m  [["id", 1]]

#=> 24

## **Includes:**

:includes performs a **left outer join** between the two tables. Thus

Comment.includes(:user)

#=><ActiveRecord::Relation [#<Comment id: 1, content: "Hi I am Aaditi.This is my first comment!", user_id: 1, created_at: "2014-11-12 18:29:24", updated_at: "2014-11-12 18:29:24">,

#<Comment id: 2, content: "Hi I am Ankita.This is my first comment!", user_id: 2, created_at: "2014-11-12 18:29:29", updated_at: "2014-11-12 18:29:29">,

#<Comment id: 3, content: "Hi I am John.This is my first comment!", user_id: 3, created_at: "2014-11-12 18:30:25", updated_at: "2014-11-12 18:30:25">,

#<Comment id: 4, content: "Hi This is an anonymous comment!", user_id: nil, created_at: "2014-11-12 18:31:02", updated_at: "2014-11-12 18:31:02">]>

will result in **a joined table with all the records from comments table.** Thus if you do

Comment.includes(:user).where("comment.user_id is null")

#=> #<ActiveRecord::Relation [#<Comment id: 4, content: "Hi This is an anonymous comment!", user_id: nil, created_at: "2014-11-12 18:31:02", updated_at: "2014-11-12 18:31:02">]>

it will fetch records where comments.user_id is nil as shown.

Moreover includes loads both the tables in the memory. Thus if you do

comment_1 = Comment.includes(:user).first

comment_1.user.age

#=> 24

The moral is, use joins when you want to do conditional set operations and use includes when you are going to be using a relation on each member of a collection.

## **56) Seeds.rb**

### **Bootstrapping Data**

The purpose of seed data is to bootstrap your database. For example, if you have a users table where you track users' city and state, you may want to seed a related table with U.S. state names and abbreviations before creating the first user.

Likewise, you may also want to seed things like administrative accounts, or other data that's necessary to run your application for the first time. As a general rule, you shouldn't add anything to a seeds.rb file that isn't necessary to bootstrap your database or its relations.

### **Related Rake Tasks**

The seeds.rb file is where the seed data is stored, but you need to run the appropriate rake task to actually *use* the seed data. Using rake -T in your project directory shows information about following tasks:

- **rake db:seed** Load the seed data from db/seeds.rb
- **rake db:setup** Create the database, load the schema, and initialize with the seed data
- **rake db:reset** Same as rake db:setup, but drop the database first

So, you can run rake db:seed to run the seeds.rb file manually at any time. However, in most cases you will probably want to run rake db:setup or rake db:reset instead whenever you bootstrap your application.

## 57) What Are The Various Components Of Rail?

1. **Action Pack**: Action Pack is a single gem that contains Action Controller, Action View and Action Dispatch. The "VC" part of "MVC".
- Action Controller: Action Controller is the component that manages the controllers in a Rails application. The Action Controller framework processes incoming requests to a Rails application, extracts parameters, and dispatches them to the intended action.
- Action View: Action View manages the views of your Rails application. It can create both HTML and XML output by default. Action View manages rendering templates, including nested and partial templates, and includes built-in AJAX support.
- Action Dispatch: Action Dispatch handles routing of web requests and dispatches them as you want, either to your application or any other Rack application. Rack applications are a more advanced topic and are covered in a separate guide called Rails on Rack.
1. **Action Mailer**: Action Mailer is a framework for building e-mail services. You can use Action Mailer to receive and process incoming email and send simple plain text or complex multipart emails based on flexible templates.
2. **Active Model**: Active Model provides a defined interface between the Action Pack gem services and Object Relationship Mapping gems such as Active Record. Active Model allows Rails to utilize other ORM frameworks in place of Active Record if your application needs this.
3. **Active Record**: Active Record are like Object Relational Mapping (ORM), where classes are mapped to table, objects are mapped to columns and object attributes are mapped to data in the table.
4. **Active Resource**: Active Resource provides a framework for managing the connection between business objects and RESTful web services. It implements a way to map web-based resources to local objects with CRUD semantics.
5. **Active Support**: Active Support is an extensive collection of utility classes and standard Ruby library extensions that are used in Rails, both by the core code and by your applications.

## 58)Mention what are the positive aspects of Rails?

Rails provides many features like:

- **Meta-programming**: Rails uses code generation but for heavy lifting it relies on meta-programming. Ruby is considered as one of the best language for Meta-programming.
- **Active Record**: It saves object to the database through Active Record Framework. The Rails version of Active Record identifies the column in a schema and automatically binds them to your domain objects using metaprogramming
- **Scaffolding**: Rails have an ability to create scaffolding or temporary code automatically
- **Convention over configuration**: Unlike other development framework, Rails does not require much configuration, if you follow the naming convention carefully
- **Three environments**: Rails comes with three default environment testing, development, and production.
- **Built-in-testing**: It supports code called harness and fixtures that make test cases to write and execute.

## 59)Explain what is a *class library* in Ruby?

**Ruby class** libraries consist of a variety of domains, such as thread programming, data types, various domains, etc. These classes give flexible capabilities at a high level of abstraction, giving you the ability to create powerful Ruby scripts useful in a variety of problem domains. The following domains which have relevant class libraries are,

- GUI programming
- Network programming
- CGI Programming
- Text processing
