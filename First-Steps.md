# C# First Steps
### Write your first C# code
What is the primary job of the compiler?
- The compiler primarily converts your code into an executable format that the computer can understand.
C# statements must always end in a colon. ;
### Take your first steps with C#
What is a literal value?
- A literal value is a hard-coded value that never changes. Previously, we displayed a literal string to the Output pane. In other words, we literally wanted that string of alphanumeric characters H, e, l, l, o, and so on, displayed in the Output window.

**Write a char literal to the console...**
- ```Console.WriteLine('b');```
**Write a char literal to the console...**
- ```Console.WriteLine('123');```
**Write a char decimal to the cons...**
- ```Console.WriteLine('12.30m');```
  - (Without the literal suffix m, the decimal number in the previous example will be treated as type double by the compiler and the output will be 12.3.)
**Write a bool literal to the console...**
- ```Console.WriteLine(true);```
- ```Console.WriteLine(false);```

**Why emphasize data types?**
- Data types play a central role in C#. In fact, the emphasis on data types is one of the key distinguishing features of C# compared to other languages like **Python** and **JavaScript**. The designers of C# believed they can help developers avoid common software bugs by enforcing data types.

**Presentation versus calculation and evaluation**
- Strings and chars are used for "presentation, not calculation". If you need to perform a mathematical operation on numeric values, you should use an int or decimal. If you have data that is used for presentation or reference purposes only, you should use a string or char data type.
