# Student Report: Modern Periodic Table (C Program)

## Project Overview
**Project Name:** Modern Periodic Table  
**Language:** C  
**Date:** September 2026  
**Student:** puviya-bit-sketch  
**Repository:** https://github.com/puviya-bit-sketch/mini-project-in-c

---

## Executive Summary
This project implements a console-based interactive periodic table application in C. The program provides a menu-driven interface allowing users to search for chemical element information by atomic number. Currently, the program supports detailed information for Hydrogen (Atomic Number 1) with an extensible structure for future elements.

---

## Project Objectives
1. ✅ Create a user-friendly menu-driven interface
2. ✅ Implement element search functionality by atomic number
3. ✅ Display comprehensive element information
4. ✅ Provide exit confirmation workflow
5. ✅ Build a foundation for a complete periodic table database

---

## Features Implemented

### 1. Welcome Screen
- Displays a welcome message to the user
- Presents main menu options clearly

### 2. Main Menu Options
- **Option 1:** Know about an element
- **Option 2:** Close the periodic table

### 3. Element Search
- Search by atomic number
- Currently supports Atomic Number 1 (Hydrogen)
- Displays the following information:
  - Element Name
  - Chemical Symbol
  - Atomic Number
  - Electronic Configuration
  - Discoverer
  - Charge

### 4. Exit Confirmation Flow
- Two-step confirmation process for closing the application
- User can choose to continue exploring after selecting exit
- Prevents accidental application closure

---

## Code Structure

### Variables Used
```c
int n;          // Main menu selection
int m;          // Search method selection
int a;          // Atomic number input
int Exit;       // Exit confirmation variables
int Exi;        // Reserved for future use
```

### Program Flow
```
Start
  ├─ Display Welcome & Main Menu
  ├─ Read Option (n)
  ├─ If n == 1 (Know about element)
  │   ├─ Prompt for search method
  │   ├─ If m == 3 (Search by atomic number)
  │   │   ├─ Read atomic number
  │   │   └─ Display element details
  │   └─ End
  └─ Else if n == 2 (Close periodic table)
      ├─ Confirm exit (Step 1)
      ├─ If Exit == 6 (Yes)
      │   ├─ Confirm exit again (Step 2)
      │   ├─ If Exit == 4 → Close application
      │   └─ If Exit == 5 → Continue program
      └─ If Exit == 7 (No) → Continue program
End
```

---

## Sample Output

```
Welcome to Modern Periodic Table

>Enter 1 to know about an element

>Enter 2 to close the periodic table

ENTER
1

>Press 3 to search the element by atomic number

ENTER
3
Enter the atomic number of the element to be searched: 1

Name : Hydrogen
Symbol : H
Atomic Number : 1
Electronic Configuration : 1s^1
Discovered By : Henry Cavendish
Charge : +1
```

---

## Strengths

✅ **Clear User Interface:** Intuitive menu-driven design  
✅ **Exit Safety:** Two-step confirmation prevents accidental closure  
✅ **Structured Code:** Organized using if-else conditionals  
✅ **Extensible Design:** Easy to add more elements to the database  
✅ **Educational Value:** Simple and easy to understand for beginners  

---

## Areas for Improvement

### Critical Issues
1. **Line 61 - Bug in scanf:**
   ```c
   printf("%d",&a);;  // Should be scanf, not printf
   ```
   This prevents user input from being captured correctly.

2. **Limited Element Database:** Only supports Hydrogen (atomic number 1)

3. **No Input Validation:** Program doesn't handle invalid menu choices gracefully

### Suggested Enhancements

#### 1. Add More Elements
```c
// Expand the if-else chain to support elements 2-118
if(a==2) {
    printf("Name : Helium\n");
    // ... element details
}
```

#### 2. Use Data Structures
```c
struct Element {
    int atomicNumber;
    char name[50];
    char symbol[5];
    char config[50];
    char discoverer[50];
    int charge;
};
```

#### 3. Implement Input Validation
```c
if(m != 3) {
    printf("Invalid choice! Please enter 3.\n");
}
```

#### 4. Create a Loop for Continuous Operation
```c
while(1) {
    // Display menu
    // Process user input
    // Allow exit when user chooses to close
}
```

#### 5. Add More Search Methods
- Search by element name
- Search by symbol
- Display all elements

#### 6. Improve Error Handling
- Handle invalid atomic numbers
- Provide user-friendly error messages

---

## Technical Details

### Programming Concepts Used
- **Sequential Programming:** Step-by-step execution
- **Conditional Statements:** if-else for decision-making
- **User Input/Output:** scanf and printf functions
- **Menu-Driven Interface:** User interaction through numbered options

### Compilation and Execution

**Compile:**
```bash
gcc -o periodic_table periodic_table.c
```

**Run:**
```bash
./periodic_table
```

---

## Bug Report

### Bug #1: Incorrect printf in Line 61
**Severity:** High  
**Location:** Line 61 in the Exit == 5 condition  
**Issue:** 
```c
printf("%d",&a);;  // WRONG - tries to print uninitialized variable
```
**Should be:**
```c
scanf("%d",&a);    // CORRECT - reads user input
```

---

## Testing Summary

| Test Case | Input Path | Expected Output | Status |
|-----------|-----------|-----------------|--------|
| View Hydrogen (Option 1) | 1 → 3 → 1 | Hydrogen details | ✅ Works |
| Exit application | 2 → 6 → 4 | Program closes | ✅ Works |
| Cancel exit | 2 → 6 → 5 | Program continues | ⚠️ Bug at line 61 |
| Don't exit initially | 2 → 7 → 1 | Program continues | ✅ Works |
| Invalid element | 1 → 3 → 2 | No output | ❌ Missing handling |

---

## Conclusion

The Modern Periodic Table project demonstrates fundamental programming concepts and provides a solid foundation for a more comprehensive periodic table application. With the suggested improvements and bug fixes, this project can be significantly enhanced to support all 118 elements and provide advanced search capabilities.

### Next Steps
1. Fix the bug at line 61
2. Add support for more elements (at least up to 10)
3. Implement input validation
4. Convert to use loops for better code efficiency
5. Consider using external data files or arrays for element data

---

## Recommendations

**Grade Assessment:** B+ (Good foundation with room for enhancement)

**Comments:**
- Clear understanding of menu-driven programming
- Good logical flow but needs bug fixes
- Code can be more DRY (Don't Repeat Yourself) using loops and arrays
- Consider refactoring for scalability

---

**Report Generated:** September 2026  
**Repository:** https://github.com/puviya-bit-sketch/mini-project-in-c
