#  Week 2 Lab – Control Flow Statements to Object-Oriented Programming in C#

##  Lab Overview

This lab introduces students to fundamental programming constructs in C#.  
The lab begins with **control flow statements** (decision-making and loops) and gradually transitions into **Object-Oriented Programming (OOP)** concepts.

By the end of this lab, students will be able to:

- Implement conditional logic
- Use switch statements and switch expressions
- Control loops using break and continue
- Create classes and objects
- Apply constructors
- Implement inheritance and polymorphism
- Use interfaces
- Handle exceptions
- Create simple event-driven programs

---

#  PART 1: CONTROL FLOW STATEMENTS IN C#

Control flow statements determine the order in which code executes.

They allow programs to:
- Make decisions
- Repeat actions
- Control execution flow

---

# 1️ Conditional Statements in C#

##  Overview

Conditional statements allow a program to execute specific code blocks based on whether a condition is true or false.

They are used for decision-making in programs.

---

##  if Statement

###  Syntax Overview

```csharp
if (condition)
{
    // code executes if condition is true
}


###  Example
```csharp
int marks = 60;

if (marks >= 50)
{
    Console.WriteLine("You Passed");
}
```

###  Explanation

- `marks >= 50` → condition  
- If true → message prints  
- If false → nothing happens  

---

##  if–else Statement

###  Syntax
```csharp
if (condition)
{
    // true block
}
else
{
    // false block
}
```

###  Example
```csharp
int number = 10;

if (number % 2 == 0)
{
    Console.WriteLine("Even Number");
}
else
{
    Console.WriteLine("Odd Number");
}
```

---

## if–else if–else Ladder

###  Overview

Used when checking multiple conditions.

###  Example
```csharp
int marks = 85;

if (marks >= 90)
{
    Console.WriteLine("Grade A");
}
else if (marks >= 70)
{
    Console.WriteLine("Grade B");
}
else
{
    Console.WriteLine("Grade C");
}
```

---

# 2️ Switch Statement in C#

##  Overview

Switch statement is used when comparing one variable against multiple fixed values.

It improves readability compared to multiple if-else conditions.

---

##  Traditional Switch Statement

###  Syntax Overview
```csharp
switch (variable)
{
    case value1:
        // code
        break;

    case value2:
        // code
        break;

    default:
        // code
        break;
}
```

###  Example
```csharp
int day = 3;

switch (day)
{
    case 1:
        Console.WriteLine("Monday");
        break;

    case 2:
        Console.WriteLine("Tuesday");
        break;

    case 3:
        Console.WriteLine("Wednesday");
        break;

    default:
        Console.WriteLine("Invalid Day");
        break;
}
```

###  Explanation

- `switch(day)` → variable being checked  
- `case` → matching value  
- `break` → exits switch  
- `default` → runs if no match  

---

##  Switch Expression (Modern C#)

###  Overview

Switch expression is a shorter and cleaner version of traditional switch.

It:
- Uses `=>`
- Does not require `break`
- Returns a value directly
- Makes code more readable
- Available in C# 8.0 and later

---

###  Syntax Overview
```csharp
variable switch
{
    value1 => result1,
    value2 => result2,
    _ => defaultResult
};
```

---

###  Example 1 – Returning a Value
```csharp
int day = 1;

string result = day switch
{
    1 => "Monday",
    2 => "Tuesday",
    3 => "Wednesday",
    _ => "Invalid Day"
};

Console.WriteLine(result);
```

---

###  Example 2 – Direct Console.WriteLine Version
```csharp
int number = 1;

_ = number switch
{
    1 => Console.WriteLine("One"),
    2 => Console.WriteLine("Two"),
    _ => Console.WriteLine("Other Number")
};
```

###  Explanation

- `1 => Console.WriteLine("One")`
- `_` acts as default
- `_ =` is required because switch expression returns a value

---

# 3️ Break and Continue

##  Overview

Break and Continue are loop control statements.

- `break` → stops loop completely  
- `continue` → skips current iteration  

---

##  break Example
```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
        break;

    Console.WriteLine(i);
}
```

### Output:
```
1
2
```

---

##  continue Example
```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
        continue;

    Console.WriteLine(i);
}
```

### Output:
```
1
2
4
5
```

---

# 4️ Loops in C#

##  Overview

Loops are used to execute a block of code repeatedly.

C# provides:

- for loop  
- while loop  
- do-while loop  
- foreach loop  

---

##  For Loop

### Syntax
```csharp
for (initialization; condition; increment)
{
    // code
}
```

### Example
```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```

---

##  While Loop

### Overview
Condition checked before execution.

### Example
```csharp
int i = 1;

while (i <= 5)
{
    Console.WriteLine(i);
    i++;
}
```

---

##  Do–While Loop

### Overview
Executes at least once.

### Example
```csharp
int i = 1;

do
{
    Console.WriteLine(i);
    i++;
}
while (i <= 5);
```

---

##  Foreach Loop

### Overview
Used to iterate through arrays and collections.

### Example
```csharp
string[] names = { "Ali", "Ahmed", "Sara" };

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

---

#  PART 2: OBJECT-ORIENTED PROGRAMMING IN C#

OOP organizes code using classes and objects.

It improves:
- Code reusability  
- Maintainability  
- Modularity  

---

# 5️ Creating Classes and Objects

##  Overview

A class is a blueprint.  
An object is an instance of a class.
A class is a fundamental building blocks in object oriented programming that defines the structure and behaviour of the objects. They encapsulate data for the object and methods to manipulate and use that data.

---

###  Syntax Overview
```csharp
class ClassName
{
    // fields
    // methods
}
```

---

###  Example
```csharp
class Student
{
    public string name;
    public int age;

    public void Display()
    {
        Console.WriteLine("Name: " + name);
        Console.WriteLine("Age: " + age);
    }
}
```

###  Explanation

- Class → Blueprint  
- Fields → Data  
- Methods → Behavior  
- Object created using `new`  

---

# 6️ Implementing Constructors

##  Overview

A constructor initializes object data when an object is created.

It:
- Has same name as class  
- Has no return type  
- Runs automatically  

---

###  Example
```csharp
class Student
{
    public string name;

    public Student(string studentName)
    {
        name = studentName;
    }
}
```

---

# 7️ Inheritance-Based Programs

##  Overview

Inheritance allows one class to reuse properties and methods of another class.

It promotes:
- Code reusability  
- Logical hierarchy  
- Reduced duplication  

---

###  Syntax Overview
```csharp
class Parent
{
}

class Child : Parent
{
}
```

---

###  Example
```csharp
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal is eating");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is barking");
    }
}
```

###  Explanation

- `Dog : Animal` → Dog inherits Animal  
- Dog can use `Eat()`  
- No need to rewrite code  

---

# 8️ Polymorphism Demonstration

##  Overview

Polymorphism means “many forms”.

A method behaves differently depending on the object.

Achieved using:
- `virtual`
- `override`

---

###  Example
```csharp
class Animal
{
    public virtual void Sound()
    {
        Console.WriteLine("Animal makes sound");
    }
}

class Dog : Animal
{
    public override void Sound()
    {
        Console.WriteLine("Dog barks");
    }
}
```

---

# 9️ Interface Implementation

##  Overview

An interface defines a contract.

It:
- Contains only method declarations  
- Forces classes to implement methods  
- Supports multiple inheritance  

---

###  Example
```csharp
interface IShape
{
    void Draw();
}

class Circle : IShape
{
    public void Draw()
    {
        Console.WriteLine("Drawing Circle");
    }
}
```

---

#  Exception Handling (try–catch)

##  Overview

Exception handling prevents program crashes when runtime errors occur.

---

###  Syntax Overview
```csharp
try
{
    // risky code
}
catch (Exception ex)
{
    // handle error
}
```

---

###  Example
```csharp
try
{
    int num = int.Parse("abc");
}
catch (Exception ex)
{
    Console.WriteLine("Error: " + ex.Message);
}
```

---

# 1️ Simple Event-Based Console Program

## 📖 Overview

An event is an action that occurs during program execution.

In console applications, events are implemented using:
- Delegates  
- `event` keyword  

---

###  Example
```csharp
using System;

class Button
{
    public event Action OnClick;

    public void Click()
    {
        OnClick?.Invoke();
    }
}

class Program
{
    static void Main()
    {
        Button btn = new Button();

        btn.OnClick += () =>
        {
            Console.WriteLine("Button was clicked!");
        };

        btn.Click();
    }
}
```

---

#  Final Lab Practice Tasks

1. Check whether a number is positive, negative, or zero.  
2. Create calculator using traditional switch.  
3. Convert calculator into switch expression.  
4. Demonstrate break and continue.  
5. Print multiplication table using loops.  
6. Create class Car with constructor.  
7. Create ElectricCar using inheritance.  
8. Override a method.  
9. Implement interface IVehicle.  
10. Handle invalid input using try–catch.  
11. Create a simple event-driven console program.  

---

#  Learning Outcomes

After completing this lab, students will be able to:

- Apply conditional logic  
- Implement switch and switch expressions  
- Control loops efficiently  
- Develop object-oriented programs  
- Use inheritance and polymorphism  
- Implement interfaces  
- Handle runtime exceptions  
- Build simple event-driven applications  

---