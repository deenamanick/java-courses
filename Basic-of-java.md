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

 ### ResultSet Interface & Metadata
 
      In JDBC (Java Database Connectivity), the ResultSet interface and its metadata play a crucial role when interacting with databases. 

### What is ResultSet?

      - ResultSet is an interface in the java.sql package.

      - It represents the result of a database query (usually a SELECT statement).

      - It is returned by executing a query using Statement, PreparedStatement, or CallableStatement.

###  How to Get a ResultSet?

     Connection con = DriverManager.getConnection(url, user, password);
     Statement stmt = con.createStatement();
     ResultSet rs = stmt.executeQuery("SELECT * FROM employees");
     
### Navigating the ResultSet

    By default, ResultSet is forward-only and read-only. You can move through it using:
    This table summarizes the key navigation methods provided by the JDBC `ResultSet` interface.

| Method             | Description                                 |
|--------------------|---------------------------------------------|
| `rs.next()`        | Moves to the next row                       |
| `rs.previous()`    | Moves to the previous row (scrollable only) |
| `rs.first()`       | Moves to the first row                      |
| `rs.last()`        | Moves to the last row                       |
| `rs.absolute(n)`   | Moves to the nth row                        |
| `rs.beforeFirst()` | Moves to the position before first          |

### Reading Data from ResultSet

   You access data column by column using getters:
   
   int id = rs.getInt("id");
   String name = rs.getString("name");
  double salary = rs.getDouble("salary");

  index:
  Column indexes start from 1 (not 0).
  
  int id = rs.getInt(1); // first column

### Common Getter Methods:

      This table lists commonly used `ResultSet` getter methods and the data types they return.

| Method           | Returns Data Type   |
|------------------|---------------------|
| `getInt()`       | int                 |
| `getString()`    | String              |
| `getDouble()`    | double              |
| `getBoolean()`   | boolean             |
| `getDate()`      | java.sql.Date       |
| `getTimestamp()` | java.sql.Timestamp  |

### What is ResultSetMetaData?
   It gives information about the structure of the ResultSet, like:

   - Number of columns

   - Column names

   - Column types

   - Table names, etc.

You get metadata from a ResultSet using:

 ResultSetMetaData rsmd = rs.getMetaData();

### Common ResultSetMetaData Methods:

    This table lists important methods of the `ResultSetMetaData` interface and what they do.

| Method                          | Description                          |
|----------------------------------|--------------------------------------|
| `getColumnCount()`              | Returns number of columns            |
| `getColumnName(int column)`     | Returns name of the specified column |
| `getColumnTypeName(int column)` | Returns SQL type of the column       |
| `getTableName(int column)`      | Returns table name (if available)    |
| `isNullable(int column)`        | Checks if column allows null         |
| `isAutoIncrement(int column)`   | Checks if column is auto-increment   |

### Example:

     import java.sql.*;
     public class ResultSetDemo 
     {
         public static void main(String[] args) 
         {
            String url = "jdbc:mysql://localhost:3306/testdb";
            String user = "root";
            String password = "your_password";
            try (Connection con = DriverManager.getConnection(url, user, password);
            Statement stmt = con.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM employees")) {

            ResultSetMetaData rsmd = rs.getMetaData();
            int columnCount = rsmd.getColumnCount();

            // Print column names
            for (int i = 1; i <= columnCount; i++) 
            {
                System.out.print(rsmd.getColumnName(i) + "\t");
            }
            System.out.println();

            // Print row data
            while (rs.next()) 
            {
                for (int i = 1; i <= columnCount; i++) 
                {
                    System.out.print(rs.getString(i) + "\t");
                }
                System.out.println();
            }
            } 
            catch (SQLException e) 
            {
            e.printStackTrace();
         }
      }
    }
    
### Output:

   | id | name  | salary |
   |----|-------|--------|
   | 1  | Alice | 50000  |
   | 2  | Bob   | 60000  |
   
###  Types of ResultSet:

| Type                      | Description                                |
|---------------------------|--------------------------------------------|
| `TYPE_FORWARD_ONLY`       | Only forward movement (default)            |
| `TYPE_SCROLL_INSENSITIVE` | Scrollable but not sensitive to DB changes |
| `TYPE_SCROLL_SENSITIVE`   | Scrollable and sensitive to DB changes     |

### ResultSet and ResultSetMetadata:

| Feature        | `ResultSet`                         | `ResultSetMetaData`                   |
|----------------|-------------------------------------|---------------------------------------|
| Purpose        | Access row data from SQL queries    | Access metadata (column info)         |
| Common Methods | `next()`, `getInt()`, `getString()` | `getColumnCount()`, `getColumnName()` |
| Usage          | Loop over results, retrieve values  | Dynamically process result structure  |
| Return Type    | Data per row                        | Info per column                       |

### Batch Updates 

    Batch Update in JDBC allows you to group multiple SQL commands and execute them as a single batch, reducing database round-trips and improving performance.
    
###   When to Use Batch Updates?  

     - Inserting multiple rows
     - Updating multiple records
     - Deleting many records
     - Any repeated DML operations

### Steps to Perform Batch Update

    - Create a Connection
    - Disable auto-commit (optional but recommended)
    - Use addBatch() to queue SQL statements
    - Call executeBatch() to execute all
    - Commit the transaction
    
###  Example:

     String query = "INSERT INTO employees (id, name, salary) VALUES (?, ?, ?)";
     PreparedStatement ps = con.prepareStatement(query);
     for (int i = 1; i <= 3; i++) 
     {
          ps.setInt(1, i);
          ps.setString(2, "Employee" + i);
          ps.setDouble(3, 40000 + i * 1000);
          ps.addBatch(); // add to batch
     }

          ps.executeBatch(); // execute all at once
          con.commit();

  ### Output:
  
        Batch insert successful!
        
### Key Methods:

   | Method           | Description                        |
   |------------------|------------------------------------|
   | `addBatch()`     | Adds SQL command to the batch      |
   | `executeBatch()` | Executes all commands in the batch |
   | `clearBatch()`   | Clears all batched commands        |

### What is Transaction Management in JDBC?

     Transaction management in JDBC ensures that a group of SQL operations are executed as a single unit of work. It helps maintain the integrity and consistency of the database.

    A transaction in JDBC begins when a connection is opened and ends when you commit or rollback the changes.

### Why Use Transactions?

    - Ensure atomicity: all operations succeed or none do.

    - Maintain data consistency.

    - Prevent partial updates during errors or failures.

    - Critical in operations like:

         - Money transfers (banking)
         - Order processing (e-commerce)

 ### Transaction Lifecycle in JDBC 

####  1. Connection Initialization:

           - When a JDBC connection is created using DriverManager.getConnection(), auto-commit is enabled by default.
           
           - That means: each individual SQL statement is treated as a transaction and is automatically committed after execution.
#### Example:

          Connection con = DriverManager.getConnection(url, user, pass);
         // By default: con.getAutoCommit() == true

####  2. Begin Transaction (Disable Auto-commit)    

       To manually control the transaction, disable auto-commit:
       
       con.setAutoCommit(false);  // Now transaction is manually managed
       
#### 3. Execute SQL Commands (Transactional Unit)

         This is where your core DML operations (INSERT, UPDATE, DELETE) happen.
         
         PreparedStatement ps1 = con.prepareStatement("UPDATE accounts SET balance = balance - 1000 WHERE id = 1");
         PreparedStatement ps2 = con.prepareStatement("UPDATE accounts SET balance = balance + 1000 WHERE id = 2");
         ps1.executeUpdate();
         ps2.executeUpdate();

        These changes are applied in-memory on the connection and not yet saved to the database until commit() is called.

#### 4. Intermediate Savepoints (Optional)

         You can set savepoints in the middle of a transaction to rollback to a specific point.
         
         Savepoint sp1 = con.setSavepoint("BeforeSecondUpdate");

         Useful in complex transactions when only a part of the work might need to be rolled back.

####  5. Commit the Transaction

         If all SQL statements are successful, commit the transaction:

         con.commit();
#### 6. Rollback Transaction (On Error)
        If any exception occurs during your SQL execution, you should rollback the entire transaction:

        con.rollback();  // Undo all operations since the beginning of transaction
        
        Or rollback to a savepoint:
        
        con.rollback(sp1);  // Undo operations only after sp1

        
####  7. End Transaction (Reset auto-commit)

        After transaction success or failure, always reset the connection state:

        con.setAutoCommit(true); // Optional, but good practice

## Servlet

#### What is a Servlet?

A Servlet is a Java program that runs on a web server and handles client requests (like from a web browser) and sends responses (like HTML or data). It is a key part of building dynamic web applications in Java.

### Servlet Life Cycle:

| Phase               | Method       | Description                                           |
|------------------   |------------  |-------------------------------------------------------|
| 1️⃣ Initialization   | `init()`    | Called once when the servlet is first created.        |
| 2️⃣ Request Handling | `service()` | Called each time the servlet is requested (GET, POST, etc.). |
| 3️⃣ Destruction      | `destroy()` | Called once when the servlet is being removed from memory. |

#### Servlet Architecture:
- Client (Browser) sends a request.

- Web Server (e.g., Tomcat) forwards the request to the servlet.

- Servlet processes the request.

- Servlet sends a response back to the client.

### Use Cases:
- Login/Signup forms

- Displaying dynamic content (user profiles, search results)

- Connecting with databases (JDBC)

- APIs and backend processing

### Example Servlet Code:

    import java.io.*;
    import javax.servlet.*;
    import javax.servlet.http.*;
    public class HelloServlet extends HttpServlet 
    {
            public void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException 
            {
               response.setContentType("text/html");
               PrintWriter out = response.getWriter();
               out.println("<h1>Hello, this is a Servlet!</h1>");
            }
    }

### Developing Servlet in Java

Servlets are Java programs that run on a server and handle client requests, typically HTTP requests. Here’s a step-by-step guide to developing a basic Servlet application using GenericServlet or HttpServlet.


















   
