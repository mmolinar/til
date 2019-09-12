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
