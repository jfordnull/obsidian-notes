**Midterm: Oct 10th (Thursday)**
**Review: Oct 8th (Tuesday)**

Schema is sometimes called the *intension*, an unchanging structure of the database. By contrast, *extension* is a database *state* or *instance*.

A **relation** is a table with columns and rows.
An **attribute** is a named column of a relation, or a property.
A **domain** is the set of allowable values for one or more attributes
A **tuple** is a row of a relation (n-elements)
The **degree** of a relation is how many attributes it contains
The **cardinality** of a relation is how many tuples it contains

**Properties of Relations (Relational Model)**
- Relation name is *distinct* from all other relation names in relational schema.
- Each cell of relation contains exactly *one* atomic value.
- Each attribute in the relation has a *distinct* name.
- Values of an attribute are all from the same *domain*.
- Each tuple is *distinct*, and there are no duplicate tuples.
- Order of attributes has no significance.
- Order of tuples has no significance, theoretically. (Practically, arrangement of tuples in physical layer might affect performance.)

**Relational Keys**
- Superkey
	- An attribute, or a set of attributes, that uniquely identifies a tuple within a relation
- Candidate Key
	- Superkey (K) such that no proper subset is a superkey within the relation
	- No proper subset of K has the uniqueness property (irreducibility). In other words, the minimum number of attributes needed to uniquely identify row in R
	- Multiple candidate keys may exist. But even if attribute is *currently* unique, should consider what is guaranteed to remain unique in choice of Primary Key
	- (Practically, prefer integers over strings, since string matching is more expensive.)
- Primary Key 
	- Candidate key selected to identify tuples uniquely within a relation
- Alternate Key(s)
	- Candidate key that is not selected to be the primary key
- Foreign Key
	- Attribute, or set of attributes, within one relation that matches the candidate key of some relation. (e.g. Branch No. is the candidate key for Branch relation, Branch No. is an attribute, or foreign key, of Staff relation)

**Integrity Constraints**
- Domain Constraints: from restrictions on the set of values allowed for the attributes of relations (e.g. data type, size, etc.)
- Integrity Rules: constraints or restrictions that apply to all instances of the database
	- Entity Integrity Constraints
		- Primary key attributes
		- In a base relation, no attribute of a primary key can be null
	- Referential Integrity Constraints
		- Linkage of foreign key values (e.g. I change the branch no. of a staff member to B10, but does that branch exist? What if a branch closes? I need to update foreign keys in staff)
		- If a foreign key exists in R, the foreign key value must match a candidate key value of some tuple in its home relation or the foreign key value must be wholly null
- Null: Value is not available or not applicable (e.g. A person without a middle name, middle name is N/A)
	- Deals with incomplete or exceptional data. Represents the absence of a value (null != spaces or zero)