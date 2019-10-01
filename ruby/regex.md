## Regex
Ruby regular expressions are defined between two forward slashes to differentiate them from other language syntax. The most simple expressions match a word or even a single letter.

```
# Find the word 'like'
"Do you like cats?" =~ /like/
```
This returns the index of the first occurrence of the word if it was found or nil otherwise. If we don’t care about the index we could use the String#include? method.

### Character Class
Lets you define a range or a list of characters to match. For example, [aeiou] matches any vowel. Example: Does the string contain a vowel?
```
def contains_vowel(str)
  str =~ /[aeiou]/
end
contains_vowel("test") # returns 1
contains_vowel("sky")  # returns nil
```
This will not take into account the amount of characters.

### Ranges
We can use ranges to match multiple letters or numbers without having to type them all out. In other words, a range like [2-5] is the same as [2345].
