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
            Console.WriteLine("Hellow world!?");
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
we can convert variables from one type to another by using the Convert.ToX where x is the data type, we can also use .Parse for type conversion as well, the only difference being that passing a null value through .Parse will result in an error, whereas Convert.To will just give 0. We can work around this by using .TryParse to check if a value will work, and will output it as boolean (see While section for an example).

# Week 2
### If statements
like python, we can use if statements in c# to check a value against a constant and then make the program act accordingly:

```
using System;

namespace BasicIf
{
    class Program
    {
        public static void Main( string [] args )
        {
            Console.WriteLine("Input something");
            string input = Console.ReadLine();
            const int number = 15;
            if (input >= number);
            {
                Console.WriteLine("Example.");
            }
        }
    }
}
```

### else, else if & nested if
in conjunction with if statements, we can also nest more if statements to check more variables, or use else/else if statements to create a suitable exit to the statement:

#### Else & Else if
```
using System;

namespace Else
{
    class Program
    {
        public static void Main( string [] args )
        {
            Console.WriteLine("Input something");
            string input = Console.ReadLine();
            const int number = 15;
            if (input >= number);
            {
                Console.WriteLine("Example.");
            }
            else if (input != number);
            {
                Console.WriteLine("Not Example.");
            }
            else
            {
                //keeping a block empty is the equivalent to the 'pass' command in python. signalling the program to move on.
            }
        }
    }
}
```

#### Nested If
```
using System;

namespace NestedElse
{
    class Program
    {
        public static void Main( string [] args )
        {
            Console.WriteLine("Input something");
            string input = Console.ReadLine();
            const int number = 15;
            if (input > number);
            {
                Console.WriteLine("Example.");
                if (input < number);
                {           
                    Console.WriteLine("Not Example.");
                }
            }
        }
    }
}
```

## Switch statements
switch statements is another kind of multi condition statement, which can sometimes be used instead of nesting ifs.

```
using System;

namespace SwitchStatements
{
    class Program
    {
        public static void Main( string [] args )
        {
            Console.WriteLine("Input something");
            string input = Console.ReadLine();

            string example;

            switch(input);
            {
                case "hello": example = "example"; break;
                case "goodbye": example = "not example"; break;
                // break will end our case checking.
                default: example = "unknown entry"; break;
            }
            Console.WriteLine(example)
        }
    }
}
```

## While
the concept is the exact same as python, but iwht a difference in syntax

```
using System;

namespace While Statements
{
    class Program
    {
        public static void Main( string [] args )
        {
            while(true)
            {
                Console.WriteLine("please enter an integer between 0 and 10");
                string input = Console.Readling();
                inputint = int.Parse(input);
                //dummy var for .TryParse
                int parseint;

                //test value to see if it is an integer or not
                if(int.TryParse(inputint, out parseint))
                // the two pipes here are really cool, we are checking for two statements at the same time.
                    if (inputint < 0 || inputint > 10)
                    {
                        Console.WriteLine("try again please");
                    }
                    else
                    {
                        continue;
                    }
                else
                {
                    Console.WriteLine("an integer is required, try again")
                }
                Console.WriteLine($"your input was {inputint}");
                
            }
        }
    }
}
```

## For
for statements are a bit different to python, allowing up to 3 arguements.

- init clause
 - our declaration statement
- guard clause
 - is a boolean expression
 - can be left as an empty expression
- update clause
 - list of expression statements
 - usually to increment a counter in +ve or -ve direction
 - can be left blank

 ```
 using System;

namespace SwitchStatements
{
    class Program
    {
        public static void Main( string [] args )
        {
            // pretend i put something here idk
            string input = Console.Readline();
            inputint = int.Parse(input);
            
            //computing the sum
            ulong total = 0;

            for (int i = 1; i <= inputint; i++)
            {
                total += (ulong) i;
            }
            Console.WriteLine($"The sum of the interegers from 1 to {inputint} is {total}")
        }
    }
}
 ```

 ## Break and Continue
 we have seen break already, that being its purpose is to stop the flow through our statements. But c# also has a command called continue, which has the same function as pass in python, jumping to the end of our loop body. preventing un needed lines from being ran and errors being created

## Boolean 
the exact same as python, ==, <, <=, !=, >, >= all have the same functions, but we also have the addition of &&, || and !a, equating to and, or and not respectively. we can use parenthesis to order our boolean expressions