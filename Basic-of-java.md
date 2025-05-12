
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
    (instead of double) if you need to save memory in large arrays of floating-point numbers. 
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

  ## if else statement in java
  
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

###  1    Structure of switch statement
     
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
} while (condition);

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
     

     

    












     



     

     

  

   
    


    


       
      

     





  
     

     
    
  



     









   

     



    
    






              

              


           



   

   
  




     














     

     
  


    
    
    

   

   

   

     
     


   
   




     



