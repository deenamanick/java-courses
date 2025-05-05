
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








     

     
  


    
    
    

   

   

   

     
     


   
   




     



