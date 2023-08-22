## Lambda Expressions

**Lambda expressions** are a powerful feature in C# that allow you to create **inline, anonymous methods**. They are commonly used in **LINQ queries, event handlers**, and other scenarios where you need to pass a delegate or function as an argument. Let's dive into the in-depth documentation on **lambda expressions in C#**.

**Table of Contents**
Introduction
What are Lambda Expressions?
Advantages of Lambda Expressions
Syntax
Basic Lambda Expression
Lambda Parameters
Lambda Body
Usage
LINQ Queries
Delegate Types
Event Handlers
Capture Variables
Capturing Outer Variables
Closures
Method Group Conversions
Common Use Cases
Sorting Lists
Filtering Lists
Transforming Lists
Best Practices
Keep it Simple
Be Mindful of Captured Variables
Summary

**1. Introduction**
What are Lambda Expressions?
A lambda expression is an **anonymous function in C#** that can be used to **create delegates or expression tree types**. It provides a concise way to represent a method without defining a separate named method.

**Advantages of Lambda Expressions**
Conciseness: Lambda expressions allow you to define short, focused functions without the need to declare a named method.
Readability: They make the code more readable when used in scenarios like LINQ queries.
Inline Usage: You can use lambda expressions directly where a delegate or an expression tree is expected.

**2. Syntax**
Basic Lambda Expression
The basic syntax of a lambda expression is as follows:

```csharp
(parameters) => expression
```
**Lambda Parameters**
Lambda expressions can have zero or more parameters. If there are multiple parameters, they should be enclosed in parentheses and separated by commas.

**Example with parameters:**

```csharp
(x, y) => x + y
```
**Lambda Body**
The body of a lambda expression represents the operation to be performed. It can be a single expression or a block of statements enclosed in curly braces.

**Example with a single expression:**

```csharp
x => x * x
```
**Example with a block of statements:**

```csharp
(x, y) => {
    int sum = x + y;
    return sum * sum;
}
```
**3. Usage**

**LINQ Queries**
Lambda expressions are frequently used in **LINQ (Language Integrated Query) to perform queries on collections**.

**Example using a lambda expression in a LINQ query to filter a list:**

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
var evenNumbers = numbers.Where(x => x % 2 == 0);
```
**Delegate Types**
Lambda expressions can be used to **create instances of delegate types**, which can then be used to invoke methods.

**Example creating a delegate using a lambda expression:**

```csharp
Func<int, int, int> add = (x, y) => x + y;
int result = add(3, 5); // result = 8
```
Event Handlers
Lambda expressions can simplify the creation of event handlers.

Example creating an event handler using a lambda expression:

```csharp
button.Click += (sender, e) => {
    // Handle button click
};
```
4. Capture Variables
Capturing Outer Variables
Lambda expressions can capture variables from the outer scope in which they are defined. This allows you to use variables from the surrounding context within the lambda body.

Example capturing an outer variable:

```csharp
int factor = 5;
Func<int, int> multiply = x => x * factor;
int result = multiply(10); // result = 50
```
Closures
When a lambda expression captures variables from the outer scope, it creates a closure, which "closes over" the captured variables. This means the lambda expression can still access and modify those variables, even if they go out of scope.

5. Method Group Conversions
You can use lambda expressions to perform method group conversions. This is especially useful when working with delegates.

Example converting a method group to a delegate:

```csharp
Func<int, int, int> add = (x, y) => AddNumbers(x, y);
```
6. Common Use Cases
Sorting Lists
Lambda expressions are commonly used to define custom sorting criteria for lists.

Example sorting a list of strings alphabetically:

```csharp
var names = new List<string> { "Alice", "Bob", "Charlie", "David" };
var sortedNames = names.OrderBy(name => name);
```
Filtering Lists
You can use lambda expressions to filter elements from a list based on a certain condition.

Example filtering a list of numbers to get even numbers:

````csharp
var numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
var evenNumbers = numbers.Where(num => num % 2 == 0);
```
Transforming Lists
Lambda expressions can be used to transform the elements of a list.

Example transforming a list of integers to their squares:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };
var squares = numbers.Select(num => num * num);
```
8. Summary
Lambda expressions in C# provide a concise and powerful way to create inline, anonymous methods. They are commonly used in LINQ queries, delegate creations, and event handlers. Understanding the syntax, capturing variables, and common use cases will help you leverage the full potential of lambda expressions in your C# code.
