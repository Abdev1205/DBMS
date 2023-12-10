# LEC-3: Entity-Relationship Model

## 1. Data Model
- Collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.

## 2. ER Model
1. It is a high-level data model based on a perception of a real world that consists of a collection of basic objects, called entities, and of relationships among these objects.
2. Graphical representation of ER Model is ER diagram, which acts as a blueprint of DB.

### 3. Entity
- An Entity is a “thing” or “object” in the real world that is distinguishable from all other objects.
   - It has physical existence.
   - Each student in a college is an entity.
   - Entity can be uniquely identified (By a primary attribute, aka Primary Key).
  
#### 4. Entity Types
1. **Strong Entity:**
   - Can be uniquely identified.
   
2. **Weak Entity:**
   - Can’t be uniquely identified, depends on some other strong entity.
   - Doesn't have sufficient attributes to select a uniquely identifiable attribute.
   - Loan -> Strong Entity, Payment -> Weak (as instalments are sequential number counter can be generated separate for each loan).
   - Weak entity depends on a strong entity for existence.

#### 5. Entity Set
- It is a set of entities of the same type that share the same properties, or attributes.
   - E.g., Student is an entity set.
   - E.g., Customer of a bank

#### 6. Attributes
- An entity is represented by a set of attributes.
   - Each entity has a value for each of its attributes.
   - For each attribute, there is a set of permitted values, called the domain, or value set, of that attribute.
   - E.g., Student Entity has the following attributes:
     A. Student_ID
     B. Name
     C. Standard
     D. Course
     E. Batch
     F. Contact number
     G. Address

##### 6.1 Types of Attributes
1. **Simple:**
   - Attributes that can’t be divided further (e.g., Customer’s account number in a bank, Student’s Roll number).

2. **Composite:**
   - Can be divided into subparts (e.g., Name of a person, can be divided into first-name, middle-name, last-name).
   
3. **Single-valued:**
   - Only one value attribute (e.g., Student ID, loan-number for a loan).

4. **Multi-valued:**
   - Attribute having more than one value (e.g., phone-number, nominee-name on some insurance, dependent-name).

5. **Derived:**
   - Value of this type of attribute can be derived from the value of other related attributes (e.g., Age, loan-age, membership-period).

6. **NULL Value:**
   - An attribute takes a null value when an entity does not have a value for it.
   - It may indicate “not applicable” or “unknown”.

#### 7. Relationships
- Association among two or more entities.
   - E.g., Person has a vehicle, Parent has Child, Customer borrows a loan.

##### 7.1 Types of Relationships
- Strong Relationship: between two independent entities.
- Weak Relationship: between a weak entity and its owner/strong entity (e.g., Loan ->instalment-payments-> Payment).

#### 7.2 Degree of Relationship
1. Unary: Only one entity participates (e.g., Employee manages employee).
2. Binary: Two entities participate (e.g., Student takes Course).
3. Ternary: Three entities participate (e.g., Employee works-on branch, employee works-on job).
   - Binary relationships are common.

#### 8. Relationships Constraints
1. **Mapping Cardinality / Cardinality Ratio:**
   - Number of entities to which another entity can be associated via a relationship.
   
   - One to one, One to many, Many to one, Many to many.

2. **Participation Constraints:**
   - Aka, Minimum cardinality constraint.
   - Types: Partial & Total Participation.
   - Partial Participation: Not all entities are involved in the relationship instance.
   - Total Participation: Each entity must be involved in at least one relationship instance.

### 9. ER Notations
- ER notations for graphical representation. 📊

![](https://i.postimg.cc/SxNPbkg3/image.png)
