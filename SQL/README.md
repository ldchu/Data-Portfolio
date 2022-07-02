# SQL Projects
Created by Lindsay Chu.

## ETL Data Warehouse for Hypothetical Content Creator Site
`Oracle SQL Developer`, `database management`, `Extract Transform Load (ETL)`

*Created for the course, MIS325: Database Management.*

For my semester-long analysis of a fictional content creators' platform for my MIS course, 
I used Oracle SQL developer to create a data warehouse called **client_dw**, populated by two tables: current users and prospective users.

To create the table, my DDL script contains:
* Fields shared by **both** types of users: id, first name, last name, phone, email, and status. I also created a field called
**data_source** to contain one of the following codes (CURR, PROS) to identify the table that the record came from. The data_source and id serve as a joint primary key to the client_dw table. 

* `2 view statements` that format the data from the two tables in a unified, consistent format that matches the user structure in client_dw. For example, all phone numbers are formatted as ###-###-####

* `2 insert statements` that select columns from the `view` and then `insert` them into the client_dw table, but only if the records don’t exist already in the data warehouse table. 

* `2 update statements` that update the records on the client_dw table with the latest name, email, or status from the source views. 

*NOTE: The insert and update statements are designed to run on a nightly scheduled procedure, and repeat their processes without error.*

* A `procedure` called **user_etl_proc** that executes the 2 insert statements and 2 update statements.
