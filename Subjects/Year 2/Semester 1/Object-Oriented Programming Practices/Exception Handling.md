---
aliases:
  - Exception Handling
tags:
  - Notes
  - Java
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
When a program runs into a runtime error, the program terminates abnormally.
In Java, runtime errors are thrown as *exceptions*

>[!DEFINITION] Exception
>An **object** that represents an error or a condition that prevents execution from proceeding normally.

If the exception is not handled normally, the program will terminate abnormally. 

**Built-in Exceptions**
These exceptions are provided by the Java Standard Library. Checked and unchecked exceptions are included and are part of the Java API

**User-defined exceptions**
It is possible to create custom exceptions in Java by defining a new class that extends either `Exception` for checked exceptions or a subclass of `Exception` - `RuntimeException` for unchecked exceptions.

There are a number of important built-in exceptions in Java:
1. `ArithmeticException`
	- When an illegal arithmetic operation has taken place
		- Division by 0
2. `ArrayIndexOutOfBoundsException`
	- When trying to access a non-existent index in an array
3. `ClassNotFoundException`
	- When a class we're trying to access does not exist
4. `FileNotFoundException`
	- When the file is not accessible or not open
5. `IOException`
	- When an input-output operation has failed or is interrupted
6. `InterruptedException`
	- When a thread is waiting, sleeping, or doing something, and is interrupted
	- [[Thread and Multithreading]]
7. `NoSuchFieldException`
	- When a class does not contain the specified field
8. `NoSuchMethodException`
	- When attempting to access a non-existent method
9. `NullPointerException`
	- When trying to reference a null object
10. `NumberFormatException`
	- When it is not possible to convert a `String` into a numeric format
11. `RuntimeException`
	- Represents any exceptions during runtime
12. `StringIndexOutOfBoundsException`
	- Thrown by `String` class
	- When accessing an character at a negative index or at an index larger than the size of the `String`

>[!definition] Error 
>System errors are thrown by JVM and represents the `Error` class. The `Error` class describes internal system errors. Luckily, such errors rarely occur; however, if one does, there really isn't much you can do beyond notifying the user and trying to terminate the program normally.

>[!DEFINITION] Exception
>Describes errors caused by the program and external circumstances. These errors can be caught and handled by the program.
>>[!DEFINITION] RuntimeException
>>Thrown when there are programming errors, such as bad casting, accessing an out-of-bounds array, and numeric errors.

`RuntimeException` and `Error`, along with their subclasses are known as *unchecked* exceptions, meaning Java does not force you to `catch` these exceptions. Every other exceptions are *checked* exceptions, meaning Java forces you to `catch` these exceptions. 
# Applying Exceptions
*So, how do you do it?*

*Snippet A:Exception Handling*
```java
public static void main(String[] args){
	int numerator = 13;
	int denominator = 0;
	int result;
	result = numerator / denominator; // an error will occur here
}
```
Since, the program above is attempting to divide by 0, `ArithmeticException` will be thrown.

In Java, we can handle exceptions with `try-catch` blocks. In the `try` block, the statements or exceptions that may cause exceptions are placed there, while outputs or expressions in response to the exceptions are placed in the `catch` block. 

>[!FYI] 
>You can have more than one `catch` block; one for each exception.

```java
public static void main(String[] args){
	int numerator = 13;
	int denominator = 0;
	int result;
	try{
		result = numerator / denominator
	}catch(ArithmeticException e){
		System.out.println("You are trying to divide by 0 >: ");
	}
}
```
If the error is simple enough, it can be fixed with `if` statements (*usually preferred.*)

```java
public class Main{
	public static void main(String[] args){
		int numerator = 5;
		int denominator = 0;
		System.out.printf("A: %d%nB: %d%nThe result is %d", numerator, denominator, division(numerator,denominator));
	}
	private int division(int a, int b){
		if (b == 0){
			System.out.println("You are trying to divide by 0 >:");
			return -1;
		}
		return a/b;
	}
}
```

We can also make the whole method *throw* an exception,

```java
public class Main{
	public static void main(String[] args){
		int numerator = 5;
		int denominator = 0;
		try{
			System.out.printf("A: %d%nB: %d%nThe result is %d", numerator, denominator, division(numerator,denominator));
		}
		catch(ArithmeticException e){
			System.out.println(e);
		}
	}
	// Declaring the exception
	private int division(int a, int b) throws ArithmeticException{
		// This returns a new exception object
		if (b == 0)
			// the method throws the exception if the condition is met
			throw new ArithmeticException("You are trying to divide by 0 >:");
		return a/b;
	}
}
```
In the snippet above, when `System.out.println(e)` is called, the `toString()` method is used. The line `throw new ArithmeticException("You are trying to divide by 0 >:")`, creates an exception object with the message *you are tyring to divide by 0 >:*. This message can also be accessed with `e.getMessage()` or `e.printStackTrace()`.

```java
System.out.println(e.getMessage());
e.printStackTrace();
```

>[!WARNING] Declaring exceptions
>Every method must state the type of **checked** exceptions it may throw. This can be done via the `throws` keyword. 

If you believe that a method may throw more than one exception, you can do that by adding a comma after each exception. 

```java
public void myMethod() throws IOException, InputMismatchException{
	callMethod();
	System.out.print("Enter an integer: ");
	int number = input.nextInt();
}
```

This means that you would need 2 `catch` blocks, each for one exception. 

>[!warning] Order of `catch`
>The order of `catch` block is very important. For example, if `InputMismatchException` comes first before `ArithmeticException`, the `catch` block for the former must be defined first. 

Once you get used to using exceptions, you can do this.
```java
boolean valid = false
int number;
while(!valid){
	try{
		number = input.nextInt();
		System.out.println("No Problem ;)");
		valid = true;
	}catch(InputMismatchException e){
		System.out.println("You can only input integers >:");
	}
}
```

There is another important keyword to know: `finally`.<br>This keyword is meant for actions that must be performed regardless of the condition. Any statements inside the `finally` block **will always be** executed. 

```java
boolean valid = false
int number;
while(!valid){
	try{
		number = input.nextInt();
		System.out.println("No Problem ;)");
		valid = true;
	}catch(InputMismatchException e){
		System.out.println("You can only input integers >:");
	}
	finally{
		System.out.println("Spongebob!");
	}
}
```

This line, `System.out.println("Spongebob!");`, will always be executed in each loop.

## Defining custom exceptions
You can define a custom exception via `extend`ing the `Exception` class
```java
public class InvalidRadiusException extends Exception{
	// creates the error mesasge. 
	super("Invalid Radius: " + radius); 

}
```

# When to use it?
The benefit of exception handling is the separation of detection of error and the handling of the error; if you want the exception to be processed by its caller, you should create an exception object and throw it, but if you want to handle the exception in the method where it occurs, there is no need to throw  or use exceptions.

>[!PRACTICE]
>It is best to use `try-catch` blocks only for unexcepted errors; avoid using them on simple errors that can be easily resolved with `if-else` statements.  

# See next
[[File Input and Output]]






























