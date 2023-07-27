btw the file extension for c# is .cs (im stupid and forget these things
)
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
>
> we cannot use these keywords as identifiers/variables within our code

### M and F suffix
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