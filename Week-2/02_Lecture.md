# Lecture 2: Object-Oriented Programming in C#

---

# Course Context & Motivation

## Why This Lecture Matters

Modern software systems are complex. They contain:

- Multiple screens  
- Multiple modules  
- Large amounts of data  
- Many interacting components  

To manage this complexity, developers use **Object-Oriented Programming (OOP).**

C# is a fully object-oriented language. Understanding OOP is essential for:

- Desktop Applications  
- Web Applications  
- Enterprise Systems  
- Game Development  
- APIs and Services  

Without OOP, large software becomes:

- Difficult to manage  
- Hard to maintain  
- Prone to errors  

---

# Real-World Connection

Object-Oriented Programming models real-world entities.

## Real Examples

| Real World        | Programming        |
|------------------|-------------------|
| Car              | Car class         |
| Student          | Student object    |
| Bank Account     | Account class     |
| ATM Machine      | ATM system object |
| Hospital System  | Patient, Doctor, Appointment objects |

OOP allows us to design software the same way we think about real life.

---

# What is Object-Oriented Programming (OOP)?

## Definition

Object-Oriented Programming is a programming paradigm based on the concept of **objects**, which contain:

- Data (attributes)  
- Behavior (methods/functions)  

## Core Idea

> "Everything in the program is treated as an object."

---

# The Four Pillars of OOP

1. Encapsulation  
2. Inheritance  
3. Polymorphism  
4. Abstraction  

These four principles make software:

- Secure  
- Reusable  
- Flexible  
- Maintainable  

---

# Classes and Objects

## What is a Class?

A class is a **blueprint** for creating objects.

### Example

If we want to create students in a system:

- `Student` is a class  
- Ali, Ahmed, Sara are objects  

## What is an Object?

An object is an instance of a class.

### Real-Life Analogy

Think of a class as:

Blueprint of a house  

And an object as:

The actual house built from that blueprint.

---

# Constructors and Methods

## Constructors

A constructor is a special method used to initialize objects.

### Key Characteristics

- Same name as class  
- Runs automatically when object is created  
- Used to assign initial values  

### Real-Life Analogy

When you buy a phone:

- Default settings are already set.  
- That setup process is like a constructor.

---

## Methods

Methods define the behavior of a class.

Example behaviors:

- `CalculateSalary()`  
- `WithdrawMoney()`  
- `DisplayDetails()`  

Methods allow objects to perform actions.

---

# Encapsulation

## Definition

Encapsulation means **hiding internal data** and allowing access only through controlled methods.

## Why It Is Important

- Protects data  
- Prevents unauthorized access  
- Improves security  

### Real-Life Example

ATM Machine:

You cannot directly access bank balance storage.  
You must use buttons (methods).

That is encapsulation.

---

# Inheritance

## Definition

Inheritance allows one class to inherit properties and behaviors from another class.

## Purpose

- Code reuse  
- Logical hierarchy  
- Reduced duplication  

### Example

Parent Class: `Vehicle`  
Child Class: `Car`  

Car automatically gets:

- Speed  
- Engine  
- `Start()` method  

### Real-Life Analogy

A child inherits characteristics from parents.

---

# Polymorphism

## Definition

Polymorphism means **one interface, multiple behaviors.**

## Types

1. Compile-time (Method Overloading)  
2. Runtime (Method Overriding)  

### Real-Life Example

`Shape` → `Draw()`

- Circle → Draw circle  
- Rectangle → Draw rectangle  

Same method name, different behavior.

---

# Interfaces

## Definition

An interface defines a contract.

It contains:

- Method declarations only  
- No implementation  

Any class implementing the interface must define those methods.

## Why Interfaces Are Important

- Enforce rules  
- Enable multiple inheritance  
- Improve flexibility  

### Real-Life Analogy

Remote Control Interface:

Every TV brand must implement:

- `Power()`  
- `VolumeUp()`  
- `VolumeDown()`  

---

# Abstract Classes

## Definition

An abstract class cannot be instantiated.

It is meant to be inherited.

It can contain:

- Abstract methods (no body)  
- Normal methods (with body)  

## Difference from Interface

| Feature              | Interface | Abstract Class |
|----------------------|----------|---------------|
| Methods              | Only declarations | Both declared and defined |
| Fields               | No       | Yes |
| Multiple inheritance | Yes      | No |

---

# Structures vs Classes

## Structures (struct)

- Value type  
- Stored in stack memory  
- Lightweight  
- Suitable for small data  

## Classes

- Reference type  
- Stored in heap memory  
- Suitable for complex objects  

## Comparison Table

| Feature      | Structure | Class |
|-------------|----------|--------|
| Type        | Value    | Reference |
| Memory      | Stack    | Heap |
| Inheritance | No       | Yes |
| Suitable For| Small data | Complex systems |

---

# Enumerations (enum)

## Definition

An enumeration is a special type that defines a set of named constants.

### Example

Days:

- Monday  
- Tuesday  
- Wednesday  

Instead of using numbers like `0,1,2`, we use meaningful names.

## Benefits

- Improves readability  
- Reduces errors  
- Makes code clean  

---

# Exception Handling

## What is an Exception?

An exception is a runtime error.

Examples:

- Divide by zero  
- File not found  
- Invalid input  

## Why Handle Exceptions?

Without handling:

- Program crashes  
- Poor user experience  

## C# Exception Handling Keywords

- `try`  
- `catch`  
- `finally`  

### Real-Life Analogy

Driving a car:

Seatbelt = Exception handling  
It protects you when something goes wrong.

---

# Delegates

## Definition

A delegate is a type that represents references to methods.

It allows methods to be passed as parameters.

## Why Delegates?

- Enable callback functions  
- Enable event-driven programming  
- Increase flexibility  

### Real-Life Example

Ordering Food:

You give your phone number (delegate).  
Restaurant calls you when order is ready (method execution).

---

# Events

## Definition

An event is a mechanism that allows a class to notify other classes when something happens.

Events are built on delegates.

## Example in Visual Programming

- Button Click  
- Mouse Hover  
- Key Press  

When button is clicked:

Event triggers  
Code runs  

---

# How OOP Connects to Visual Programming

In GUI Applications:

- Form is a class  
- Button is an object  
- Click is an event  
- Event handler is a method  
- Delegates connect event to method  

OOP makes event-driven programming possible.

---

# Why OOP is Essential in C#

C# is designed as an object-oriented language.

Everything is built around:

- Classes  
- Objects  
- Methods  
- Events  

Without OOP:

- Large applications cannot be structured properly  
- Code reuse becomes difficult  
- Maintenance becomes complex  

---

# Summary of Lecture 2

- OOP models real-world systems  
- Classes create objects  
- Constructors initialize objects  
- Encapsulation protects data  
- Inheritance enables reuse  
- Polymorphism allows flexibility  
- Interfaces define contracts  
- Abstract classes provide partial abstraction  
- Structures differ from classes in memory handling  
- Enumerations improve clarity  
- Exception handling improves reliability  
- Delegates and events enable event-driven programming  

---

# What’s Next?

- Implementing Classes in C#  
- Writing Constructors and Methods  
- Applying Inheritance Practically  
- Handling Exceptions in Visual Studio  
- Creating Events in Windows Forms  

---

# Reference

- Text Book 3  
- Microsoft Official C# Documentation  
- .NET Programming Guide  