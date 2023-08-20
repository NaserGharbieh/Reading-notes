# class 06 reading: 
## Object Oriented Programming ,Inheritance , Static Keyword and Design Patterns.
## Object vs Class ?
An object is a software consist of related state (fields,variables) and behavior (methods,functions).
A class is a blueprint or prototype from which objects are created even a simple class can cleanly model state and behavior. 
* for examlple a student object van have these : * 
- State : studentName , studentId , studentCourses, studentGrades,.
- Behavior :EnrollInCourse ,withdrawFromCourse, checkIfPassed , 
## Classes In Java 
## A Class  constructors that are invoked to create objects from the class blueprint.
## Constructor declarations look like method declarations <span style="color: red;">except that </span>  <span style="color:green ;">they use the name of the class and have no return type. </span>


-A declaration statement for a class named “Student":
```java
class Student {
    // fields  , 
    // constructor, 
    // method declarations
}


```
# Understanding Inheritance in Java 

## Analogy: Different Types of Paintings

Imagine you're a painter with various styles of artwork: landscapes, portraits, and abstract art. Each style requires some common tools like canvas, brushes, and colors. In the world of Java programming, we have a similar concept called "inheritance" that simplifies how we create classes.

## What is Inheritance?

In Java, inheritance is like having a base class that holds common features shared by different classes. This base class represents a general idea or blueprint. Just as all your paintings share basic tools, different classes can share properties and methods through inheritance.

## How Does Inheritance Work?

Think of creating a base "Painting" class with general properties. Then, you can create more specific classes like "LandscapePainting," "PortraitPainting," and "AbstractArtPainting." These specific classes inherit the common features from the base class, just like a landscape painting inherits tools from the general painting concept.

Instead of starting from scratch for each type of painting, you build upon the shared base class. You can add unique details to each specific class while reusing the common features. This way, inheritance allows programmers to efficiently reuse code and enhance it by adding specific functionalities.

## Static Methods in Java

Static methods in Java are commonly referred to as "class methods." This naming convention arises from the fact that these methods belong to the class itself rather than any specific instance or object of the class. Unlike instance methods that operate on object-specific data, static methods are associated with the class blueprint and can be invoked using the class name.

### Why "Class Methods"?

Static methods are termed "class methods" to emphasize their distinction from instance methods. The term highlights that these methods operate at the class level, independent of any specific object instance. They can be directly called on the class without requiring the creation of an object. This characteristic makes them suitable for utility functions, common operations, and situations where specific object data is not needed.

On the other hand, instance methods require the instantiation of an object from the class and can access instance-specific variables and methods. The differentiation between static methods (class methods) and instance methods is crucial in object-oriented programming as it guides the design and organization of classes in Java.

In summary, the "class methods" label underscores that static methods pertain to the class itself and can be utilized without object instantiation. This distinction contributes to the clarity and structure of Java programs.
## Accessing Class Variables without Instantiating Objects

In Java, you can access class variables without the need to instantiate an object from that class. This is achieved by using the `static` keyword. When a variable is declared as `static`, it becomes associated with the class itself rather than with instances of the class. This enables you to access the variable directly through the class, even without creating objects.

Consider the following example:

```java
public class MyClass {
    static int myStaticVariable = 10;
    int myInstanceVariable = 20;
}
```

In this example, `myStaticVariable` is a static variable, and `myInstanceVariable` is an instance variable. To access the static variable, you can use the class name:

```java
int value = MyClass.myStaticVariable;
```

However, to access the instance variable, you would need to create an instance of the class:

```java
MyClass obj = new MyClass();
int instanceValue = obj.myInstanceVariable;
```

By using the `static` keyword, you can create variables that are shared among all instances of the class. This is particularly useful for constants, utility methods, and data that should be consistent across different instances. Static variables provide a way to access class-level data without the need for object instantiation.

## Design Patterns: Blueprint for Efficient Solutions

A **design pattern** is a general, reusable solution to a common problem in software design. Similar to a blueprint that architects use to create buildings, design patterns provide developers with proven solutions to recurring software development challenges. These patterns improve code quality, maintainability, and scalability by offering standardized approaches to solving specific problems.

### Analogy 1: Singleton Pattern - Security Guard

Imagine you're in charge of a top-secret research facility where only authorized personnel are allowed. To maintain strict control over access, you ensure that only one security guard is stationed at the main entrance at all times. This single guard acts as a gatekeeper, preventing unauthorized individuals from entering.

In software terms, this situation resembles the **Singleton** design pattern. The security guard represents the single instance of a class, ensuring that only one instance exists throughout the application. Just as the facility relies on one guard to manage access, a Singleton instance manages specific resources or actions in your program. This pattern ensures that there's a global point of access to a single instance, preventing unnecessary object creation and providing centralized control.

### Analogy 2: Observer Pattern - News Subscribers

Picture yourself managing a news agency with a large subscriber base. Rather than manually notifying each subscriber whenever a new story is published, you set up a subscription system. Subscribers opt in to receive updates, and whenever a new story is published, all subscribers are automatically notified.

This scenario aligns with the **Observer** design pattern. In this pattern, your news agency acts as the subject, while the subscribers are observers. Observers watch for changes in the subject's state and get notified when those changes occur. This pattern facilitates efficient communication without direct interaction between publishers and subscribers. Similarly, in software, the Observer pattern helps decouple components, promoting flexibility and minimizing dependencies.

Both analogies highlight the essence of design patterns – providing standardized solutions to common problems. Just as real-world scenarios benefit from established procedures, software development benefits from the structured guidance that design patterns offer.

## Singleton: Ensuring a Unique Instance

A **Singleton** is a design pattern that guarantees a class has only one instance and provides a global point of access to that instance throughout an application's lifecycle. This pattern ensures that a class has a single instance and controls the instantiation process, preventing multiple instances from being created.

### Why Singleton?

The Singleton pattern is used when you want to ensure there's only one instance of a class responsible for a specific task. This can be particularly useful when dealing with shared resources, such as database connections, logging systems, or configuration settings. By limiting the number of instances to just one, you maintain control over these resources and prevent unnecessary overhead.

### What Makes a Singleton?

To implement a Singleton pattern, a class must adhere to the following principles:

1. **Private Constructor:** The Singleton class should have a private constructor, preventing external instantiation. This means other parts of the code can't create new instances of the class.

2. **Private Instance:** The Singleton class should contain a private instance of itself. This instance will be the single instance available for use.

3. **Static Method:** A public static method should be provided to access the instance. This method will ensure that only one instance of the class is created and returned.

### Example: Database Connection Pool

Imagine you're building a web application that interacts with a database. Establishing database connections is resource-intensive, so you want to ensure efficient usage of connections. Using the Singleton pattern, you create a **DatabaseConnectionManager** class.

1. You make the constructor private, so developers can't create instances directly.
2. You provide a private static instance of **DatabaseConnectionManager** to manage the connections.
3. You offer a public static method **getInstance()** that returns the single instance.

```java
public class DatabaseConnectionManager {

    private static DatabaseConnectionManager instance;
    // Private constructor to prevent direct instantiation
    private DatabaseConnectionManager() {
        // Initialize database connections
    }

    // Provide a global point of access to the single instance
    public static DatabaseConnectionManager getInstance() {
        if (instance == null) {
            instance = new DatabaseConnectionManager();
        }
        return instance;
    }

    // Other methods to manage database connections
}
```

In this example, any part of the application can use **DatabaseConnectionManager.getInstance()** to access the single instance. This ensures that all components share the same connection pool, preventing excessive resource usage.

The Singleton pattern simplifies resource management, promotes consistency, and avoids unnecessary object creation. However, it's crucial to use Singletons judiciously and be aware of potential threading issues in multithreaded environments.


