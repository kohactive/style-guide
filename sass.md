#Sass

*Some things borrowed from [idiomatic css](https://github.com/necolas/idiomatic-css) and [css-tricks](http://css-tricks.com/sass-style-guide/).*

1. [Property Organization](#property-organization)
1. [Whitespace](#whitespace)
1. [Nesting](#nesting)
1. [Mixins](#mixins)
1. [Responsive](#responsive)

##Property Organization
Block similar properties for readability.
```
.selector
  /* Pseudo Element */
  content: ""

  /* Positioning */
  position: absolute
  z-index: 10
  top: 0
  right: 0
  bottom: 0
  left: 0

  /* Display & Box Model */
  display: inline-block
  overflow: hidden
  box-sizing: border-box
  width: 100px
  height: 100px
  padding: 10px
  border: 10px solid #333
  margin: 10px

  /* Other */
  background: #000
  color: #fff
  font-family: sans-serif
  font-size: 16px
  text-align: right
```

##Whitespace
Maintain whitespace between selectors(with properties) for continuity and readability.
```
.bojangles
  overflow: visible
  font-family: georgia

  .chicken
    color: $brown

      &:after
        content: "biscuit"

.bojangles
  .chicken
    color: $brown

  .biscuit
    color: $off-white
```

##Nesting
Avoid nesting more than three levels deep. It creates bloated output & over-specificity.
```
// Bad
.bicycle
  .wheel
    ul.spoke
      li.nipple

// Good
.bicycle
  .wheel
    border-radius: 40px

  ul.spoke
    color: red

  li.nipple
    color: black
```

##Mixins
Use Sass shorthand for creating and using mixins.
```
=hot-sauce
  background-color: $green
  color: $red

+hot-sauce
```

##Responsive
Use responsive mixins within the selector to keep organized.
```
=media-sm
  +media(min-width $screen-sm)
    @content

.selector
  // Normal styles

  +media-sm
    // Small breakpoint styles
```