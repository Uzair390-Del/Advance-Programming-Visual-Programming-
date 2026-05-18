
## Total Marks: 70

This updated quiz now includes:

- Html.BeginForm()
- HTML Helper Methods
- JSON
- AJAX
- jQuery
- ViewBag
- ViewData
- TempData
- Validation using Data Annotations
- ModelState.IsValid

---

# Section A — MVC Concepts & Theory (15 Marks)

## Q1. Explain MVC Architecture (3 Marks)

Define:

- Model
- View
- Controller

Also explain:

Why is Controller called the “middleman” in MVC?

---

## Q2. What is ActionResult? (2 Marks)

Explain ActionResult and write examples of:

- ViewResult
- RedirectToRouteResult
- ContentResult

---

## Q3. Differentiate Between HTTP GET and HTTP POST (3 Marks)

Write at least 4 differences between:

| GET | POST |
|---|---|

Also explain:

Which method is more secure and why?

---

## Q4. Explain Layout and Partial View (3 Marks)

Differentiate between:

- Layout
- Partial View

Also explain:

- Purpose of `@RenderBody()`
- Why partial views improve reusability

---

## Q5. Explain ViewBag, ViewData, and TempData (4 Marks)

Differentiate between:

- ViewBag
- ViewData
- TempData

Include:

- Lifetime
- Usage
- Type casting
- Example of each

---

# Section B — Controllers, Views & Routing (20 Marks)

## Q6. Create MVC Project (4 Marks)

Create a new ASP.NET MVC Empty Project named:

```text
MVC_IntermediateQuiz
```

Requirements:

- Select Empty Template
- Enable MVC
- Run project successfully

---

## Q7. Create HomeController (4 Marks)

Create:

```text
HomeController
```

Add actions:

```csharp
Index()
About()
Contact()
```

Requirements:

- `Index()` → return Content
- `About()` → return View
- `Contact()` → redirect to About()

---

## Q8. Routing with Parameters (4 Marks)

Create:

```csharp
public ActionResult ProductDetail(int id)
{
    return Content("Product ID: " + id);
}
```

Test URL:

```text
/Home/ProductDetail/10
```

Expected Output:

```text
Product ID: 10
```

---

## Q9. Redirect Between Controllers (4 Marks)

Create:

```text
ProductController
```

Add action:

```csharp
AddProduct()
```

Now inside `HomeController` create:

```csharp
GoToProduct()
```

Requirement:

Redirect user to:

```text
ProductController → AddProduct()
```

---

## Q10. Using ViewBag and ViewData (4 Marks)

Inside controller:

```csharp
ViewBag.Job = "Software Engineer";

ViewData["Age"] = 25;
```

Display both values inside View using Razor syntax.

---

# Section C — Layouts, Partial Views & Forms (15 Marks)

## Q11. Create Layout File (5 Marks)

Create:

```text
_EmployeeLayout.cshtml
```

Requirements:

- Header
- Navigation Menu
- Footer
- `@RenderBody()`

Use this layout in:

- Index.cshtml
- AddEmployee.cshtml

---

## Q12. Create Partial View (5 Marks)

Create partial view:

```text
_EmployeeForm.cshtml
```

Fields:

- Id
- Name
- Salary

Use partial view inside:

- AddEmployee.cshtml
- UpdateEmployee.cshtml

---

## Q13. Html.BeginForm() and HTML Helpers (5 Marks)

Create Employee Form using:

```csharp
@using (Html.BeginForm())
```

Use helper methods:

- `Html.TextBoxFor()`
- `Html.LabelFor()`

Requirements:

- Submit button
- POST action
- Bind form data to Employee model

---

# Section D — Models, Validation & Model Binding (20 Marks)

## Q14. Create Employee Model (4 Marks)

Create model:

```csharp
Employee
```

Properties:

- Id
- Name
- Salary
- Email

Apply validations:

- `[Required]`
- `[Range]`
- `[EmailAddress]`
- `[MinLength]`

---

## Q15. ModelState Validation (4 Marks)

Inside POST action:

```csharp
if(ModelState.IsValid)
{
    return Content("Valid Data");
}
else
{
    return Content("Invalid Data");
}
```

Explain:

- Purpose of `ModelState.IsValid`
- What happens when validation fails

---

## Q16. Pass Single Object to View (4 Marks)

Create Employee object:

```csharp
Id = 1
Name = "Charles"
Salary = 5000
```

Pass object to View and display using table.

---

## Q17. Pass List of Employees (4 Marks)

Create list:

| Id | Name | Salary |
|---|---|---|
| 1 | Charles | 5000 |
| 2 | Bernard | 4000 |

Display data using:

```csharp
foreach
```

---

## Q18. HTTP POST Form Submission (4 Marks)

Create:

```text
AddEmployee Form
```

Requirements:

- GET action
- POST action
- Use Employee model binding
- Use `Html.BeginForm()`
- Display submitted values

---

# Section E — JSON, AJAX & jQuery (15 Marks)

## Q19. JsonResult in MVC (5 Marks)

Create action:

```csharp
public JsonResult GetDateWithJson()
{
    string date = DateTime.Today.ToShortDateString();

    return Json(date);
}
```

Explain:

- Purpose of JsonResult
- Why JSON is used in MVC

---

## Q20. AJAX with jQuery (5 Marks)

Create AJAX request using:

```javascript
$.ajax()
```

Requirements:

- Call `GetDateWithJson()`
- Use POST method
- Display result inside:

```html
<span id="date"></span>
```

---

## Q21. Dynamic Update Without Page Reload (5 Marks)

Explain step-by-step flow of:

```text
Button Click
↓
AJAX Request
↓
Controller Action
↓
JSON Response
↓
Span Update
```

Also explain:

Why AJAX improves user experience.

---

# Bonus Challenge (Optional — 10 Extra Marks)

Create a mini Employee Management System containing:

- MVC Architecture
- Employee Model
- Layout
- Partial View
- Html.BeginForm()
- Validation
- ViewBag/ViewData
- TempData
- AJAX JSON Date Example
- Form Submission using POST
- ModelState Validation

---

# Viva Questions (Practice)

## MVC Basics

1. Why do we use MVC architecture?
2. What is ActionResult?
3. Difference between View() and Content()?
4. What happens if a View is missing?

---

## Forms & Helpers

5. What is Html.BeginForm()?
6. What is model binding?
7. Difference between HTML input tags and HTML Helpers?
8. Why use `TextBoxFor()`?

---

## Validation

9. What is validation?
10. What are Data Annotations?
11. What is `ModelState.IsValid`?
12. Difference between `[Required]` and `[Range]`?

---

## AJAX & JSON

13. What is JSON?
14. What is JsonResult?
15. What is AJAX?
16. Why is jQuery used in AJAX?

---

## ViewBag/ViewData/TempData

17. Difference between ViewBag and ViewData?
18. Why does TempData persist for one request?
19. Which object requires type casting?
20. Which object uses dynamic properties?

---

# Final Practical Challenge (10 Marks)

Create this complete MVC execution flow practically with code:

```text
Browser
   ↓
Routing
   ↓
Controller
   ↓
Action Method
   ↓
Model
   ↓
View
   ↓
Layout out
   ↓
Partial View
   ↓
AJAX Request
   ↓
JsonResult
   ↓
Browser Output
```

Explain each step with proper code implementation.

---

# Evaluation Criteria

| Task | Marks |
|---|---|
| MVC Concepts | 15 |
| Controllers & Routing | 20 |
| Layout & Partial Views | 15 |
| Models & Validation | 20 |
| AJAX & JSON | 15 |
| Final Challenge | 10 |
| Bonus | +10 |

---

# Total Marks

```text
70 Marks
```
