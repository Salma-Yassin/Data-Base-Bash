# Data-Base-Bash

A Database Engine created using bash scripts.

## To run:

- Please add the project folder path to the environment variables.

- Run the command: 

`main_menu`

## Supported functionalities:

### Main Menu
1) Create DB: does not allow the creation of duplicate databases (checks that the user hasn't created a database with the same name before), and handles whitespace in the name of the database. It ensures that the name only starts with letters and only contains alphamumeric and underscore.
2) List DB: either lists existing databases if any exist or tells the user that no databases exist. 	
3) Drop DB: delete the database, it asks for user confirmation to avoid deletion by mistake.
4) Connect to DB: asks the user to choose a database to connect to if any exists then opens the Table Menu. It asks the user to create a database if none exists. 
5) Press 5 or any key to exit

### Table Menu:
1) Create Table:
   - Asks for the table name, checks if it is unique, and that no table inside this database has the same name. It ensures that the name follows the naming rules. It does not allow whitespace in the middle but gives the user the option to replace whitespace, it aborts table creation if the user refuses.
   - Takes the number of fields and checks that it is an integer.
   - For each field (Column), it takes the name of the field and checks that it is unique inside this table, the name has to be two characters at least and start with a letter.
   - For each field, it asks for the datatype: String or Integer. It does not allow the user to create a table without properly setting these options.
   - The first field created is the primary key and the unique constraint is applied to this field.
2) Drop Table:
   - It shows the user a list of existing databases to delete, and delete the chosen table, it asks for user confirmation to avoid deletion by mistake.	If the user chooses an option that does not exist in the list, it will show an Invalid Option.        
3) Insert into Table 
    - It shows a list of existing tables for the user to choose from and handles invalid user selection.
    - Before each insertion, it checks the primary key constraint for the first field. 
    - Before each insertion, it checks that all integer fields have numeric values and that all string fields have non-empty values.
4) select from Table
   - It lists tables inside the database for the user to choose from and then shows the next menu:
     1) Select all: shows column names and all existing records.		    
     2) Select a column: shows a list of column names for the user to choose from and when the user chooses a valid option it shows all values inside the corresponding column.	    
     3) Select by a column value: shows all records (the whole record) that match a given value entered by the user for a given column. It first lists all existing columns for the user to choose from and then asks for a value to match inside this column, it will either return the matched columns or that the value does not exist.
     4) Back to connection menu
     5) Back to main menu
     6) Exit
5) Delete from Table
    - It lists tables inside the database for the user to choose from if any exist or tells the user that no tables were created. Then shows the next menu:
      1) Delete by Id: takes the value for the primary key to delete the whole record. If it does not exist, it tells the user that the id does not exist.	    
      2) Delete by a Column Value: specify a column value and then delete all records that match this value in the chosen column. 
      3) Drop a Column: it deletes a whole column. it shows the user a list of columns to choose from, except primary key, and then deletes this column from all records.	     
      4) Delete All: it deletes all records inside the table, it asks for user confirmation to avoid deletion by mistake.
      5) Back to connection menu
      6) Back to main menu

6) Update Table:
   - It lists tables inside the database for the user to choose from if any exist or tells the user that no tables were created. 
   - If a table is selected and has no entries, it will inform the user.
   - If a table is selected and it has entries (records), it asks the user to enter the id of the record they want to modify or enter q if they want to exit.
   - If they entered an id, it will ask for the column they want to modify and take the corresponding value.
   - it applies unique and datatypes check same as the insert.
7) List Tables:
   - Either lists all tables if any exist or tells the user that none exist.
8) Back to main menu

