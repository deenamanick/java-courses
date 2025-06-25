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
   To connect Java to a database, we use JDBC (Java Database Connectivity), which provides          classes and interfaces for communication between Java applications and relational databases      like MySQL, Oracle, etc.
   
### Steps to Establish a Connection
  - Import JDBC Packages

  - Load the JDBC Driver

  - Establish the Connection

  - Create a Statement

  - Execute Queries

  - Close the Connection

### Example:
     import java.sql.Connection;
     import java.sql.DriverManager;
     import java.sql.SQLException;
     public class DBConnect 
     {
        public static void main(String[] args) 
        {
             String url = "jdbc:mysql://localhost:3306/testdb"; // Replace with your DB name
             String username = "root"; // Replace with your username
             String password = "password"; // Replace with your password
             try 
             {
                // Load and register the driver
                Class.forName("com.mysql.cj.jdbc.Driver");
                // Establish the connection
                Connection conn = DriverManager.getConnection(url, username, password);
                System.out.println("Connected to the database!");
                // Always close the connection
                conn.close();
              }
              catch (ClassNotFoundException e)
              {
                  System.out.println(" JDBC Driver not found.");
                  e.printStackTrace();
               } 
               catch (SQLException e) 
               {
                  System.out.println(" Connection failed.");
                  e.printStackTrace();
                }
              }
         }

   ### Statement:
   
   In JDBC, a Statement is used to send SQL queries (like SELECT, INSERT, UPDATE, DELETE) to the    database from a Java program.

   ### Types of Statement:
   
   Statement :           
      Used for simple SQL queries without parameters.

   Preparedtatement :   
      Used for queries with input parameters (faster and safer).

   CallableStatement :  
      Used to execute stored procedures in the database.

   ### 1.Statement :
   
   Use Case: When the SQL is static (no input from the user).
  ### Example :
         import java.sql.*;
         public class StatementExample 
         {
             public static void main(String[] args) 
             {
                  try 
                  {
                     Connection conn = DriverManager.getConnection(
                     "jdbc:mysql://localhost:3306/testdb", "root", "password");
                     // Create Statement
                     Statement stmt = conn.createStatement();
                     // Execute Query
                     ResultSet rs = stmt.executeQuery("SELECT * FROM students");
                     while (rs.next()) 
                     {
                       System.out.println("ID: " + rs.getInt("id") + ", Name: " + rs.getString("name"));
                     }
                     rs.close();
                     stmt.close();
                     conn.close();
                    }
                    catch (Exception e) 
                    {
                       e.printStackTrace();
                    }
                }
            }

  ### 2.PreparedStatement :
  
  Use Case: When the query needs user input or parameters.
  
### Example:
       import java.sql.*;
       public class PreparedStatementExample 
       {
          public static void main(String[] args) 
          {
              try 
              {
                  Connection conn = DriverManager.getConnection(
                      "jdbc:mysql://localhost:3306/testdb", "root", "password");
                  // Create PreparedStatement
                  String query = "SELECT * FROM students WHERE id = ?";
                  PreparedStatement pstmt = conn.prepareStatement(query);
                  pstmt.setInt(1, 2); // setting ID = 2
                  ResultSet rs = pstmt.executeQuery();
                  while (rs.next()) 
                  {
                     System.out.println("Name: " + rs.getString("name"));
                  }
                  rs.close();
                  pstmt.close();
                  conn.close();
                } 
                catch (Exception e) 
                {
                    e.printStackTrace();
                 }
             }
          }
### PreparedStatement Benefits:

- Precompiled for better performance.

- Safe from SQL injection.

- Allows setting parameters using:

    - setInt(index, value)

    - setString(index, value)

    - setDate(), setDouble(), etc.
      
### 3.CallableStatement (Used for Stored Procedures)

Use Case: When the logic is stored inside the database as a stored

### Example Procedure in MySQL:
     DELIMITER //
     CREATE PROCEDURE GetStudentById(IN sid INT)
     BEGIN
        SELECT * FROM students WHERE id = sid;
     END //
     DELIMITER ;
     
### Example:
      import java.sql.*;
      public class CallableStatementExample
      {
          public static void main(String[] args) 
          {
             try
             {
                Connection conn = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/testdb", "root", "password");
               // Call stored procedure
               CallableStatement cstmt = conn.prepareCall("{call GetStudentById(?)}");
               cstmt.setInt(1, 2); // ID = 2
               ResultSet rs = cstmt.executeQuery();
               while (rs.next()) 
               {
                System.out.println("Name: " + rs.getString("name"));
               }
               rs.close();
               cstmt.close();
               conn.close();
            } 
            catch (Exception e) 
            {
               e.printStackTrace();
            }
         }
      }






























   
