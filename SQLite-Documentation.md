### SQLite - Documentation
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
INSERT INTO students VALUES (5,'Mahiha', 'Rangpur',  10);
INSERT INTO students VALUES (6,'Trisha', 'Rajbari',  50);
INSERT INTO students VALUES (7,'Roky', 'Dhaka', 10);
```

### Query Check
```sql
SELECT * FROM students;
``` 



