# ASP.NET MVC Practical Quiz

---

# Section A — Basic Concepts (10 Marks)

## Q1. Define MVC Architecture (2 Marks)

Explain:

- Model
- View
- Controller

Also explain:

> Why Controller is called the “middleman” in MVC?

---

## Q2. What is an ActionResult? (2 Marks)

Write a short explanation and give one example.

---

## Q3. Differentiate Between GET and POST (3 Marks)

Write at least 3 differences between:

- HTTP GET
- HTTP POST

---

## Q4. Explain Layout and Partial View (3 Marks)

Differentiate between:

- Layout
- Partial View

---

# Section B — Practical Coding Tasks (25 Marks)

## Q5. Create Empty MVC Project (5 Marks)

Create a new ASP.NET MVC Empty Project named:

```text
MVC_PracticalQuiz
```

### Requirements:

- Select Empty Template
- Enable MVC option
- Run project successfully

---

## Q6. Create HomeController (5 Marks)

Create a controller named:

```text
HomeController
```

Add following action methods:

```csharp
Index()
About()
Contact()
```

### Requirements:

- `Index()` → return simple text using `Content()`
- `About()` → return `View()`
- `Contact()` → redirect to `About()`

---

## Q7. Create Views (5 Marks)

Create views for:

```text
About.cshtml
```

Inside view display:

```html
<h1>About MVC Application</h1>
```

---

## Q8. Routing and Parameters (5 Marks)

Create:

```csharp
public ActionResult ProductDetail(int id)
{
    return Content("Product ID: " + id);
}
```

### Test URL:

```text
/Home/ProductDetail/10
```

### Expected Output:

```text
Product ID: 10
```

---

## Q9. Redirect Between Controllers (5 Marks)

Create:

```text
ProductController
```

Add action:

```csharp
AddProduct()
```

Now from `HomeController` create:

```csharp
GoToProduct()
```

### Requirement:

Redirect user to:

```text
AddProduct action inside ProductController
```

---

# Section C — Layout and Partial View (10 Marks)

## Q10. Create Layout (5 Marks)

Create layout file:

```text
_EmployeeLayout.cshtml
```

### Requirements:

- Header
- Footer
- `@RenderBody()`

Use this layout in:

- `Index.cshtml`
- `AddEmployee.cshtml`

---

## Q11. Create Partial View (5 Marks)

Create partial view:

```text
_EmployeeForm.cshtml
```

### Add fields:

- Name
- Salary

### Use partial in:

- `AddEmployee.cshtml`
- `UpdateEmployee.cshtml`

---

# Section D — Models and Data Passing (15 Marks)

## Q12. Create Employee Model (3 Marks)

Create model:

```csharp
Employee
```

### Properties:

- Id
- Name
- Salary

---

## Q13. Pass Single Object to View (4 Marks)

Inside controller:

- Create Employee object
- Add values:
  - Id = 1
  - Name = "Charles"
  - Salary = 5000

Send model to view.

### In View:

Display data using table.

---

## Q14. Pass List of Employees (4 Marks)

Create list of employees:

| Id | Name    | Salary |
|----|----------|---------|
| 1  | Charles  | 5000 |
| 2  | Bernard  | 4000 |

Pass list to view and display using:

```csharp
foreach
```

---

## Q15. HTTP POST Form Submission (4 Marks)

Create:

```text
AddEmployee Form
```

### Requirements:

- Use `method="post"`
- Input fields:
  - Id
  - Name
  - Salary

Create:

- GET action
- POST action

Bind form data to Employee model.

---

# Bonus Challenge (Optional – 5 Extra Marks)

Create a mini Employee Management MVC application containing:

- Controller
- Views
- Layout
- Partial View
- Employee Model
- Form Submission
- Redirects

---

# Viva Questions (Practice)

1. Why do we use ActionResult?
2. What happens if View is missing?
3. Difference between `View()` and `Content()`?
4. Why are layouts useful?
5. What is model binding?
6. Why is POST more secure than GET?
7. What is the purpose of `@RenderBody()`?
8. Why do we use Partial Views?

---

# Final Practical Challenge

Create this complete flow:

```text
Browser
   ↓
Controller
   ↓
Action Method
   ↓
Model
   ↓
View
   ↓
Layout
   ↓
Partial View
   ↓
Browser Output
```

Explain each step practically with code.

---

# Evaluation Criteria

| Task | Marks |
|---|---|
| MVC Concepts | 10 |
| Controllers & Actions | 10 |
| Views | 5 |
| Layout & Partial View | 10 |
| Models | 7 |
| HTTP GET/POST | 8 |
| Total | 50 |

---