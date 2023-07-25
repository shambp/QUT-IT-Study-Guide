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
| char | 16 bit unicode character, the literals are letters but internally its a 16 bit unsigned integer |
| int | 32 bit signed integer * |
| uint | 32 bit unsigned integer |
| long | 64 bit signed integer |
| ulong | 64 bit unsigned integer |

alongside this we also have 3 floating point types
| type | descriptions |
| --- | --- |
| double* | 64 bit floating point, best for most tasks|
| decimal | 128 bit flaoting point, smaller range, but greater precision |
| float | 32 bit flaoting point, not accurate |

> *they are considered the 'normal' numeric types

if you ever forget the range of the values you can use x.MinValue or x.MaxValue to get the range that you can use, where x is the numeric type

#### M and F suffix
When declaring certain types of variables we need to add a certain suffix so that we know what kind of literal we are using
```
decimal x = 10.1
this will error out, instead we do

decimal x= 10.1M
```
each literal has a different suffix that we can use
| suffix | description |
| --- | --- |
| F | float |
| D | double |
| L | long |
| M | decimal |
| U | uint |
| UL | ulong |