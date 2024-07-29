# **This unit was dropped before completion, I prefer data over this i am too stupid**
# **This is good for basics, however is depreciated and is missing content**


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

# Week 3
## Arrays
stored multiple values of the same type, using the syntax

```
int[] myarray = new int[10]
where the new keyword is used to create an object inside of the array, and the number 10 signifying how big the array is
```

accessing an item in the array is the same as python, that being ```myarray[3]``` will get us the 4th item in the array

an example of this in use would be

```
Console.Writeline("how many different kinds of fruit do you have?")
fruit_count = Console.Readline()

while (fruit_count > 0)
    Console.Writeline("can you tell me one of your fruits?")
    string[] fruit_entry = new string[Console.Readline()]
    fruitcount -= 1

Console.Writeline($"your fruit collection includes {fruit_entry}")
```

you can also intialise the array with itrems already in it ```int[] myarray = new int[] {1, 2, 3, 4}```.

### Manipulating Arrays
we can manipulate arrays in a few different ways. done through Array.arg(list_name), i woudl reccomend reading the c# docs to gain a full understanding of the different ways we can manipulate arrays.
[Documentation on Arrays](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-7.0)

### foreach
the foreach command allows us to iterate through an array. allowing us to do something for every x in our arrays

```
foreach (int g in fruit_count)
{
    code goes here
}
```
works very similairly to for loops in python

### single and multi-dimensional arrays
above we have covered single dimensional arrays, however we can create an array with multiple different entries by using the statement ```int[] myarray = new int[10, 10]``` this is good if we want to bundle entries together, lets say that we are creating a profile for a list of different cities with the cities name, population, gdp etc. We would want to consider a multi-dimensional array. The drawback of this is that they would all need to be the same data type, which brings us to our next topic of classes

## classes
classes are a collection of related data and/or methods, encapsulate data/operations performed on data and provide a template for the objects that we are creating

lets say we want to store multple things about a student. things like name, date of brith, their grades etc, we can use a class to store that information in a way that makes sense and allows us to group it all together accordingly.

```
using System;

namespace HelloWorld
{
    class Student
    {
        public int id;
        public string name;
        public float GPA;
    }
    class Program
    {
        static void Main( string [] args )
        {
            int studentCount = 5;

            Student[] students = new Student[studentCount];
            
            // we may have one student class, but we can create multiple student objects using our class of student.
            for (int i = 0; i < studentCount; i++)
            {
                students[i] = new Student();
                Console.WriteLine("Enter Student Name:");
                students[i].Name = Console.ReadLine();
                etcetc with the other aspects of student that we want to get
                students[i].ID = i;
            }
            foreach (Student student in students)
            {
                Console.WriteLine($"{student.ID}: {student.name} has a gpa of {student.GPA}")
            }

        }
    }
}
```

by making the student a class, we have essentially created x (in this case 3) arrays that store information ABOUT the class student, meaning that we can

### Methods
methods are blocks of code inside of classes. and they perform functionality that is related to that class. we provided methods within our previous example, creating 3 variables that stores information about our students. however these are what we call static methods, a non-static method performs functionality on an object belonging to that class. Lets expand on our current example to properly display a non static method

```
using System;

namespace HelloWorld
{
    class Student
    {
        public int id;
        public string name;
        public float GPA;
        //example expansion here!!!!
        public void setGPA(float[] grades)
        {
            GPA = grades.Sum() / grades.Length;
        }
    }
    class Program
    {
        static void Main( string [] args )
        {
            int studentCount = 5;

            Student[] students = new Student[studentCount];
            
            // we may have one student class, but we can create multiple student objects using our class of student.
            for (int i = 0; i < studentCount; i++)
            {
                students[i] = new Student();
                // also an alteration here!!!!
                Console.WriteLine("enter the number of classes the student has taken");
                int numsubjects = int.Parse(Console.ReadLine());
                float[] subjectGrades = new float[numsubjects];
                for (int subjectId = 0; subjerct Id < numsubjects; subjectId++>)
                {
                    Console.WriteLine("Enter grade:")
                    subjectgrades[subjectid] float.Parse(Console.ReadLine());
                }
                etcetc with the other aspects of student that we want to get
                students[i].ID = i;
            }
            foreach (Student student in students)
            {
                Console.WriteLine($"{student.ID}: {student.name} has a gpa of {student.GPA}")
            }

        }
    }
}
```

what we added was that  we have made a method that calculates gpas to our program and then added said gpa calculation to our loop. changing our gpa element in our class to something that can be calculated and not blindlyh inputted

### return statements
methods can specify a type of value that they return to the caller, alternatively they can specify void as the return value (not returning anything). if a method has a return type other than void, it must contain a minumum of 1 return statement. for example return 0

 - when a return statement is encountered, the method will stop executing, giving us a way to exit the method early
 - return can be used without providiung any value if the method is void:return

to illustrate this ill take a snippet from our previous examples and expand on iut again

```
    class Student
    {
        public int id;
        public string name;
        public float GPA;
        //example expansion here!!!!
        public void setGPA(float[] grades)
        {
            GPA = grades.Sum() / grades.Length;
        }
    }
        public float GetGPA()
        {
            return GPA;
        }
```

we can combine return with ifs etc to make sure that we are exiting the method when we want to.

## constructors
classes have a special method called a constructor, which is called when an object is created, with its purpose being to intialise the objects fields with some valid data. Constructers do NOT have a return type (but you are able to use return without any parameteres if you need to exit one early).

if you do not provide a constrcutor a parameterless empty constructor will be generated automatically.
```
public Student(int iD, string name, float gPA)
{
    ID = iD
    name = name
    GPA = gPA
}
the funky capitalisaiton is to remove ambiguity
```
 
## visibility
basically what level we want it to be at. it can be internal (private) or external (public) think of it like whether you declare your variables as global or not in python.

# Week 4
software projects are complex. with a projects complexity scaling with size. this is because with every new line of code we add, we are adding a new interaction to our program and we must consider how they will all interact.

>> this makes programming highly efficient due to this networking nature, however the complexity can often be overwhelming. Obviusly with time it becomes easier.

This is where abstraction comes in.

## Abstraction
is the process where we strip away details of less importance in order to focus on the parts teh really matter, an imporant concept within abstraction is the reusing of code, there are several different kinds of abstraction.

### Procedural Abstraction
a fundamental class of abstractoin in computer science.

Common tasks are identified and split out into procedures (Functions, Methods). this enables the procedure to be reused multiple time

>> this reduces the amount of complexity in an application, through adding overall less lines and being easily changed in the even that the requirements change

the only really good way to explain this is with an example, with before and after being shown
```
before
string name;
do
{
    Console.WriteLine("what is your name?");
    name = Console.ReadLine()
} while (name == "")

string address;
do
{
    Console.WriteLine("what is your address?");
    name = Console.ReadLine()
} while (address == "")

Console.WriteLine($"hello {name} of {address}")
```

alternatively we could use procedural we would just make it its own method and use it twice
```
static string getInput(string message)
{
    string input
    do
    {
    Console.WriteLine("message");
    input = Console.ReadLine()
    } while (address == "")
    return input

}
static void main(string[] args)
{
    string name = getInput("What is your name?")
    string address = getInput("what is your address?")
    Console.WriteLine($"hello {name} of {address}")
}
```

what we have done is noticed that both of these use the exact same method to gather a response, with the only difference the information inputted and the question that is being asked, therefore we can create a procedure that gets the information with the two differing points being the variable that it is stored in and the question input. the lectures have more examples that help illustrate this

### Programming to a Contract
basically what oldmate is going on about here is that you have 2 people, the implementor and the programmer, the implementor creates the procedure and the programmer uses the procedure. its a two way street where both people are involved. The programmer agress to certain things when they call the method, and the implementor agrees that the method will behave as advertised. the programer could be you going to use the code. and the implementor could be you going back in 6 months time to edit/maintain the method so that it continues to do what it says on the tin.

#### method parameters and reference types
objects are passed to methods as references, this means if the the object has public fields, or public methods, than the method that you pass can also modify those as well

if we consider a method called normaliseAraay(), which takes an array of doubles and then normalises it so the magnitude of one. We need to consider a few things, like does the method modify the array itself and pass it in place? what if it creates an entirely brand new array? leaving the originial untouched?

##### out and ref
these keywords are used both in the method signature and in the calling code. out is used for an output parameter, and ref is used for reference parameters

as an example:

Out
```
void getPosition(out inx, out int y)

bool Int32.TryParse(strings, out int result)
^^ will allow us to check whether or not the parse works or not.
this effectly creates a copy of our variable
```

Ref
```
void Array.Resize(ref t[] array, int newSize)
unlike out, ref does not create a copy of the variable, giving us granularity in our reference types.
```

##### null and nullable types
null means that our reference does not point to any object, a varialbe is null before we initialise any information into it. object variables can be set to null, and we can check if something is null as well using our operators == and !=. on top of this c# has something called nullable types, introduced to prevent potential issues in the future. essentially object types shout not be null at any ponit where they might be accessed unless the type is nullable

nullable types have a ? after the type name
```
int[]? array;
Student? myStudent;
```

the compiler should be warning you if you are using non-nullable variables that have the potential to be null. nullable values are allowed to be null, but operatoins that do not work on null values cannot be carried out on nullable values UNLESS they are guaranteed to not be null.

eg ```if (response != null)``` would be a valid way to prove that a nullable object is not null

### Data Abstraction
just as we identify similairites and differences in code for procedural abstraction, the same can be done for data in **data abstraction**

>> only classes support data abstraction, methods will support procedural

Abstract data types are very powerful in object oriented programming. We can seperate the external interface from the internal implementation to enable greater code reuse

#### interfaces
an interface is similair to a class, but it does not contain any code, private members or fields

```
interface Ifoo
{
    public void bar (out int x, out in y)
}
^^
we tend to name interfaces with the capital I at the start.
```

classes can implement interfaces ```class Student : Ifoo```. which means that they follow the contract presented by the interface (such as implementing all of the methods). Code can be designed to work with any classes implementing that interface.

### Generics
some types/methods in c# can be designed to work with multiple different types, and customisede to refer to a specific type when they are called. These are known as generics. They are commonly used for collectoin types, which can be configured to contain a specific type of data. we wont be covering generics in detail, just going over it.

```
List<float> waveform = new List<float>();

Dictionary<string, int> grades;
```

#### Lists
lists are arrays but with a variable size instead of fixed. syntax is ```List<DataType> listName = new List<DataType>();``` we can add a set of {curly braces} after the parenthesis if we want to initialise the list with data inside.

#### dictionaries
they are an associative array, and are efficient when inserting new values or lookup up existing values using the key

keep in mind that the keys are unique but the values are not

```
Dictionary<key, value> dictName = new Dictionary<key, value();

eg
Dictionary<string, Person> people = new Dictionary<string, Person>();
people.Add("Sam", new Student("Sam", 123456));
etc
where the first sam is the key, and the second sam with the number are the contents.
```

you can populate the dictionary in advance like its a list

## Week 5
### encapsulation
encapsulation is identifying what parts make up the external interface and what parts make up the internal implementaion, and subsequently cleanly seperating the two (this helps us achieve adequate abstraction).

within our external interface we want everything needed for the external code to use the type, and we want details that do not restrict implementation

without our internal implementation we want to worry about how our data is represented, stored, calculated etc.

### designing for the future
the biggest improvement to productivity that object oriented programming provides is through the ability to design reusable classes.

A good class gets used a lot, a bad class is in turn used very little. you are HIGHLY unlikely to get the class right the first time, and will take you some reworks to truly make a good class. It is best to assume that you will have to change it later on and make the steps to ensure that your external interface allows you to. this is only feasible if you are able to adequately implement abstaction through boiling down your external interface to their simplest elements

### type design
every time you create a class you are designing a type (unless you are creating a static class)

a properly designed type is:

#### responsible for one thing
that thing can be highly complex, or include a lot of details, but its purpose should be singular

#### are complete
every possible valid state can be represented and achieved through use of the public interface

a complete type means you can use the public interface to create any possible value for that type, and to retreive relevent information about said type

#### are efficient
a type is efficient if the external interface allows operation son a type to be performed in the most efficient way. An inefficient type often leads to 'shadow' types and unnecessary duplicatoin in a system, reducing maintainability

#### do not permit invalid values to exist
says it on the tin, tldr dont let a type to be created in an incomplete state.

### Properties
properties are a c# exclusive feature, they have the semantics of fields, but are otherwise equivalent to methods.
> this means that they can place limits on the operations that are performed, and they are not bound to the underlying representation


### syntax to create a property

### Getter
properties have an access level (private etc), a type, a getter and/or a setter. The getter works like a method that takes no parameters and returns a value of the property type

```
public int idk
{
    get
    {
        return example.idk
    }
}
```

a method with only a getter is read only, and a getter can simply return a value from a private field. Or, alternatively it oculd calculate the value in some other way 

### Setters
the setter works like a method that takes a single parameter (which is always named value) and returns nothing

```
public int idk
{
    set
    {
        if (value == "" || value.Length > (max_length))
        {
            throw new ArguementException("invalid");
        }
        idk = value;
    }
    get
    {
        return idk;
    }
}
```

### auto-implemented properties
as a shorthand for creating a private backing field and creating a property that reads from and writes to that field

so instead of doing this

```
private string addr
public string Address
{
    get
    {
        return addr;
    }
    set
    {
        addr = value;
    }
}
```

we can instead do this

```
public string Address {get; set;}
```

the compiler will create a blank backing field for you, this backing field has no name and cannot be referenced

#### auto implement prop vs fields
autoimplemented properties are functionally identical to fields, so why dont we use fields outright?

fields cant be replaced with anything other than a field without breaking the ABI (application binary interface). However our properties can be converted from auto implement back to normal without breaking the existed code, even without recompiling the calling code.