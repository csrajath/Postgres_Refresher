<--TODO-->
https://www.linkedin.com/learning/sql-essential-training-2018
pgplsql, nested queries, priamry key, foreign key, ERs, normalization, DML, DDL, joins
I started refershing Postgres skills using [this](https://www.youtube.com/playlist?list=PLwvrYc43l1MxAEOI_KwGe8l42uJxMoKeS) youtube playlist.

I believe in learning through excercies. Thus at last there is also a section for excerise questions.
### Understanding Database
* Database is a place to store, manipulate and retrive data.
* Example of data storage: Amazon.com, all user related and products related data is stored in specified structure on a database and is hosted on a server.

### Understanding PostgreSQL
* SQL is the programming language used to interact with databases.
* Postgres is the engine that powers that interactions.
* PostgreSQL is a Relational Database Management System used to store data in structured format.
    * A RDBS consists of one or more tables related to each other.
        * Each table is formed of rows and columns structure.
            * A column is an *attribute* that describes a specific item in the database.
            * Each row contains values for the attributes.
            * A field in a database is each cell in the database. Example: If a database has 10 columns and 10 rows; then it as 100 fields
* Actually.... PostgreSQL is an object relational database management system. Meaning, each table and its contents can be converted to an object oriented model design to be programatically accessed via classes, methods and functions. 
* Two most important components for interacting with a database are:
    * Database Server
        * This is the machine hosting the database.
    * Database Client
        * This is the application used to view database related items, like: schema, tables, columns and other configs.
        * Such Clients are: DataGrip, Postico, pgAdmin and one can use psql Shell too.
### Understanding Commands and Operations
#### Basic Commands
* NOTE: ***PostgreSQL is not case sensitive***
* *\q* to quit from postgres terminal
* *\l* to list the databases
* *psql --help* list the most used options
* *\i* to execute a query from a file

1. Connecting to the DB using command Prompt
    * Add the Postgres *bin* and *lib* to *PATH*
    * Open *cmd* or *terminal* and type this command for connection:
        `
        psql -U username
        `
    * If there are multiple databases associated to an account, then you can switch between database post login using the 
    `\c database_name` command
2. Creating a Database
    * ` create database db_name;
    `
    * The most important this is the *semi-colon (;)* at the end of the command.
1. Deleting a database
    * In database language, this is called *droppin* a database.
    * The postgres equivalent command for it is `drop database db_name;`
    * ***NOTE:*** 
        * One cannot drop the database when connected to it
        * One cannot drop the database during a query transaction
        * Be very careful and cautious while executing this command as it cannot be undone.
1. Creating tables
    * Table creation is a DDL operation
    * Use the below syntax to create tables
    `
    create table table_name ( 
        column_name column_type(contraints) constraints1
    );
    `
    * Creating a column in a table without constraint value for it is a bad practice
    * *contraints1* is usually features like `NOT NULL` and `Serial`....etc
    * If a column is tagged with `NOT NULL` contraint it means it cannot be empty
    * If a column is tagged with `serial` constraint it means it automatically calculates the series of values
        * Whenever something auto incrementing is needed, it is best to use the `bigserial` constraint
    * Each table can be inter-related to each other using *primary* and *secondary_keys*
1. Viewing Tables
* `\d table_name` gives details of a table.
* `\dt` list tables of the public schema
* `\dt <schema-name>.*` list tables of certain schema, e.g., \dt public.*
* `\dt *.*` list tables of all schemas
1. Deleting Tables
`drop table table_name;`
#### INSERTING AND QUERYING
1. Inserting Values
* Syntax: `inser into table_name () values ();`
* While inserting values to a table, it is important to follow same order as the columns input onto the *INTO* keyword.
    1. This is the correct format:
        `insert into table_name(fname,lname,age) values ('john','doe',12);`
    1. This is the wrong formar:
        `insert into table_name(fname,lname,age) values (12, 'doe', 'john');`
* One can also insert values from a file using the *\i* command.
1. Retrieving Values
* *SELECT* keyword is used to retrive records.
* Syntax: `select column_name from table_name;`
    * the column name can be accoumpanied by other keywords, like:
        `select count(*) from table_name;`
1. Sorting Values



#### Date and TimeStamps
* Whenever a date is entered in a psql command, it is important to note that the default format is *yy-mm-dd*
### Excercises
#### Database
1. Create, delete and view databases
#### Tables
1. Create a two tables and link each other appropriately 
2. Create an employee table with DOB column defaulting to date column_type
3. Create a table with auto incrementing serial values
1. Insert values into above created tables
1. Insert values into from a file
1. Retrive unique values only   
#### Data Normalization
1. Create the place table with zip_code as a five-character PRIMARY KEY, city as a text-type with up to 50 characters, and state as a two-character column. Add a column named place_id (a foreign key) to the borrower table that references the zip_code column of the place table.
2. Create a client table for a client with employee number of 70-100 (num_employee column) and with columns id (a primary key), name (max length of 50),  
Create a contact table with columns id (a primary key), name (max length of 50), and email (max length of 50). Alter the client table by adding a contact_id column as a foreign key.

#### COUNTING
* *count* keyword is used to obtain the number of rows for a specfic column or the table as a whole.
* *count* is always accompanied by *select* keyword
* Syntax:
`select count(column_name) from table_name;`
* Example:
`select count(*) from countries;` # finding the total number of rows within *countries* table.
* *distinct* keyword can be nested with count. Sometimes a column will have duplicate values. If one needs to find total number of unique values below syntax can be followed:
`select count(distinct(column_name)) from table_name;` 
#### CONDITIONAL QUERIES
##### CASE
* Conditional statements are always prefixed with *CASE* keyword and shall always close with *END* keyword.
* *WHEN* and *THEN* keywords are used for performing conditional operations in postgresql.
* The conditional block should always end with an *ELSE* keyword. If *ELSE* is not defined and all the conditions fail then the query will return *NULL*.  
* Case Syantx:\
`CASE `\
`WHEN condition_1 THEN result_1`\
`WHEN condition_2 THEN result_2`\
`ELSE result_n` \
`END`
* *NOTE:*
    * It not is required to place a *comma* after each *WHEN* statement.
    * If there are multiple *THEN* conditions or if there are multiple *results* then all the results should be of uniform datatype. i.e. *result_1* cannot be *integer* while *result_2* being 'character'.
    * *CASE* conditioning is applied with a select
### Data Types
### Data Normalization
* It is an activity performed to clean the data in order to obtain the data in an organized structure. It is essentially performed when the data at hand is reduandant,duplicate or inaccurate.
* Data redundancy  = Applicant is a borrower, the record for him is present in both *applicant* and *borrower* tables.
* Data duplication and redundancy are similar concepts except the former occurs on flat files than on databases.
#### *PRIMARY KEY*
* Uniquely identify a record in the table
* *Syntax*: `column_name column_type(constraint) primary key`
* Can't accept null values
* Multiple columns can be mentioned as primary key in a single line.
    * Example: `primary key (colmn_name1, colmn_name2)`
#### *FOREIGN KEY*
* A field in the table that is primary key in another table.
* *Syntax*:  `column_name column_type(constraint) references other_table_name(column_name_in_other_table)`
* Can accept multiple null value.
* *Alter* command is used to add a foreign key to an existing table
    * `ALTER TABLE *child_table* ADD CONSTRAINT *constraint_name* FOREIGN KEY (c1) REFERENCES parent_table (p1);`
##### *UPDATE* & *DELETE* operation on foreign key
* PostgreSQL provides various options/contraints for the same.
    * ON DELETE RESTRICT or ON UPDATE RESTRICT
        * The rows in the parent table are not deleted/updated until all the rows in the child table are.
    * ON DELETE CASCADE or ON UPDATE CASCADE
        * All the referenced rows in the child table are deleted/updated on deletion of a single row in the parent table
    * NO ACTION
    *  If none of the above two are mentioned then by default *NO ACTION* is executed which throws an error based on operation.
#### 1st Normal Form (*1NF*)
* A table/relation in in 1NF only if the columns are atomic in nature i.e. each field contains only one entry.
* Reasons why following 1NF is important:
    * To avoid Insertion errors
        * If a column is restricted for 50 characters only but does not follow atomicity adding multiple values in same field results in insertion error
    * To avoid update erros
        * If multiple values are allowed within a field then updating one of the values needs to be programatically handled outside database queries
    * To avoid deletion errors
        * Voids *Data Integrity* if multiple values are included in a field.
            * Data Integrity is all about maintaining consitenciy of data throughout its lifecycle. If there are multiple values in a field, lets say = (chemistry, biology, physics), then changing one of the values voids data integrity of all the other values.
#### 2nd Normal Form (*2NF*)
* Should satisfy 1NF
* It is important to maintain seperation of concerns, that is, if there are two definite entities then their needs to exist their own table for them.
	* If Books and Publishers data is to be stored, then there needs to be two tables. One for books and other for publisher.
	* Having the publisher data within books table will create problems like:
		* Publishers with no textbook cannot be added to the table
		* Batch attribute update becomes a manual process
		* If there exists multiple books of same publishers, one cannot remove indivisual books of that specific publisher. It will end up removing all the books of that publisher.
https://www.postgresqltutorial.com/postgresql-foreign-key/
### Postgres Interview Questions

### Project
* After some useful learning, I decided to do a mini database building project. This is WiP.
### Resources
* Some handy resources to understanding PostgreSQL
     * Book - [Mastering PostgreSQL 12: Advanced Techniques to Build and Administer Scalable and Reliable PostgreSQL Database Applications, 3rd Edition](https://www.amazon.com/Mastering-PostgreSQL-techniques-administer-applications-ebook/dp/B0822GCCDT)
     * Udemy - [PostgreSQL Project](https://www.udemy.com/course/create-a-web-application-with-python-django-postgresql/)
     * Blogs - [Data Engineering with PostgreSQL](https://towardsdatascience.com/data-engineering-with-python-django-and-postgresql-99409492769)
     * Practice - [Hands-On PostgreSQL](https://pgexercises.com/questions/basic/)
        * DataCamp - There are three PostgreSQL courses on datacamp which provides explaination with instant hands-on experience
            * https://www.datacamp.com/courses/creating-postgresql-databases
            * https://www.datacamp.com/courses/postgresql-functions-for-manipulating-data
            * https://www.datacamp.com/courses/improving-query-performance-in-postgresql
