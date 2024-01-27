# Variable description decoration with DebuggerDisplay attribute

## Short Description

This is a task for investigation of variable description decoration with DebuggerDisplay attribute.

## Estimation (h)

4

## Topics

* DebuggerDisplay attribute

## Requirements

You should be able to provide user-friendly description for debug objects.

Create a DebuggingAndPerformance C# console app and update the it with the code as below.
Add a breakpoint at the end of main function and debug the app.
Check how the objects in the array looks like.
Uncomment DebuggerDisplay attribute and check it again.
Check how it works without 'nq' parameter.

```cs
using System.Diagnostics;

namespace DebuggingAndPerformance
{
    //[DebuggerDisplay("{Surname,nq} {Name,nq}")]
    public class Person
    {
        public string Name { get; set; }
        public string Surname { get; set; }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Person[] people = new Person[] {
                new Person {
                    Name = "Ivan",
                    Surname = "Ivanov"
                },
                new Person
                {
                    Name = "Petr",
                    Surname = "Petrov"
                }
            };
        }
    }
}
```cs
