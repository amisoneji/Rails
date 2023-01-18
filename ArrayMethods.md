**Array Methods**

array = [0,1,2,3,4,5,6]

## . length

Return length of array

array.length => 7

**first**

Return first element of array

array.first => 0

**.last**

Retutrn last element of array.

Array.last  => 6

.**take**

The .take method returns the first n elements of the array

array.take(4) => [0, 1, 2, 3]

**.drop**

The .drop method returns the elements after n elements of the array

array.drop(3) =>  [3, 4, 5, 6]

**array index**

Return index element (start from 0th index)

Array[2] =>  2

**.pop**

The .pop method will permanently remove the last element of an array

array.pop() => 6

array => [0, 1, 2, 3, 4, 5]

array.pop(3) => [3, 4, 5] remove last three elements.

Array => [0, 1, 2]

**.shift**

The .shift method will permanently remove the first element of an array and return ths element:

array.shift() => 0

array => [1, 2]

**.unshift**

The .unshift method will allow you to add an element to the beginning of an array

array=> [1, 2]

array.unshift(66) => [66, 1, 2]

**.push**

The .push method will allow you to add an element to the end of an array

array.push(20) => [66, 1, 2, 20]

**.delete**

The .delete method removes a specified element from an array permanently and return that element

array.delete(20)=> 20

Array => [66, 1, 2]

**.delete_at**

The .delete_at method allows you to permanently remove an element of an array at a specified index and return that element

array.delete_at(index)

array.delete_at(2) => 2

Array => [66, 1]

my_pets = ["cat", "dog", "bird", "cat", "snake"] => ["cat", "dog", "bird", "cat", "snake"]

my_pets.delete("cat") => "cat"

My_pets => ["dog", "bird", "snake"]

**.reverse**

The .reverse method reverses the array but does not mutate it (the original array stays as is)  return new array

array.reverse=> [1, 66]

Array => [66, 1]

**.select**

### **The .select method iterates over an array and returns a new array that includes any items that return true to the expression provided.**

array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]=> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

select_array=array.select{|a| a%2==0} => [2, 4, 6, 8, 10]

array => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

**.include?**

The include? method checks to see if the argument given is included in the array return boolean value

array = [1, 2, 3, 4, 5]=> [1, 2, 3, 4, 5]

array.include?(3)=> true

 **.flatten**

Flatten will return multidimensional array to 1D array

array = [[1,2],[3,4]]

Array.flatten => [1,2,3,4]

**.join**

The .join method returns a string of all the elements of the array separated by a separator parameter. If the separator parameter is nil, the method uses an empty string as a separator between strings.

array=[1,2,3,4]

array.join => "1234" => given empty argument

array.join("*") => "1*2*3*4"

The map method iterates over an array applying a block to each element of the array and returns a new array with those results.The collect method is an alias to map - they do the same thing.

 

**.uniq**

Uniq will return array with uniq element

array.uniq => [1, 2, 3, 4]

Array => [1, 2, 3, 2, 3, 4]

Once again, notice that the uniq method did not modify the original b array; it returned a new array with the duplicates removed.

If you add the bang suffix (!) to this method, you can perform the uniq function destructively. Much like the way the delete method works.

b = [1, 1, 2, 2, 3, 3, 4, 4] => [1, 1, 2, 2, 3, 3, 4, 4]

b.uniq! => [1, 2, 3, 4]

B => [1, 2, 3, 4]

[**each_index**](https://launchschool.com/books/ruby/read/arrays#each_index)

The **each_index** method iterates through the array much like the **each** method, however the variable represents the index number as opposed to the value at each index. It passes the index of the element into the block and you may do as you please with it. The original array is returned.

a = [1, 2, 3, 4, 5]=> [1, 2, 3, 4, 5]

a.each_index { |i| puts "This is index #{i}" }

This is index 0

This is index 1

This is index 2

This is index 3

This is index 4

=> [1, 2, 3, 4, 5]

20)**[each_with_index](https://launchschool.com/books/ruby/read/arrays#each_with_index)**

each_with_index gives us the ability to manipulate both the value and the index by passing in two parameters to the block of code. The first is the value and the second is the index. You can then use them in the block.

a.each_with_index { |val, idx| puts "#{idx+1}. #{val}" }

1. 1

2. 2

3. 3

4. 4

5. 5

=> [1, 2, 3, 4, 5]

**[sort](https://launchschool.com/books/ruby/read/arrays#sort)**

The **sort** method is a handy way to order an array. It returns a new sorted array

a = [5, 3, 8, 2, 4, 1]=> [5, 3, 8, 2, 4, 1]

a.sort=> [1, 2, 3, 4, 5, 8]

 **[product](https://launchschool.com/books/ruby/read/arrays#product)**

The **product** method can be used to combine two arrays in an interesting way. It returns an array that is a combination of all elements from all arrays.

1, 2, 3].product([4, 5]) => [[1, 4], [1, 5], [2, 4], [2, 5], [3, 4], [3, 5]]

## **[Methods With a !](https://launchschool.com/books/ruby/read/arrays#bang_suffix)**

The bang suffix (!) at the end of the method name usually indicates that the method will change (or mutate) the caller permanently. Unfortunately this is not always the case. It is a good rule to be wary of any method that has the bang suffix and to make sure to check the Ruby documentation to see if it will behave destructively (the word "destructive" here just means mutating the caller).

Also, please note that there are methods like pop and push that are destructive, but do not have a ! at the end. It's a little confusing in the beginning, but as you write more programs in Ruby, you'll start to get a feel for which methods are destructive and which are not.
