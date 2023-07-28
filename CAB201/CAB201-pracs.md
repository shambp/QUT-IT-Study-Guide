# week 1 prac
<details>

## boiler plate
get extremely use to
```
using System;

namespace HelloWorld
{
    class Program
    {
        public static void Main( string [] args )
        {
            // YOUR CODE GOES HERE
            Console.WriteLine("Hellow world!?")
        }
    }
}
```

you will need to type this every time if you want your code to work.

## strings
we can print strings through ```Console.Writeline('content')```, we can also get user input through ```Console.Readline()```
### string index
by using the varname.IndexOf() we can find certain things within strings eg
```
string varname = 'this is my variable'
int varind = varname.IndexOf('v')
Console.WriteLine(varind)

the console would print 12, as that is the index of the string
```
### string trimming
like with python, we can trim the excess whitespace that may be present within our inputs and variables by using String.Trim()
#### string formatting
like with f strings in python we can also do format strings in a simialir manner in c# using the $ symbol
```
Console.WriteLine($'this is my {var1:F4} formatted string {var2}', var1, var2)

using \\ we can embed quotes within a string
Console.WriteLine("this is my string\"with embedded quotes"\")
\n new line
\t is a tab
\\ is a \
```

>if you want to read more about string formatting and manipulation, consider reading the docs
>
>[string documentation](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
using these formatted strings we can also add a suffix to the variables to alter their output, eg the F in the above example will ensure that var1 is treated as a float
> see the cheat sheet for moe info on suffixes
## variables
when declaring variables in c#, we must declare the data type that it is (see the cheat sheet for more info on data types)
```
string varname = 'string contents'
```
### type conversion
we can convert variables from one type to another by using the Convert.ToX where x is the data type

</details>

# week 2 prac
<details>

</details>