EER
Superclass/subclass
(Triangle under superclass fans out into subclass)

Superclass represents common attributes (primary key, etc.); Superclass/subclass relationship always 1:1

Need to specify:
- Participation constraints: Mandatory/optional participation of all tuples in superclass
- Disjoint constraints: Indicate, if tuple participates, is it in one subclass or multiple (joint/disjoint, or/and)

If a superclass has only one subclass, we only need participation constraint

Each superclass can have multiple groupings of subclasses with their own constraints

Shared subclasses are an example of multiple inheritance

Aggregation: represents a "has-a" or "is-part-of" relationship between entity types (unfilled diamond)

Composition: Strong ownership between "whole" and "part", authority to destroy/create object (filled diamond)