Database relationships are associations between tables that are created using join statements to retrieve data. 
- 1 : 1
- 1 : N
- N : 1
- N : N


### Implement relationships
Referencing and embedding are two common approaches to implementing relationships between entities in a database.

#### Referencing
Referencing is the approach where an **entity contains a reference to another entity through a unique identifier**, usually a primary key. The reference is often implemented as a foreign key in the referencing entity that points to the primary key of the referenced entity. This allows entities to be connected and relationships to be established between them.

##### Example
In a database of books and authors, a book entity might reference an author entity by including the author's unique identifier (such as an author ID) as a foreign key. This way, the book entity can link to the corresponding author entity, allowing queries and other operations to retrieve information about the author.
See another example with code: [[Reference Relationship Example]]

#### Embedding:
Embedding, on the other hand, **involves including one entity inside another entity**. This approach is typically used for one-to-one or one-to-many relationships, where the embedded entity is a part of the parent entity and has no existence independent of it. The embedded entity is typically stored as a nested object or document within the parent entity.

##### Example 
in a database of user profiles, a user entity might embed a contact information entity within it, containing the user's phone number and email address. This way, all the relevant information about a user can be stored together in one entity.
See another example with code: [[Embedded Relationship Example]]



In general, referencing is more suitable for many-to-many and one-to-many relationships, while embedding is more suitable for one-to-one and one-to-many(few) relationships where the embedded entity is a subordinate of the parent entity. The choice of approach depends on the specific requirements of the system and the constraints of the database technology being used.


