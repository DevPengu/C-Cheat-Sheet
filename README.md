# C# Basics Cheatsheet

This is a simple cheatsheet for C#

## Table Of Content

- [Variables](#1-variables)
- [Change Variables](#15-changing-variable-types)
- [Operations](#2-operations)
- [For loop](#3-for-loop)
- [While loop](#4-while-loop)
- [If statement](#5-if-statement)
- [Switch Case](#8-switch-case)
- [Array](#9-arrays)
---

## 1. Variables

**Definition:** A variable stores data values of different types.
**Definition:** A variable stores data values of different types.

```csharp
// Syntax: Type variableName = value;
int age = 22;          // integer
double pi = 3.14;      // floating-point number
string name = "Bob";   // text
bool isTrue = true;    // boolean (true/false)
```
**Explanation:** In C#, variables have specific types that determine what kind of data they can hold:

* **int** for whole numbers (e.g., 22, -5).
* **double** for decimal numbers (e.g., 3.14, 2.5).
* **string** for text (e.g., "Bob", "Hello").
* **bool** for true/false values (e.g., true, false).

**Important:** A variable declared as one type can only hold that type. For example, an int variable can never hold text or a boolean value.

Here's how the examples can look when formatted in your existing structure:

---

## 1.5 Changing Variable Types

**Definition:** Variables in C# are strongly typed, meaning each variable has a fixed type. However, sometimes you may need to convert one type to another, such as converting a `string` to an `int` when reading numeric user input from `Console.ReadLine()`.

```csharp
string input = Console.ReadLine(); // User inputs: 55
// `input` is now "55" (a string), so it can't be used directly as an integer
int value = Convert.ToInt32(input); // Converts the input string to an integer
```

### Other Type Conversion Examples

**Numeric Conversions:** Converting between numeric types (e.g., from `double` to `int`) may lead to data loss if moving to a less precise type.

```csharp
double pi = 3.14159;
int truncatedPi = (int)pi; // Converts `double` to `int`, resulting in 3 (decimal part is lost)

int num = 42;
float numFloat = (float)num; // Converts `int` to `float`
```

```csharp
string numberString = "100";
int number = Convert.ToInt32(numberString); // Parses "100" to an integer

string decimalString = "2.718";
double eulerNumber = Convert.ToDouble(decimalString); // Parses "2.718" to a double
```
**Date and Time Conversion:** `DateTime.Parse` or `DateTime.TryParse` are useful for handling date inputs.

```csharp
string dateString = "2024-10-27";
DateTime date = DateTime.Parse(dateString); // Converts the string to a DateTime object
```

**Note:** Most data types don’t need to be explicitly converted to `string` when used with `Console.Write` or `Console.WriteLine` because C# automatically converts them to a string for display.

Here's how the examples can look when formatted in your existing structure:

---

## 1.5 Changing Variable Types

**Definition:** Variables in C# are strongly typed, meaning each variable has a fixed type. However, sometimes you may need to convert one type to another, such as converting a `string` to an `int` when reading numeric user input from `Console.ReadLine()`.

```csharp
string input = Console.ReadLine(); // User inputs: 55
// `input` is now "55" (a string), so it can't be used directly as an integer
int value = Convert.ToInt32(input); // Converts the input string to an integer
```

### Other Type Conversion Examples

**Numeric Conversions:** Converting between numeric types (e.g., from `double` to `int`) may lead to data loss if moving to a less precise type.

```csharp
double pi = 3.14159;
int truncatedPi = (int)pi; // Converts `double` to `int`, resulting in 3 (decimal part is lost)

int num = 42;
float numFloat = (float)num; // Converts `int` to `float`
```

```csharp
string numberString = "100";
int number = Convert.ToInt32(numberString); // Parses "100" to an integer

string decimalString = "2.718";
double eulerNumber = Convert.ToDouble(decimalString); // Parses "2.718" to a double
```
**Date and Time Conversion:** `DateTime.Parse` or `DateTime.TryParse` are useful for handling date inputs.

```csharp
string dateString = "2024-10-27";
DateTime date = DateTime.Parse(dateString); // Converts the string to a DateTime object
```

**Note:** Most data types don’t need to be explicitly converted to `string` when used with `Console.Write` or `Console.WriteLine` because C# automatically converts them to a string for display.

## 2. Operations
```csharp
int value = 5;       // Start with 5
value = value + 5;   // Add 5, now value is 10
value = value - 5;   // Subtract 5, now value is 5 again
value = value * 10;  // Multiply by 10, now value is 50
value = value / 2;   // Divide by 2, now value is 25
value = value % 5;   // Modulus (remainder) by 5, now value is 0
value = 28 % 5;      // Modulus 28 by 5, remainder is 3, so value = 3
```
**Explanation:**

* Addition (+), subtraction (-), multiplication (*), and division (/) work as you'd expect with numbers.
* Modulus (%) gives the remainder when dividing two numbers. For example, 28 % 5 gives 3 because 28 divided by 5 leaves a remainder of 3.

### Shorter Version of Operations
You can shorten operations by using special shorthand operators. This updates the variable with the result:

Here we use the values declared from 1. Variables
```csharp
name += " & Bo";    // Adds to the string, making name now "Bob & Bo"
pi *= 2;            // Multiplies pi by 2, now pi is 6.28
age /= 2;           // Divides age by 2, now age is 11
isTrue = false;     // Changes isTrue to false
isTrue = !isTrue;   // Flips isTrue to the opposite, since !true is false, and !false is true
```
**Explanation:** 
Explanation:

* += adds to the existing value and updates the variable.
* *= multiplies and updates the variable.
* /= divides and updates the variable.
* ! flips a boolean value (true becomes false, false becomes true).
* = is used to assign a new value to a variable.

### Operations for check
```csharp
==   // Equal to
>    // Greater than
<    // Less than
>=   // Greater than or equal to
<=   // Less than or equal to
!=   // Not equal to
```

**Examples:**
```csharp
int x = 10;
int y = 5;

// Checking if x and y are equal
bool result = (x == y); // result is false because 10 is not equal to 5

// Checking if x is greater than y
result = (x > y); // result is true because 10 is greater than 5

// Checking if x is less than y
result = (x < y); // result is false because 10 is not less than 5

// Checking if x is greater than or equal to y
result = (x >= y); // result is true because 10 is greater than 5

// Checking if x is less than or equal to y
result = (x <= y); // result is false because 10 is not less than or equal to 5

// Checking if x and y are not equal
result = (x != y); // result is true because 10 is not equal to 5
```
**Explanation:**
* == (Equal to): This checks if two values are exactly the same. It returns true if they are equal, and false if they are not.

Example: x == y checks if x and y have the same value.
* \> (Greater than): This checks if the value on the left is greater than the value on the right.

Example: x > y returns true if x is greater than y.
* < (Less than): This checks if the value on the left is less than the value on the right.

Example: x < y returns true if x is less than y.
* \>= (Greater than or equal to): This checks if the value on the left is greater than or equal to the value on the right.

Example: x >= y returns true if x is greater than or exactly equal to y.
* <= (Less than or equal to): This checks if the value on the left is less than or equal to the value on the right.

Example: x <= y returns true if x is less than or exactly equal to y.
* != (Not equal to): This checks if two values are not equal. It returns true if they are different, and false if they are the same.

Example: x != y returns true if x and y are not the same.

## 3. For Loop
**Definition:** A for loop repeats a block of code a specific number of times. It’s useful when you know exactly how many times you want to loop.
```csharp
// Syntax: for (initialization; condition; increment)
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```
**Explanation:**
* int i = 0: This initializes a counter variable i starting at 0. You can choose any starting value.
* i < 5: The loop will keep running as long as this condition is true. In this case, it runs while i is less than 5.
* i++: After each loop (or "iteration"), i increases by 1. This means the loop runs with i = 0, i = 1, i = 2, and so on until i reaches 5.

**Use case:** For loops are great when you know the exact number of times you need to run a block of code, like printing numbers 0 to 4 as shown above.

## 4. While Loop
**Definition:** A while loop repeats a block of code as long as the condition is true. It’s useful when you don’t know exactly how many times to loop.

```csharp
// Syntax: while (condition)
int x = 0;
while (x < 3)
{
    Console.WriteLine(x);
    x++; // increment the variable to avoid infinite loop
}
```

**Explanation:**
* The loop starts by checking the condition x < 3.
* If x < 3 is true, the code inside the loop runs. In this case, it prints the value of x and then increases x by 1 using x++.
* The loop keeps repeating until x is no longer less than 3, meaning the condition is false.

**Important:** Make sure the variable (like x) changes in the loop, so the condition eventually becomes false. Otherwise, the loop will run forever (infinite loop).

**Use case:** Use a while loop when you don’t know exactly how many times the loop will run but need it to continue until a certain condition is met.


## 5. If Statement
**Definition:** An if statement checks a condition. If the condition is true, it runs the code inside the block.
```csharp
// Syntax: if (condition)
int number = 5;
if (number > 3)
{
    Console.WriteLine("Number is greater than 3");
}
```
**Explanation:**
* if (number > 3) checks if the value of number is greater than 3.
* If this condition is true (in this case, 5 > 3), the code inside the curly braces {} will run.
* It will print "Number is greater than 3" because 5 is indeed greater than 3.

## 6. Else If Statement
**Definition:** An else if statement checks another condition if the first if condition was false.

```csharp
int number = 5;
if (number > 7)
{
    Console.WriteLine("Number is greater than 7");
}
else if (number == 5)
{
    Console.WriteLine("Number is exactly 5");
}
```
**Explanation:**
* The first if checks number > 7. In this case, the condition is false because 5 is not greater than 7.
* Since the first condition is false, the else if checks if number == 5. This condition is true, so it prints "Number is exactly 5".
* If the first condition is false, but the else if condition is true, the code inside the else if block will run.

## 7. Else Statement
**Definition:** An else statement runs if all previous if and else if conditions are false.

```csharp
int number = 2;
if (number > 5)
{
    Console.WriteLine("Number is greater than 5");
}
else
{
    Console.WriteLine("Number is less than or equal to 5");
}
```
**Explanation:**
* The if checks if number > 5, which is false because 2 is not greater than 5.
* Since the if condition is false, the code inside the else block runs, printing "Number is less than or equal to 5".
* else will always run if none of the earlier conditions were true.

## 8. Switch Case
**Definition:** A switch statement checks a variable's value and runs different code depending on the result. It's useful when you have multiple possible values for a variable.
```csharp
// Syntax: switch (variable)
int day = 2;
switch (day)
{
    case 1:
        Console.WriteLine("Monday");
        break;
    case 2:
        Console.WriteLine("Tuesday");
        break;
    case 3:
        Console.WriteLine("Wednesday");
        break;
    default:
        Console.WriteLine("Other day");
        break;
}
```
**Explanation:**
* The switch checks the value of the day variable.
* case 1: runs if day is 1 (which it’s not in this case).
* case 2: runs because day is 2, so it prints "Tuesday".
* The break; statement is important because it tells the program to stop checking further cases after finding a match. If break; wasn't there, the program would continue to the next case, which is usually not what you want.
* The default block runs if none of the cases match. It’s like an else for the switch statement. If day had been a value other than 1, 2, or 3, "Other day" would have been printed.

## 9. Arrays

**Definition:** An array is a collection of variables of the same type, stored together and accessible by index (The position of the value in the array 0 first index and for a size 5 array 4 is last index). Arrays allow you to store multiple values in a single variable, making it easier to manage related data.

```csharp
// Syntax: Type[] arrayName = new Type[size];
int[] numbers = new int[5]; // Initializes an int array of size 5 with values { 0, 0, 0, 0, 0 }
string[] names = new string[] { "Alice", "Bob", "Charlie" }; // An array with initial values of size 3 with values { "Alice", "Bob", "Charlie" }
```
**Important:** When you create an array without specifying values, C# initializes it with default values for that data type (e.g., `0` for `int`, `null` for `string`).

**Explanation:** Arrays are fixed in size, meaning you define their length at the time of creation and it cannot be changed. Each element in the array is accessible by its index, with the first element at index 0.

* **Type[]** defines the array’s data type (e.g., `int[]`, `string[]`).
* **Indexing** starts at 0, so the first element is at `arrayName[0]`.
* **Fixed Size** means once an array is created with a specific length, that length cannot be modified.

### Accessing and Modifying Array Elements

```csharp
int[] numbers = { 10, 20, 30, 40, 50 };
Console.WriteLine(numbers[2]); // Accesses the third element, output: 30

numbers[2] = 35;               // Modifies the third element to 35
Console.WriteLine(numbers[2]); // Outputs: 35
```

### Common Array Operations

1. **Looping through Arrays:** Use loops like `for` or `foreach` to process array elements.

    ```csharp
    int[] numbers = { 1, 2, 3, 4, 5 };

    // Using a for loop
    for (int i = 0; i < numbers.Length; i++)
    {
        Console.WriteLine(numbers[i]);
    }

    // Using a foreach loop
    foreach (int number in numbers)
    {
        Console.WriteLine(number);
    }
    ```

2. **Finding the Length of an Array:** Use `.Length` to get the number of elements.

    ```csharp
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers.Length); // Outputs: 3
    ```
**Important:** Since arrays are fixed in size, you can’t add or remove elements once created. You can only change their value.