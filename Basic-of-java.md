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

  <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/80eb3bb3-df78-4c21-89ff-59793605beb1" />


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

### ServletRequest & ServletResponse:
## ServletRequest Interface:
Purpose:

Used to get information from the client (e.g., form data, headers, parameters).

package:

javax.servlet.ServletRequest
###  Common Methods of `ServletRequest`

| Method                                      | Description                                           |
|--------------------------------------------|-------------------------------------------------------|
| `String getParameter(String name)`         | Returns the value of a request parameter.            |
| `Enumeration<String> getParameterNames()`  | Returns an enumeration of all parameter names.       |
| `String[] getParameterValues(String name)` | Returns multiple values for a parameter (e.g., checkboxes). |
| `String getRemoteAddr()`                   | Returns IP address of the client.                    |
| `int getContentLength()`                   | Returns the length of the request body.              |
| `String getCharacterEncoding()`            | Returns the character encoding of the request.       |
| `InputStream getInputStream()`             | Gets binary data from the client.                    |
| `BufferedReader getReader()`               | Gets character data from the client.                 |

### ServletResponse Interface
Purpose:

Used to send data back to the client, like HTML, JSON, plain text, etc.

Package:

javax.servlet.ServletResponse

###  Common Methods of `ServletResponse`

| Method                                     | Description                                                             |
|-------------------------------------------|-------------------------------------------------------------------------|
| `PrintWriter getWriter()`                 | Sends character text to the client.                                     |
| `ServletOutputStream getOutputStream()`   | Sends binary data to the client.                                        |
| `void setContentType(String type)`        | Sets MIME type of the response (e.g., `text/html`, `application/json`). |
| `void setCharacterEncoding(String charset)` | Sets response encoding (e.g., `UTF-8`).                                |
| `void setContentLength(int length)`       | Sets the content length of the response.                                |

### ServletConfig
### What is ServletConfig?
ServletConfig is an interface in the javax.servlet package. It is used to pass initialization parameters to a particular servlet.

When a servlet is initialized by the servlet container (like Tomcat), the container creates a ServletConfig object and passes it to the servlet’s init() method.

### Why is it needed?
Sometimes, we want to pass custom parameters to a servlet like:
- Database connection info
- Author name
- Company details
- API keys, etc.
Instead of hardcoding these in Java code, we can put them in the web.xml file and access them using ServletConfig.

### When is ServletConfig used?

- When servlet-specific configuration is needed.
- At the time of servlet initialization (init() method).

### Methods in ServletConfig

| Method | Description |
|--------|-------------|
| `String getServletName()` | Returns the name of the servlet |
| `String getInitParameter(String name)` | Returns the value of a specific initialization parameter |
| `Enumeration<String> getInitParameterNames()` | Returns all parameter names |
| `ServletContext getServletContext()` | Returns the `ServletContext` object (shared across all servlets) |

### Difference between ServletConfig and ServletContext

| Feature       | ServletConfig                            | ServletContext                         |
|---------------|-------------------------------------------|----------------------------------------|
| Scope         | One servlet                              | All servlets                           |
| Purpose       | Init parameters for specific servlet      | App-wide parameters                    |
| Access        | Inside `init()` or via `getServletConfig()` | Via `getServletContext()`             |
| Defined in    | Inside `<servlet>` tag                    | Inside `<context-param>` tag           |
| Example Use   | API key for one servlet                   | Site-wide branding name                |

### ServletContext

###  What is ServletContext?
ServletContext is an interface in the javax.servlet package that provides a way for servlets to:
- Access shared resources
- Communicate with other servlets
- Store global application data
It represents the entire web application running in a single Java EE web server (like Tomcat). It is shared across all servlets and JSPs in the application.

###  Why is it needed?
When you want to:
- Store global parameters (e.g., app name, admin email)
- Share data across multiple servlets
- Access resources (HTML, images, files) in your app
- Get the absolute path to your resources (for file I/O)
- Log messages to the server log
- 
### When is ServletContext created?
It is created once by the servlet container when the web application starts, and it is destroyed when the application shuts down.

### How to Get ServletContext?
1. Inside a Servlet:
   ServletContext context = getServletContext();
   
2. From ServletConfig:
    ServletContext context = config.getServletContext();

### Methods in ServletContext

| Method | Description |
|--------|-------------|
| `getInitParameter(String name)` | Gets context-wide init parameter (from `web.xml`) |
| `getInitParameterNames()` | Gets all global init parameter names |
| `getRealPath(String path)` | Gets absolute file system path of a resource |
| `getContextPath()` | Returns the base URL path of the web app |
| `getMimeType(String file)` | Returns MIME type of a file |
| `getAttribute(String name)` | Gets an attribute (global variable) |
| `setAttribute(String name, Object obj)` | Sets a global attribute |
| `removeAttribute(String name)` | Removes a global attribute |
| `getServerInfo()` | Returns server information |
| `log(String message)` | Logs a message to server log |

### Example: Define context-param in web.xml

    <context-param>
       <param-name>appName</param-name>
       <param-value>Student Portal</param-value>
    </context-param>
    
### Servlet Code to Access ServletContext:

         public class MyServlet extends HttpServlet 
         {
              public void doGet(HttpServletRequest request, HttpServletResponse response) throws IOException
              {
                 ServletContext context = getServletContext();
                 // Access init parameter
                 String appName = context.getInitParameter("appName");
                // Set a global attribute
                 context.setAttribute("username", "raja");
                 // Get the real path of a file in the app
                String filePath = context.getRealPath("/WEB-INF/config.properties");
                // Log a message
                context.log("App name accessed: " + appName);
                PrintWriter out = response.getWriter();
                out.println("Welcome to " + appName);
              }
          }
          
### HttpServlet

###  What is HttpServlet? 

The HttpServlet is a class in Java EE (Jakarta EE) that is part of the Servlet API used to create web applications.

It is used to handle HTTP requests and responses — the core of how the Java-based web server communicates with web browsers or other HTTP clients.

### Basic Lifecycle of HttpServlet:

1.Loading: Servlet class is loaded by the container.
2.Instantiation: An instance is created.
3.Initialization: init() is called.
4.Request Handling:
  - Each HTTP request is handled in a separate thread
  - Container calls service() method which dispatches to doGet(), doPost(), etc.
5.Destruction: destroy() is called when the servlet is being removed.

###  Example Code:

        import java.io.*;
        import javax.servlet.*;
        import javax.servlet.http.*;
        public class MyServlet extends HttpServlet 
        {
            public void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException 
            {
              response.setContentType("text/html");
              PrintWriter out = response.getWriter();
              out.println("<h1>Hello from HttpServlet!</h1>");
            }
            public void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException 
            {
               String name = request.getParameter("username");
               response.setContentType("text/html");
               PrintWriter out = response.getWriter();
               out.println("<h1>Welcome " + name + "</h1>");
            }
          }
          
  ### web.xml Mapping

        <servlet>
            <servlet-name>MyServlet</servlet-name>
            <servlet-class>MyServlet</servlet-class>
       </servlet>
       <servlet-mapping>
          <servlet-name>MyServlet</servlet-name>
          <url-pattern>/hello</url-pattern>
     </servlet-mapping>

### Advantages:

   - Part of standard Java EE (widely supported)
   - Simple for small apps
   - Efficient for low-level web handling
   - 
### HttpServletRequest & HttpServletResponse

### HttpServletRequest:

HttpServletRequest is an interface in the Java Servlet API that represents the client's HTTP request.
It allows a servlet to read form data, query parameters, headers, cookies, and session information.
Common methods include getParameter(), getHeader(), getMethod(), and getSession().
It provides access to both URL details and request body content.
Used in doGet(), doPost(), etc., to handle incoming requests in servlets.
It is passed automatically to servlets by the servlet container (like Tomcat).

 ### Purpose:
Used to read client request data like:

- Form inputs
- Query parameters
- Request headers
- Cookies
- HTTP method
- Path info
- Session details
- 
### Methods

| Method                   | Description                                            |
|--------------------------|--------------------------------------------------------|
| `getParameter(String name)`     | Gets a request parameter (e.g., form field).         |
| `getParameterNames()`           | Returns an enumeration of all parameter names.       |
| `getHeader(String name)`        | Gets the value of a specific HTTP header.            |
| `getCookies()`                  | Returns an array of cookies sent by the client.      |
| `getMethod()`                   | Returns the HTTP method (GET, POST, etc.).           |
| `getRequestURI()`               | Returns the requested URI.                           |
| `getRequestURL()`               | Returns the full URL.                                |
| `getContextPath()`              | Gets the web application’s context path.             |
| `getRemoteAddr()`               | Returns the IP address of the client.                |
| `getSession()`                  | Returns the `HttpSession` object.                    |
| `getInputStream()`              | Reads binary request body (e.g., file upload).       |
| `getReader()`                   | Reads character request body (e.g., JSON payload).   |

### HttpServletResponse:

HttpServletResponse is an interface in the Java Servlet API used to send data back to the client.
It allows servlets to set response content type, status codes, headers, and cookies.
Common methods include getWriter(), setContentType(), sendRedirect(), and addCookie().
It supports sending both character and binary data using output streams.
Used in doGet(), doPost(), etc., to generate HTTP responses.
The servlet container provides this object to the servlet automatically.

 Purpose:
 Used to send data back to the client, like:

- HTML content
- JSON data
- File downloads
- Status codes
- Redirects
- Cookies

### Methods

  | Method                             | Description                                                  |
|------------------------------------|--------------------------------------------------------------|
| `setContentType(String type)`      | Sets the MIME type (e.g., `text/html`, `application/json`).  |
| `getWriter()`                      | Returns `PrintWriter` to send character data.                |
| `getOutputStream()`                | Sends binary data (e.g., file, image).                       |
| `sendRedirect(String url)`         | Redirects the client to another URL.                         |
| `setStatus(int sc)`                | Sets the HTTP status code (e.g., 200, 404).                  |
| `addCookie(Cookie cookie)`         | Adds a cookie to the response.                               |
| `setHeader(String name, String value)` | Sets a custom response header.                            |

### HttpServletRequest vs HttpServletResponse

| Feature                 | `HttpServletRequest`                           | `HttpServletResponse`                               |
|------------------------|-----------------------------------------------|-----------------------------------------------------|
| Represents              | Client request                                 | Server response                                     |
| Read or Write?          | Read from client                               | Write to client                                     |
| Key Methods             | `getParameter()`, `getHeader()`, `getMethod()` | `getWriter()`, `setContentType()`, `sendRedirect()` |
| Session Handling        | `getSession()`                                 | `addCookie()`                                       |
| Stream Access           | `getInputStream()`, `getReader()`              | `getOutputStream()`, `getWriter()`                  |
| Handles Content Type    | No                                             | Yes, `setContentType()`                             |
| Response Status Control | No                                             | Yes, `setStatus()`, `sendError()`                   |

### HTML to Servlet Communication:

It is the process by which form data or user input from an HTML page is sent to a Java Servlet on the server, typically using HTTP methods like GET or POST.
This is the basis for dynamic web applications in Java using Java EE / Jakarta EE

### Workflow Diagram

<img width="305" height="165" alt="image" src="https://github.com/user-attachments/assets/3efe1048-f5c7-4053-9a7e-9a0037f005fe" />


[User fills HTML form] 
          ↓
[Submits form via HTTP (GET or POST)]
          ↓
[Web server (e.g., Tomcat) receives request]
          ↓
[Servlet handles it via doGet() or doPost()]
          ↓
[Servlet processes input and returns response (HTML, JSON, etc.)]

### Key Components Involved:

| Component           | Role                                                   |
|---------------------|--------------------------------------------------------|
| HTML Form           | Collects input from the user                           |
| Servlet             | Handles request, processes input, sends back response  |
| Web Server          | Hosts the servlet (e.g., Apache Tomcat)                |
| Web.xml / @WebServlet | Maps URL to servlet                                 |

### Example:

### HTML Form (Frontend)

        <!DOCTYPE html>
        <html>
          <head><title>Login Form</title></head>
          <body>
            <form action="LoginServlet" method="post">
            Username: <input type="text" name="username" /><br />
            Password: <input type="password" name="password" /><br />
            <input type="submit" value="Login" />
          </form>
        </body>
     </html>

  ### Servlet (Backend Java Code)

        import java.io.*;
        import javax.servlet.*;
        import javax.servlet.http.*;
        @WebServlet("/LoginServlet")  // URL mapping
        public class LoginServlet extends HttpServlet 
        {
            protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException 
            {
               String user = request.getParameter("username");
               String pass = request.getParameter("password");
               response.setContentType("text/html");
               PrintWriter out = response.getWriter();
               if ("admin".equals(user) && "1234".equals(pass)) 
               {
                   out.println("<h2>Login successful!</h2>");
               } 
               else 
               {
                  out.println("<h2>Invalid credentials!</h2>");
               }
             }
         }
### Explanation of Key Servlet Code

      | Method                          | Purpose                                          |
|---------------------------------|--------------------------------------------------|
| `getParameter("name")`          | Retrieves the form field value from request      |
| `setContentType("text/html")`   | Sets MIME type for response                      |
| `getWriter()`                   | Returns a writer to send HTML as response        |
| `@WebServlet("/...")`           | Maps a URL to this servlet (annotation-based)    |

### Servlet to DataBase Communication

It is the process where a Java Servlet connects to a relational database (e.g., MySQL, Oracle, PostgreSQL) using JDBC (Java Database Connectivity) to perform CRUD operations as part of a web application.

### Workflow Diagram

<img width="512" height="163" alt="image" src="https://github.com/user-attachments/assets/818e7d41-fc58-43ef-940d-d8a40d0933e0" />


[User submits HTML form]
         ↓
[Servlet receives request]
         ↓
[Servlet reads input using HttpServletRequest]
         ↓
[Servlet uses JDBC to connect to the database]
         ↓
[Servlet executes SQL (INSERT, SELECT, etc.)]
         ↓
[Result sent back using HttpServletResponse]

### Key Components

| Component           | Description                                                  |
|---------------------|--------------------------------------------------------------|
| HTML Form           | Collects user input                                          |
| Servlet             | Handles request, performs DB logic                           |
| JDBC Driver         | Java library to interact with a specific database            |
| Database (e.g., MySQL) | Stores the data                                           |
| Connection URL      | Defines DB connection settings (host, port, user, password)  |

###  Example:

       <form action="RegisterServlet" method="post">
       Name: <input type="text" name="name" /><br />
      Email: <input type="text" name="email" /><br />
      <input type="submit" value="Register" />
      </form>

### Servlet Code

       import java.io.*;
       import java.sql.*;
       import javax.servlet.*;
       import javax.servlet.http.*;
       import javax.servlet.annotation.WebServlet;
       @WebServlet("/RegisterServlet")
       public class RegisterServlet extends HttpServlet 
       {
           protected void doPost(HttpServletRequest request, HttpServletResponse response)
           throws ServletException, IOException 
           {
              String name = request.getParameter("name");
              String email = request.getParameter("email");
              response.setContentType("text/html");
              PrintWriter out = response.getWriter();
              try 
              {
               // 1. Load JDBC driver
               Class.forName("com.mysql.cj.jdbc.Driver");
               // 2. Establish connection
               Connection con = DriverManager.getConnection(
               "jdbc:mysql://localhost:3306/mydb", "root", "password");
               // 3. Create SQL query
               String query = "INSERT INTO users (name, email) VALUES (?, ?)";
               PreparedStatement pst = con.prepareStatement(query);
               pst.setString(1, name);
               pst.setString(2, email);
              // 4. Execute update
              int row = pst.executeUpdate();
              if (row > 0) 
              {
                out.println("<h2>Registration Successful!</h2>");
              }
              // 5. Close resources
              pst.close();
              con.close();
            } 
            catch (Exception e) 
            {
            e.printStackTrace();
            out.println("<h2>Error: " + e.getMessage() + "</h2>");
           }
        }
      }

### Database Table (MySQL)

       CREATE DATABASE mydb;
      USE mydb;
      CREATE TABLE users (
      id INT AUTO_INCREMENT PRIMARY KEY,
      name VARCHAR(100),
      email VARCHAR(100)
     );

### JDBC Driver Dependency (for Maven projects)

Add to pom.xml:

    <dependency>
       <groupId>mysql</groupId>
       <artifactId>mysql-connector-j</artifactId>
       <version>8.0.33</version>
    </dependency>






























   
