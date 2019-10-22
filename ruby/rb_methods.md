### .length
Strings, Arrays  
Returns: Integer  
Get the length of a String. Or how many elements are in an Array.
```
"ruby".length          
# 4

OR

["cat", "dog", "pizza"].length
# 3

silly_aray = ["cat", "dog", "pizza"]
silly_array.length
# 3
```

### .empty?
Strings  
Returns: True/False  
A blank string is a string which has either zero length, or is composed ONLY of white space characters.
```
"".empty?
# true

OR 

"    ".empty?
# true
```

### .downcase

### .split
String  
Returns: Array   
Takes in a string and returns an array. If we pass it a bit of text in parentheses, .split will divide the string wherever it sees that bit of text, called a delimiter. If no delimiter is passed the Split will use a space as the separator character. The first example below splits the 'text' after any ',' 
```
csv = "a,b,c,d"
string.split(",")
# ["a", "b", "c", "d"]
```

##### Split on Regex
In this example Split acts upon a regular expression (regexp). In Ruby we specify these with forward slashes '//'. Here the regex is '\W+' which means one or more non-word characters.
```
value = "one, two three: four"

# Split on one or more non-word characters. \W+ is a regex 
a = value.split(/\W+/)

# Display result.
puts a

Output

one
two
three
four
```
##### Split with limits
This is the maximum number of array elements that are returned. If more elements are found than are allowed by the limit, the excess ones are grouped in the final array element. Limiting the number of array elements can be useful if you only need the first several parts from a string.
```
# Contains five vegetable names.
value = "carrot,squash,corn,broccoli,spinach"

# Split with limit of 3.
vegetables = value.split(",", 3)
puts vegetables

Output

carrot
squash
corn,broccoli,spinach
```

##### Split a single String
With split we can get the characters from a string. Pass an empty string literal ("") to the split method. The length of the array equals the length of the string.
```
value = "xyz 1"

# Separate chars.
array = value.split ""

# Write length.
puts array.length

# Write elements.
print array

Output

5
["x", "y", "z", " ", "1"]
```

### .join
Arrays  
Returns: String  
Takes an array of strings & join these strings into a big string.
```
arr = ['a', 'b', 'c']
arr.join
# "abc"
```

### .times
Do something a specific number of times
```
5.times { puts "Odelay!" }
# Prints 5 "Odelay!"s on separate lines
```

### .each
Arrays
Repeat an action for every element in a collection. Returns the original, unchanged object.
```
[1, 2, 3].each { |x| puts x * 10 }
# Prints 10, 20, 30 on separate lines
```

### even?
Integers
Returns true if int is even
```
my_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
my_array.each {|num| puts num if num.even? }
# Print 2  4 6 8 10 on seperate lines
```

### .to_s
Integers, arrays  
Converts non-string values to strings.

### .upto
When we know the range of numbers we’d like to include
```
"L".upto("P") { |letter| puts letter }
# Prints L M N O P on seperate lines
```

### .downto
Same thing is as .upto but with descending values
```
95.downto(90) { |num| print num, " " }
# Prints 95 94 93 92 91 90
```

### .push or <<
Strings, Arrays  
To add an element to the end of an array you can use .push or the "shovel" (concatenation operator)
```
puts ["a","b","c"] << "d" or puts ["a","b","c"].push("d")
# Prints ["a", "b", "c", "d"]

"Yukihiro " << "Matsumoto"
# ==> "Yukihiro Matsumoto"
```
For non-string values, you have to use .to_s to make it a string:
```
age = 26
"I am " << age.to_s << " years old."
# ==> "I am 26 years old."
```

### .respond_to?
Symbol  
Returns: True/False  
Takes a symbol and returns true if an object can receive that method and false otherwise. 
```
[1, 2, 3].respond_to?(:push)
# Return true since you can call .push on an array object
[1, 2, 3].respond_to?(:to_sym)
# Return false since you can’t turn an array into a symbol.
age = 26
puts age.respond_to?(:next)
# Prints true because age does respond to next, since age is a integer
```

### .next 
Integer  
Returns: Integer  
Will return the integer immediately following the integer it’s called on
```
puts 5.next
# Returns 6
age = 26
puts age.respond_to?(:next)
# Prints true because age is an integer so will respond to .next
```

### .collect or .map
Arrays, Hashes, Ranges 
Returns: Array
The main use for map is to transform data.  
Takes a block and applies the expression in the block to every element in an array without changing the initial array. Returns a new array filled with whatever gets returned by the block each time it runs.
```
my_nums = [1, 2, 3]
my_nums.collect { |num| num ** 2 }
# ==> [1, 4, 9]
my_nums
# ==> [1, 2, 3]

@numbers = [1, 0, 3, 2, 5, 4, 7, 6, 9, 8]
 
# all numbers multiplied by two:
@numbers.map{|number| number * 2}
  #=> [2, 0, 6, 4, 10, 8, 14, 12, 18, 16]
 
# the even status for all numbers:
@numbers.map(&:even?)
    #=> [false, true, false, true, false, true, false, true, false, true]

```
### .collect!
It mutates the original array instead of creating a new one.
```
my_nums.collect! { |num| num ** 2 }
# ==> [1, 4, 9]
my_nums
# ==> [1, 4, 9]
```

### .floor
Integer
Returns: Ingeger
Rounds a float (a number with a decimal) down to the nearest integer.

### .is_a?
Returns: True/False
Which returns true if an object is the type of object named and false otherwise:
```
:hello.is_a? Symbol
# ==> true
```

### .select
Array, Hashes  
Returns: Array  
Returns a new array containing all elements of array for which the given block returns a true value. In other words, selects the set of items of the array that correspond to the characteristics you are looking for.
```
a = [18, 22, 33, 3, 5, 6]  
b = [1, 4, 1, 1, 88, 9]  
   
puts "Select Method a: #{a.select {|num| num > 10 }}"

puts "Select Method b: #{b.select {|x| x.odd? }}"

# Select Method a: [18, 22, 33]

# Select Method b: [1, 1, 1, 9]

```
For Hashes:
```
stock = {
  apples: 10,
  oranges: 5,
  bananas: 1
}

stock.select { |k, v| v > 1 }
# {:apples=>10, :oranges=>5}
```

### .select.with_index
Arrays, Hashes
Returns: Array
Allows you to filter using the index, instead of the object (in this case a string) itself. Here we want every other word starting with the first word.
```
fruits = %w(apple orange banana)
fruits.select.with_index { |word, idx| idx.even? }
# ["apple", "banana"]
```

###  Differences between map, collect, select and each
#### .each 
Returns the original object it was called on because it's really used for its side effects and not what it returns
#### .each_with_index 
Passes not just the current item but whatever position in the array it was located in.
#### .select 
Returns a new object (e.g. array) filled with only those original items where the block you gave it returned true
#### .map 
Returns a new array filled with whatever gets returned by the block each time it runs.

### .include? (.member?)
String  
Test whether a given item is in the enumerable collection. Evaluates to true if it finds what it’s looking for and false otherwise.
```
def include? array, item
  array.include?(item)
end

OR

def include? array, item
  array.include?(item) ? true : false
end

OR

def include?(array, item)
  if array.include?(item)
    return true
  else 
    return false
  end
end
```
### .minmax_by
Takes an enumerable collection and returns a 2-element array consisting of the minimum and maximum values, as calculated via the given block.
```
@numbers = [1, 0, 3, 2, 5, 4, 7, 6, 9, 8]
 
# lowest/highest numbers:
@numbers.minmax_by{|number| number}  #=> [0, 9]
 
# lowest/highest numbers when negative:
@numbers.minmax_by{|number| 0 - number}  #=> [9, 0]


# pets with minimum/maximum quantity:
@inventory.minmax_by(&:quantity).map(&:name).join(', ')  #=> ["rock", "beetle"]
 
# pets with fewest/most legs:
@inventory.minmax_by(&:legs).map(&:name).join(', ')  #=> ["fish", "scorpion"]
```
### .first
Takes an enumerable collection and optional number of elements. If no element count is given, it returns the first element in the collection. If a number is given, it returns that many elements from the beginning of the collection. Careful! This can be tricky, since it returns different types of objects (scalars or arrays) depending on the paramenters given.

```
def first list, n=nil
  if n == nil
    return list.first
  else
    return list.first(n)
  end
end

OR

def first list, n=nil
  n ? list.first(n) : list.first
end
```

### .drop_while
Takes an enumerable collection and a block, skips elements until the given block returns true, and then returns the rest of the collection.


### .each_cons
Takes an enumerable collection and iterates through a cascading list of elements. For instance, a list of [1, 2, 3, 4] called with each_cons(2) would yield [1,2], [2,3], and finally [3,4].
```
# Pet inventory by name: ['dog', 'cat', 'fish', 'scorpion', 'beetle', 'monkey', 'rock']
 
# pets in cascading groups of two:
inventory.each_cons(2){|pets| p pets.map(&:name) }
 
# output:
# ["dog", "cat"]
# ["cat", "fish"]
# ["fish", "scorpion"]
# ["scorpion", "beetle"]
# ["beetle", "monkey"]
# ["monkey", "rock"]
 
# pets in cascading groups of three:
inventory.each_cons(3){|pets| p pets.map(&:name) }
 
# output:
# ["dog", "cat", "fish"]
# ["cat", "fish", "scorpion"]
# ["fish", "scorpion", "beetle"]
# ["scorpion", "beetle", "monkey"]
# ["beetle", "monkey", "rock"]
```
### .count
Takes an enumerable collection and counts how many elements match the given criteria. If no parameters are given, it returns the total number of elements in the collection. If a parameter is given, it returns the number of elements that match the given parameter. If a block is supplied, this method returns the total number of elements for which the block returned true.
```
@numbers = [1, 0, 3, 2, 5, 4, 7, 6, 9, 8]
 
# count all numbers
@numbers.count  
=> 10
 
# count even numbers
@numbers.count(&:even?)  
=> 5
 
# count divisible by three
@numbers.count{|number| number % 3 == 0}  
=> 4

# count pets:
@inventory.count  
=> 7
 
# count in-stock pets:
@inventory.count(&:in_stock?)  
=> 6
 
# count pets with four legs:
@inventory.count{|pet| pet.legs == 4}  
=> 2
```

### .zip
Combines more than one list in a zipping fashion.
```
animals = ["dogs", "ducks", "seals"]
complexions = ["furry", "feathery", "slippery"]
 
animals.zip(complexions)
    #=> [["dogs", "furry"], ["ducks", "feathery"], ["seals", "slippery"]]
```

### .gsub (or .gsub!)
Provide another quick and easy way of replacing a substring with another string. They take two arguments: the search string and the replacement string. The gsub method returns a modified string, leaving the original string unchanged, whereas the gsub! method directly modify the string object on which the method was called.
```
myString = "Welcome to PHP Essentials!"
=> "Welcome to PHP Essentials!"

myString.gsub("PHP", "Ruby")
=> "Welcome to Ruby Essentials!"
```

### .replace
Replace an entire string instead of just a substring.
```
myString = "Welcome to PHP!"
=> "Welcome to PHP!"

myString.replace "Goodbye to PHP!"
=> "Goodbye to PHP!"
```

### .chop
Removes any last character from the string. It doesn't take arguments.

### .insert


### .to_sym


### .to_h


### .delete_at(n)
Array  
Deletes the nth element of the array.
```
array.delete_at(0)
# removes the first element of the array
```

### .delete
String
Returns: Copy of string 
Used to return a copy of the given string with all characters in the intersection of its arguments deleted.
```
str = "String Counting"
puts str.delete "ing"
# Str Count
......................................................

str = "String Counting"
puts str.delete "ing", "^n"
  
str2 = "Ruby Mode\\r\\n"
puts str2.delete "\\"

# Strn Countn
# Ruby Modern
```

### .pop
Arrays  
Removes the last element from the array and returns it

### .unshift
Arrays  
Adds an element in front of the array.
```
users = ["John", "Paul", "Ringo"]
users.unshift "George"
# ["George", "Jonh", "Paul", "Ringo"]
```

### .shift
Arrays  
Removes the first element of the array and returns it.
```
users = ["John", "Paul", "George"]
users.unshift
# John
print users
# ["Paul", "George"]
```
### .inject
Arrays, enumerables and converting array elements into hashes  
Adds the elements of an array together. In the example below, the inital value has been set to "0" but can be ommitted and the value assigned will be the first element of the array. 
```
[5, 6, 7, 8].inject (0) { |result_memo, object| result_memo + object }
# 26

OR

[5, 6, 7, 8].inject(:+)
# 26
```

### .sort
Arrays  
Returns: Array  

### .min

### .each_byte
String  
Returns: enumerator  

String class method in Ruby which is used to passes each byte in the given string to the given block or returns an enumerator if no block is given.

```
puts "Sample".each_byte{|b| print b, ' ' } 
puts "Input".each_byte{|b| print b, ' ' } 
# 83 97 109 112 108 101 Sample
# 73 110 112 117 116 Input
```
