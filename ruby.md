# Ruby

## Casing

Use underscores aka "Snake case" for variable and method name declaration.

`my_sweet_variable = some_method("hi")`


## Line Length

Code lines should break every 80 characters.
Code broken into additional lines should be indented under the main line of the code statement.

Strings broken accross lines should be indented so all text is stacked in the same columns.

```ruby
def do_something
  redirect_to home_path, 
    flash: { 
      warning: "Please do not do that thing
                it is a very bad thing to do." 
    }
end
```



## Inline vs Block Conditionals / Rescues

If the conditional is on a one line statement the conditional is placed in-line.

```ruby
something = "some other thing" unless not_something? 
```

If the conditional applies to multiple lines of code, wrap the code in a conditional block.


```ruby
module MyModule
  class MyController < ApplicationController
    
    before_filter :do_something

    def do_something
      if !thing?
        redirect_to home_path, 
          flash: { 
            warning: "Please do not do that thing
                      it is a very bad thing to do." 
          }
      end
    end

  end
end
```

# Never use else inline

Dont:

`something ="foo" if something? else something_else = "bar"` 

# Using unless

Unless should only be used for inline conditionals apearing at the end of lines.

` run_some_code unless admin? `

Avoid wrapping blocks in unless, use `if !` instead.

```ruby
if !happy?(user)
  do_thing_1
  do_thing_2
end
```


# Semantic Conditional Evaluators / Conditional Limits

If a conditional requires mutliple evaluations, break the evaluations into functions that can be composed into your conditional and are read semantically.

```ruby

def older_than?(x)
  self.age > x
end

def weighs_more_than?(x)
  self.weight > x
end

if user.older_than?(25) && user.weighs_more_than?(150)
  do_thing
  do_thing2  
end

do_thing3 if user.older_than?(25) && user.weighs_more_than?(150)

```

Avoid having deeply nested conditionals with mutiple &&'s and ||'s

Dont:

```ruby
if ((i > 11 && i < 42) || ((x < 11 && x > i) && is_prime?(i)))
  lol_whut "do it"
end
```

