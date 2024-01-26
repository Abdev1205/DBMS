## LEC-7: Relational Model

1. Relational Model (RM) organises the data in the form of relations (tables).
2. A relational DB consists of a collection of tables, each of which is assigned a unique name.
3. A row in a table represents a relationship among a set of values, and the table is a collection of such relationships.
4. **Tuple:** A single row of the table representing a single data point / a unique record.
5. **Columns:** Represents the attributes of the relation. Each attribute has a permitted value, called the domain of the attribute.
6. **Relation Schema:** Defines the design and structure of the relation, contains the name of the relation and all the columns/attributes.
7. Common RM based DBMS systems, aka RDBMS: Oracle, IBM, MySQL, MS Access.
8. **Degree of table:** Number of attributes/columns in a given table/relation.
9. **Cardinality:** Total number of tuples in a given relation.
10. **Relational Key:** Set of attributes which can uniquely identify each tuple.
11. Important properties of a Table in Relational Model
    1. The name of relation is distinct among all other relation.
    2. The values have to be atomic. Can’t be broken down further.
    3. The name of each attribute/column must be unique.
    4. Each tuple must be unique in a table.
    5. The sequence of row and column has no significance.
    6. Tables must follow integrity constraints - it helps to maintain data consistency across the tables.
12. **Relational Model Keys**
    1. **Super Key (SK):** Any P&C of attributes present in a table which can uniquely identify each tuple.
    2. **Candidate Key (CK):** Minimum subset of super keys, which can uniquely identify each tuple. It contains no redundant attribute.
       - CK value shouldn’t be NULL.
    3. **Primary Key (PK):**
       - Selected out of CK set, has the least number of attributes.
    4. **Alternate Key (AK):**
       - All CK except PK.
    5. **Foreign Key (FK):**
       - It creates a relationship between two tables.
       - A relation, say r1, may include among its attributes the PK of another relation, say r2. This attribute is called FK from r1 referencing r2.
       - The relation r1 is aka Referencing (Child) relation of the FK dependency, and r2 is called Referenced (Parent) relation of the FK.
       - FK helps to cross-reference between two different relations.
    6. **Composite Key:** PK formed using at least 2 attributes.
    7. **Compound Key:** PK which is formed using 2 FK.
    8. **Surrogate Key:**
       - Synthetic PK.
       - Generated automatically by DB, usually an integer value.
       - May be used as PK.
13. **Integrity Constraints**
    1. CRUD Operations must be done with some integrity policy so that DB is always consistent.
    2. Introduced so that we do not accidentally corrupt the DB.
    3. **Domain Constraints**
       - Restricts the value in the attribute of relation, specifies the Domain.
       - Restrict the Data types of every attribute.
       - E.g., We want to specify that the enrollment should happen for a candidate birth year < 2002.
    4. **Entity Constraints**
       - Every relation should have PK. PK != NULL.
    5. **Referential Constraints**
       - Specified between two relations & helps maintain consistency among tuples of two relations.
       - It requires that the value appearing in specified attributes of any tuple in the referencing relation also appear in the specified attributes of at least one tuple in the referenced relation.
       - If FK in referencing table refers to PK of referenced table then every value of the FK in referencing table must be NULL or available in referenced table.
    6. **Key Constraints:** The six types of key constraints present in the Database management system are:-
       1. NOT NULL: This constraint will restrict the user from not having a NULL value. It ensures that every element in the database has a value.
       2. UNIQUE: It helps us to ensure that all the values consisting of a column are different from each other.
       3. DEFAULT: It is used to set the default value to the column. The default value is added to the columns if no value is specified for them.
       4. CHECK: It is one of the integrity constraints in DBMS. It keeps the check that integrity of data is maintained before and after the completion of the CRUD.
       5. PRIMARY KEY: This is an attribute or set of attributes that can uniquely identify each entity in the entity set. The primary key must contain unique as well as not null values.
       6. FOREIGN KEY: Whenever there is some relationship between two entities, there must be some common attribute between them. This common attribute must be the primary key of an entity set and will become the foreign key of another entity set. This key will prevent every action which can result in the loss of connection between tables.
