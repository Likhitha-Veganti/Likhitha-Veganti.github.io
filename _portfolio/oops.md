---
title: "DiverseLifestyles(Simple Python OOPS Task)"
excerpt: "This Python program demonstrates the principles of Object-Oriented Programming (OOP) by implementing classes for Human, Hiker, Scientist, Swimmer, and ScientificSwimmer. The classes showcase the concepts of inheritance, encapsulation, and polymorphism."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/Python/tree/main/OOPS%20Task).

# OOP Python Program: Human, Hiker, Scientist, Swimmer, ScientificSwimmer

## Overview:
This Python program demonstrates the principles of Object-Oriented Programming (OOP) by implementing classes for Human, Hiker, Scientist, Swimmer, and ScientificSwimmer. The classes showcase the concepts of inheritance, encapsulation, and polymorphism.

1. **Human Class:**
   - Contains private attributes: name and age.
   - Methods:
     - `__init__()`: Initializes name and age.
     - `hobby()`: Prints a generic hobby message.
     - `info()`: Prints the values of name and age.

2. **Hiker Class:**
   - Inherits from the Human class.
   - Overrides the `hobby()` method to print "likes going on hikes."

3. **Scientist Class:**
   - Inherits from the Human class.
   - Additional private attribute: lab.
   - Methods:
     - `__init__()`: Calls the Human class `__init__()` and sets the lab attribute.
     - `hobby()`: Overrides the `hobby()` method to print "likes doing scientific experiments."
     - `labName()`: Prints "works at the X lab," where X is the value of the lab attribute.

4. **Swimmer Class:**
   - Inherits from the Human class.
   - Additional private attribute: hours.
   - Methods:
     - `__init__()`: Calls the Human class `__init__()` and sets the hours attribute.
     - `hobby()`: Overrides the `hobby()` method to print "likes swimming."
     - `hoursSwimming()`: Prints "Swims X hours per week," where X is the value of the hours attribute.

5. **ScientificSwimmer Class:**
   - Inherits from both Scientist and Swimmer classes.
   - Methods:
     - `__init__()`: Calls the parent `__init__()` methods.
     - `hobby()`: Overrides the `hobby()` method to print "likes swimming and doing scientific experiments."

## Program Execution:
- The program prompts the user to enter data for a Human, Hiker, Scientist, Swimmer, ScientificSwimmer, or exit.
- This process occurs in a loop until the user chooses to exit.
- For each class chosen by the user, an object is created using user-provided data.
- If the user chooses to exit, the program prints relevant information for each created object and ends.

This OOP Python program offers a practical example of class implementation, inheritance, and user interaction, providing a hands-on experience with OOP concepts.
