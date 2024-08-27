# File-Based v. Database Approach (cont.):

Database Approach:
- Data Definition Language (DDL)
	- Depends on query language you're using (e.g. SQL: create table, schema)
- Data Manipulation Language (DML)
	- Allow user to manipulate data in database. Fundamental operations:
		- Insert
		- Delete
		- Update
		- Query (SQL: SELECT)
- Controlled access to database may include:
	- Security system
		- Assign privileges to each class of users
	- Integrity system, to ensure user operation does not violate two constraints:
		- Accuracy
		- Consistency; a change made by one user is reflected in the database to other users
	- Concurrency control system
		- Allow concurrent user access to same piece of data
	- Recovery control system
		- Software or hardware components can fail without compromising DBS
		-  A user operation is a transaction, like a temporary execution pending approval:
			- Begin transaction
			- End transaction; unless we reach the end of a transaction, no changes committed to DB. Restore last consistent state (backup recovery)
	- User-accessible catalog (dictionary)
		- Metadata
---
# Views:
- A subset of the DB. Allows each user to have their own view of the DB based on their privileges. 
	- Reduces complexity
	- Provides security
	- Customizes DB appearance
		- e.g. User wants annual rent displayed as monthly rent. We apply some operation in our view definition
	- Provides consistent, unchanging view of DB structure even if underlying DB is changed; (program-data independence)
- In SQL:
	- CREATE VIEW
		- We define an encapsulated chain of queries/SELECT statements

**FE Application Programs**:
- Interacts with DB (BE) by issuing appropriate request (e.g. SQL statement) to the DBMS. Could be web-based, standalone interface, etc.
# Database Environment Roles:
- Data Administrator (DA)
	- High-level, less technical than DBA
- Database Administrator (DBA)
- Database Designers
	- Logical: Identifies data (entities, attributes) and relationships among entities. Defines integrity constraints. Designs:
		- Conceptual database schema (first draft)
		- Logical database schema
	- Physical: Realizes logical design in physical memory space (computer, device, server layer). Map design into tables and storage structure
- Application Developers
	- Front-end development
- End Users (naive and sophisticated)

**DBMS Environment Components**:
- Hardware
	- PC, server, network
- Software
	- DBMS, OS, application programs
- Data
	- Including description of this data (schema)
- Procedure
	- Instructions and rules applied to design and use of DB and DBMS
		- i.e. How to login, how to use particular DBMS facility or application program, how to start and stop DBMS

**History of Database Systems**:
- First-generation
	- Hierarchical
	- Network
- Second generation
	- Relational
- Third generation
	- Object relational
	- Object-oriented