# Week 1
btw the file extension for c# is .cs (im stupid and forget these things
)
## Common Expressions
### Expressions and types
- you have literals and operators
  - ()+-*/%
  - these exressions almost identically to python btw

yeah uhhh this section is just about your operators, also covers things like floating point division etc. something interesting is that if you append .GetType() to the end of your calculation it will tell you what kind of operation is is.
```
(123 * 12).GetType()
[System.Double]
```
## Variables
unlike python where we can just declare variables like ```x = 2```, we need to declare the variables a bit differently. The order we follow is the Declartaion, Type specifier and then the expression. For example:
```
First we need to declare WHAT the variable is
int x; <- we first assign a class to the variable, in this case we want x to be an integer
x = 2 <- now we can assign the value to the variable

we can also do this within the same operation:
int x = 2;
```

### Integer types
There are 9 integer types that we can use in C#

| type | Description |
| --- | --- |
| sbyte | 8 bit signed integer |
| byte | 8 bit unsigned integer |
| short | 16 bit signed integer |
| ushort | 16 bit unsigned ineteger |
| char | 16 bit unicode character, the literals are letters but internally it is a 16 bit unsigned integer |