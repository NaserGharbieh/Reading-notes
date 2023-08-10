# class 3 reading: Primitives vs Objects ,Exceptions and Scanner.
## Difference Between int and Integer in Java

In Java, both "int" and "Integer" are used to represent whole numbers, but they belong to different data types and have distinct characteristics.

### int

- "int" is a primitive data type in Java.
- It represents a 32-bit signed integer value.
- It does not require memory allocation on the heap as it is a primitive type.
- It can hold values from -2^31 to 2^31 - 1 (-2147483648 to 2147483647).
- Operations on "int" are generally faster because they are directly handled by the CPU.

**Example:**
```java
int age = 25;
```

### Integer

- "Integer" is a wrapper class for the primitive type "int".
- It is part of the Java standard library and is used to provide additional functionalities.
- It allows you to treat an "int" as an object and provides methods for various operations.
- It requires memory allocation on the heap, making it slightly less memory-efficient compared to "int".
- It can hold the same range of values as "int".

**Example:**
```java
Integer score = new Integer(100);
```

In summary, the main differences between "int" and "Integer" are that "int" is a primitive data type with lower memory overhead and faster operations, while "Integer" is an object that provides additional features and flexibility, at the cost of slightly higher memory usage. Java's autoboxing and unboxing feature allow automatic conversion between "int" and "Integer" in most cases, making it convenient to switch between the two as needed.


## Default Values for int and Integer in Java

In Java, both "int" and "Integer" have default values assigned to them when they are declared but not explicitly initialized.

**the default value for "int" is 0, and the default value for "Integer" is null.**

### int

- The default value for an "int" primitive data type is **0**.
- If you declare an "int" variable without initializing it, it will automatically have the value of 0.

**Example:**
```java
int number; // Default value is 0
```

## Integer

- The default value for an "Integer" object is **null**.
- Unlike primitive types, objects such as "Integer" have a default value of null, indicating that they have not been assigned a valid value.

**Example:**
```java
Integer value; // Default value is null
```

**It's important to note that using an uninitialized "int" variable will result in a compilation error, whereas an uninitialized "Integer" variable will compile successfully but will have a default value of null until assigned an actual value.**


## Autoboxing and Unboxing in Java

Autoboxing and unboxing are features in Java that facilitate the conversion between primitive data types and their corresponding wrapper classes. These features help simplify code and make it more convenient to work with both primitive types and objects.

### Autoboxing

Autoboxing is the process of automatically converting a primitive data type into its corresponding wrapper class object. In other words, it allows you to use primitive values as if they were objects, and the conversion is handled by the Java compiler.

Autoboxing is primarily used to make code more readable and avoid the need for explicit type conversions.

**Example of Autoboxing:**
```java
int num = 42;
Integer numObject = num; // Autoboxing int to Integer
```

### Unboxing

Unboxing is the reverse process of autoboxing – it involves automatically converting a wrapper class object back to its primitive data type.

Unboxing is used to extract the actual value from a wrapper class object, allowing you to perform operations that require primitive types.

**Example of Unboxing:**
```java
Integer ageObject = 25;
int age = ageObject; // Unboxing Integer to int
```

Both autoboxing and unboxing are useful in scenarios where you need to switch between primitive types and objects seamlessly. However, it's important to note that while these features enhance code readability, they might have a slight impact on performance due to the underlying conversions.

In summary, autoboxing is the automatic conversion of primitive types to their corresponding wrapper classes, and unboxing is the automatic conversion of wrapper class objects back to primitive types.

## Categories of Exceptions in Java

In Java, exceptions are classified into three basic categories:

### 1. Checked Exceptions

Checked exceptions are exceptional conditions that a well-written application should anticipate and recover from. They are subject to the Catch or Specify Requirement. All exceptions are checked exceptions, except for those indicated by `Error`, `RuntimeException`, and their subclasses.

### 2. Errors

Errors are exceptional conditions that are external to the application and that the application usually cannot anticipate or recover from. They are not subject to the Catch or Specify Requirement. Errors are those exceptions indicated by `Error` and its subclasses.

### 3. Runtime Exceptions

Runtime exceptions are exceptional conditions that are internal to the application and that the application usually cannot anticipate or recover from. They usually indicate programming bugs, such as logic errors or improper use of an API. They are not subject to the Catch or Specify Requirement. Runtime exceptions are those indicated by `RuntimeException` and its subclasses. Errors and runtime exceptions are collectively known as unchecked exceptions. 


## Handling Exceptions in Java

In Java, you can use a `try` statement to handle exceptions. The `try` statement is followed by a block of code that might throw exceptions. Within the `try` block, you can place the code that you want to monitor for exceptions. If an exception occurs within the `try` block, the control is transferred to a corresponding `catch` block that handles the exception.

Here's the basic structure of a `try-catch` statement:

```java
try {
    // Code that might throw exceptions
} catch (ExceptionType1 e1) {
    // Code to handle exception of type ExceptionType1
} catch (ExceptionType2 e2) {
    // Code to handle exception of type ExceptionType2
} // ... more catch blocks as needed
```

In this structure:

- The `try` block contains the code that might throw an exception.
- After the `try` block, one or more `catch` blocks can follow. Each `catch` block specifies the type of exception it can handle (e.g., `ExceptionType1`, `ExceptionType2`, etc.), and if an exception of that type is thrown, the corresponding `catch` block is executed.
- You can have multiple `catch` blocks to handle different types of exceptions.
- The `catch` blocks are optional, but if you include them, they allow you to handle exceptions gracefully and provide appropriate error-handling code.

Here's a simple example:

```java
try {
    int result = 10 / 0; // This will throw an ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("An arithmetic error occurred: " + e.getMessage());
}
```

In this example, if an `ArithmeticException` is thrown within the `try` block (due to division by zero), the control will be transferred to the `catch` block, where you can handle the exception by printing an error message.

## Automated Text Scanning for Efficient Data Analysis

In various scenarios, utilizing a text scanning program can greatly enhance data analysis processes, especially when dealing with extensive unstructured text data. Consider a situation where a company receives a high influx of customer feedback emails, reviews, and social media comments daily. Manual analysis of each message is time-consuming and error-prone.

In this context, an automated text scanning program proves invaluable by streamlining the analysis of these textual inputs. The program can quickly process text, identifying keywords, sentiments, patterns, and specific mentions. This extraction of information includes customer sentiments, prevalent issues, and product/service references. The benefits of employing a text scanning program include:

1. **Enhanced Efficiency**: Swift processing saves time and ensures consistent analysis.
2. **Improved Accuracy**: Automation reduces the chances of human errors during data extraction.
3. **Actionable Insights**: Extracted data provides valuable insights into customer preferences, emerging trends, and concerns.
4. **Scalability**: The program efficiently handles and analyzes large datasets without compromising performance.
5. **Real-time Analysis**: Quick analysis enables timely responses to emerging matters, enhancing customer engagement.

In summary, a text scanning program transforms raw unstructured text into actionable insights. This empowers companies to better comprehend customer sentiments, address concerns effectively, and make informed decisions to enhance their offerings. This example underscores how text scanning significantly elevates data analysis, particularly for sizable volumes of textual data.

## Scanner in Java: Breaking Input into Tokens

In Java, the `Scanner` class is used to break down input into tokens. By default, a `Scanner` uses white space (blanks, tabs, and line terminators) to separate tokens. This process involves dividing the input into smaller units, or tokens, which can then be processed individually based on their data type.

Tokens are the individual components that constitute the input data. For instance, if we have the input sentence "Hello world! How are you?", a `Scanner` would break it down into the following tokens:

- "Hello"
- "world!"
- "How"
- "are"
- "you?"

Each token can be processed or translated based on its intended data type. For example, numeric tokens can be converted to integers or doubles.

You can also customize how input is divided into tokens using the `useDelimiter()` method of the `Scanner` class. This allows you to specify a regular expression pattern that defines the token separator, providing more control over how input is parsed and processed.

Tokens play a crucial role in efficiently handling and interpreting structured input data in Java programs.




