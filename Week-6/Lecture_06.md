#  Week 6 Lab – Event-Driven Programming & Windows Forms (C#)

##  Lab Overview

This lab introduces students to **event-driven programming using Windows Forms** in C#.

Students will design a **mini GUI-based application** and implement logic using:

- Control flow statements  
- UI components  
- Event handling  
- Input validation  

---

##  Learning Objectives

By the end of this lab, students will be able to:

- Design Windows Forms applications  
- Understand event-driven programming  
- Handle user interactions using events  
- Apply loops and conditional logic in GUI apps  
- Validate user input  

---

#  PART 1: INTRODUCTION TO EVENT-DRIVEN PROGRAMMING

##  What is Event-Driven Programming?

Event-driven programming means:

👉 The program waits for the user to do something  
👉 Then it responds to that action  

---

##  What is an Event?

An **event** is any action performed by the user or system.

### Examples:
- Clicking a button  
- Typing in a textbox  
- Selecting from a dropdown  

---

##  Real-Life Analogy

Think of a **doorbell**:

- Someone presses the bell (event)  
- The bell rings (response)  

👉 Same in programming:
- User clicks button → Code runs  

---

##  Structure of an Event

Every event has:

1. **Control (who triggers it)** → Button, TextBox  
2. **Event (what happens)** → Click, KeyPress  
3. **Event Handler (response code)**  

---

##  Example of Event Handler

```csharp
private void btnClick_Click(object sender, EventArgs e)
{
    MessageBox.Show("Button Clicked!");
}
```

### Explanation:
- `btnClick` → control  
- `Click` → event  
- Code inside `{}` → action  

---

#  PART 2: WINDOWS FORM CONTROLS

##  Label

```csharp
label1.Text = "Enter Value";
```

---

##  TextBox

```csharp
string input = textBox1.Text;
```

---

##  Button

```csharp
private void btnSubmit_Click(object sender, EventArgs e)
{
    MessageBox.Show("Submitted");
}
```

---

##  ComboBox

```csharp
comboBox1.Items.Add("Option 1");
```

---

##  RadioButton

```csharp
if (radioButton1.Checked)
{
    MessageBox.Show("Selected");
}
```

---

#  PART 3: IMPORTANT EVENTS (DETAILED)

##  1. Click Event

📌 Triggered when user clicks a button

```csharp
private void btnRun_Click(object sender, EventArgs e)
{
    MessageBox.Show("Running...");
}
```

---

##  2. KeyPress Event

📌 Triggered when user presses a key

```csharp
private void textBox1_KeyPress(object sender, KeyPressEventArgs e)
{
    if (!char.IsDigit(e.KeyChar))
    {
        e.Handled = true;
    }
}
```

### Explanation:
- Blocks invalid input  
- Allows only numbers  

---

##  3. SelectedIndexChanged Event

 Triggered when user selects item in ComboBox

```csharp
private void comboBox1_SelectedIndexChanged(object sender, EventArgs e)
{
    string value = comboBox1.SelectedItem.ToString();
}
```

---

#  PART 4: INPUT VALIDATION

```csharp
if (textBox1.Text == "")
{
    MessageBox.Show("Field required!");
}
```

```csharp
if (comboBox1.SelectedIndex == -1)
{
    MessageBox.Show("Select option!");
}
```

---

#  PART 5: CONTROL FLOW

##  Condition

```csharp
if (num % 2 == 0)
{
    Console.WriteLine("Even");
}
```

---

##  Loop

```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```

---

#  PART 6: MINI PROJECT FLOW

```csharp
int start = Convert.ToInt32(textBox1.Text);
int end = Convert.ToInt32(textBox2.Text);

string result = "";

for (int i = start; i <= end; i++)
{
    if (i % 2 == 0)
    {
        result += i + " ";
    }
}

textBoxResult.Text = result;
```

---

#  PRACTICE TASKS

1. Create UI with TextBox & Button  
2. Implement Click event  
3. Validate input  
4. Use loop to generate numbers  
5. Apply condition  

---

#  LEARNING OUTCOMES

- Understand event-driven programming  
- Handle user events  
- Build GUI applications  
- Apply logic in real applications  

