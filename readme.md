<--TODO-->
https://www.linkedin.com/learning/sql-essential-training-2018
priamry key, foreign key, ERs, normalization, DML, DDL, joins
I started refershing Postgres skills using [this](https://www.youtube.com/playlist?list=PLwvrYc43l1MxAEOI_KwGe8l42uJxMoKeS) youtube playlist.
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
    * *contraints1* is usually features like `NOT NULL` and `Serial`....etc
    1. Each table can be inter-related to each other using *primary* and *secondary_keys*
1. Viewing Tables
* `\dt` list tables of the public schema
* `\dt <schema-name>.*` list tables of certain schema, e.g., \dt public.*
* `\dt *.*` list tables of all schemas
1. Deleting Tables
`drop table table_name;`
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
### Project
* After some useful learning, I decided to do a mini database building project. This is WiP.