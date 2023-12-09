# LEC-2: DBMS Architecture

## 1. View of Data (Three Schema Architecture)

- The major purpose of DBMS is to provide users with an abstract view of the data. That is, the system hides certain details of how the data is stored and maintained.
- To simplify user interaction with the system, abstraction is applied through several levels of abstraction.
- The main objective of three-level architecture is to enable multiple users to access the same data with a personalized view while storing the underlying data only once.

### a. Physical level / Internal level

- The lowest level of abstraction describes how the data is stored.
- Low-level data structures are used.
- It has a Physical schema that describes the physical storage structure of the DB.
- Talks about: Storage allocation (N-ary tree etc), Data compression & encryption etc.
- Goal: Define algorithms that allow efficient access to data.

### b. Logical level / Conceptual level:

- The conceptual schema describes the design of a database at the conceptual level, describing what data is stored in the DB and what relationships exist among those data.
- Users at the logical level do not need to be aware of physical-level structures.
- Database Administrators (DBAs), who must decide what information to keep in the DB, use the logical level of abstraction.
- Goal: Ease of use.

### c. View level / External level:

- The highest level of abstraction aims to simplify users’ interaction with the system by providing different views to different end-users.
- Each view schema describes the database part that a particular user group is interested in and hides the remaining database from that user group.
- At the external level, a database contains several schemas, sometimes called subschemas, describing different views of the database.
- Views also provide a security mechanism to prevent users from accessing certain parts of the DB.

![](https://i.postimg.cc/gc63fDrb/image.png)

## 2. Instances and Schemas

- The collection of information stored in the DB at a particular moment is called an instance of the DB.
- The overall design of the DB is called the DB schema.
- Schema is a structural description of data. Schema doesn’t change frequently. Data may change frequently.
- DB schema corresponds to the variable declarations (along with type) in a program.
- We have 3 types of Schemas: Physical, Logical, several view schemas called subschemas.
- Logical schema is most important in terms of its effect on application programs, as programmers construct apps by using the logical schema.
- Physical data independence, physical schema changes should not affect the logical schema/application programs.

## 3. Data Models:

- Provide a way to describe the design of a DB at the logical level.
- Underlying the structure of the DB is the Data Model; a collection of conceptual tools for describing data, data relationships, data semantics & consistency constraints.
- Examples include ER model, Relational Model, object-oriented model, object-relational data model, etc.

## 4. Database Languages:

- Data Definition Language (DDL) is used to specify the database schema.
- Data Manipulation Language (DML) is used to express database queries and updates.
- Practically, both language features are present in a single DB language, e.g., SQL language.
- DDL: Specify consistency constraints, which must be checked every time the DB is updated.
- DML: Involves retrieval, insertion, deletion, and updating of information stored in the DB. It includes a query language, a part of DML, to specify statements requesting the retrieval of information.

## 5. How is Database accessed from Application programs?

- Apps (written in host languages, C/C++, Java) interact with the DB.
- For example, a banking system’s module generating payrolls access the DB by executing DML statements from the host language.
- API is provided to send DML/DDL statements to the DB and retrieve the results.
  - Open Database Connectivity (ODBC), Microsoft “C”.
  - Java Database Connectivity (JDBC), Java.

## 6. Database Administrator (DBA)

- A person who has central control of both the data and the programs that access those data.
- Functions of DBA include Schema Definition, Storage structure and access methods, Schema and physical organization modifications, Authorization control, and Routine maintenance (e.g., periodic backups, security patches, any upgrades).

## 7. DBMS Application Architectures

- Client machines, on which remote DB users work, and server machines on which the DB system runs.
- **T1 Architecture**
  - The client, server & DB all present on the same machine.
- **T2 Architecture**
  - App is partitioned into 2 components.
  - Client machine, which invokes DB system functionality at the server end through query language statements.
  - API standards like ODBC & JDBC are used to interact between the client and server.
- **T3 Architecture**
  - App is partitioned into 3 logical components.
  - Client machine is just a frontend and doesn’t contain any direct DB calls.
  - Client machine communicates with App server, and App server communicates with the DB system to access data.
  - Business logic, what action to take at that condition is in App server itself.
  - T3 architectures are best for WWW Applications.
  - Advantages:
    - Scalability due to distributed application servers.
    - Data integrity: App server acts as a middle layer between client and DB, minimizing the chances of data corruption.
    - Security: The client can’t directly access the DB, hence it is more secure.

![](https://i.postimg.cc/8CKnnHcr/image.png)

