#  Lecture No 8: Introduction to ASP.NET MVC (Empty Project)

---

##  Lab Overview

In this lab, students will learn:

- What is ASP.NET MVC
- How to create an empty MVC project in Visual Studio
- How to add a Controller
- What is an Action Method
- How to run a basic MVC application

---

##  Learning Objectives

By the end of this lab, students will be able to:

- Understand the basic concept of MVC architecture
- Create an empty ASP.NET MVC project
- Add a controller manually
- Write a simple ActionResult method
- Run and test the application in a browser

---

##  Basic Concept: What is MVC?

MVC stands for:

- **Model** → Handles data and business logic  
- **View** → Handles UI (what user sees)  
- **Controller** → Handles user input and controls flow  

 In simple words:

> Controller acts like a **middleman** between Model and View.

---

##  Software Requirement

- Visual Studio (2019 / 2022)
- .NET SDK installed

---

##  Step 1: Create Empty MVC Project

Follow these steps:

1. Open **Visual Studio**
2. Click on **Create a new project**
3. Select **ASP.NET Web Application (.NET Framework)** OR **ASP.NET Core Web App**
4. Click **Next**
5. Enter:
   - Project Name: `MVC_Lab9`
6. Click **Create**

###  Important Step:

- Choose **Empty Template**
- ✔ Check **MVC (Model-View-Controller)** option

Click **Create**

---

##  Project Structure (Basic Understanding)

After creation, you will see:

- Controllers Folder
- Models Folder
- Views Folder

 Since this is an empty project, folders may be minimal.

---

##  Step 2: Add Controller

Now we will manually create a controller.

### Steps:

1. Right-click on **Controllers Folder**
2. Click **Add → Controller**
3. Select **MVC Controller - Empty**
4. Click **Add**
5. Name it:

Click **Add**

---

##  Step 3: Write Action Method

Inside `HomeController.cs`, write the following code:

```csharp
using System.Web.Mvc;

public class HomeController : Controller
{
    public ActionResult Index()
    {
        return Content("Welcome to ASP.NET MVC Application!");
    }
}
```
---

###  Understanding the Code
- Controller → Base class for all controllers
- ActionResult → Return type of action method
- Index() → Default method
- Content() → Returns simple text response

-  This means when we open the page, it will display text in browser.

---


##  Introduction

In ASP.NET MVC, **controllers play a very important role**.

- All the application logic and data handling is mainly done inside **controller classes**.

Inside controllers, we write special methods called:

> **Action Methods (ActionResult methods)**

---

##  What is an ActionResult?

An **ActionResult** is a return type of a controller method.

- In simple words:

> An ActionResult is used to **process user request and return a response**.

---

##  Key Idea

- All **operations (logic, data handling, processing)** happen inside action methods
- After processing, the result is sent to:
  - A **View (UI page)** OR
  - Another **Action** OR
  - A **different website**

---

##  Flow of Action Method

User Request → Controller → Action Method → Processing → Response (View / Redirect / Data)

- This shows that the **controller manages all the information flow**.

---

##  Basic Example

```csharp
public ActionResult Index()
{
    return View();
}
```
---

##  Explanation:
- ActionResult → Return type
- Index() → Action method
- View() → Sends response to a View page

This means:

After processing, the system will open a View page to display result.
---

## What Can We Do Inside Action Methods?

Inside an action method, we can:

- Send data to the View
- Receive data from the View
- Perform database operations
- Apply business logic
- Redirect to another action or website

- So, action methods are the main working area of MVC applications.

- Different Types of Action Results
- Returning a View
### return View();

- Used when:

You want to display a UI page
 -  Returning Content
return Content("Hello Students!");

 Used when:

You want to display simple text in browser
 -  Redirect to External URL
return Redirect("https://example.com");

 Used when:

You want to open another website
- Redirect to Another Action
return RedirectToAction("Index");

 Used when:

You want to move to another action in same controller
- Redirect to Action in Another Controller
return RedirectToAction("AddProduct", "Product");

- Important Rule:

First parameter → Action Name
Second parameter → Controller Name (without "Controller")
- Important Concept: Multiple Controllers

---

In real-world applications:

We have multiple controllers
Each controller has multiple action methods

- Example:

HomeController
ProductController
StudentController

- Each controller handles different parts of the application.

-Example: Redirect Between Actions

public ActionResult GoToProduct()
{
    return RedirectToAction("AddProduct", "Product");
}

👉 This means:

Go to AddProduct action
Inside ProductController
📥 Passing Parameters in Action Methods

We can also pass data (parameters) to action methods.

Example:
public ActionResult UpdateProduct(int id)
{
    return Content("Product ID: " + id);
}
🔄 Redirect with Parameters
return RedirectToAction("UpdateProduct", "Product", new { id = 20 });

👉 Output:

Product ID: 20
🧠 Behind the Scene (Routing Concept)
MVC uses a routing system to map URLs to actions
Example URL:
/Product/UpdateProduct/20

👉 This means:

Controller → Product
Action → UpdateProduct
Parameter → 20
⚠️ Important Notes
Controller name is written without "Controller" in URLs and redirects
Action methods must be public
Action methods usually return ActionResult
🧪 Mini Practice
Task:
Create a controller named ProductController
Add the following actions:
public ActionResult Index()
{
    return Content("Product Home");
}

public ActionResult AddProduct()
{
    return Content("Add Product Page");
}

public ActionResult GoToAddProduct()
{
    return RedirectToAction("AddProduct");
}
📝 Summary
Action methods are the core of MVC logic
They handle:
Data
Processing
Navigation
They return results using ActionResult

👉 In short:

Controller = Brain of MVC
Action Methods = Working units inside the brain