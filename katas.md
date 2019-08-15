In a sentence reverse words with more than 5 letters. "My wollef sroirraw." "emocleW home."

`def spinWords(string) \n
  string.split.map { |s| s.length >= 5 ? s.reverse : s }.join ' '
end
`
