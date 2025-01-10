---
theme: seriph
background: https://cover.sli.dev
title: Database and SQL Fundamental | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Database and SQL Fundamental | QAJune2024 Automation with Java
author: Mahmudul Hasan Masum
drawings:
  persist: false
transition: slide-left
mdc: true
lineNumbers: true
fonts:
  sans: Outfit
  weights: '200,400,600'
  serif: Robot Slab
  mono: Fira Code
hideInToc: true
addons:
  - ../addons/mhmasum0
---

# Database and SQL Fundamental

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/mhmasum0/qa-june-2024-automation-with-java-slides" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
hideInToc: true
---

# Agenda
<Toc />

---
layout: center
---

# Data VS Information

| Data                                                   | Information                                                                     |
|--------------------------------------------------------|---------------------------------------------------------------------------------|
| Data refers to raw facts that have no specific meaning | Information refers to processed data that has a purpose and meaning             |
| The data is independent of the information             | Information is dependent on data                                                | 
| Data or raw data is not enough to make a decision      | The information is sufficient to help make a decision in the respective context | 

---
layout: center
---

# Database

> A database is a collection of organized data, information, and records that can be easily accessed and managed. It is a structured repository that stores data in a way that allows for efficient retrieval and manipulation.

<br>
<B>Key Characteristics:</B><br>
<HL className="text-rose-700">Organized Data:</HL> Data is stored in a structured format, making it easy to access and manage.<br>
<HL className="text-rose-700">Collection of Records:</HL> A database can contain multiple records, each with its own set of attributes.<br>
<HL className="text-rose-700">Easy Access and Management:</HL> Data can be easily retrieved, updated, and manipulated using database management systems (DBMS).

---
layout: center
---

# Examples of Databases

- <HL className="text-rose-700">Personal Database::</HL> A list of phone numbers, addresses, or personal contacts.<br>
- <HL className="text-rose-700">Business Database:</HL> A collection of customer information, sales records, or inventory data.<br>
- <HL className="text-rose-700">Educational Database:</HL> A repository of student records, course information, or exam results.<br>

---
layout: center
---

# Common Database Types

- <HL className="text-rose-700">Relational Databases:</HL> Organizes data into tables with rows and columns.<br> Example: MySQL, PostgreSQL, Oracle.<br>
- <HL className="text-rose-700">NoSQL Databases:</HL> Stores data in a non-tabular format, such as key-value pairs or document stores.<br> Example: MongoDB, Cassandra, Redis.<br>
- <HL className="text-rose-700">Key-Value Database:</HL> Stores data as key-value pairs.<br> Example: Redis, DynamoDB.<br>

---
layout: center
---

# Components of a Databases

- <HL className="text-rose-700">Tables:</HL> A collection of related data, organized into rows and columns.<br>
- <HL className="text-rose-700">Record: :</HL> A single entry in a table, representing a single instance of data.<br>
- <HL className="text-rose-700">Fields:</HL> A single column in a table, containing a specific piece of data for each record.<br>

| Roll No | Name   | Age | GPA |
|---------|--------|-----|-----|
| 101     | Alice  | 20  | 3.5 |
| 102     | Bob    | 21  | 3.2 |

---
layout: center
---

# Common types of keys in a database

<HL className="text-orange-300">Primary Key:</HL> A unique identifier for each record in a table.<br>
- Uniquely identifies each record.
- No duplicate values or NULL values allowed.
- Typically indexed for faster search and retrieval.
- Example: Employee ID in an Employees table.

<HL className="text-orange-300">Foreign Key:</HL> A field in a table that refers to the primary key of another table.<br>
- Establishes relationships between tables.
- Can contain NULL values and duplicate values.
- Used to link data across tables.
- Example: Order ID in an Orders table referencing the Customer ID in a Customers table.

---
layout: center
---

# Download and Install MySQL

- Download XAMPP from: [apachefriends.org](https://www.apachefriends.org/download.html)
- Install XAMPP on your computer.
- Start the Apache and MySQL services.
- Open phpMyAdmin in your browser: [http://localhost/phpmyadmin/](http://localhost/phpmyadmin/)

---
layout: center
---

# Execute SQL Queries

- Open phpMyAdmin in your browser.
- Click on the SQL tab.
- `SHOW DATABASES;` to list all databases.
- `CREATE DATABASE mydatabase;` to create a new database.
- `USE mydatabase;` to switch to the new database.
- `DROP DATABASE mydatabase;` to delete the database.

---
layout: center
---

# Data Types in MySQL

<HL className="text-orange-300">Numeric Data Types:</HL> INT, FLOAT, DOUBLE, DECIMAL.<br>
- <B>INT:</B> Integer values. <br>`CREATE TABLE employees (id INT PRIMARY KEY, salary INT);`
- <B>DECIMAL:</B> Fixed-point numbers. <br>`CREATE TABLE products (price DECIMAL(10, 2));`
- <B>FLOAT:</B> An approximate floating-point number.<br>`CREATE TABLE products (price FLOAT);`

<HL className="text-orange-300">Date and Time Data Types:</HL> DATE, TIME, DATETIME.<br>
- <B>DATE:</B> Date values. Example format 'YYYY-MM-DD' <br>`CREATE TABLE employees (dob DATE);`
- <B>DATETIME:</B> Date and time values. Example format 'YYYY-MM-DD HH:MM:SS'<br>`CREATE TABLE employees (created_at DATETIME);`

<HL className="text-orange-300">String Data Types:</HL> CHAR, VARCHAR, TEXT.<br>
- <B>VARCHAR:</B> Variable-length string. <br>`CREATE TABLE users (username VARCHAR(50), email VARCHAR(100));`

---
layout: center
---

# SQL Commands

<HL className="text-orange-300">DDL (Data Definition Language)</HL><br>
- <B>CREATE TABLE:</B> Creates a new database, table, index, or view <br>
- <B>ALTER TABLE:</B> Modifies an existing database, table, or view<br>
- <B>DROP TABLE:</B> Deletes a database, table, index, or view<br>
- <B>TRUNCATE TABLE:</B> Removes all records from a table, but keeps the table structure<br>

<HL className="text-orange-300">DML (Data Manipulation Language):</HL> <br> Example: INSERT, UPDATE, DELETE<br>
<HL className="text-orange-300">DQL (Data Query Language):</HL> <br> Example: SELECT, SELECT DISTINCT, SELECT INTO<br>

---
layout: center
---

# Create a Table in MySQL

```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  class INT,
  section CHAR(1),
  fees INT,
  house VARCHAR(20)
);
```

---
layout: center
---

# Insert Data into a Table

```sql
INSERT INTO students (id, name, class, section, fees, house) VALUES
 (101, 'Alice', 10, 'A', 5000, 'Red'),
 (102, 'Bob', 11, 'B', 6000, 'Blue'),
 (103, 'Charlie', 12, 'C', 7000, 'Green'),
 (104, 'David', 10, 'A', 5500, 'Yellow'),
 (105, 'Emma', 11, 'B', 5000, 'Red'),
 (106, 'Fiona', 10, 'C', 6200, 'Green'),
 (107, 'George', 12, 'A', 6500, 'Blue'),
 (108, 'Hannah', 11, 'C', 7000, 'Red'),
 (109, 'Ivy', 12, 'B', 6000, 'Yellow'),
 (110, 'Jack', 10, 'B', 5800, 'Green'),
 (111, 'Kara', 11, 'A', 5500, 'Blue'),
 (112, 'Liam', 12, 'C', 7500, 'Red'),
 (113, 'Mason', 10, 'A', 5000, 'Yellow'),
 (114, 'Nora', 11, 'B', 5300, 'Green'),
 (115, 'Oscar', 12, 'C', 6400, 'Blue'),
 (116, 'Paula', 10, 'B', 5100, 'Red'),
 (117, 'Quinn', 11, 'A', 7000, 'Yellow'),
 (118, 'Rachel', 12, 'B', 6900, 'Green'),
 (119, 'Steve', 10, 'C', 4800, 'Blue'),
 (120, 'Tina', 11, 'A', 5600, 'Red');
```

# Rename a Table and Drop a Table

```sql
RENAME TABLE students TO new_students;
DROP TABLE new_students;
```

---
layout: center
---

# Select Data from a Table

<B> Example 1: Select Specific Columns</B>
```sql
SELECT name, class, fees FROM students;
```
This query selects the name, class, and fees columns from the students table.<br>

<B> Example 2: Select All Columns</B>
```sql
SELECT * FROM students;
```
This query selects all columns from the students table.<br>

<B> Example 3: Select with WHERE Clause</B>
```sql
SELECT * FROM students WHERE class = 10;
```
This query selects all columns from the students table where the class is 10.<br>

<B> Example 4: Select with AND Operator</B>
```sql
SELECT * FROM students WHERE class = 10 AND section = 'A';
```
This query selects all columns from the students table where the class is 10 and the section is 'A'.<br>

---
layout: center
---

# Select Query

<B> Example 5: Select with OR Operator</B>
```sql
SELECT * FROM students WHERE class = 12 OR fees > 2500;
```
This query selects all columns from the students table where the class is 12 or the fees are greater than 2500.


<B> Example 6: Select with ORDER BY</B>
```sql
SELECT * FROM students ORDER BY fees DESC;
```
This query selects all columns from the students table and orders the result by the fees column in descending order.

<B> Example 7: Select with DISTINCT Clause</B>
```sql
SELECT DISTINCT Class FROM students;
```
This query selects all distinct values from the class column in students table.<br>

<B> Example 8: Select with LIMIT Clause</B>
```sql
SELECT * FROM students LIMIT 5;
```
This query selects all columns from the students table and limits the result to the first 5 rows.

---
layout: center
---

# More Select Query

<B> Example 9: Select with GROUP BY Clause</B>
```sql
SELECT class, AVG(fees) FROM students GROUP BY class;
```
This query selects the class and the average fees from the students table, grouped by the class column.

<B> Example 10: Select with HAVING Clause</B>
```sql
SELECT class, AVG(fees) FROM students GROUP BY class HAVING AVG(fees) > 2500;
```
This query selects the class and the average fees from the students table, grouped by the class column, and filters the result to only include groups where the average fees are greater than 2500.

---
layout: center
---

# Update and Delete Data

<B> Update Query</B>
```sql
UPDATE students SET fees = 3000 WHERE name = 'Anu Jain';
```
This query updates the fees column in the students table to 3000 where the name is 'Anu Jain'.

<B> Delete Query</B>
```sql
DELETE FROM students WHERE name = 'Mohit Sharma';
```
This query deletes the record from the students table where the name is 'Mohit Sharma'.

---
layout: center
---

# Database Testing

<HL>Purpose of Database Testing:</HL>

- To ensure that the database operates correctly and efficiently.
- To verify data integrity, data consistency, and data accuracy.
- To ensure that CRUD operations (Create, Read, Update, Delete) work as expected.
- To check for performance issues like indexing and query optimization.

---
layout: center
---

# Key Aspects of Database Testing

- <HL className="text-rose-700">Schema Testing:</HL> Verifying that the database schema (tables, columns, indexes, etc.) is set up correctly.
- <HL className="text-rose-700">Data Integrity Testing:</HL> Ensuring that data remains consistent and accurate across operations.
- <HL className="text-rose-700">Performance Testing:</HL> Checking how the database performs under load.
- <HL className="text-rose-700">Security Testing:</HL> Ensuring that the database is secure from unauthorized access and vulnerabilities.

---
layout: center
---

# Adding Dependency


Link: [https://mvnrepository.com/artifact/com.mysql/mysql-connector-j](https://mvnrepository.com/artifact/com.mysql/mysql-connector-j)
```xml
<dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>9.1.0</version>
</dependency>
```

---
layout: center
---

# Database Connection

```java
Connection connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/nexxvali", "root","");
System.out.println("Connected to MySQL Database");

Statement statement = connection.createStatement();
System.out.println("Statement created");
```

---
layout: center
---

# Execute SQL Query

```java
Connection connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/nexxvali", "root","");
System.out.println("Connected to MySQL Database");

Statement smt = connection.createStatement();
System.out.println("Statement created");

ResultSet rs=smt.executeQuery("select * from students");
int id;
String name;
while (rs.next()) {
    id = rs.getInt("id");
    name = rs.getString("name").trim();
    System.out.println("ID : " + id + " Name : " + name);
}
rs.close();
smt.close();
connection.close();
```

---
layout: center
--- 

# Update Query

<B> Update Query</B>
```java
String updateQuery = "UPDATE students SET fees = 3000 WHERE name = 'Alice'";
int rowsAffected = smt.executeUpdate(updateQuery);
System.out.println("Rows Affected: " + rowsAffected);
```

---
layout: center
---

# Database Testing with TestNG

```java
public class DatabaseTest {
    Connection connection;
    Statement statement;

    @BeforeTest
    public void setup() throws SQLException {
        try {
            connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/nexxvali", "root", "");
            // Create statement
            statement = connection.createStatement();
        } catch (Exception e) {
            e.printStackTrace();
            Assert.fail("Database connection setup failed!");
        }
    }

    @AfterClass
    public void tearDown() {
        try {
            if (statement != null) statement.close();
            if (connection != null) connection.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

---
layout: center
---

# Database Testing with TestNG : Example

```java
@Test(priority = 1)
public void testInsert() {
    try {
        String query = "INSERT INTO students (id, name, class) VALUES (501, 'TestUser', 10)";
        int rowsInserted = statement.executeUpdate(query);
        Assert.assertEquals(rowsInserted, 1, "Insert operation failed!");
    } catch (SQLException e) {
        e.printStackTrace();
        Assert.fail("Insert query execution failed!");
    }
}
@Test(priority = 2, dependsOnMethods = "testInsert")
public void testSelect() {
    try {
        String query = "SELECT * FROM students WHERE id = 501";
        ResultSet resultSet = statement.executeQuery(query);
        Assert.assertTrue(resultSet.next(), "Record not found after insert!");
        Assert.assertEquals(resultSet.getString("name").trim(), "TestUser", "Name mismatch!");
        Assert.assertEquals(resultSet.getInt("class"), 10, "Class mismatch!");
        resultSet.close();
    } catch (SQLException e) {
        e.printStackTrace();
        Assert.fail("Select query execution failed!");
    }
}
```



---
src: ../../pages/common/end.md
---