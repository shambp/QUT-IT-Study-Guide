<details>

# week 1 prac
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

## content covered
strings, variables, data types (see cheat sheet)

similair to python with a few key differences 

### strings
we can print strings through ```Console.Writeline('content')```, we can also get user input through ```Console.Readline()```
#### string formatting
like with f strings in python we can also do format strings in a simialir manner in c# using the $ symbol
```
Console.WriteLine($'this is my {var1:F4} formatted string {var2}', var1, var2)
```

using these formatted strings we can also add a suffix to the variables to alter their output, eg the F in the above example will ensure that var1 is treated as a float
> see the cheat sheet for moe info on suffixes
### variables
when declaring variables in c#, we must declare the data type that it is (see the cheat sheet for more info on data types)
```
string varname = 'string contents'
```
#### type conversion
we can convert variables from one type to another by using the Convert.ToX where x is the data type

</details>
<details>

# week 2 prac

</details>