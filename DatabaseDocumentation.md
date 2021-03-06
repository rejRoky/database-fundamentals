# Database Documentation

### Terminology
1. Relation
2. Schema ( Structure of Database -  Top Row ) 
3. Record (tuples/Rows are Record of Database)
4. Field (Collumns are Field of Database )
5. Primary Key (unique) (Row have No Null(None))
6. Relationship (One Table columns are match another tables columns for Referring)
7. Foreign Key (Two tables columns for Referring both call ) (as Primary Key of another table) (Row have No Null(None))
8. Constrains (Primary Key,Foreign Key) (Not be null)



## SQL
##### Types of Command  of sql

**DDL - Data Definition Language**
1. CREATE (***CREATE DATABASE database_name;***)
2. DROP (***DROP TABLE table_name;***)
3. ALTER *(**ALTER TABLE table_name** DROP COLUMN column_name;)*
4. TRUNCATE ***(TRUNCATE TABLE  table_name;)***
5. RENAME *(ALTER TABLE table_name **RENAME COLUMN old_name TO new_name;**)*
6. COMMENT (__/* multi line comment another comment */__)


**DML - Data Manipulation Language**
1. INSERT *(**INSERT INTO table_name VALUES (value1, value2, value3,..);**)*
2. DELETE *(**DELETE FROM table_name** WHERE some_condition;)*
3. UPDATE *(**UPDATE table_name** SET column1 = value1, column2 = value2,... WHERE condition;)*


**DQL - Data Query Language**
1. SELECT *(**SELECT** * FROM table_name;)*
2. FROM
3. WHERE 


**DCL - Data Control Language**
1. **GRANT** : This command gives users access privileges to the database.
2. **DENY**
3. **REVOKE** : This command withdraws the user's access privileges given by using the GRANT command.


**TCL - Transaction Control Language**
1. **COMMIT**: Commits a Transaction.
2. **ROLLBACK**: Rollbacks a transaction in case of any error occurs.
3. **SAVEPOINT**: Sets a savepoint within a transaction.
4. **SET TRANSACTION**: Specify characteristics for the transaction.



## SQLite - Documentation
 #### DataType of SQLite
 - NULL (None)
 - INTEGER 
 - REAL / FLOAT / NUMERIC
 - TEXT (String)
 - CHAR / VARCHAR 
 - BLOB (Binary Large Object)  (Raw data .. Image/video/....)


### Basic Command Practice 
Create Database 
> .open DATABASE_NAME.db

For Checking Database 
> .databases 

### Create Table
```sql
CREATE TABLE dept (deptno INTEGER PRIMARY KEY NOT NULL UNIQUE, dname TEXT);
```

```sql
CREATE TABLE students (roll INTEGER PRIMARY KEY NOT NULL UNIQUE, name TEXT, city TEXT, deptno INTEGER,FOREIGN KEY (deptno) REFERENCES dept(deptno));
```

### Insert Value  Dept
```sql
INSERT INTO dept VALUES (20, 'CSE');
INSERT INTO dept VALUES (10, 'SE');
INSERT INTO dept VALUES (30, 'EEE');
INSERT INTO dept VALUES (40, 'ETE');
INSERT INTO dept (dname, deptno) VALUES ('Arch', 50);
```

### Query Check
```sql
SELECT * FROM dept;
``` 

### Make Foregin Key Constraint 
> pragma foreign_keys=ON;

### Insert Value  Students
```sql
INSERT INTO students VALUES (1,'Abir', 'Rangpur', 30);
INSERT INTO students VALUES (2,'Abir', 'Rangpur',  10);
INSERT INTO students VALUES (3,'Abir', 'Rangpur', 20);
INSERT INTO students VALUES (4,'Abir', 'Rangpur',  40);
INSERT INTO students VALUES (5,'Maliha', 'Rangpur',  10);
INSERT INTO students VALUES (6,'Trisha', 'Rajbari',  50);
INSERT INTO students VALUES (7,'Roky', 'Dhaka', 10);
```


### Query Check
```sql
SELECT * FROM students;
``` 

### Data Retrieval Language (Query)

#### SELECT and FROM 
/* 
Select is using for filtering Columns
*/
```sql
SELECT * FROM students; 
```
```sql
SELECT * FROM dept;
```

#### DISTINCT (Unique Value)
```sql
SELECT DISTINCT name  FROM students;
```

#### WHERE 
-------------------------------------
- Where is using for filtering Rows
- Condition 
- < > 
- <=>
- =
- AND
- OR
- NOT
- LINK _
- BETWEEN _ AND _
- IN
----------------------------------

```sql
SELECT * FROM students WHERE city = 'Dhaka';
```
```sql
SELECT * FROM students WHERE deptno > 20;
```

#### AND OR NOT 
```sql
SELECT * FROM students WHERE deptno >= 10  AND city = 'Dhaka';
```

#### LIKE 
```sql
SELECT * FROM students WHERE name LIKE 'A%';
```
```sql
SELECT * FROM students WHERE name LIKE '%y';
```

#### Between __ AND __
```sql
SELECT * FROM students WHERE deptno BETWEEN 10 and 30;
```

#### IN
```sql
SELECT * FROM students WHERE deptno IN (30,10);
```

#### ORDER BY
```sql
SELECT * FROM students ORDER BY name;
```
```sql
SELECT * FROM students ORDER BY name DESC;
```

#### JOIN
```sql
SELECT * FROM 
students,dept 
WHERE students.deptno = dept.deptno;
```
```sql
SELECT * FROM students JOIN dept ON students.deptno = dept.deptno;
```
```sql
SELECT * FROM 
students S JOIN dept D 
ON S.deptno = D.deptno;
```

#### GROUP BY
```sql
SELECT city FROM 
students GROUP BY city;
```
```sql
SELECT COUNT(*),city FROM 
students GROUP BY city;
```
```sql
SELECT COUNT(*),city FROM 
students GROUP BY city HAVING COUNT(*)>=3;
```



### Aggregate Functions 

#### COUNT()
```sql
SELECT COUNT(*) FROM students;
```
```sql
SELECT COUNT(name) FROM students;
```

#### MAX()
```sql
SELECT MAX(roll) FROM students;
```
```SQL
SELECT MAX(roll), city FROM students GROUP BY city;
```

#### MIN()
```sql
SELECT MIN(roll) FROM students;
```

#### SUM()
```sql
SELECT SUM(roll) FROM students;
```

#### AVG()
```sql
SELECT AVG(roll) FROM students;
```

### Set Operations

#### Union
```sql
SELECT * FROM students WHERE city = 'Dhaka' UNION SELECT * FROM students WHERE city = 'Rangpur';
```

#### INTERSECT
```sql
SELECT * FROM students WHERE city = 'Dhaka' INTERSECT SELECT * FROM students WHERE city = 'Rangpur';
```
#### EXCEPT
```sql
SELECT * FROM students WHERE city = 'Dhaka' EXCEPT SELECT * FROM students WHERE city = 'Rangpur';
```

### Sub Query
```sql
SELECT * FROM students WHERE city in (SELECT city FROM students WHERE name = 'Maliha');
```


### DML 
#### INSERT
```sql
INSERT INTO dept VALUES (20, 'CSE');
```
#### DELETE
```sql
DELETE FROM dept dname = 'EEE';
```
#### UPDATE
```sql
UPDATE dept set  dname = 'Areo' WHERE deptno = 20;
```