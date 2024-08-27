# Data and Metadata

- **Structured Data**
	- Stored in standardized, tabular format (conventional relational model)
	- Strings, numbers
- **Unstructured Data**
	- Images, videos, documents
- **Semi-Structured Data**
	- e.g. Email, web pages

# Entity-Attribute-Relationship, ER Modeling

*Entity* := a distinct object to be represented (like an OO "class")
	e.g. student, course, faculty, ...
*Attribute* := a property to describe an entity
	e.g. student > fname, lname, ID, GPA, ...
Attributes require their own metadata: type, size, etc.

*Relationship* := an association among entities, logical structure of database
	e.g. Registration {student, course, faculty}
Dominant entity has many associations, while a supportive entity has few

# Abstraction

Data definition and application program are separated. (Principle of program-data independence.) Allows us to change internal object definition without affecting users. (Assuming external definition remains unchanged.)

# File-Based v. Database Approach

Limitations of File-Based Approach (each program defines, manages own data):
- Separation, isolation of data
- Duplication of data
- Program-data dependence
- Incompatible file formats

