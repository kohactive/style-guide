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
      } unless current_user.member.patient?
  end
```



## Inline vs Block Conditionals / Rescues

If they only affect one code statement, even if that one line is broken into multiple lines, the conditional is placed in-line.

If the conditional applies to multiple code statements, wrape the code in a conditional block.


```ruby
module MyModule
  class MyController < ApplicationController
    
    before_filter :do_something

    def do_something
      redirect_to home_path, 
        flash: { 
          warning: "Please do not do that thing
                    it is a very bad thing to do." 
        } unless current_user.member.patient?
    end

  end
end
```
