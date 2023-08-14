# class 04 reading: Object Oriented Programming.
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
## Binary, Decimal and Hexadecimal Numbers

- the binary number 1101 is equivalent to the decimal number 13.
- With these steps: 
```
(1 * 2^3) + (1 * 2^2) + (0 * 2^1) + (1 * 2^0)
```
```
= (8) +  (4) + (0) + (1) = 13 
```

### converting the decimal number 52 to binary and hexadecimal:

#### Decimal to Binary Conversion (52 to Binary):

Step 1: Divide the decimal number (52) by 2.
```
52 ÷ 2 = 26, Remainder = 0
```

Step 2: Divide the quotient (26) by 2.
```
26 ÷ 2 = 13, Remainder = 0
```

Step 3: Divide the quotient (13) by 2.
```
13 ÷ 2 = 6, Remainder = 1
```

Step 4: Divide the quotient (6) by 2.
```
6 ÷ 2 = 3, Remainder = 0
```

Step 5: Divide the quotient (3) by 2.
```
3 ÷ 2 = 1, Remainder = 1
```

Step 6: Divide the quotient (1) by 2.
```
1 ÷ 2 = 0, Remainder = 1
```

Reading the remainders from bottom to top gives the binary representation:
```
52 (Decimal) = 110100 (Binary)
```

#### Decimal to Hexadecimal Conversion (52 to Hexadecimal):

Step 1: Divide the decimal number (52) by 16.
```
52 ÷ 16 = 3, Remainder = 4 (Equivalent Hex: 4)
```

Step 2: Divide the quotient (3) by 16.
```
3 ÷ 16 = 0, Remainder = 3 (Equivalent Hex: 3)
```

Reading the remainders from top to bottom gives the hexadecimal representation:
```
52 (Decimal) = 34 (Hexadecimal)
```

So, the decimal number 52 is equivalent to 110100 in binary and 34 in hexadecimal.

