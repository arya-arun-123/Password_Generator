# Secure Password Generator in Python

## Overview

This project is a secure password generator built using Python. It allows users to generate strong and customizable passwords by selecting the desired password length and character categories.

The program uses Python's `secrets` module for cryptographically secure random number generation, making the generated passwords suitable for real-world use.

---

## Features

* Generate passwords of user-defined length
* Include uppercase letters (A-Z)
* Include lowercase letters (a-z)
* Include digits (0-9)
* Include special symbols (!, @, #, $, etc.)
* Guarantees at least one character from every selected category
* Secure random generation using the `secrets` module
* Input validation for password length
* Handles invalid user input gracefully
* Prevents impossible password requirements

---

## Libraries Used

### 1. secrets

Used for cryptographically secure random selection of characters.

Functions used:

```python
secrets.choice()
```

### 2. string

Provides predefined character sets.

Attributes used:

```python
string.ascii_uppercase
string.ascii_lowercase
string.digits
string.punctuation
```

### 3. random

Used to shuffle the final password so that mandatory characters appear in random positions.

Function used:

```python
random.shuffle()
```

---

## Algorithm

### Step 1: Select Character Categories

The user chooses whether to include:

* Uppercase letters
* Lowercase letters
* Digits
* Symbols

### Step 2: Guarantee Required Characters

For every selected category, one random character is added to the password.

Example:

```text
Uppercase → M
Lowercase → a
Digit → 7
Symbol → @
```

### Step 3: Build Character Pool

All selected character categories are combined into a single pool.

Example:

```text
ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
0123456789
!@#$%^&*
```

### Step 4: Fill Remaining Length

Additional characters are randomly selected from the combined pool until the desired password length is reached.

### Step 5: Shuffle Password

The generated characters are shuffled to ensure the required characters do not always appear at the beginning.

### Step 6: Display Password

The final password is returned and displayed to the user.

---

## Input Validation

The program validates:

### Invalid Input

Rejects inputs such as:

```text
abc
22.5
hello
```

### Invalid Length

Rejects:

```text
0
-5
```

### No Character Type Selected

Displays an error if no character category is chosen.

### Length Too Small

Example:

```text
Length = 2
Uppercase = Yes
Lowercase = Yes
Digit = Yes
```

The minimum required length is 3, so the program displays an error message.

---

## Sample Execution

```text
Enter length of password : 12

Include uppercase ? (yes/no) : yes
Include lowercase ? (yes/no) : yes
Include digits ? (yes/no) : yes
Include symbols ? (yes/no) : yes

Your password is :
Q@9bL7!mA2#x
```

---

## Time Complexity

Let n be the password length.

### Password Generation

```text
O(n)
```

### Shuffle Operation

```text
O(n)
```

### Overall Complexity

```text
O(n)
```

### Space Complexity

```text
O(n)
```

---

## Learning Outcomes

This project demonstrates:

* Python functions
* Exception handling
* Loops and conditional statements
* String manipulation
* List operations
* Cryptographically secure random generation
* Input validation
* Error handling
* Password security concepts

---

## Future Enhancements

* Password strength meter
* Password history storage
* GUI using Tkinter or CustomTkinter
* Copy password to clipboard
* Export password to a file
* Generate multiple passwords simultaneously
* Custom character exclusions



