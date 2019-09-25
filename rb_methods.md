### .length

### .downcase

### .split
Takes in a string and returns an array. If we pass it a bit of text in parentheses, .split will divide the string wherever it sees that bit of text, called a delimiter. The example below splits the 'text' after any ',':
```
text.split(',')
```

### .times
Do something a specific number of times
```
5.times { puts "Odelay!" }
# Prints 5 "Odelay!"s on separate lines
```

### .each
Repeat an action for every element in a collection
```
[1, 2, 3].each { |x| puts x * 10 }
# Prints 10, 20, 30 on separate lines
```

### even?
Returns true if int is even
```
my_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
my_array.each {|num| puts num if num.even? }
# Print 2  4 6 8 10 on seperate lines
```

### .to_s
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
Will return the integer immediately following the integer it’s called on
```
puts 5.next
# Returns 6
age = 26
puts age.respond_to?(:next)
# Prints true because age is an integer so will respond to .next
```

### .collect or .map
Takes a block and applies the expression in the block to every element in an array without changing the initial array. 
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
Rounds a float (a number with a decimal) down to the nearest integer.

### .is_a?
Which returns true if an object is the type of object named and false otherwise:
```
:hello.is_a? Symbol
# ==> true
```

### .select
Selects a set of numbers or items of the array that correspond to the characteristics you are looking for. 

##  Differences between map, collect, select and each
#### .each 
returns the original object it was called on because it's really used for its side effects and not what it returns
#### .each_with_index 
passes not just the current item but whatever position in the array it was located in.
#### .select 
returns a new object (e.g. array) filled with only those original items where the block you gave it returned true
#### .map 
returns a new array filled with whatever gets returned by the block each time it runs.

### .include? (.member?)
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
