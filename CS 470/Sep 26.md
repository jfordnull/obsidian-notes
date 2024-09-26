**Relations (cont.)**

**Views**
- Base Relation
	- Named relation defined in conceptual schema, whose tuples are physically stored in a database. 
- View
	- A virtual relation produced upon request, at the time of request. Dynamic result of relational operation(s) or more other relations (including other views) to produce a new relation.
	- Contents of view defined as query on one or more base relations
	- Views are dynamic, meaning that changes made to base relations are immediately reflected in the view
---
```SQL
-- Can define different attribute names
CREATE VIEW Staff3(SNo, First_name, Last_name, position, gender)
-- Attribute names in base relation
AS SELECT StaffNo, fName, lName, position, sex
-- Base relation
	FROM Staff
	-- At Branch 3
	WHERE branchNo = 'B003';
```
---
```SQL
INSERT INTO Staff
	VALUES('SG16','Alan','Brown','Assistant','M','B003');
```
---
```SQL
UPDATE Staff3
	SET position = 'Manager'
	WHERE sNo = 'SG37';
```
---

**Updating Views**
- All updates to a base relation should be immediately reflected in all views that reference that base relation
- If view is updated, underlying base relation should reflect the change.
- Classes of views are defined as:
	- theoretically not updateable
	- theoretically updateable
	- partially updateable
- Easier to modify base and have changes reflected in view than other direction. Therefore, some constraints exist on possible updates of a view.
	- Updates allowed if the query involves a single base relation (and contains a candidate key of a base relation)
	- Updates involving multiple base relations are not allowed
	- Updates are not allowed involving aggregation (e.g. COUNT, MAX, MIN, SUM, AVG) or grouping (e.g. GROUP BY) operations

# Ch. 12 & 13 - Entity-Relationship Modeling and Enhanced Entity-Relationship Modeling

- Unified Modeling Language (UML) - Diagrammatic technique for displaying ER model
	- Box nodes are *entities*. Upper field is entity name, lower field is Primary Key
		- Entities have a set of attributes (properties)
	- Connections are *relationships*
	- Diamond nodes are non-binary (involving > 2 entities), ternary or n-ary 
		- There are also recursive (unary) relationships
	- Entity with many connections is called *dominant*
		- Other entities may be *supporting*
- How to identify and resolve problems with ER models called connection traps
- How to build an ER model from a requirements specification
- How to represent more complex applications using EER model:
	- specialization/generalization
	- aggregation
	- composition
