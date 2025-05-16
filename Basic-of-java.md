
# Java Virtual Machine ( JVM )
Java is how to write a program that can run on different platforms. Write Once and Run
Anywhere.

Before Java was born, a program that was written and compiled into a machine code running on
Windows operating systems would not be able to run on Linux operating systems because of a
lot of differences.

![image](https://github.com/user-attachments/assets/c25416f9-f380-4286-a432-a8180da89c34)

Sun Microsystems engineers had created JVM (Java Virtual Machine) to install on different
platforms such as Windows, Linux, Mac, etc

![image](https://github.com/user-attachments/assets/f23613b3-db37-4af4-8254-f1ed88068fcd)

# 2   JDK and JRE
## JRE
JRE (Java Runtime Environment) is a software package that provides everything needed to run Java programs.

JRE is short for Java Runtime Environment, which includes JVM (Java Virtual Machine) and a number of Java libraries that support to execute programs 
written in the Java language.

![image](https://github.com/user-attachments/assets/c1c98c6c-fff5-417a-a296-b07735590874)

## Components of JRE:
1.JVM (Java Virtual Machine)
   * The engine that runs Java bytecode
   * Converts class files (compiled Java code) into machine code your computer understands.
     
2.Java Class Libraries
   * A set of prewritten Java code (like java.lang, java.util, java.io, etc.) that Java programs depend on.
  
     Example: The System.out.println() method comes from these libraries.

3.Other supporting files

 * Configuration files, property files, fonts, etc.

## JDK ( Java Development Kit )   
JDK is necessary for programmers because Java Development Tools provides tools for Java application development, such as Javac which compile the developer's source codes into Byte Codes, etc. then uses JRE to run the application during the development process.

![image](https://github.com/user-attachments/assets/a9777a6e-7e8c-4d8a-a4f8-04046a24a1e9)

## Purpose of JDK:
* Write, compile, debug, and run Java applications.

* Used by developers to build Java software for desktop, web, mobile, and enterprise environments.

# Difference Between JDK and JRE
![image](https://github.com/user-attachments/assets/0672d744-ff67-4664-8bd5-1d354cacd382)   ____________________________________________________________________________________________________________________________________________________
# Chapter 2 :
## Data Types in java
### 1	Overview of data types 

### 2	byte 
### 3	boolean 
### 4	char     
### 5	short     
### 6	int   
### 7	long    
### 8	float 
### 9	double 
### 10 Reference Types

## 1 Overview of data types

 Any programming language has a set of data types. Data types are basic, and quite similar for all languages. 
 All data types are composed from bits.
 
 Java has two types of data types:
   
* Primitive Types
* Non-Primitive

![image](https://github.com/user-attachments/assets/60a488e8-86ea-4f30-ba71-1c974b09f942)

## Primitive Data Types in Java
## 2. byte
The byte data type is an 8-bit signed two’s complement integer. The byte data type is useful for saving memory in large arrays.
### Syntax:
     byte byteVar;
     
## 3. boolean Data Type
The boolean data type represents a logical value that can be either true or false.

It plays a central role in decision-making processes, such as in if,while and for statements, and in logical operations.

### Syntax:
     boolean booleanVar;
     
## 4.char

Although "char" is the first four characters of the "Character" term, the char type in Java is used to store non-negative 
integers with the two-byte size.It is also used to represent for a Unicode character because in nature, each character 
corresponds to a specific number. 
(This number is understood as the code of character.)

## Syntax:
   char charVar;
   
## 5.short

short is data type for the purpose of representing a two-byte integer (16 bits), including negative integer.

   The smallest value is -32,768 (-2^15) and the largest value is 32,767 (2^15 -1). Default value is 0.
   
## Syntax:
   short shortVar;
## 6.int 

int data type is used to represent an integer with the size of 4 bytes (32 bits).

The smallest value: -2,147,483,648 (-2^31)

The largest value: 2,147,483,647 (2^31 -1) 

Default value:0.

 ## Syntax
   
      int intVar;
      
## 7.long

 The long data type is a 64-bit signed two’s complement integer. It is used when an int is 
 not large enough to hold a value, offering a much broader range.
 
## Syntax

    long longVar;
    
## 8.float

The float data type is a single-precision 32-bit IEEE 754 floating-point. Use a float 
if you need to save memory in large arrays of floating-point numbers. 
The size of the float data type is 4 bytes (32 bits).

## sysntax

   float floatVar;
   
## 9.Double

The double data type is a double-precision 64-bit IEEE 754 floating-point. For decimal 
values, this data type is generally the default choice. The size of the double data type 
is 8 bytes or 64 bits.

## Syntax

     double doubleVar;
________________________________________________________________________________________________________________________
 
  # Chapter 3 

  ##    if else statement in java
  
  ##    1.if statment
     
   ##  2. if - else statement
     
  ##   3. if - else if - else statement
     
   ##  4. Boolean value
     
  ##   5. Operators involved in conditional expression

 ##  if statment
 
The if statement is the most basic of all the control flow statements. It tells your program to execute a certain section of code 
only if a particular test evaluates to true.

### Syntax:  

    if(condition)
  
    {

    // Statements to execute if
   
    // condition is true
   
    }

![image](https://github.com/user-attachments/assets/1822e6fe-d792-47b1-9cf2-1be078ae4184)

1	The program checks the condition.

2	If the condition is true, code in the if block will be executed. It then continues executing the codes below the if block.

3	If the condition is false, the program will ignores the code in the if block and execute code snippets below the if block.

### Example:

        int num =3;

        if(num>0)

        {

        System.out.print("The number is positive");

        }

Output:

       The number is positive

# if - else statement

The if-else statement in Java is a powerful decision-making tool used to control the program’s flow based on conditions. 
It executes one block of code if a condition is true and another block if the condition is false.

### Syntax of if-else Statement

     if (condition)
     
     {
   
    // Executes this block if
    
    // condition is true

    }

     else

     {
    
    // Executes this block if
    
    // condition is false

     }

![image](https://github.com/user-attachments/assets/200548e4-05b0-42c8-9411-759efd49cd97)

# if - else if - else statement

the if-else if-else statement is used to execute different blocks of code based on multiple conditions.

    
### Syntax:
    if (condition1) 
    
    {
    
    // code block for condition1
    
    } 

    else if (condition2) 

    {
    
    // code block for condition2
    
    } 

    else 

    {
    
    // code block if none of the above conditions are true
    
    }

![image](https://github.com/user-attachments/assets/90295ded-271e-464e-94a6-5c883177adb8)

# Boolean value

boolean is a data type, it only has two values true or false.

This is useful to build logic, and find answers.

For example, you can use a comparison operator, such as the greater than (>) operator, to find out if an expression is true or false

      int x = 10;
  
      int y = 9;
  
      System.out.println(x > y); // returns true, because 10 is higher than 9

      Output:
  
          true
_______________________________________________________________________________________________________________________________________

# Chapter 4

## Switch Statement in Java

##               1.Structure of switch statement 
               
 ##              2.switch Example 
               
 ##              3.break statement in switch

###  1.Structure of switch statement
     
       switch(expression)   
       {
    
       case value1 :
  
       // Statements
     
        break; // break is optional
  
       case value2 :
  
     // Statements
     
     break; // break is optional
     ….
     ….
     ….
     default :
   
     // default Statement
     
     }

###  2.Switch Example

      public class SwitchWithoutBreak 
      
         {
      
      public static void main(String[] args) 
      
        {
       
        int day = 3;
        
        String dayName = "";

        switch (day) 
        
           {
            
            case 1:
                
                dayName = "Monday";
            
            case 2:
                
                dayName = "Tuesday";
            case 3:
                
                dayName = "Wednesday";
            
            case 4:
                
                dayName = "Thursday";
            
            case 5:
                
                dayName = "Friday";
           
            case 6:
                
                dayName = "Saturday";
           
            case 7:
                
                dayName = "Sunday";
            
            default:
               
                dayName = "Invalid day";
        
           }

        
        System.out.println("The day is: " + dayName);
    
           }

         }

     Output :

        The day is: Invalid day


### 3 break statement in switch

break means a statement to be able to appear in the case block, or default block of switch.

When meeting the break statement, the program will exit the switch.

![image](https://github.com/user-attachments/assets/284da333-5e38-4277-a0de-16090dab7a4d)

 ### Example

        public class SwitchExample
   
       {
    
       public static void main(String[] args) 
    
       {
        
        int day = 3;
        
        String dayName;

        switch (day) 
        
        {
           
            case 1:
                
                dayName = "Monday";
                
                break;
            
            case 2:
                dayName = "Tuesday";
                break;
            case 3:
                dayName = "Wednesday";
                break;
            case 4:
                dayName = "Thursday";
                break;
            case 5:
                dayName = "Friday";
                break;
            case 6:
                dayName = "Saturday";
                break;
            case 7:
                dayName = "Sunday";
                break;
            default:
                dayName = "Invalid day";
        }

         System.out.println("The day is: " + dayName);
        }
        }

        Ouput:
        
         The day is: Wednesday
         
________________________________________________________________________________________________________________________________________________________________________

   # Chapter 5 
   
  ### 1.Loops in Java 
  ### 2.for Loop 
  ### 3.for-each loop 
  ### 4.while Loop 
###   5.do-while Loop 
###   6.The break statement in loop 
###   7.The continue statement in a loop 
###   8.Labelled Loop

##  1.  Loops in Java

In Java, loops are used to execute a block of code repeatedly under certain conditions. 

Java supports the following main types of loops

1.for loop

2.while loop 

3.do-while loop
      
### 2.   for loop  
A for loop is a control flow statement used to repeat a block of code a specific number of times
            
          Statement 1 
          
              sets a variable before the loop starts (int i = 0).

          Statement 2 
          
              defines the condition for the loop to run (i must be less than 5).
              
              If the condition is true, the loop will start over again, 
              
              if it is false, the loop will end.

          Statement 3 
          
             increases a value (i++) each time the code block in the loop has been executed.

###  Example 
              
               public class Main 
               {
               public static void main(String[] args) 
               {
                 int sum = 0;
                 for (int i = 1; i <= 10; i++) {
                 sum += i;
              }
                 System.out.println("Sum: " + sum);
             }
           }

           Output:

              sum:55

# While Loop

Java while loop is a control flow statement used to execute the block of statements repeatedly until the given condition evaluates to false.
Once the condition becomes false, the line immediately after the loop in the program is executed.

### Example
    public class WhileLoop {
    public static void main(String[] args) {
      
      // Initialize the counter variable
      int c = 1; 

        // While loop to print numbers from 1 to 5
        while (c <= 5) {
          
          System.out.println(c); 
            
          // Increment the counter
          c++; 
        }
    }
    }

  ### output
         1
         2
         3
         4
         5

# do-While Loop

In Java, a do-while loop is a control flow statement that executes a block of code at least once, and then repeatedly executes the block as long as the given condition is true.

### Syntax

       do {
          // Code to execute
         } 
       while (condition);

### Example

     int i = 1;
     do {
      System.out.println("Value of i: " + i);
      i++;
      } while (i <= 5);

### output

       Value of i: 1
       Value of i: 2
       Value of i: 3
       Value of i: 4
       Value of i: 5

# for-each loop

a for-each loop (also called the enhanced for loop) is used to iterate over elements in arrays or collections like ArrayList, HashSet, etc.  It provides a cleaner and more readable alternative to the traditional for loop when you don’t need to track the index.

 ### Syntax
 
      for (type variable : collection) 
      {
    // Code to execute with each element
      }

### Example

    int[] numbers = {1, 2, 3, 4, 5};
    for (int num : numbers) 
    {
    System.out.println(num);
    }
    
### output
    1
    2
    3
    4
    5

# The break statement in loop 

The Break Statement in Java is a control flow statement used to terminate loops and switch cases. As soon as the break statement is encountered from within a loop, the loop iterations stop there, and control returns from the loop immediately to the first statement after the loop.

### Example:

    import java.io.*;

    class sample {
  
    public static void main (String[] args) 
    {
      
      //assigning n as integer value
      int n = 1;
      
      //passing n to switch
      switch(n) {
        case 1: 
          System.out.println("first case");
          break;
        case 2:
          System.out.println("Second Case");
          break;
        default:
          System.out.println("default case");
        }
         }
        }
 ### output
 
     first case

# The continue statement in a loop 

In Java, the continue statement is used inside the loops such as for, while, and do-while to skip the current iteration and move directly to the next iteration of the loop.   

# Example:

      public class Geeks
     {
     public static void main(String args[])
    {      
        // For loop for iteration
        
        for (int i = 0; i <=5; i++)
        {
            // Check condition for continue
          	// skip the execution of loop when i==3                  
          	
           if (i == 3)
                continue;
            System.out.print(i + " ");
        }
       }
       }

### output

       0 1 2 4 5
       
# labeled loop

a labeled loop is a loop that has a name (label) attached to it. Labels are used to control the flow of nested loops more precisely—especially when using break or continue. With a label, you can break out of or continue a specific outer loop instead of just the inner one.

### Example

     public class LabeledLoopExample {
     public static void main(String[] args) {
        outer:
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                if (i == 2 && j == 2) {
                    break outer; // breaks out of both loops
                }
                System.out.println("i = " + i + ", j = " + j);
            }
        }
        }
       }
### output

     i = 1, j = 1
     i = 1, j = 2
     i = 1, j = 3
     i = 2, j = 1
_____________________________________________________________________________________________

# Chapter 6
### Arrays in Java

## What is Array

an array is a container object that holds a fixed number of elements of the same data type. Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.

![image](https://github.com/user-attachments/assets/1b3a7205-9fa3-443a-b0f1-19f51dd474bc)

To declare an array, define the variable type with square brackets

#### Systax

      String[] cars;

We have now declared a variable that holds an array of strings. To insert values to it, you can place the values in a comma-separated list, inside curly braces

### syntax
    
   String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

   To create an array of integers

  int[] myNum = {10, 20, 30, 40};

### Key Features of Arrays:

1.Fixed size: Once created, its size can't be changed.

2.Zero-based index: The first element is at index 0.

3.Homogeneous: All elements must be of the same type.

4.Indexed access: You can quickly access any element using its index.

### Access the Elements of an Array

    String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
    System.out.println(cars[0]);

  ### output:
        Volvo

### Change an Array Element

To change the value of a specific element, refer to the index number:

### Example
    String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
    cars[0] = "Audi";
    System.out.println(cars[0]);

### output:
    Audi

# Array Length

To find out how many elements an array has, use the length property:

    String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
    System.out.println(cars.length);
    
    Output:
           4

### Example

      public class ArrayExample 
      {
      public static void main(String[] args) 
      {
        int[] marks = {90, 80, 70, 60};
        for (int i = 0; i < marks.length; i++) 
        {
            System.out.println("Mark " + (i + 1) + ": " + marks[i]);
        }
          }
        }
        
 ### output:
 
     Mark 1: 90
     Mark 2: 80
     Mark 3: 70
     Mark 4: 60

# Types of Arrays in Java

1. Single-Dimensional Arrays
2. Multi-Dimensional Arrays

## Single-Dimensional Array
A linear array that stores elements in a single row (like a list)

![image](https://github.com/user-attachments/assets/2cdc21b2-9943-4915-9425-7ee3064f9f03)


### Syntax:

      int[] numbers = new int[5];  // declares an array of 5 integers
      
### Example:

      int[] numbers = {10, 20, 30, 40, 50};
      System.out.println(numbers[2]);  
      
### Output:

           30

 ## Two-dimensional (2D) array:          
Multidimensional arrays can be considered as an array of arrays or as a matrix consisting of rows and columns.

![image](https://github.com/user-attachments/assets/e69a35ae-b3d4-4772-bc3b-50b2885ca10c)

### Syntax 

       data_type array_name[sizeof_1st_dimension][sizeof_2nd_dimension];

### Example:
            int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
            };
            System.out.println(matrix[1][2]);  
### Output: 
            6
_______________________________________________________________________________________________

# Chapter 7 :
### Inheritance and polymorphism in Java
1.Class, Constructor and instance

2.Inheritance in java

3.Polymorphism in Java


### Class

* Class is not a real-world entity. It is just a template or blueprint, or a prototype from which objects are created.
Class does not occupy memory.
* A class is a group of variables of different data types and a group of methods.
* a class is a blueprint for creating objects
* It defines a type by bundling data (fields/attributes) and methods (functions/behaviors) into a single unit.
* A Class in Java can contain:
  
  1.Data member
  
  2.Method
  
  3.Constructor
  
  4.Nested Class
  
  5.Interface

### Class Declaration in Java
         access_modifier class <class_name> 
        {      
        data member;       
        method;       
        constructor;     
        nested class;     
        interface;
        }

 ### Example    
     // Define the class
     public class Person 
     {
    // Fields (variables)
    String name;
    int age;
    // Method (function)
    void sayHello() {
    System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }
    public class Main {
    public static void main(String[] args)
    {
        // Create an object of Person
        Person p1 = new Person();

        // Set values
        p1.name = "Arun";
        p1.age = 25;

        // Call the method
        p1.sayHello();
       }
      }
      }
### output:

     Hello, my name is Arun and I am 25 years old.

### Constructors

a constructor is a special method used to initialize objects when they are created. 

### Characteristics of Constructors:
* Same Name as the Class: A constructor has the same name as the class in which it is defined.
* No Return Type:
    Constructors do not have any return type, not even void. The main purpose of 
    a constructor is to initialize the object, not to return a value.
* Automatically Called on Object Creation:
    When an object of a class is created, the constructor is called automatically to initialize 
    the object’s attributes.
  
### Example
    public class Person {
    String name;
    int age;

    // Constructor
    public Person(String n, int a) {
        name = n;
        age = a;
    }

    // Method
    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
    }
     public class Main {
    public static void main(String[] args) {
        // Constructor is called automatically
        Person p1 = new Person("arun", 25);
        p1.display(); 
     }
      }
### output:

     Name: arun, Age: 25

# Inheritance

Inheritance is one of the core concepts of Object-Oriented Programming (OOP).
It allows one class (called subclass or child class) to inherit the properties and behaviors (fields and methods) of another class (called superclass or parent class).

### Syntax:
     class Parent 
     {
    // fields and methods
     }

     class Child extends Parent 
     {
    // additional fields and methods
     }
     
## Types of Inheritance in Java
     
1.Single Inheritance

2.Multilevel Inheritance

3.Hierarchical Inheritance

4.Multiple Inheritance

5.Hybrid Inheritance

### 1. Single Inheritance

In single inheritance, a sub-class is derived from only one super class. It inherits the properties and behavior of a single-parent class. Sometimes, it is also known as simple inheritance. In the below figure, ‘A’ is a parent class and ‘B’ is a child class. The class ‘B’ inherits all the properties of the class ‘A’.

![image](https://github.com/user-attachments/assets/5a41cd62-2bdc-4f71-bde3-e519e0b72ebb)

### Example

     // Parent class
     class Animal {
    void eat() {
        System.out.println("This animal eats food.");
           }
     }

     // Child class
     class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
    }

     // Main class to test
     public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // Inherited from Animal
        d.bark();  // Defined in Dog
         }
      }
  ### output:
  
         This animal eats food.
         The dog barks.
         
### 2.Multilevel Inheritance
    
In Multilevel Inheritance, a derived class will be inheriting a base class, and as well as the derived class also acts as the base class for other classes. In the below image, class A serves as a base class for the derived class B, which in turn serves as a base class for the derived class C. In Java, a class cannot directly access the grandparent’s members if they are private.

### syntax:

          class Grandparent 
          {
         // members
          }

        class Parent extends Grandparent 
         {
        // members
         }

        class Child extends Parent
        {
        // members
        }


![image](https://github.com/user-attachments/assets/ed909aa8-45c7-4290-a3f5-338f63ccb670)

### Example:

         // Grandparent class
         class Animal {
         void eat()
         {
        System.out.println("This animal eats food.");
          }
       }
    // Parent class
         class Dog extends Animal {
          void bark() {
        System.out.println("The dog barks.");
       }
      }

     // Child class
     class Puppy extends Dog {
      void weep() {
        System.out.println("The puppy weeps.");
         }
         }

      // Main class to test
     public class Main {
     public static void main(String[] args) {
        Puppy p = new Puppy();
        p.eat();   // From Animal
        p.bark();  // From Dog
        p.weep();  // From Puppy
     }
     }
### output:

       This animal eats food.
       The dog barks.
       The puppy weeps.
       
### Hierarchical Inheritance

In Hierarchical Inheritance, one class serves as a superclass (base class) for more than one subclass. In the below image, class A serves as a base class for the derived classes B, C, and D.

### syntax:
    class Parent
    {
    // members
     }

    class Child1 extends Parent 
    {
    // members
    }

    class Child2 extends Parent 
    {
    // members
    }


![image](https://github.com/user-attachments/assets/2a034fd4-257a-419a-927f-248484aa4ea4)

###  Example:

         // Parent class
        class Animal {
        void eat()
        {
        System.out.println("This animal eats food.");
        }
      }
      // First child class
      class Dog extends Animal {
     void bark() {
        System.out.println("The dog barks.");
          }
      }

      // Second child class
      class Cat extends Animal {
      void meow() {
        System.out.println("The cat meows.");
       }
     }

      // Main class to test
    public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // Inherited from Animal
        d.bark();  // From Dog

        Cat c = new Cat();
        c.eat();   // Inherited from Animal
        c.meow();  // From Cat
    }
    }

### output:
     
    This animal eats food.
    The dog barks.
    This animal eats food.
    The cat meows.

### Multiple Inheritance

In Multiple inheritances, one class can have more than one superclass and inherit features from all parent classes. Please note that Java does not support multiple inheritances with classes. In Java, we can achieve multiple inheritances only through Interfaces. In the image below, Class C is derived from interfaces A and B.

### syntax:

      interface Interface1
     {
      // method declarations
      }

      interface Interface2 
      {
    // method declarations
      }

      class ClassName implements Interface1, Interface2
      {
    // implementation of all interface methods
       }


![image](https://github.com/user-attachments/assets/3ccf2bec-5ffa-4960-ba71-b441c4b14c15)


### Example:Multiple Inheritance using Interfaces
     
         // First interface
         interface Flyable {
         void fly();
         }

        // Second interface
        interface Movable {
        void move();
        }

        // Class implementing both interfaces
        class Bird implements Flyable, Movable {
        public void fly() {
        System.out.println("The bird is flying.");
        }

        public void move() {
        System.out.println("The bird is moving.");
       }
      }

       // Main class
         public class Main {
         public static void main(String[] args) {
            Bird b = new Bird();
            b.fly();   // From Flyable
            b.move();  // From Movable
           }
        }

### output:

     The bird is flying.
     The bird is moving.

###  Hybrid Inheritance

Hybrid Inheritance is a combination of two or more types of inheritance 

Single + Multiple

Multilevel + Multiple

Hierarchical + Interface-based multiple

![image](https://github.com/user-attachments/assets/36e803c6-bd9b-4dc6-87dc-cbfaeeff4617)


### syntax:

        interface InterfaceA {
        void methodA();
        }

       interface InterfaceB {
       void methodB();
       }

       class BaseClass {
       void baseMethod() {
        // code
       }
       }

      // Hybrid: inherits from a class and implements multiple interfaces
        class Derived extends BaseClass implements InterfaceA, InterfaceB {
        public void methodA() {
        // implementation
       }

        public void methodB() {
        // implementation
        }
      }

### Example:

       // Interface 1: Flyable
       interface Flyable {
        void fly();
       }

      // Interface 2: Walkable
      interface Walkable {
      void walk();
     }

     // Parent class: Animal
     class Animal {
     void eat() {
        System.out.println("This animal eats food.");
           }
      }
       class Bird extends Animal implements Flyable, Walkable 
      {
        public void fly() {
        System.out.println("The bird is flying.");
         }
        public void walk() {
        System.out.println("The bird is walking.");
          }
        }
        // Main class to test
        public class Main
        {
        public static void main(String[] args) {
        Bird bird = new Bird();
        bird.eat();    // From Animal class
        bird.fly();    // From Flyable interface
        bird.walk();   // From Walkable interface
           }
        }
   
### output:

     This animal eats food.
     The bird is flying.
     The bird is walking.

### Polymorphism 

Polymorphism in Java is one of the core concepts of object-oriented programming (OOP). It means "many forms", and it allows objects to be treated as instances of their parent class rather than their actual class. Polymorphism enables flexibility and reusability of code.   
There are two main types of polymorphism in Java:

1.Compile-Time Polymorphism (Static Binding)

2.Run-Time Polymorphism (Dynamic Binding)

### 1. Compile-Time Polymorphism (Static Binding) 

Compile-time polymorphism is achieved through method overloading, where multiple methods have the same name but differ in number or type of parameters. The decision about which method to invoke is made at compile time by the compiler.

### Example:
    class Calculator {
    int add(int a, int b) {
        return a + b;
      }
    int add(int a, int b, int c) {
        return a + b + c;
     }

    double add(double a, double b) {
        return a + b;
     }
     }
         public class Main {
         public static void main(String[] args) {
         Calculator calc = new Calculator();
        System.out.println("Sum of 2 ints: " + calc.add(10, 20));
        System.out.println("Sum of 3 ints: " + calc.add(10, 20, 30));
        System.out.println("Sum of 2 doubles: " + calc.add(10.5, 20.3));
       }
        }
        
  ### output:
     
         Sum of 2 ints: 30
         Sum of 3 ints: 60
         Sum of 2 doubles: 30.8
         
### 2.Run-Time Polymorphism (Dynamic Binding)

Run-time polymorphism is achieved through method overriding. It allows a subclass to provide a specific implementation of a method already defined in its parent class. The method call is resolved at runtime, not at compile time.

### Example:
            class Animal {
            void sound() {
            System.out.println("Animal makes a sound");
            }
         }

         class Dog extends Animal {
         @Override
        void sound() {
        System.out.println("Dog barks");
         }
       }

       class Cat extends Animal {
       @Override
       void sound() {
        System.out.println("Cat meows");
       }
    }

    public class Main {
    public static void main(String[] args) {
        Animal a;  // reference of parent class

        a = new Dog();  // Dog object
        a.sound();      // Output: Dog barks

        a = new Cat();  // Cat object
        a.sound();      // Output: Cat meows
    }
    }

### output:

       Dog barks
       Cat meows
  ___________________________________________________________________________________________     
# Chapter 8 

### 1.Abstract Class 
### 2.Abstract class, the examples
### 3.Overview of the interface 
### 4.Structure of an Interface
### 5.Class implements Interface

### 1. Abstract Class

An abstract class in Java is a class that cannot be instantiated on its own and is designed to be inherited by other classes. It may contain abstract methods (without a body) and concrete methods (with implementations).

### Syntax:
     
       abstract class Animal
       {
       abstract void sound(); // abstract method
       void sleep() 
       {         // concrete method
        System.out.println("Animal is sleeping");
       }
      }
      
### Example:
      abstract class Animal 
      {
      abstract void sound(); // abstract method

     void sleep() {         // concrete method
        System.out.println("Sleeping");
       }
     }

    class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
    }

    public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound();   
        myDog.sleep();   
      }
      }
      
### output:
     Dog barks
     
     Sleeping

### Interface
An interface is a completely "abstract class" that is used to group related methods with empty bodies
It is used to achieve abstraction and multiple inheritance in Java.
   
### Syntax
    interface Animal
    {
    void sound(); // abstract method
     }

### Example:
         interface Animal 
         {
         void sound(); // abstract method
         }

         class Dog implements Animal {
         public void sound()
         {
        System.out.println("Dog barks");
          }
          }

        public class Main {
        public static void main(String[] args)
        {
        Animal myDog = new Dog();
        myDog.sound(); // Output: Dog barks
       }
       }

  ### output
  
         Dog barks

### Class Implements Interface
   
When a class implements an interface, it agrees to provide implementations for all of the abstract methods declared in the interface. This is a core part of achieving abstraction and polymorphism in Java.

### Syntax:
    interface InterfaceName
    {
    void method1();
    void method2();
    }

   class ClassName implements InterfaceName
   {
    public void method1() 
    {
        // Implementation of method1
    }

    public void method2() 
    {
        // Implementation of method2
     }
    }
    
### Multiple Interface Implementation Example
         
        // Interface definition
       interface Animal 
       {
        void sound();  // abstract method
        void eat();    // abstract method
       }

       // Class implementing the interface
       class Dog implements Animal {
       public void sound() 
       {
        System.out.println("Dog barks");
       }

      public void eat()
      {
        System.out.println("Dog eats bones");
      }
    }

    // Main class
    public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog(); // interface reference to Dog object
        myDog.sound();  // Calls Dog's implementation
        myDog.eat();    // Calls Dog's implementation
    }
    }

### output:
    Dog barks
    Dog eats bones

###   Threads

Java threads are lightweight subprocesses, representing the smallest unit of execution with separate paths. The main advantage of multiple threads is efficiency (allowing multiple things at the same time)

### Why Use Threads?
* To perform multiple tasks simultaneously

* To improve performance

* Useful in scenarios like:

1.Games
2.Web servers
3.Animations

### Create Threads

By Extending the Thread Class   

    class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
      }

    public class TestThread {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();  // Start the thread
    }
    }
### output:
      Thread is running...
      
### By Implementing the Runnable Interface

      class MyRunnable implements Runnable {
      public void run()
      {
        System.out.println("Runnable thread is running...");
      }
      }

     public class TestRunnable {
      public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
     }
     }
     
### Output:
         Runnable thread is running...

### Multithreading

Multithreading means running two or more threads simultaneously, each performing its task independently.

it helps:

*Increase performance

*Run multiple operations concurrently

*Utilize CPU cores efficiently

### Example:
         class MyThread1 extends Thread {
         public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Thread 1 - Count: " + i);
            try {
                Thread.sleep(500); // sleep for 0.5 second
            } catch (InterruptedException e) {
                System.out.println(e);
            }
           }
        }
       }

         class MyThread2 extends Thread {
         public void run() {
         for (int i = 1; i <= 5; i++) {
            System.out.println("Thread 2 - Count: " + i);
            try {
                Thread.sleep(500); // sleep for 0.5 second
            } catch (InterruptedException e) {
                System.out.println(e);
            }
           }
        }
      }

        public class MultiThreadDemo {
        public static void main(String[] args) {
        MyThread1 t1 = new MyThread1();
        MyThread2 t2 = new MyThread2();

        t1.start(); // Start first thread
        t2.start(); // Start second thread
      }
      }

### output:
        Thread 1 - Count: 1
        Thread 2 - Count: 1
        Thread 1 - Count: 2
        Thread 2 - Count: 2
        Thread 1 - Count: 3
        Thread 2 - Count: 3
        Thread 1 - Count: 4
        Thread 2 - Count: 4
        Thread 1 - Count: 5
        Thread 2 - Count: 5


### join() and sleep() in Threads

### sleep() Method

Pauses the current thread for a specified time (in milliseconds).

### Syntax:

     Thread.sleep(milliseconds);
     
### Example:

     public class SleepExample {
     public static void main(String[] args) {
        try {
            for (int i = 1; i <= 5; i++) {
                System.out.println("Count: " + i);
                Thread.sleep(1000); // pause for 1 second
            }
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        }
     }
### output:
       Count: 1   ← after 1 sec
       Count: 2   ← after 1 sec
       Count: 3   ← after 1 sec
       Count: 4   ← after 1 sec
       Count: 5   ← after 1 sec

 ### join() Method  

 Tells one thread to wait for another thread to finish before continuing.

 ### Syntax:
 
         thread.join();

 ### Example:
           class MyThread extends Thread {
           public void run() {
           for (int i = 1; i <= 3; i++) {
            System.out.println(getName() + " - Count: " + i);
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
      }
      }

        public class JoinExample {
        public static void main(String[] args)
	{
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();

        t1.setName("Thread A");
        t2.setName("Thread B");

        t1.start();
        try {
            t1.join(); // main waits for t1 to finish
        } catch (InterruptedException e) {
            System.out.println(e);
        }

        t2.start(); // t2 starts only after t1 completes
        }
       }
       
### Output:
      
         Thread A - Count: 1
         Thread A - Count: 2
         Thread A - Count: 3
         Thread B - Count: 1
         Thread B - Count: 2
         Thread B - Count: 3
	 
  ### Class Implementing Runnable Interface
 
 Runnable is a functional interface in Java used to define a task that can be executed by a thread.
It has a single method:

      public void run();
      
 ### Example 
      // Implementing the Runnable interface
      class MyTask implements Runnable 
      {
      public void run() 
      {
        System.out.println("Thread is running: " + Thread.currentThread().getName());
    }
    }

    public class Main {
    public static void main(String[] args) {
        // Create an object of the Runnable implementation
        MyTask task = new MyTask();

        // Create a Thread object and pass the task to it
        Thread thread = new Thread(task);

        // Start the thread
        thread.start();
    }
    }

### output:
         Thread is running: Thread-0

### Exception Handling 

### Exception

In Java, an exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. These exceptions can occur for various reasons, such as invalid user input, file not found, or division by zero. When an exception occurs, it is typically represented by an object of a subclass of the java.lang.Exception class.

Exception Handling is a mechanism to handle runtime errors such as ClassNotFoundException, IOException, SQLException, RemoteException, etc.

### 1.The try-catch Block

One of the primary mechanisms for handling exceptions in Java is the try-catch block. The try block contains the code that may throw an exception, and the catch block is used to handle the exception if it occurs.

### Syntax:
               try {  
               
                  // Code that may throw an exception  
                  
              } catch (ExceptionType e) { 
              
               // Exception handling code  
               
               }  

 ### Exampple:

         public class TryCatchExample {
         public static void main(String[] args) {
        try {
            int result = 10 / 0;  // ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero.");
        }
        }
      }

### output:
      Cannot divide by zero.

### 2. Multiple Catch Blocks

Used to handle different types of exceptions separately.

### Example

       public class MultipleCatchExample {
       public static void main(String[] args) {
        try {
            int[] arr = new int[5];
            arr[10] = 25;  // ArrayIndexOutOfBoundsException
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Error");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds");
        } catch (Exception e) {
            System.out.println("General exception");
        }
       }
     }

 ### output
 
       Array index out of bounds

### 3. Nested Try Block       

A try block within another try block.

### Example:

         public class NestedTryExample {
        public static void main(String[] args) {
        try {
            System.out.println("Outer try block");
            try {
                int a = 10 / 0;  // ArithmeticException
            } catch (ArithmeticException e) {
                System.out.println("Inner catch: " + e);
            }
        } catch (Exception e) {
            System.out.println("Outer catch: " + e);
        }
       }
     }

 ### output:
 
        Outer try block
        Inner catch: java.lang.ArithmeticException: / by zero

### 4. Finally Block
       
Code inside the finally block always executes, whether or not an exception occurs.

### Example:

       public class FinallyExample {
      public static void main(String[] args) {
        try {
            int data = 25 / 5;
            System.out.println("Result: " + data);
        } catch (NullPointerException e) {
            System.out.println("Exception caught");
        } finally {
            System.out.println("This is the finally block");
        }
      }
    }

### output:

        Result: 5
        This is the finally block



### 5. Throw Keyword

       Used to explicitly throw an exception.

### Example:

        public class ThrowExample {
        public static void main(String[] args) {
        int age = 15;
        if (age < 18) {
            throw new ArithmeticException("Age must be 18 or above");
        } else {
            System.out.println("Eligible");
        }
       }
      }

 ### output:

      Exception in thread "main" java.lang.ArithmeticException: Age must be 18 or above
	   at ThrowExample.main(ThrowExample.java:5)


### 6. Throws Keyword:

Used to declare exceptions a method might throw.

### Example

     import java.io.*;
     public class ThrowsExample {
    static void readFile() throws IOException
     {
        FileReader fr = new FileReader("abc.txt");  // Checked exception
     }

     public static void main(String[] args) {
        try {
            readFile();
        } catch (IOException e) {
            System.out.println("Handled exception: " + e.getMessage());
        }
      }
    }

 ### output:
 
         Handled exception: abc.txt (No such file or directory)


### 7. Custom Exception

You can define your own exception class

### Example:

        class MyException extends Exception {
        public MyException(String message) {
        super(message);
        }
      }
       public class CustomExceptionExample {
       static void validate(int age) throws MyException {
        if (age < 18) {
            throw new MyException("Custom Exception: Age must be 18 or above");
        }
       }  

      public static void main(String[] args) {
        try {
            validate(16);
        } catch (MyException e) {
            System.out.println("Caught: " + e.getMessage());
        }
      }
     }

### output:

     Caught: Custom Exception: Age must be 18 or above

### types of Exception

### ArithmeticException occurs

If we divide any number by zero, there occurs an ArithmeticException.

int a=50/0;//ArithmeticException  

### Example 

        public class Main {    
        public static void main(String[] args) {    
        int dividend = 10;    
        int divisor = 0;    
        try {    
            int result = dividend / divisor; // Division by zero    
            System.out.println("Result: " + result);    
        } catch (ArithmeticException e) {    
            System.out.println("Error: Division by zero is not allowed.");    
            // Additional error handling code can be added here    
        }    
        }    
      }  

### output:

       Error: Division by zero is not allowed.
       
### ArrayIndexOutOfBoundsException occurs

When an array exceeds to it's size, the ArrayIndexOutOfBoundsException occurs. there may be other reasons to occur ArrayIndexOutOfBoundsException.

### Example

         public class Main {    
         public static void main(String[] args) {    
        int[] numbers = {1, 2, 3, 4, 5}; // Initializing an array with 5 elements    
        try {    
            int index = 10; // Accessing an index that is out of bounds    
            int value = numbers[index]; // Attempting to access an element at an invalid index    
            System.out.println("Value at index " + index + ": " + value);    
        } catch (ArrayIndexOutOfBoundsException e) {    
            System.out.println("Error: Index is out of bounds.");    
            // Additional error handling code can be added here    
        }    
      }    
     }  
     
### output:

      Error: Index is out of bounds.
      
### NullPointerException occurs

If we have a null value in any variable, performing any operation on the variable throws a NullPointerException.   

### Example:

         public class Main {    
         public static void main(String[] args) {    
        String str = null; // Initializing a String variable to null    
        try {    
            int length = str.length(); // Attempting to call a method on a null reference    
            System.out.println("Length of the string: " + length);    
        } catch (NullPointerException e) {    
            System.out.println("Error: Null reference encountered.");    
            // Additional error handling code can be added here    
        }    
       }    
      } 

### output:

        Error: Null reference encountered.

### IOException   

IOException is a checked exception in Java that occurs during input/output operations, like reading from a file, writing to a file, or working with streams.

It belongs to the package: java.io

It must be either handled with try-catch or declared using throws
       
#### Common Causes of IOException:

Trying to read from or write to a file that does not exist

Device failure (e.g., disk crash)

Network issues during I/O

File is being used by another process

Incorrect file path

### Example:

     import java.io.*;
     public class IOExceptionExample {
      public static void main(String[] args) {
        try {
            // Attempting to read a file
            BufferedReader reader = new BufferedReader(new FileReader("sample.txt"));

            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }

            reader.close();
        } catch (IOException e) {
            System.out.println("An I/O error occurred: " + e.getMessage());
        }
       }
      }
### output:

       An I/O error occurred: sample.txt (No such file or directory)

       


      



        
















   
     
     

  

  
    
    
    


        

   

       

 
   
     

     

    












     



     

     

  

   
    


    


       
      

     





  
     

     
    
  



     









   

     



    
    






              

              


           



   

   
  




     














     

     
  


    
    
    

   

   

   

     
     


   
   




     



