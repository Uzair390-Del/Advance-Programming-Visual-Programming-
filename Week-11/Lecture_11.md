# Lab Lecture: Using BeginForm and HTML Helper Methods in ASP.NET MVC

## Introduction

In this lab lecture, we will learn how to use `Html.BeginForm()` in ASP.NET MVC for submitting form data. We will also explore how to use HTML Helper methods such as `TextBoxFor()` and `LabelFor()` to generate form elements dynamically.

This lecture demonstrates:

- Creating forms using BeginForm
- Updating employee data
- Sending model data from View to Controller
- Using HTTP POST methods
- Working with Partial Views
- Using HTML Helper methods instead of normal HTML input tags

---

# 1. Understanding Html.BeginForm()

Previously, forms were created using the standard `<form>` tag. ASP.NET MVC also provides another method called `Html.BeginForm()` which simplifies form creation and model binding.

## Syntax

```csharp
@using (Html.BeginForm("ActionName", "ControllerName", FormMethod.Post,
                       new { enctype = "multipart/form-data" }))
{
    // Form Elements
}
```

## Parameters

| Parameter | Description |
|---|---|
| ActionName | Name of the controller action |
| ControllerName | Name of the controller |
| FormMethod.Post | Specifies HTTP POST method |
| enctype | Used when partials/files are involved |

---

# 2. Creating Update Employee View

## UpdateEmployee.cshtml

```csharp
@using (Html.BeginForm("UpdateEmployee", "Employee", FormMethod.Post,
                       new { enctype = "multipart/form-data" }))
{
    @Html.Partial("EmployeePartial")
}
```

## Explanation

- `Html.BeginForm()` creates a form.
- `"UpdateEmployee"` is the action method.
- `"Employee"` is the controller name.
- `FormMethod.Post` sends data using POST request.
- `enctype` is added because the page contains a partial view.

---

# 3. Creating Employee Model

## Employee.cs

```csharp
public class Employee
{
    public int Id { get; set; }

    public string Name { get; set; }

    public int Salary { get; set; }
}
```

## Explanation

This model stores employee information:

- Employee ID
- Employee Name
- Employee Salary

---

# 4. Sending Data from Controller to View

## EmployeeController.cs

### GET Method

```csharp
public ActionResult UpdateEmployee()
{
    Employee employee = new Employee();

    employee.Id = 1;
    employee.Name = "Charles";
    employee.Salary = 1000;

    return View(employee);
}
```

## Explanation

- A new employee object is created.
- Initial values are assigned.
- Data is passed to the View.

---

# 5. Creating POST Method

## POST Action Method

```csharp
[HttpPost]
public ActionResult UpdateEmployee(Employee employee)
{
    return View(employee);
}
```

## Explanation

- `[HttpPost]` handles form submission.
- Updated values are automatically received in the `employee` object.
- MVC model binding maps form values to the model.

---

# 6. Creating Partial View

## EmployeePartial.cshtml

### Using Normal HTML Input Tags

```html
<label>ID</label>
<input type="text" name="Id" />

<label>Name</label>
<input type="text" name="Name" />

<label>Salary</label>
<input type="text" name="Salary" />
```

---

# 7. Using HTML Helper Methods

ASP.NET MVC provides helper methods to generate form controls easily.

## Replacing Input Tags with TextBoxFor()

```csharp
@Html.TextBoxFor(model => model.Id)

@Html.TextBoxFor(model => model.Name)

@Html.TextBoxFor(model => model.Salary)
```

---

# 8. Using LabelFor()

Instead of manually writing labels, MVC provides `LabelFor()`.

```csharp
@Html.LabelFor(model => model.Id)

@Html.LabelFor(model => model.Name)

@Html.LabelFor(model => model.Salary)
```

---

# 9. Complete Partial View Example

## EmployeePartial.cshtml

```csharp
<div>
    @Html.LabelFor(model => model.Id)
    @Html.TextBoxFor(model => model.Id)
</div>

<div>
    @Html.LabelFor(model => model.Name)
    @Html.TextBoxFor(model => model.Name)
</div>

<div>
    @Html.LabelFor(model => model.Salary)
    @Html.TextBoxFor(model => model.Salary)
</div>

<input type="submit" value="Update Employee" />
```

---

# 10. Execution Flow

## Step 1: Open Update Employee Page

Initial values appear:

| Field | Value |
|---|---|
| Id | 1 |
| Name | Charles |
| Salary | 1000 |

## Step 2: Modify Values

Example:

| Field | New Value |
|---|---|
| Id | 2 |
| Name | Bernard |
| Salary | 2000 |

## Step 3: Submit Form

When the button is clicked:

- Form data is posted to the controller.
- POST method receives updated data.
- MVC automatically updates the model.

---

# 11. Important Concepts Learned

## Html.BeginForm()

Used to create forms in ASP.NET MVC.

## FormMethod.Post

Used to submit data securely to the server.

## Partial Views

Reusable UI components.

## Model Binding

Automatically maps form data to model properties.

## HTML Helper Methods

Used to generate form controls dynamically.

---

# 12. Difference Between Input Tags and HTML Helpers

| HTML Input Tags | HTML Helpers |
|---|---|
| Manual coding | Automatic generation |
| No model binding support | Strong model binding |
| More chances of errors | Cleaner and safer |
| Less maintainable | Easier to maintain |

---

# 13. Advantages of HTML Helper Methods

- Strongly typed
- Better readability
- Automatic model binding
- Reduces coding effort
- Easier maintenance

---

# 14. Conclusion

In this lab lecture, we learned:

- How to create forms using `Html.BeginForm()`
- How to send data using POST methods
- How MVC model binding works
- How to use Partial Views
- How to replace HTML input fields with MVC HTML Helper methods like:
  - `TextBoxFor()`
  - `LabelFor()`

We also observed that both normal HTML input tags and MVC Helper methods can be used for form submission, but HTML Helper methods provide cleaner and more maintainable code.

---

# Viva Questions

## Q1. What is Html.BeginForm() in ASP.NET MVC?

`Html.BeginForm()` is an HTML Helper method used to create forms that submit data to a controller action.

## Q2. What is the purpose of FormMethod.Post?

It sends form data securely to the server using the HTTP POST method.

## Q3. What is Model Binding?

Model Binding automatically maps submitted form values to model properties.

## Q4. What is a Partial View?

A Partial View is a reusable view component used inside other views.

## Q5. Name two HTML Helper methods used in this lecture.

- `TextBoxFor()`
- `LabelFor()`

---

# Practical Output

After execution:

- Employee data appears in textboxes.
- User updates values.
- Updated values are received in controller successfully.
# Lab Lecture: Using JSON and AJAX in ASP.NET MVC

# Introduction

In this lab lecture, we will learn how to use JSON in ASP.NET MVC applications. JSON is commonly used for transferring data between the server and the client without reloading the web page.

We will also learn how to use AJAX and jQuery to call controller methods asynchronously and display data dynamically on the View page.

This lecture demonstrates:

- Introduction to JSON
- Understanding JsonResult
- Returning JSON data from Controller
- Using AJAX in ASP.NET MVC
- Using jQuery with MVC
- Updating page content without reloading
- Displaying dynamic data using `<span>`

---

# 1. What is JSON?

JSON stands for JavaScript Object Notation.

It is:

- A lightweight data format
- Easy to read and write
- Used for data exchange between client and server
- Widely used in web applications

JSON is commonly used in ASP.NET MVC applications for:

- AJAX operations
- Dynamic page updates
- API communication
- Sending and receiving data asynchronously

---

# 2. What is JsonResult in MVC?

JsonResult is an Action Result type in ASP.NET MVC used to return data in JSON format.

## Syntax

```csharp
public JsonResult MethodName()
{
    return Json(data);
}
```

## Purpose

- Sends JSON data from Controller to View
- Works efficiently with AJAX requests
- Avoids full page reloads

---

# 3. Creating Dynamic Date Example

In this example:

- A button will request the current date from the server.
- The controller returns the date in JSON format.
- AJAX receives the result.
- The date is displayed inside a `<span>` element.

---

# 4. Designing the View

## Index.cshtml

```html
<span id="date"></span>

<br /><br />

<button onclick="GetDateWithJson()">
    Get Date With JSON
</button>
```

---

# 5. Explanation of View Elements

| Element | Purpose |
|---|---|
| `<span>` | Displays returned JSON data |
| `id="date"` | Used to target the span |
| Button | Calls JavaScript function |

---

# 6. Creating JSON Action in Controller

## EmployeeController.cs

```csharp
public JsonResult GetDateWithJson()
{
    string jsonDate = DateTime.Today.ToShortDateString();

    return Json(jsonDate);
}
```

---

# 7. Explanation of Controller Code

## JsonResult

Returns data in JSON format.

## DateTime.Today.ToShortDateString()

Gets today's date.

## return Json(jsonDate)

Sends the date value to the View page.

---

# 8. Adding jQuery to Project

To perform AJAX operations, jQuery library must be included.

## Example

```html
<script src="~/Scripts/jquery-3.4.1.min.js"></script>
```

---

# 9. Writing AJAX Function

## JavaScript Section

```html
<script>

    function GetDateWithJson()
    {
        $.ajax({
            url: '@Url.Action("GetDateWithJson", "Employee")',
            type: 'POST',

            success: function(result)
            {
                $("#date").html(result);
            }
        });
    }

</script>
```

---

# 10. Explanation of AJAX Code

| Code | Purpose |
|---|---|
| `$.ajax()` | Performs asynchronous request |
| `url` | Redirects to controller action |
| `type: 'POST'` | Uses HTTP POST method |
| `success` | Executes when data is received |
| `$("#date").html(result)` | Displays returned data in span |

---

# 11. Execution Flow

## Step 1: Open Web Page

Initially:

- Span is empty
- Button is visible

## Step 2: Click Button

When button is clicked:

- JavaScript function executes
- AJAX request is sent to controller

## Step 3: Controller Executes

Controller:

- Gets current date
- Converts it into JSON format
- Sends result back

## Step 4: Display Result

AJAX receives result and updates the `<span>` element without reloading the page.

---

# 12. Output Example

## Before Button Click

```text
[Empty Span]
```

## After Button Click

```text
05/11/2026
```

---

# 13. Advantages of Using JSON and AJAX

| Advantage | Description |
|---|---|
| Faster Response | No full page reload |
| Better User Experience | Dynamic content update |
| Lightweight | Small data transfer |
| Efficient | Reduces server load |
| Interactive UI | Improves responsiveness |

---

# 14. Important Concepts Learned

## JSON

A lightweight data exchange format.

## JsonResult

Returns JSON data from Controller.

## AJAX

Allows asynchronous communication with server.

## jQuery

Simplifies JavaScript and AJAX operations.

## Dynamic Page Update

Changes page content without refreshing.

---

# 15. Real-World Uses of JSON in MVC

JSON is commonly used for:

- Delete operations
- Search functionality
- Live notifications
- Auto-complete textboxes
- Data loading
- APIs
- Dashboard updates

---

# 16. Complete Example Code

## View Code

```html
<span id="date"></span>

<br /><br />

<button onclick="GetDateWithJson()">
    Get Date With JSON
</button>

<script src="~/Scripts/jquery-3.4.1.min.js"></script>

<script>

    function GetDateWithJson()
    {
        $.ajax({
            url: '@Url.Action("GetDateWithJson", "Employee")',
            type: 'POST',

            success: function(result)
            {
                $("#date").html(result);
            }
        });
    }

</script>
```

## Controller Code

```csharp
public JsonResult GetDateWithJson()
{
    string jsonDate = DateTime.Today.ToShortDateString();

    return Json(jsonDate);
}
```

---

# 17. Conclusion

In this lab lecture, we learned:

- What JSON is
- How JsonResult works in ASP.NET MVC
- How to use AJAX with jQuery
- How to send data from Controller to View
- How to update page content dynamically
- How to avoid page reloads using AJAX

This technique is widely used in modern web applications for creating interactive and responsive websites.

---

# Viva Questions

## Q1. What is JSON?

JSON is a lightweight data format used for data exchange between client and server.

## Q2. What is JsonResult in MVC?

JsonResult is an Action Result type used to return JSON data from the controller.

## Q3. What is AJAX?

AJAX is a technique used to communicate with the server asynchronously without reloading the page.

## Q4. Why is jQuery used in AJAX?

jQuery simplifies AJAX operations and JavaScript coding.

## Q5. What is the purpose of success function in AJAX?

It executes after the server successfully returns data.

## Q6. What does $("#date").html(result) do?

It inserts the returned JSON data into the span element.

---

# Practical Output

After execution:

- Clicking the button fetches today's date.
- Date appears dynamically inside the span.
- Web page does not reload.
- Data transfer happens using JSON and AJAX.
# Lab Lecture: ViewBag, ViewData, and TempData in ASP.NET MVC

# Introduction

In this lab lecture, we will learn about three important data transfer objects in ASP.NET MVC:

- ViewBag
- ViewData
- TempData

In previous lectures, data was transferred using Model objects. However, sometimes we need to transfer small amounts of additional data that do not belong to the model. In such situations, ASP.NET MVC provides ViewBag, ViewData, and TempData.

This lecture demonstrates:

- Understanding ViewBag
- Understanding ViewData
- Understanding TempData
- Passing data from Controller to View
- Passing data between Actions
- Using data transfer objects in MVC
- Displaying transferred data in Views

---

# 1. Understanding Data Transfer Objects

ASP.NET MVC provides three built-in data transfer objects:

| Object | Purpose |
|---|---|
| ViewBag | Transfers data from Controller to View |
| ViewData | Transfers data from Controller to View |
| TempData | Transfers data from one Action to another Action |

---

# 2. Difference Between ViewBag, ViewData, and TempData

## ViewBag and ViewData

- Used to send data from Controller to View
- Data exists only during the current request
- Mostly used for small amounts of data

## TempData

- Used to transfer data between Actions
- Can transfer data between same or different controllers
- Stores data temporarily

---

# 3. Using ViewData

## Syntax

```csharp
ViewData["Key"] = Value;
```

## Example

```csharp
ViewData["Age"] = 20;
```

### Explanation

- `"Age"` is the key
- `20` is the value
- Data is stored temporarily during the request

---

# 4. Using ViewBag

## Syntax

```csharp
ViewBag.Key = Value;
```

## Example

```csharp
ViewBag.Job = "Engineer";
```

### Explanation

- `Job` is the property name
- `"Engineer"` is the assigned value

---

# 5. Controller Example Using ViewBag and ViewData

## EmployeeController.cs

```csharp
public ActionResult Index()
{
    ViewData["Age"] = 20;

    ViewBag.Job = "Engineer";

    return View();
}
```

---

# 6. Accessing ViewData in View

## Index.cshtml

```html
<p>
    Age = @ViewData["Age"]
</p>
```

### Explanation

- Retrieves data using the key `"Age"`
- Displays value inside paragraph tag

---

# 7. Accessing ViewBag in View

## Index.cshtml

```html
<p>
    Job = @ViewBag.Job
</p>
```

### Explanation

- Retrieves data using property name `Job`
- Displays value inside paragraph tag

---

# 8. Complete Example of ViewBag and ViewData

## Controller Code

```csharp
public ActionResult Index()
{
    ViewData["Age"] = 20;

    ViewBag.Job = "Engineer";

    return View();
}
```

## View Code

```html
<p>
    Age = @ViewData["Age"]
</p>

<p>
    Job = @ViewBag.Job
</p>
```

---

# 9. Output Example

```text
Age = 20

Job = Engineer
```

---

# 10. Understanding TempData

TempData is used to transfer data from one Action to another Action.

## Syntax

```csharp
TempData["Key"] = Value;
```

## Example

```csharp
TempData["Company"] = "Oak";
```

---

# 11. Using TempData in Controller

## Index Action

```csharp
public ActionResult Index()
{
    string company2 = "Oak";

    TempData["Company"] = company2;

    return View();
}
```

### Explanation

- Data is stored inside TempData
- `"Company"` acts as the key
- `"Oak"` is the stored value

---

# 12. Retrieving TempData in Another Action

## UpdateEmployee Action

```csharp
public ActionResult UpdateEmployee()
{
    string company = (string)TempData["Company"];

    Employee employee = new Employee();

    employee.Name = company;

    return View(employee);
}
```

---

# 13. Explanation of TempData Retrieval

| Code | Purpose |
|---|---|
| `TempData["Company"]` | Retrieves stored data |
| `(string)` | Type casting |
| `employee.Name = company` | Assigns value to model |

---

# 14. Adding Navigation Button in View

## Index.cshtml

```html
<input type="submit"
       onclick="window.location.href='/Employee/UpdateEmployee'" />
```

### Explanation

- Redirects user to `UpdateEmployee` action
- TempData value becomes available in next action

---

# 15. Execution Flow

## Step 1: Open Index Page

Controller stores:

```text
Company = Oak
```

inside TempData.

---

## Step 2: Click Button

Button redirects user to:

```text
/Employee/UpdateEmployee
```

---

## Step 3: UpdateEmployee Action Executes

Action retrieves TempData value:

```text
Oak
```

---

## Step 4: Data Appears in View

Employee Name field displays:

```text
Oak
```

---

# 16. Important Concepts Learned

## ViewData

- Dictionary-based object
- Uses key-value pairs
- Requires type casting

## ViewBag

- Dynamic object
- Easier syntax
- No explicit casting needed

## TempData

- Used between actions
- Stores data temporarily
- Useful for redirects

---

# 17. Comparison Table

| Feature | ViewData | ViewBag | TempData |
|---|---|---|---|
| Type | Dictionary | Dynamic Object | Dictionary |
| Usage | Controller to View | Controller to View | Action to Action |
| Type Casting | Required | Not Required | Required |
| Lifetime | Current Request | Current Request | Next Request |

---

# 18. Advantages of Using Data Transfer Objects

- Simple data transfer
- Reduces dependency on models
- Useful for temporary data
- Easy implementation
- Supports MVC architecture

---

# 19. Complete Example Code

## Controller Code

```csharp
public ActionResult Index()
{
    ViewData["Age"] = 20;

    ViewBag.Job = "Engineer";

    string company2 = "Oak";

    TempData["Company"] = company2;

    return View();
}

public ActionResult UpdateEmployee()
{
    string company = (string)TempData["Company"];

    Employee employee = new Employee();

    employee.Name = company;

    return View(employee);
}
```

---

## View Code

```html
<p>
    Age = @ViewData["Age"]
</p>

<p>
    Job = @ViewBag.Job
</p>

<input type="submit"
       onclick="window.location.href='/Employee/UpdateEmployee'" />
```

---

# 20. Conclusion

In this lab lecture, we learned:

- What ViewBag is
- What ViewData is
- What TempData is
- How to transfer data from Controller to View
- How to transfer data between Actions
- Differences between ViewBag, ViewData, and TempData
- How to display transferred data in Views

These data transfer objects are very useful in ASP.NET MVC applications for passing temporary and additional data.

---

# Viva Questions

## Q1. What is ViewBag in ASP.NET MVC?

ViewBag is a dynamic object used to transfer data from Controller to View.

---

## Q2. What is ViewData?

ViewData is a dictionary object used to transfer data from Controller to View.

---

## Q3. What is TempData?

TempData is used to transfer data from one Action to another Action.

---

## Q4. Which object is used between two Actions?

TempData is used between two Actions.

---

## Q5. Which object requires type casting?

ViewData and TempData require type casting.

---

## Q6. Which object uses dynamic properties?

ViewBag uses dynamic properties.

---

# Practical Output

After execution:

- Age displays as 20 using ViewData
- Job displays as Engineer using ViewBag
- Company value "Oak" transfers using TempData
- Employee Name field displays Oak after redirection
# 📘 Lecture: Validation in ASP.NET MVC using Data Annotations

---

# 📖 Course Context & Motivation

## Why This Lecture Matters

When users enter data into an application, developers cannot simply trust that all data will be correct.

For example:

- A user may leave important fields empty
- A user may enter text where numbers are required
- A user may type an invalid email address
- A user may upload the wrong file type

If applications do not check these inputs, they can produce:

- Incorrect records
- Application errors
- Security issues
- Poor user experience

To solve these problems, ASP.NET MVC provides a feature called **Validation**.

Validation helps developers define rules for user input before data is saved or processed.

---

# 🎯 Learning Objectives

After completing this lecture, students will be able to:

- Understand the concept of validation in MVC
- Understand Data Annotations
- Apply validation rules to model properties
- Use built-in validation attributes
- Understand `ModelState.IsValid`
- Display validation messages in MVC views
- Prevent invalid data from being submitted

---

# 🧠 What is Validation?

Validation means checking whether user input follows the required rules.

For example:

| Input Field | Validation Rule |
|---|---|
| Name | Minimum 3 characters |
| Age | Only numbers allowed |
| Salary | Must be within a valid range |
| Email | Must follow email format |
| File Upload | Only image files allowed |

Validation ensures that invalid or empty data is not accepted by the application.

---

# 📌 Validation in ASP.NET MVC

In ASP.NET MVC, validation is commonly implemented using:

- **Data Annotations**
- **Validation Attributes**

MVC automatically checks these rules when data is submitted from a form.

If validation fails:

- MVC marks the model as invalid
- Error messages are shown in the view
- Data is not processed

---

# 📦 Data Annotations

Data Annotations are special attributes added to model properties.

These attributes define validation rules.

MVC framework automatically reads these rules and validates the data.

---

# 📚 Namespace for Data Annotations

To use validation attributes, include the following namespace:

```csharp
using System.ComponentModel.DataAnnotations;
```

---

# 🏗️ Common Validation Attributes

## 1. Required

Used when a field must not be empty.

```csharp
[Required]
```

### Example

```csharp
[Required]
public string Name { get; set; }
```

If the user leaves the Name field empty, validation will fail.

---

# 2. StringLength

Defines the maximum length of a string.

```csharp
[StringLength(50)]
```

### Example

```csharp
[StringLength(50)]
public string Name { get; set; }
```

This allows a maximum of 50 characters.

---

# 3. MinLength

Defines the minimum number of characters.

```csharp
[MinLength(3)]
```

### Example

```csharp
[MinLength(3)]
public string Name { get; set; }
```

The user must enter at least 3 characters.

---

# 4. MaxLength

Defines the maximum number of characters.

```csharp
[MaxLength(100)]
```

### Example

```csharp
[MaxLength(100)]
public string Description { get; set; }
```

---

# 5. Range

Used for numeric fields.

Defines minimum and maximum values.

```csharp
[Range(1000, 50000)]
```

### Example

```csharp
[Range(1000, 50000)]
public int Salary { get; set; }
```

Salary must be between 1000 and 50000.

---

# 6. EmailAddress

Checks whether the entered text follows email format.

```csharp
[EmailAddress]
```

### Example

```csharp
[EmailAddress]
public string Email { get; set; }
```

---

# 7. FileExtensions

Validates allowed file types.

```csharp
[FileExtensions(Extensions = "jpg,png")]
```

### Example

```csharp
[FileExtensions(Extensions = "jpg,png")]
public string ImageFile { get; set; }
```

Only JPG and PNG files are allowed.

---

# 🏢 Real-World Example

Suppose a company registration form contains:

- Name
- Age
- Salary
- Email
- Profile Image

Validation rules may be:

| Field | Rule |
|---|---|
| Name | Required |
| Age | Must be numeric |
| Salary | Between 1000–50000 |
| Email | Valid email format |
| Image | Only JPG or PNG |

Without validation:

- Invalid data may enter the database
- Reports become incorrect
- System reliability decreases

---

# 🧱 Example MVC Model

## Employee Model

```csharp
using System.ComponentModel.DataAnnotations;

namespace MVCValidation.Models
{
    public class Employee
    {
        [Required(ErrorMessage = "Please fill the Name field")]
        [MinLength(3)]
        [MaxLength(50)]
        public string Name { get; set; }

        [Required(ErrorMessage = "Please enter Age")]
        [Range(18, 60)]
        public int Age { get; set; }

        [Required(ErrorMessage = "Please enter Salary")]
        [Range(1000, 50000)]
        public int Salary { get; set; }

        [EmailAddress(ErrorMessage = "Invalid Email Address")]
        public string Email { get; set; }
    }
}
```

---

# 🔍 Understanding ModelState.IsValid

MVC provides a property called:

```csharp
ModelState.IsValid
```

This property checks whether all validation rules are satisfied.

---

# ⚙️ Working of ModelState.IsValid

| Condition | Result |
|---|---|
| All validations pass | True |
| Any validation fails | False |

---

# 🧪 Example in Controller

```csharp
public ActionResult Create(Employee emp)
{
    if(ModelState.IsValid)
    {
        return Content("Model State is Valid");
    }
    else
    {
        return Content("Model State is NOT Valid");
    }
}
```

---

# 🧠 How MVC Validation Works

## Step-by-Step Process

### Step 1

User fills the form.

### Step 2

Form data is sent to controller.

### Step 3

MVC checks validation attributes.

### Step 4

`ModelState.IsValid` becomes:

- `true` if data is correct
- `false` if data is incorrect

### Step 5

Validation messages are shown in the view.

---

# 🖥️ Displaying Validation Messages in View

MVC provides helper methods to display errors.

---

# Example Razor View

```html
@model MVCValidation.Models.Employee

@using (Html.BeginForm())
{
    <div>
        Name:
        @Html.TextBoxFor(x => x.Name)
        @Html.ValidationMessageFor(x => x.Name)
    </div>

    <div>
        Age:
        @Html.TextBoxFor(x => x.Age)
        @Html.ValidationMessageFor(x => x.Age)
    </div>

    <div>
        Salary:
        @Html.TextBoxFor(x => x.Salary)
        @Html.ValidationMessageFor(x => x.Salary)
    </div>

    <div>
        Email:
        @Html.TextBoxFor(x => x.Email)
        @Html.ValidationMessageFor(x => x.Email)
    </div>

    <button type="submit">Save</button>
}
```

---

# 🧪 Practical Demonstration

## Case 1 — Empty Name Field

Validation Rule:

```csharp
[Required]
```

### User Input

Name field left empty.

### Result

- `ModelState.IsValid = false`
- Error message appears

---

# Case 2 — Valid Name

### User Input

```text
Charles
```

### Result

- `ModelState.IsValid = true`
- Data accepted successfully

---

# Case 3 — Invalid Salary

Validation Rule:

```csharp
[Range(1000,50000)]
```

### User Input

```text
200
```

### Result

Validation fails because salary is outside allowed range.

---

# 🎨 Custom Error Messages

Custom messages improve user experience.

### Example

```csharp
[Required(ErrorMessage = "Please fill the Name field")]
```

---

# 📌 Multiple Validation Rules Together

Multiple annotations can be applied to one property.

### Example

```csharp
[Required]
[MinLength(3)]
[MaxLength(50)]
public string Name { get; set; }
```

This means:

- Field cannot be empty
- Minimum 3 characters
- Maximum 50 characters

---

# ⚡ Advantages of MVC Validation

| Advantage | Description |
|---|---|
| Data Accuracy | Prevents incorrect input |
| Better Security | Blocks invalid data |
| Improved User Experience | Shows clear messages |
| Easy Maintenance | Rules stay inside model |
| Automatic Validation | MVC handles validation automatically |

---

# 🚫 Problems Without Validation

Without validation:

- Empty records may be stored
- Incorrect emails may enter database
- Users may upload invalid files
- Numeric fields may contain text
- Application errors may occur

---

# 🧠 Interview Questions

## Q1. What is validation in MVC?

Validation is the process of checking whether user input follows required rules before processing data.

---

## Q2. What are Data Annotations?

Data Annotations are attributes used in models to define validation rules.

---

## Q3. What is the purpose of `ModelState.IsValid`?

It checks whether all validation rules are satisfied.

---

## Q4. Which namespace contains validation annotations?

```csharp
System.ComponentModel.DataAnnotations
```

---

## Q5. What is the difference between `MinLength` and `MaxLength`?

- `MinLength` defines minimum characters
- `MaxLength` defines maximum characters

---

# 🧪 Complete Example

## Employee Model

```csharp
using System.ComponentModel.DataAnnotations;

public class Employee
{
    [Required(ErrorMessage = "Name is required")]
    [StringLength(50)]
    public string Name { get; set; }

    [Range(1000,50000)]
    public int Salary { get; set; }

    [EmailAddress]
    public string Email { get; set; }
}
```

---

## Controller

```csharp
public class EmployeeController : Controller
{
    public ActionResult Create()
    {
        return View();
    }

    [HttpPost]
    public ActionResult Create(Employee emp)
    {
        if(ModelState.IsValid)
        {
            return Content("Data Saved Successfully");
        }

        return View(emp);
    }
}
```

---

# 🧾 Summary

In this lecture, we learned:

- What validation is
- Why validation is important
- Data Annotations in MVC
- Common validation attributes
- `ModelState.IsValid`
- Displaying validation messages
- Practical implementation in MVC

Validation is one of the most important features in professional web application development because it ensures data correctness and improves application reliability.

---

# 📚 Next Lecture

In the next lecture, we will study:

- Multi-Layer Architecture
- Separation of Concerns
- Business Layer
- Data Access Layer
- Professional MVC Project Structure

---
