# 📘 Lecture 2: Arrays and Functions in Windows Forms (Based on Practical Implementation)

---

## Course Context & Motivation

### Why This Lecture Matters

In previous sessions, we learned how to:

- Create Windows Forms applications  
- Use buttons, textboxes, and labels  
- Understand event-driven programming  

Now, we move toward **real programming logic inside GUI applications**.

> This lecture connects backend logic (arrays, functions) with frontend (Windows Forms).

---

## Real-World Connection

Consider a simple system:

- Days of the week → stored in array  
- User clicks button → data displayed  
- User inputs numbers → result calculated  

This is how real applications work:

- Data storage  
- Data processing  
- User interaction  

---

# 🧠 Part 1: Arrays in Windows Forms

---

## What is an Array?

An array is used to store multiple values of the same type in a single variable.

---

## Types of Arrays Used

- **1D Array** → List of values  
- **2D Array** → Table format (rows & columns)  

---

## 🧪 Lab Activity 1: Display 1D Array (Days Example)

### Concept

We store **days of the week** in an array and display them in a table.

---

### Code (From Your Form1)

```csharp
private void btnShow_Click(object sender, EventArgs e)
{
    string[] days = new string[7];

    days[0] = "Monday";
    days[1] = "Tuesday";
    days[2] = "Wednsday";
    days[3] = "Thursday";
    days[4] = "Friday";
    days[5] = "Saturday";
    days[6] = "Sunday";

    for (int i = 0; i < days.Length; i++)
    {
        string rowtext = days[i];
        dataGridView1.Rows.Add(rowtext);
    }
}
