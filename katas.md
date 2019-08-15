In a sentence reverse words with more than 5 letters. "My wollef sroirraw." "emocleW home."

````
def spinWords(string)
  string.split.map { |s| s.length >= 5 ? s.reverse : s }.join ' '
end
````
```
def spinWords(string)
  sentence = string.split(' ')
  
  sentence.map! do |word|
    if word.length >= 5
      word = word.reverse
    else 
      word
    end
  end
  
  sentence.join(' ')
end
```
