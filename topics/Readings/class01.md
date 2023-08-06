# Class 01 -Java introduction
# Strong Typing in Java
In Java, **strongly typed** refers to a fundamental characteristic of the programming language, where each variable and expression is associated with a specific data type that is enforced at compile-time. This ensures that the type of data a variable can hold is explicitly defined and validated by the compiler before the code is executed.

## Key Aspects of Strong Typing:

1. **Type Safety:** Java requires variables to be declared with explicit data types. Once a variable is assigned a certain data type, it is expected to hold only that type of data within its scope. This promotes early detection of type-related errors and prevents unintended type conversions.

2. **Compile-Time Checks:** The compiler rigorously examines operations on variables to ensure they align with their designated data types. This precludes many errors before the program runs, minimizing the occurrence of runtime errors stemming from type mismatches.

3. **Explicit Conversions:** Performing operations involving different data types often necessitates explicit type conversion. This compels developers to consciously manage type conversions and helps maintain control over the code's behavior.

## Example of Strong Typing in Action:

Consider the following Java code snippet:

```java
public class StrongTypingExample {
    public static void main(String[] args) {
        int num = 10;           // num is an integer
        String text = "Hello";  // text is a String
        
        int result = num * 5;   // Valid: Arithmetic operation on an integer
        System.out.println("Result: " + result);
        
        // The next line would trigger a compilation error
        // int concatResult = num + text; 
        // You cannot concatenate an int and a String without explicit type conversion
        
        String concatText = num + text; // Valid: Integer num is explicitly converted to String for concatenation
        System.out.println("Concatenated Text: " + concatText);
    }
}
```

In this example, num is an integer (int), while text is a String. Arithmetic operations like multiplication can be directly performed on the integer variable (num * 5). However, attempting to concatenate the integer num with the String text using the + operator without explicit type conversion would result in a compilation error.

The concept of strong typing enhances code reliability by identifying errors early in development, thereby contributing to a more maintainable and robust codebase.

By enforcing strict data typing and catching type-related issues before runtime, Java's strong typing system plays a crucial role in the software development process, ultimately leading to higher quality and more dependable applications. 

# Primitive Data Types in Java

In Java, primitive data types are the most basic data types that represent simple values. They are used to define variables that store fundamental types of data. Java has eight primitive data types:

1. `byte`: Represents an 8-bit signed integer. Range: -128 to 127.
2. `short`: Represents a 16-bit signed integer. Range: -32,768 to 32,767.
3. `int`: Represents a 32-bit signed integer. Range: -2^31 to 2^31 - 1.
4. `long`: Represents a 64-bit signed integer. Range: -2^63 to 2^63 - 1.
5. `float`: Represents a 32-bit floating-point number. Used for decimal numbers with a fractional part.
6. `double`: Represents a 64-bit floating-point number. Used for decimal numbers with a fractional part.
7. `char`: Represents a single 16-bit Unicode character. Range: '\u0000' to '\uffff'.
8. `boolean`: Represents true or false value.

These primitive data types are used to efficiently store and manipulate simple values in Java programs.

## Compilation Differences: Java vs JavaScript

Think of compilation like translating a book from one language to another. Both Java and JavaScript use compilation to ensure that your code can be understood by computers, but they approach it differently.

### Java Compilation: The Strict Editor

In Java, the compilation process is akin to having an uncompromising editor. When you write your "story" (code) in Java, you must adhere to all grammar rules meticulously. This vigilant editor, also known as a compiler, meticulously reviews your story before it's read by anyone else. Its primary role is to ensure that everything is impeccably composed. If even a minor error is detected, the editor intervenes, providing a comprehensive list of necessary fixes. Only when everything is flawless does the editor proceed to transform your story into a complete "book" (compiled code), readable by a specialized machine called the Java Virtual Machine (JVM).

### JavaScript Compilation: The Supportive Friend

Contrastingly, JavaScript compilation is more akin to narrating a story to a helpful friend. As you begin telling your story (writing code) in JavaScript, your attentive friend, reminiscent of a browser or JavaScript engine, listens closely. If a small mistake occurs, your understanding friend comprehends your intended meaning and rectifies the error on the spot. This accommodating approach enables you to continue unfolding your story even if minor errors exist. Your friend takes on the responsibility of deciphering how to make the story coherent and functional as you articulate it.

### In Summary:

- Java's compilation resembles the meticulous review of a strict editor, ensuring your story is flawless before reaching readers. It enforces strict adherence to rules and grammar.
- JavaScript's compilation is more like sharing a story with a supportive friend who assists in real-time, enabling progress even in the presence of minor imperfections.

Both approaches have their merits – Java's rigorous compilation catches substantial errors early, promoting robustness, while JavaScript's real-time correction fosters quicker development and adaptability, even in the face of minor discrepancies.

# Code Compilation vs. Code Working

 code compilation doesn't necessarily mean that the code works correctly. Compilation is the process of translating human-readable source code into machine-readable binary code or bytecode. It checks for syntax and type-related errors in the code, ensuring that it follows the rules of the programming language.

However, compilation primarily focuses on the structure and correctness of the code according to the language's rules. It doesn't guarantee that the code will produce the desired output or behavior when executed. Logical errors or issues in the algorithmic design of the code may not be caught during compilation but might lead to incorrect results when the code is executed.

In essence, while successful compilation is an important step towards getting your code to work, it's just one part of the overall process. Thorough testing and debugging are necessary to ensure that the code functions correctly in different scenarios and produces the expected outcomes.



# Keywords in Java

Keywords, also known as Reserved words, are essential components of a programming language. These words hold predefined meanings and are reserved for specific internal operations and predefined actions within the language.

Programmers are restricted from using these keywords as identifiers, variable names, or any other user-defined purpose. Attempting to use these keywords for other purposes will result in a compilation error.

Java, being a robust programming language, consists of a total of 51 keywords, each carrying a predefined significance and role within the language. Among these 51 keywords, 49 keywords are actively used in Java, while the remaining 2 are no longer in use.

I found a list of Java keywords  as follows:

```plaintext
abstract   continue   for          new         switch
assert     default    goto*        package     synchronized
boolean    do         if           private     this
break      double     implements   protected   throw
byte       else       import      public      throws
case       enum       instanceof   return      transient
catch      extends    int          short       try
char       final      interface    static      void
class      finally    long         strictfp    volatile
const*     float      native       super       while
```

It's important to keep in mind that the usage of these keywords is reserved for specific programming constructs and actions dictated by the Java language specifications. Any attempt to repurpose these keywords will lead to errors during the compilation process. 
Printing Words to the Console in Java

# printing in Java 

In Java, you can display words and text on the console using the `System.out.println()` method. This method is part of the `System` class and is commonly used to show output in the standard console or terminal where your Java program is executed. Here's an example:

```java
public class PrintExample {
    public static void main(String[] args) {
        System.out.println("Hello, Java! My name is Naser Gharbieh");

    }
    }
```

When you run this Java program, it will produce the following output in the console:

```
Hello, Java! My name is Naser Gharbieh
```

The `System.out.println()` method prints the provided text and automatically appends a newline character (`\n`) at the end. This newline character moves the cursor to the next line, so each `println` statement begins on a new line in the console.

If you prefer to print without adding a newline character, you can use the `System.out.print()` method:

```java
System.out.print("Hello, ");
System.out.print("Java!");
```

This would result in the output:

```
Hello, Java!
```




