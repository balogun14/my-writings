# ✅ Week 3: Analyzing Healthcare Data

## 🎯 Objective
Use functions and libraries to analyze medical data and draw insights.

---

## 🗓️ Day 1: Functions – Writing Reusable Code

### 🔹 Goals
- Learn how to define and use functions
- Structure logic into reusable blocks
- Start modularizing the vitals analyzer

### 🔍 Topics to Cover
- `def` keyword and function syntax
- Parameters and return values
- Scope and local/global variables
- Simple examples: `calculate_bmi`, `average_pulse`

### 📌 Checklist
- [ ] Define a function to calculate BMI or average
- [ ] Write a function that takes vitals and returns a dictionary
- [ ] Reuse functions in multiple parts of the code
- [ ] Discuss the concept of clean and reusable code

### 📚 Resources
- [ ] YouTube: “Python Functions” by Programming with Mosh
- [ ] Python Docs: Defining Functions
- [ ] Real Python: Defining Your Own Functions

---

## 🗓️ Day 2: Conditionals and Logic – Flagging Abnormal Vitals

### 🔹 Goals
- Apply conditional logic to medical use-cases
- Flag abnormal vital signs like high BP, low pulse, etc.

### 🔍 Topics to Cover
- `if`, `elif`, `else` statements
- Logical operators (`and`, `or`, `not`)
- Comparison operators (`==`, `!=`, `>`, `<`)
- Integrating with functions

### 📌 Checklist
- [ ] Write a function to check if vitals are in normal range
- [ ] Flag values like:
  - Pulse < 60 or > 100
  - Temp < 36 or > 38
  - BP systolic > 130
- [ ] Print warning messages with patient name
- [ ] Create a summary report of flagged patients

### 📚 Resources
- [ ] Python Crash Course by Eric Matthes (Ch. 2–4)
- [ ] W3Schools: Python Conditions
- [ ] Real Python: If Statements in Python

---

## 🗓️ Day 3: Project – Vitals Analyzer with Pandas Intro

### 🔹 Goals
- Use pandas to organize and analyze patient data
- Combine previous sessions into a functional analyzer
- Introduce dataframes, basic statistics, and filtering

### 🔍 Project Plan
- Input: patient records (name, temp, pulse, BP)
- Process:
  - Store in DataFrame
  - Flag abnormal values using logic
  - Calculate mean, min, max
- Output:
  - Print flagged patients
  - Show summary stats table

### 📌 Checklist
- [ ] Import `pandas` and create a DataFrame
- [ ] Add vitals for 3–5 patients
- [ ] Use `.mean()`, `.max()`, `.min()` for summary
- [ ] Use boolean indexing to flag abnormalities
- [ ] Print patient names with issues
- [ ] Use `df.to_csv()` to export results (bonus)

### 📚 Resources
- [ ] pandas Quick Start: 10 Minutes to pandas
- [ ] “Python Crash Course” by Eric Matthes (Ch. 5)
- [ ] YouTube: Pandas Basics by Data School (optional)

---

## 🧠 Project Outcome
By the end of the week, students should be able to:
- Build a vitals analyzer that processes and flags health data
- Use functions for cleaner code
- Begin using pandas for real-world healthcare data analysis
