# class02 : Packages ,Loops and Arrays
## Packages in Java 
### Analogy for Built-In Java Packages

- Built-in Java packages are analogous to the tools that come with a new car. Just as these tools are provided by the car manufacturer to assist you with common tasks, built-in packages in Java contain pre-made classes and utilities for common programming needs.

- For instance, similar to a car being equipped with an air pump for tires, Java's `java.util` package provides tools for managing dates and lists. Similarly, much like a car's radio system, the `java.io` package offers tools for input and output operations, such as reading and writing files. These built-in packages act as a set of predefined tools that developers can readily use, saving time and effort by providing readily available solutions for everyday programming tasks. 

### Creating a New Package in IntelliJ IDEA

1. **Open IntelliJ IDEA:**
   Launch IntelliJ IDEA on your computer.

2. **Create a New Project or Open an Existing Project:**
   You can either create a new project or open an existing one where you want to create the new package.

3. **Navigate to the Source Folder:**
   In the Project Explorer or Project view on the left side of the screen, locate and right-click on the source folder of your project. The source folder is usually named "src" and contains your Java source code files.

4. **Select "New" and then "Package":**
   Right-click on the source folder, then hover over "New" in the context menu and select "Package."

5. **Enter Package Name:**
   A pop-up dialog will appear. In the "Package name" field, type the name of your new package. Use a dot (.) to separate the levels of the package hierarchy. For example, if you want to create a package named "com.example.myapp," enter "com.example.myapp" in the field.

6. **Click "OK":**
   After entering the package name, click the "OK" button. IntelliJ will create the new package for you in the appropriate directory within the source folder.

7. **Add Classes to the Package:**
   You can now start adding Java classes, interfaces, and other files to your newly created package. Right-click on the package name in the Project view, then select "New" and choose the type of Java class or file you want to create.

8. **Write Code:**
   Open the Java class you've created within the new package and start writing your code.

That's it! You've successfully created a new package in IntelliJ IDEA. You can organize your classes and code files within this package to keep your project structured and maintainable.

Certainly! Here's the provided information formatted in a Markdown (.md) file as requested:

## Loop Types Using a Loop Counter in Java

### Simple For Loop

The simple for loop is a fundamental loop structure in Java that uses a loop counter to control iteration. It consists of an initialization, a condition, and an increment or decrement expression. The loop counter is explicitly defined and serves as a control mechanism for the loop.

**Example of a simple for loop:**

```java
for (int i = 0; i < 5; i++) {
    // Loop body
}
```

## Do-While Loop

The do-while loop is another loop structure in Java that indirectly utilizes a loop counter concept. While it doesn't have an explicit loop counter,<span style="color:green">**it follows a similar idea.executes at least once before checking the loop condition.**</span>  Often, a counter variable is initialized before the loop and incremented within the loop body.

**Example of a do-while loop with a counter-like mechanism:**

```java
int count = 0;
do {
    // Loop body
    count++;
} while (count < 5);
```

Both the simple for loop and the do-while loop provide control over loop iteration using a loop counter or a counter-like mechanism.




## Built-in Methods of `java.util.Arrays` Class

## `binarySearch` Method

The `binarySearch` method searches for a specified value in a sorted array using the binary search algorithm. If the value is found, it returns the index of the value; otherwise, it returns a negative value that represents the insertion point.

### Syntax:

```java
public static int binarySearch(Object[] a, Object key)
```

### Example:

```java
import java.util.Arrays;

public class BinarySearchExample {
    public static void main(String[] args) {
        int[] array = { 2, 5, 8, 12, 16, 23, 38, 56, 72, 91 };
        int key = 16;

        int index = Arrays.binarySearch(array, key);

        if (index >= 0) {
            System.out.println("Element found at index " + index);
        } else {
            System.out.println("Element not found, would be inserted at index " + (-index - 1));
        }
    }
}
```

## `equals` Method

The `equals` method checks if two arrays are equal by comparing their corresponding elements.

### Syntax:

```java
public static boolean equals(type[] a, type[] a2)
```

### Example:

```java
import java.util.Arrays;

public class ArraysEqualsExample {
    public static void main(String[] args) {
        int[] array1 = { 1, 2, 3, 4, 5 };
        int[] array2 = { 1, 2, 3, 4, 5 };

        boolean areEqual = Arrays.equals(array1, array2);

        if (areEqual) {
            System.out.println("Arrays are equal");
        } else {
            System.out.println("Arrays are not equal");
        }
    }
}
```

## `fill` Method

The `fill` method assigns a specified value to all elements of an array.

### Syntax:

```java
public static void fill(type[] a, type value)
```

### Example:

```java
import java.util.Arrays;

public class ArrayFillExample {
    public static void main(String[] args) {
        int[] array = new int[5];

        Arrays.fill(array, 42);

        System.out.println("Filled array: " + Arrays.toString(array));
    }
}
```


- These examples demonstrate the usage of the `binarySearch`, `equals`, and `fill` methods from the `java.util.Arrays` class in Java. 

Certainly! Here's the information formatted in a Markdown (.md) file:


## Determining the Size of an Array in Java

In Java, the size of an array is determined when the array is created, and it remains fixed throughout the lifetime of the array. When you create an array, you specify its size using an integer value, indicating the number of elements the array can hold.

For example, to create an array that can hold 10 integers, you would define it like this:

```java
int[] myArray = new int[10];
```

In this example, `myArray` is an array of integers with a size of 10. It can hold 10 integer values, and once the array is created, you cannot change its size. Attempting to access or modify elements beyond the array's size will result in an `ArrayIndexOutOfBoundsException`.

Remember that arrays in Java are zero-indexed, which means the valid index range for accessing elements is from `0` to `size - 1`. For the above example, valid indices would be `0` to `9`.

If you require a data structure that can dynamically grow or shrink in size, you might consider using `ArrayList` from the `java.util` package. Unlike arrays, `ArrayList` can dynamically adjust its size as elements are added or removed.


