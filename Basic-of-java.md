# JDBC (Java Database Connectivity)
### Introduction to JDBC
JDBC (Java Database Connectivity) is a Java API that allows Java programs to connect and interact with databases. It provides a standard interface for connecting to relational databases from Java applications.

### Key Concepts of JDBC:
1.API Definition:

  JDBC is a set of interfaces and classes in the java.sql and javax.sql packages that handle 
  database operations.
  
2.Purpose:

  - Connect Java applications with databases (like MySQL, Oracle, PostgreSQL, etc.)
  
  - Execute SQL queries (SELECT, INSERT, UPDATE, DELETE)
  
  - Retrieve and manipulate results

3.Architecture:
JDBC follows a layered architecture:
   - Application Layer – Your Java program

   - JDBC API Layer – Interfaces like Connection, Statement, ResultSet

   - JDBC Driver Layer – Translates JDBC calls into database-specific calls

   - Database – The target RDBMS (e.g., MySQL)

### Establishing Connection to Database


     
