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