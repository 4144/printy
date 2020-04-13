# Printy

[![Build Status](https://travis-ci.org/edraobdu/printy.svg?branch=master)](https://travis-ci.org/edraobdu/printy) 
![PyPI](https://img.shields.io/pypi/v/printy) 
![PyPI - License](https://img.shields.io/pypi/l/printy)
![Codecov](https://img.shields.io/codecov/c/gh/edraobdu/printy)


Printy lets you colorize and apply some standard formats to your text with
an intuitive and friendly API based on flags to specify the formats. You can
either apply a global format or inline formats to specific parts of your text!


![Printy Demo](github/printy_demo.gif)


### Installation

you can either clone this repository or install it via pip
```python
pip install printy
```
### How to use it?

Once you install printy, you can find a short but concise documentation about the
available flags and the syntax opening a python console and running the following 
command:
```python
from printy import helpme
```
This will print out some instructions right away.
##### Using global flags

First of all, import printy:
```python
from printy import printy
```

Printy is still a 'print' statement, so you can use it as it is:
```python
printy("Some text")
```
You can use a global set of flags to specify a format you want to apply to the text,
let's say we want to colorize a text with a bold blue and also adding an underline:
```python
printy("Some text", 'bBU')
```
##### Using inline format
Although applying a global format is interesting, it is not as much as applying
some specific format to some section of the text only. For that, printy uses a 
intuitive syntax to accomplish that goal. Use the [] to specify the flags to use
for formatting the text, right before the text, and the @ to finish the formatting 
section:
```python
printy("Still [rI]Some@ Text")
```
The text that is not surrounded by the format syntax will remain with the predefined 
format.

But you can always override this default color for inline format specifying the flags 
in the 'default' parameter
```python
printy("Still [rI]Some@ Text", default="b")
```
Or, you can override the whole format without having to change the inline format:
```python
printy("Still [rI]Some@ Text", "b")
```

###### New in v1.1.0
### What about input()?
```python
from printy import inputy
```
Printy also includes an alternative function for the builtin input(), that, not only
lets us applies formats to the prompted message (if passed), but also, we can force
the user to enter a certain type of data.

Let's say we want to get an integer from the user's input, for that, we can set
type='int' in the 'inputy' function (we can specify formats the same way we'd do
 with printy)
```python
a = inputy("How many apples do you want?", 'rB', type='int')
b = inputy("How many [rB]apples@ did you get?", type='int')
c = inputy("Are you happy with that?", type='bool')
```
In all of the above examples, if the user enters a value with a type other than
an integer, the message will show again and will prompt also a warning (like this
until the user enters a valid value according to the type) 

The best part is that the returned value's type is also the one of the specified 
type, therefore, from the above examples, both *a* and *b* will be integers, and
*c* will be a boolean, so, you're gonna get the information right as you need it.   

The current supported types are:
* 'int' for integers, floating point numbers are not accepted, strings that can
be converted to integer are accepted
* 'float' for floating point numbers, or strings that can be converted to integer
* 'bool' for booleans, either True or False, or also case insensitive strings
'false' or 'true', etc.
* 'str' by default if no 'type' is passed, eny input will be converted to string.


### Dependencies

Printy currently support Python 3.5 and up. Printy is currently only tested in 
Unix-like operative systems.

### Contributing

Please feel free to contact me if you want to be part of the project and contribute.
We'll looking forward to improve this simple but effective application.
