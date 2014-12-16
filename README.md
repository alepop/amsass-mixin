amsass-mixin
============

The Attribute-Module SASS (AMCSS) mixins

#Installing

Plug this file to your project.
```
@import "amsass-mixins"
```
Define prefixes for your modules

```
$am-prefix: ui
```
#Usage
Once you have imported the file and declared a variable, you can start using mixins

```
+module(Button)
  border: 1px solid black
  background: #ccc
  color: white
  &:hover
    color: black
  +variant(warning)
    background: red
  +variant(success)
    background: green
```
This will be compiled into the following css code:

```
[ui-Button] {
  border: 1px solid black;
  background: #ccc;
  color: white;
}
[ui-Button]:hover {
  color: black;
}
[ui-Button~="warning"] {
  background: red;
}
[ui-Button~="success"] {
  background: green;
}
```

You can also use nesting

```
+module(Button)
  border: 1px solid black
  background: #ccc
  color: white
  +variant(warning)
    background: red
  +child(child)
    color: red
    background: white
    +variant(bad)
      background: none
```
Result
```
[ui-Button] {
  border: 1px solid black;
  background: #ccc;
  color: white;
}
[ui-Button~="warning"] {
  background: red;
}
[ui-Button-child] {
  color: red;
  background: white;
}
[ui-Button-child~="bad"] {
  background: none;
}
```
