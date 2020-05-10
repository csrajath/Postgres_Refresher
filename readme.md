<--TODO-->
priamry key, foreign key, ERs, normalization, DML, DDL, joins
### Understanding Database
I started refershing Postgres skills using [this](https://www.youtube.com/playlist?list=PLwvrYc43l1MxAEOI_KwGe8l42uJxMoKeS) youtube playlist.
* Database is a place to store, manipulate and retrive data.
* Example of data storage: Amazon.com, all user related and products related data are stored in specified structure on a database and hosted on a server.

### Understanding PostgreSQL
* SQL is the programming language used to interact with databases.
* Postgres is the engine that powers that interactions.
* PostgreSQL is a Relational Database Management System used to store data in structured format.
    * A RDBS consists of one or more tables related to each other.
        * Each table is formed of rows and columns structure.
            * A column is an *attribute* that describes a specific item in the database.
            * Each row contains values for the attributes.
            * A field in a database is each cell in the database. Example: If a database as 10 columns and 10 rows; then it as 100 fields
* Actually.... PostgreSQL is an object relational database management system. Meaning, each table and its contents can be converted to an object oriented model design to be programatically accessed via classes, methods and functions. 
* Two most important components for interacting with a database are:
    * Database Server
        * This is the machine hosting the database.
    * Database Client
        * This is the application used to view database related items, like: schema, tables, columns and other configs.
        * Such Clients are: DataGrip, Postico, pgAdmin and one can use psql Shell too.
### Understanding Commands
#### Basic Commands
* NOTE: ***PostgreSQL is not case sensitive***
* *\q* to quit from postgres terminal
* *\l* to list the databases

1. Connecting to the DB using command Prompt
    * Add the Postgres *bin* and *lib* to *PATH*
    * Open *cmd* or *terminal* and type this command for connection:
        `
        psql -U username
        `
2. Creating a Database
    * ` create database *db_name*
    `
### Resources
* Some handy resources to understanding PostgreSQL
     * Book - [Mastering PostgreSQL 12: Advanced Techniques to Build and Administer Scalable and Reliable PostgreSQL Database Applications, 3rd Edition](https://www.amazon.com/Mastering-PostgreSQL-techniques-administer-applications-ebook/dp/B0822GCCDT)
     * Udemy - [PostgreSQL Project](https://www.udemy.com/course/create-a-web-application-with-python-django-postgresql/)
     * Blogs - [Data Engineering with PostgreSQL](https://towardsdatascience.com/data-engineering-with-python-django-and-postgresql-99409492769)
     * Practice - [Hands-On PostgreSQL](https://pgexercises.com/questions/basic/)