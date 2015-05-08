#Ruby


### Coding Style

- Use soft-tabs with a two space indent.
- Keep lines fewer than 80 characters.
- Never leave trailing whitespace.
- End each file with a blank newline.

Use spaces around operators, after commas, colons and semicolons, around { and before }.
```ruby
sum = 1 + 2
a, b = 1, 2
1 > 2 ? true : false; puts "Hi"
[1, 2, 3].each { |e| puts e }
```

No spaces after (, [ or before ], ).
```ruby
some(arg).other
[1, 2, 3].length
```

Don't use parentheses around the condition of an if/unless/while.
```ruby
# bad
if (x > 10)
  # body omitted
end

# good
if x > 10
  # body omitted
end
```

Use empty lines between defs and to break up a method into logical paragraphs.
```ruby
def some_method
  data = initialize(options)
  
  data.manipulate!
  
  data.result
end

def some_method
  result
end
```
