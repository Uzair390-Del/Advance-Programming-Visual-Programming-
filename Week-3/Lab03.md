# Week 3 Lab – Introduction to Windows Forms Application in C#

## Lab Overview

This lab introduces students to **Windows Forms Application development** using C#.

The lab begins with understanding the Visual Studio environment and gradually moves toward building interactive GUI applications using forms, controls, properties, and events.

By the end of this lab, students will be able to:

- Create a Windows Forms Application
- Understand the Visual Studio interface components
- Work with Forms and Controls
- Use MessageBox with different options
- Modify control properties (Anchor, Dock, Visible, etc.)
- Handle button click and keyboard events
- Build simple event-driven desktop applications

---

# PART 1: GETTING STARTED WITH WINDOWS FORMS

Windows Forms is a GUI (Graphical User Interface) framework used to build desktop applications in C#.

It allows developers to create applications using:
- Forms
- Buttons
- Labels
- TextBoxes
- MessageBoxes
- Events

---

# 1️⃣ Creating a Windows Forms Application

## Overview

A Windows Forms application provides a visual interface where users can interact using buttons, textboxes, and other controls.

### Steps to Create Project

1. Open Visual Studio
2. Click **Create New Project**
3. Select **Windows Forms App (.NET Framework or .NET)**
4. Enter project name
5. Click Create

After creation, Visual Studio generates:

- `Form1.cs`
- `Program.cs`
- Designer files

---

# 2️⃣ Understanding Visual Studio Windows

## Overview

Visual Studio provides multiple windows to manage projects efficiently.

---

## 🔹 Solution Explorer

### Overview

Solution Explorer displays:

- Project files
- Forms
- References
- Resources

It allows you to:
- Add new forms
- Rename files
- Manage project structure

---

## 🔹 Toolbox Window

### Overview

Toolbox contains all UI controls such as:

- Button
- Label
- TextBox
- ComboBox
- CheckBox
- DataGridView

You can drag and drop controls onto the form.

---

## 🔹 Properties Window

### Overview

The Properties Window allows you to:

- Change control name
- Modify text
- Change size
- Adjust color
- Set Anchor, Dock, Visible, etc.

Each control has unique properties.

---

## 🔹 Server Explorer

Used to manage:

- Database connections
- Servers
- Services

---

## 🔹 Team Explorer

Used for:

- Git version control
- Managing repositories
- Team collaboration

---

## 🔹 Data Sources Window

Used to connect application to:

- Databases
- DataTables
- Objects

---

## 🔹 Error List Window

Displays:

- Compilation errors
- Warnings
- Messages

Helps in debugging.

---

# PART 2: WORKING WITH FORMS

---

# 3️⃣ Understanding Forms

## Overview

A Form is the main window of a Windows Forms application.

It acts as a container for controls.

When you create a Windows Forms project, `Form1` is automatically generated.

---

### Basic Form Structure

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
    }

    private void Form1_Load(object sender, EventArgs e)
    {

    }
}
```

### Explanation

- `Form1 : Form` → Form1 inherits from Form class
- `InitializeComponent()` → Initializes UI components
- `Form1_Load` → Executes when form loads

---

# 4️⃣ MessageBox in Windows Forms

## Overview

MessageBox is used to display messages to the user.

---

## Basic MessageBox

```csharp
string message = "This is My first MessageBox!";
string messagetitle = "Uzair Hassan";
MessageBox.Show(message, messagetitle);
```

---

## MessageBox with Yes/No Buttons

```csharp
string message = "Do you want to close window?";
string messagetitle = "Close Window!";
MessageBoxButtons buttons1 = MessageBoxButtons.YesNo;

DialogResult result = MessageBox.Show(message, messagetitle, buttons1);

if (result == DialogResult.Yes)
{
    this.Close();
}
```

---

## MessageBox with Icon

```csharp
string message = "Do you see icon?";
string messagetitle = "OK";

MessageBox.Show(message, messagetitle, 
    MessageBoxButtons.YesNo, 
    MessageBoxIcon.Information);
```

---

# 5️⃣ Working with Buttons

## Overview

Buttons allow users to trigger actions when clicked.

---

## Button Click Event

```csharp
private void button1_Click(object sender, EventArgs e)
{
    string message = "First Button Clicked!";
    MessageBox.Show(message);
}
```

---

## Changing Button Text on Click

```csharp
private void firstBtn_Click(object sender, EventArgs e)
{
    firstBtn.Text = "Clicked!";
}
```

---

## Button KeyPress Event

```csharp
private void firstBtn_KeyPress(object sender, KeyPressEventArgs e)
{
    firstBtn.Text = "Enter";
}
```

---

# 6️⃣ Important Button Properties

## Overview

Each control has properties that define its behavior and appearance.

---

## 🔹 Anchor Property

Keeps control fixed relative to form edges when resizing.

Example:
- Top, Bottom
- Left, Right

---

## 🔹 Dock Property

Attaches control to a side of the form.

Options:
- Top
- Bottom
- Left
- Right
- Fill

---

## 🔹 Visible Property

Determines whether control is visible.

```csharp
button1.Visible = false;
```

---

## 🔹 Enabled Property

Enables or disables control.

```csharp
button1.Enabled = false;
```

---

## 🔹 Text Property

Changes displayed text.

```csharp
button1.Text = "Submit";
```

---

## 🔹 Name Property

Used to reference control in code.

Example:
`firstBtn`

---

# 7️⃣ Understanding Events in Windows Forms

## Overview

An event is an action triggered by the user or system.

Examples:

- Click
- Load
- KeyPress
- MouseHover

Events follow this structure:

```csharp
private void ControlName_EventName(object sender, EventArgs e)
{
    // event logic
}
```

---

# Complete Example Covered in Class

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
    }

    private void Form1_Load(object sender, EventArgs e)
    {
        // MessageBox examples covered
    }

    private void button1_Click(object sender, EventArgs e)
    {
        string message = "First Button Clicked!";
        MessageBox.Show(message);
    }

    private void firstBtn_Click(object sender, EventArgs e)
    {
        firstBtn.Text = "Clicked!";
    }

    private void firstBtn_KeyPress(object sender, KeyPressEventArgs e)
    {
        firstBtn.Text = "Enter";
    }
}
```

---

# Final Lab Practice Tasks

1. Create a Windows Forms application.
2. Add two buttons and display different messages.
3. Create a confirmation MessageBox before closing form.
4. Change button text after click.
5. Disable a button after clicking.
6. Use Anchor property and resize form.
7. Dock a button to bottom of form.
8. Handle KeyPress event.
9. Hide and show button using Visible property.
10. Create a simple interactive form with at least three controls.

---

# Learning Outcomes

After completing this lab, students will be able to:

- Develop basic GUI applications
- Understand Visual Studio environment
- Use Windows Forms controls
- Implement MessageBox with different options
- Modify control properties
- Handle events in Windows Forms
- Build interactive desktop applications

---