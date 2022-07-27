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

You can also add encoded characters in literal strings using the ```\u``` escape sequence, then a four-character code representing some character in Unicode (UTF-16).

**What is string concatenation?**

Concatenate a literal string and a variable:
```
string firstName = "Bobby";
string message = "Hello" + firstName;
Console.WriteLine(message);
```
Concatenate multiple variables and literal strings:
```
string firstName = "Bobby";
string greeting = "Hello";
string message = greeting + " " + firstName + "!";
Console.WriteLine(message);
```
**What is string interpolation?**
An interpolation expression is a variable surrounded by an opening and closing curly brace symbol ```{ }```. The literal string becomes a template when it's prefixed by the ```$``` character.

```string message = $"{greeting} {firstName}!";```

**Put it all together...**
```
string projectName = "ACME";
Console.WriteLine($@"View English output:
        c:\Exercise\{projectName}\data.txt");
string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";
Console.WriteLine($@"{russianMessage}:
       c:\Exercise\{projectName}\ru-RU\data.txt");
```
```
View English output:
		c:\Exercise\ACME\data.txt

Посмотреть русский вывод:
		c:\Exercise\ACME\ru-RU\data.txt
```
### Perform basic operations on numbers in C#
To add two numbers together, we'll use the addition operator, which is the plus symbol ```+```
- You should probably avoid performing both a calculation and concatenation in a single line of code.
- When it can, the C# compiler will implicitly convert an int into a string if it's obvious that the developer is trying to concatenate the string representation of a number for presentation purposes.
- Use parentheses to define an order of operations to explicitly tell the compiler that we want to perform certain operations before other operations.

```+``` is the addition operator

```-``` is the subtraction operator

```*``` is the multiplication operator

```/``` is the division operator

Three uses, or overloads: for the parenthesis operator: method invocation, order of operations and casting.

The remainder operator ```%``` tells you the remainder of int division.

While there's no exponent operator in C#, you can use the ```System.Math.Pow()``` method, which is available from the .NET Class Library.

**Increment and decrement**

The ```+=``` operator adds and assigns the value on the right of the operator to the value on the left of the operator. So, lines two and three in the following code snippet are the same:
```
int value = 0;
value = value + 5;
value += 5;
```
The ```++``` operator increments the value of the variable by 1. So, lines two and three in the following code snippet are the same:
```
int value = 0;
value = value + 1;
value++;
```
These same techniques can be used for subtraction, multiplication and more. 

If you use the operator before the value as in ```++value```, then the increment will happen before the value is retrieved. Likewise, ```value++``` will increment the value after the value has been retrieved.

**Put it all togther...**
```
int fahrenheit = 94;
// To convert temperatures in degrees Fahrenheit to Celsius, first subtract 32, then multiply by five ninths (5 / 9).
decimal decimalQuotient = 5/9.0m;
Console.WriteLine($"The temperature is {(fahrenheit - 32) * decimalQuotient} Celsius.");
```
```
The temperature is 34.444444444444444444444444447 Celsius.
```

### Call methods from the .NET Class Library using C# 
To call methods of a class in the .NET Class Library, you use the format ```ClassName.MethodName()```, where the ```.``` symbol is the member access operator to access a method defined on the class, and the ```()``` symbols are the method invocation operators.

When calling a stateless method, you don't need to create a new instance of its class first.

When calling a stateful method, you need to create an instance of the class, and access the method on the object.

Use the ```new``` operator to create a new instance of a class.

An instance of a class is called an object.

```
Random dice = new Random();
int roll = dice.Next(1, 7);
Console.WriteLine(roll);
```
**Overloaded methods**
Many methods in the .NET Class Library have overloaded method signatures.
An overloaded method is defined with multiple method signatures. Overloaded methods provide different ways to call the method or provide different types of data.
```
Random dice = new Random();
int roll1 = dice.Next();
int roll2 = dice.Next(101);
int roll3 = dice.Next(50, 101);

Console.WriteLine($"First roll: {roll1}");
Console.WriteLine($"Second roll: {roll2}");
Console.WriteLine($"Third roll: {roll3}");
```
- The first version of the ```Next()``` method doesn't set an upper and lower boundary, so the method will return values ranging from ```0``` to ```2,147,483,647```, which is the maximum value an int can store.

- The second version of the ```Next()``` method specifies the maximum value as an upper boundary, so in this case, we can expect a random value between ```0``` and ```100```.

- The third version of the ```Next()``` method specifies both the minimum and maximum values, so in this case, we can expect a random value between ```50``` and ```100```.

**Put it all together...**
```
int firstValue = 500;
int secondValue = 600;
int largerValue = System.Math.Max(firstValue, secondValue);

Console.WriteLine(largerValue);
```
### Add decision logic to your code using `if`, `else`, and `else if` statements in C#

Use an ```if``` statement to branch your code logic. The if decision statement will execute code in its code block if its Boolean expression equates to true. Otherwise, the runtime will skip over the code block and continue to the next line of code after the code block.

A Boolean expression is any expression that returns a Boolean value (```true``` or ```false```).
Boolean operators will compare the two values on its left and right for equality, comparison, and more.

Other simple Boolean expressions can be created by using operators to compare two values. Operators include:

- ```==```, the "equals" operator, to test for equality.
- ```>```, the "greater than" operator, to test that the value on the left is greater than the value on the right.
- ```<```, the "less than" operator, to test that the value on the left is less than the value on the right.
- ```>=```, the "greater than or equal to" operator.
- ```<=```, the "less than or equal to" operator.
and so on

A code block is defined by curly braces ```{ }```. It collects lines of code that should be treated as a single unit.

The logical AND operator ```&&``` aggregates two expressions so that both subexpressions must be true in order for the entire expression to be true.

The logical OR operator ```||``` aggregates two expressions so that if either subexpression is true, the entire expression is true.

**Use the `else` and `else if` statements**
The combination of ```if``` and ```else``` statements allows you to test for a condition and perform code when a Boolean expression is true and run different code when the Boolean expression is false.

You can nest ```if``` statements to narrow down a possible condition. However, you should consider using the ```if```, ```else```, and ```else if``` statements instead.

Use else if to create multiple exclusive conditions.
An ```else``` optional, but it must always come last.

**Put it all togehter...**

```
Random random = new Random();
int daysUntilExpiration = random.Next(12);
int discountPercentage = 0;

// Your code goes here
if ((daysUntilExpiration <= 10) && (daysUntilExpiration > 5))
{
    Console.WriteLine("Your subscription will expire soon. Renew now!");
}
else if((daysUntilExpiration <= 5) && (daysUntilExpiration > 1))
{
    Console.WriteLine($@"Your subscription expires in {daysUntilExpiration} days.
    Renew now and save 10%!");
}
else if(daysUntilExpiration == 1)
{
    Console.WriteLine($@"Your subscription expires in {daysUntilExpiration} days.
    Renew now and save 20%!");
}
else if(daysUntilExpiration == 0)
{
    Console.WriteLine($@"Your subscription has expired.
");
}
```

### Store and iterate through sequences of data using Arrays and the foreach statement in C#

**What is an array?**
An array is a sequence of individual data elements accessible through a single variable name. You use a zero-based numeric index to access each element of an array. (Like a list)

**Step 1 - Declare a new array:**

```string[] fraudulentOrdersIDs = new string[3];```

**Step 2 - Assign values to elements on an array:**
```
string[] fraudulentOrderIDs = new string[3];

fraudulentOrderIDs[0] = "A123";
fraudulentOrderIDs[1] = "B456";
fraudulentOrderIDs[2] = "C789";
```

**Step 3 - Attempt to use an index that is out of bounds of the array:**
```
fraudulentOrderIDs[3] = "D000";
```

**Step 4 - Retrieve values of an array:**
```
string[] fraudulentOrderIDs = new string[3];

fraudulentOrderIDs[0] = "A123";
fraudulentOrderIDs[1] = "B456";
fraudulentOrderIDs[2] = "C789";
// fraudulentOrderIDs[3] = "D000";

Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");
```

**Step 5 - Reassign the value of an array:**
```
string[] fraudulentOrderIDs = new string[3];

fraudulentOrderIDs[0] = "A123";
fraudulentOrderIDs[1] = "B456";
fraudulentOrderIDs[2] = "C789";
// fraudulentOrderIDs[3] = "D000";

Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");

fraudulentOrderIDs[0] = "F000";

Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");
```

**Step 6 - Initialize an array**
```
string[] fraudulentOrderIDs = { "A123", "B456", "C789" };

Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");

fraudulentOrderIDs[0] = "F000";

Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");

Console.WriteLine($"There are {fraudulentOrderIDs.Length} fraudulent orders to process.");
```
**Getting the Size of an Array**

The ```Length``` property gives you a programmatic way to determine the number of elements in an array.
```
string[] fraudulentOrderIDs = { "A123", "B456", "C789" };

Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");

fraudulentOrderIDs[0] = "F000";

Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");

Console.WriteLine($"There are {fraudulentOrderIDs.Length} fraudulent orders to process.");
```
**Looping through an array using foreach**

**Step 1 - Create and initialize an array of int**

```int[] inventory = { 200, 450, 700, 175, 250 };```

**Step 2 - Add a foreach statement to iterate through the array**
```
int[] inventory = { 200, 450, 700, 175, 250 };

foreach (int items in inventory)
{

}
```
**Step 3 - Add a variable to sum the value of each element in the array**
```
int sum = 0;
```
```
int[] inventory = { 200, 450, 700, 175, 250 };
int sum = 0;
foreach (int items in inventory)
{
    sum += items;
}
```
**Step 4 - Display the final value of sum**
```
int [] inventory = { 200, 400, 567, 123, 325};
int sum = 0;
foreach (int items in inventory)
{
    sum += items;
}
Console.WriteLine($"We have {sum} items in inventory.");
```
Use the ```++``` increment operator to add 1 to the current value of a variable.

**Put it all together...**
```
string [] fakeOrderIDs = {"B123","C234","A345","C15","B177","G3003","C235","B179"};

foreach (string item in fakeOrderIDs)
{
  if (item.StartsWith("B"))
  {
      Console.WriteLine(item);
  }
}
```
