# C# First Steps
### Write your first C# code
What is the primary job of the compiler?
- The compiler primarily converts your code into an executable format that the computer can understand.
C# statements must always end in a colon. ;
### Store and retrieve data using literal and variable values in C#
What is a literal value?
- A literal value is a hard-coded value that never changes. Previously, we displayed a literal string to the Output pane. In other words, we literally wanted that string of alphanumeric characters H, e, l, l, o, and so on, displayed in the Output window.

**Write a char literal to the console...**
- ```Console.WriteLine('b');```

**Write a char int to the console...**
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
- Strings and chars are used for "presentation, not calculation". 
- If you need to perform a mathematical operation on numeric values, you should use an int or decimal. If you have data that is used for presentation or reference purposes only, you should use a string or char data type.

**What is a variable?**
- A variable is a data item that may change its value during its lifetime. You use variables to temporarily store values that you intend to use later in your code. 
- A variable is a friendly label that we can assign to a computer memory address. When we want to temporarily store a value in that memory address, or whenever we want to retrieve the value that is stored in the memory address, we just use the variable name we created.

**Variable name examples:**
```
char userOption;

int gameScore;

decimal particlesPerMillion;

bool processedCustomer;
```

**Asigning Variables**
```
String firstName;
firstName = "Bobby";
Console.WriteLine(firstName);
```
**Reassigning variables:**
```
string firstName;
firstName = "Bob";
Console.WriteLine(firstName);
firstName = "Charles";
Console.WriteLine(firstName);
firstName = "Jerome";
Console.WriteLine(firstName);
firstName = "Grant";
Console.WriteLine(firstName);
```
Set the value as soon as possible after you declare it. In fact, you can perform both the **declaration** and **setting** the value of the variable in one line of code. This technique is called initializing the variable.

```
string firstName = "Bobby";
Console.WriteLine(firstName);
```
**What are implicitly typed local variables?**
- An implicitly typed local variable is created using the var keyword, which instructs the C# compiler to infer the type. After the type is inferred, it's the same as if the actual data type had been used to declare the variable.
- The var keyword is dependent on the value you use to initialize the variable.

**Putting it alll together:**
```
string firstName = "Bob";
int inboxMessages = 3;
decimal degreesCelcius = 34.4m;
Console.WriteLine($"Hello {firstName}! You have {inboxMessages} messages in your inbox. The temperature is {degreesCelcius} celcius");
```
### Character Escape Sequences and Verbatim Strings
The ```\n``` sequence will add a new line, and a ```\t``` sequence will add a tab. When wanting to add a quotation mark within a literal string, use the ```\"``` escape sequence, with ```\``` being the escape character. If you need to use the backslash for other purposes, like to display a file path use the ```\\``` to display a single backslash.

A verbatim string literal will keep all whitespace and characters without the need to escape the backslash. To create a verbatim string, use the ```@``` directive before the literal string. Two consecutive double-quote characters (```""```) are printed as a single double-quote character (```"```) in the output string.
