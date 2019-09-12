```
if 1 < 2
  puts "One is less than two!"
else
  puts "One is not less than two."
end

------ OR ------

puts 1 < 2 ? "One is less than two!" : "One is not less than two"
```

### Trenary operator
```
if 1 < 2
  puts "One is less than two!"
end

------ OR ------

puts "One is less than two!" if 1 < 2
```

### Case statement
```
puts "What's your favorite language?"
language = gets.chomp

if language == "Ruby"
  puts "Ruby is great for web apps!"
elsif language == "Python"
  puts "Python is great for science."
elsif language == "JavaScript"
  puts "JavaScript makes websites awesome."
elsif language == "HTML"
  puts "HTML is what websites are made of!"
elsif language == "CSS"
  puts "CSS makes websites pretty."
else
  puts "I don't know that language!"
end

------ OR ------

case language
when "Ruby"
  puts "Ruby is great for web apps!"
when "Python"
  puts "Python is great for science."
when "JavaScript"
  puts "JavaScript makes websites awesome."
when "HTML"
  puts "HTML is what websites are made of!"
when "CSS"
  puts "CSS makes websites pretty."
else
  puts "I don't know that language!"
end
```
