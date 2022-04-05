# Database Documentation

## SQL

##### Types of Command  of sql

**DDL - Data Definition Language**
1. CREATE *(CREATE DATABASE database_name;)*
2. DROP *(DROP TABLE table_name;)*
3. ALTER *(**ALTER TABLE table_name** DROP COLUMN column_name;)*
4. TRUNCATE *(TRUNCATE TABLE  table_name;)*
5. RENAME *(ALTER TABLE table_name **RENAME COLUMN old_name TO new_name;**)*
6. COMMENT *(/* multi line comment another comment */)*


**DML - Data Manipulation Language**
1. INSERT
2. DELETE
3. UPDATE


**DQL - Data Query Language**
1. select 
2. from
3. where 


**DCL - Data Control Language**
1. GRANT
2. DENY
3. REVOKE 


**TCL - Transaction Control Language**
1. **COMMIT**: Commits a Transaction.
2. **ROLLBACK**: Rollbacks a transaction in case of any error occurs.
3. **SAVEPOINT**: Sets a savepoint within a transaction.
4. **SET TRANSACTION**: Specify characteristics for the transaction.