# Lecture 2: Object-Oriented Programming (OOP) in C++

---

## Course Context & Motivation

### Why This Lecture Matters

- Modern software systems are built using **Object-Oriented Programming**
- OOP helps in managing **large and complex programs**
- C++ is one of the most powerful languages for learning core OOP concepts
- Almost every modern language (Java, C#, Python) follows OOP principles

### Real-World Connection

- Banking systems manage customers as **objects**
- Hospital systems manage patients as **objects**
- University systems manage students as **objects**
- Companies manage employees as **objects**

> OOP helps us model real-world entities into programming structures.

---

# Introduction to OOP in C++

---

## What is Object-Oriented Programming?

### Definition

Object-Oriented Programming (OOP) is a programming approach where we organize software design around **objects** rather than functions.

### Key Idea

> “Everything in OOP revolves around objects.”

An object contains:
- Data (variables)
- Functions (behaviors)

---

# Data Hiding and Encapsulation

---

## What is Data Hiding?

### Definition

Data hiding means restricting direct access to some components of an object.

We do not allow everyone to access internal data directly.

### Why Do We Need Data Hiding?

- To protect data from misuse
- To prevent accidental changes
- To improve security

---

## Real-Life Analogy

### ATM Machine Example

When you use an ATM:

- You enter PIN
- You withdraw money

But you cannot:
- Directly access the bank database
- Change your account balance manually

The internal system is hidden from you.

> This is called **Data Hiding**.

---

## What is Encapsulation?

### Definition

Encapsulation is the process of **wrapping data and functions together into a single unit (class)** and restricting direct access.

In C++, encapsulation is achieved using:

- `private`
- `public`
- `protected`

---

## Access Specifiers in C++

| Access Type | Accessible From |
|------------|-----------------|
| private    | Inside class only |
| public     | Anywhere |
| protected  | Inside class & derived class |

---

## Example of Encapsulation

```cpp
#include <iostream>
using namespace std;

class BankAccount
{
private:
    double balance;   // Hidden data

public:
    void deposit(double amount)
    {
        balance += amount;
    }

    void showBalance()
    {
        cout << "Balance: " << balance << endl;
    }
};

int main()
{
    BankAccount obj;
    obj.deposit(5000);
    obj.showBalance();

    return 0;
}


```

## Explanation

- balance is private → cannot be accessed directly  
- deposit() is public → allows controlled modification  
- showBalance() → allows safe viewing  


# Structure in C++

## What is a Structure?

### Definition

A structure (struct) is a user-defined data type that groups different data types under one name.

It is used to represent a record.

## Declaring a Structure

### Syntax

``` cpp

struct StructureName
{
    dataType member1;
    dataType member2;
};

```


### Example: Student Structure
``` cpp
#include <iostream>
using namespace std;

struct Student
{
    int rollNo;
    string name;
    float marks;
};
```
# Structures and Classes in C++

## Defining Structure Variables

``` cpp
Student s1;
```

### Or

``` cpp
struct Student s1;
```

------------------------------------------------------------------------

## Accessing Structure Members

We use the dot (.) operator.

``` cpp
s1.rollNo = 101;
s1.name = "Ali";
s1.marks = 85.5;

cout << s1.name;

```

------------------------------------------------------------------------

## Real-Life Example of Structure

Think of a student admission form:

-   Roll Number
-   Name
-   Marks

All grouped together under one entity → **Student**

------------------------------------------------------------------------

# Company Structure Example

``` cpp
#include <iostream>
using namespace std;

struct Employee
{
    int id;
    string name;
    string department;
    double salary;
};

int main()
{
    Employee emp1;

    emp1.id = 1;
    emp1.name = "Usman";
    emp1.department = "IT";
    emp1.salary = 50000;

    cout << "Employee Name: " << emp1.name << endl;
    cout << "Department: " << emp1.department << endl;
    cout << "Salary: " << emp1.salary << endl;

    return 0;
}
```

------------------------------------------------------------------------

# Limitation of Structure

In traditional C++:

-   All members are public by default
-   No strong data protection
-   Less security compared to class

This leads us to **Class**.

------------------------------------------------------------------------

# Class in C++

## What is a Class?

### Definition

A class is a user-defined data type that contains:

-   Data members (variables)
-   Member functions (functions)

It supports full OOP features like:

-   Encapsulation
-   Data hiding
-   Inheritance
-   Polymorphism

------------------------------------------------------------------------

# Structure vs Class

  Structure                       Class
  ------------------------------- --------------------------------
  Members are public by default   Members are private by default
  Used for simple data grouping   Used for complete OOP design
  Less security                   More secure

------------------------------------------------------------------------

# Example: Company Class

``` cpp
#include <iostream>
using namespace std;

class Company
{
private:
    string companyName;
    int totalEmployees;

public:
    void setData(string name, int employees)
    {
        companyName = name;
        totalEmployees = employees;
    }

    void showData()
    {
        cout << "Company Name: " << companyName << endl;
        cout << "Total Employees: " << totalEmployees << endl;
    }
};

int main()
{
    Company c1;
    c1.setData("TechSoft", 150);
    c1.showData();
    return 0;
}
```

------------------------------------------------------------------------

# Why Class is Better than Structure?

-   Provides data protection
-   Controls access using private and public
-   Supports advanced OOP features
-   Suitable for large software systems

------------------------------------------------------------------------

# Real-World Comparison

### Structure is like:

A simple form that just holds data.

### Class is like:

A complete system that:

-   Holds data
-   Validates data
-   Controls how data is accessed

------------------------------------------------------------------------

# Summary of Today's Lecture

-   OOP organizes programs using objects
-   Data hiding protects internal data
-   Encapsulation wraps data and functions together
-   Structure groups data but has limited protection
-   Class provides full OOP features

------------------------------------------------------------------------

# Class Activity (Short Quiz -- Informal)

## Activity Instructions

Discuss in pairs and answer verbally.

1.  What is the difference between data hiding and encapsulation?
2.  Why is private data important in a class?
3.  What operator is used to access structure members?
4.  What is the default access specifier in:
    -   struct?
    -   class?
5.  Which one is more secure: structure or class? Why?

------------------------------------------------------------------------

# Mini Coding Task (5 Minutes)

Create a structure named **Car** with:

-   brand
-   model
-   price

Then print its values.

------------------------------------------------------------------------

# Thought Question

If we want to protect employee salary from direct modification, should
we use struct or class? Why?

------------------------------------------------------------------------

# What's Next?

-   Constructors in C++
-   Member Functions in Detail
-   Object Creation and Memory Concepts

------------------------------------------------------------------------

# Reference

C++ OOP Text Book
