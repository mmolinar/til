## Regex
Ruby regular expressions are defined between two forward slashes to differentiate them from other language syntax. The most simple expressions match a word or even a single letter.

```
# Find the word 'like'
"Do you like cats?" =~ /like/
```
This returns the index of the first occurrence of the word if it was found or nil otherwise. If we don’t care about the index we could use the String#include? method.

_***!!! Remember: the return value when using `=~` is either the string index or `nil`!!!***_

### Character Class
Lets you define a range or a list of characters to match. For example, [aeiou] matches any vowel. Example: Does the string contain a vowel?
```
def contains_vowel(str)
  str =~ /[aeiou]/
end
contains_vowel("trust") # returns 2
contains_vowel("sky")  # returns nil
```
This will not take into account the amount of characters.

### Ranges
We can use ranges to match multiple letters or numbers without having to type them all out. In other words, a range like [2-5] is the same as [2345].

#### Useful Ranges
[0-9] matches any number from 0 to 9  
[a-z] matches any letter from a to z (no caps)  
[^a-z] negated range  
\w is equivalent to [0-9a-zA-Z_]  
\d is the same as [0-9]  
\s matches white space (tabs, regular space, newline)  
There is also the negative form of these:  
\W anything that’s not in [0-9a-zA-Z_]  
\D anything that’s not a number  
\S anything that’s not a space  

Example: Does this string contain any numbers?
```
def contains_number(str)
  str =~ /[0-9]/
end
contains_number("The year is 2015")  # returns 12
contains_number("The cat is black")  # returns nil
```
### Modifiers
Up until now we have only been able to match a single character at a time. To match multiple characters we can use pattern modifiers:
+	-> 1 or more  
*	-> 0 or more  
?	->  0 or 1  
{3,5}	-> between 3 and 5  

Example: Does this look like an IP address?
```
# Note that this will also match some invalid IP address
# like 999.999.999.999, but in this case we just care about the format.
def ip_address?(str)
  # We use !! to convert the return value to a boolean
  !!(str =~ /^\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}$/)
end
ip_address?("192.168.1.1")  # returns true
ip_address?("0000.0000")    # returns false
```
