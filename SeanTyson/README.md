# Module 20 Final Project

## Segment 1

For Segment 1, I was responsible for cleaning and preparing data from the all_tables dataset. This dataset tracks the end-of-season standings of all MLS teams for every season through 2021. 

### Cleaning Process

- Updated column titles for clarity
- Fixed Goal_Differential calculation errors
- Removed all data prior to 2004
- Removed Head_to_Head column
- Changed file name to all_tables_cleaned.csv
- Cleaned mismatching club names
- Removed Qualification column
- Removed Shootout_Wins & Shootout_Losses
- Removed Points_Per_Game Column
- Removed duplicative eastern & western conference rows
- Fixed Points column calculations
- Reordered columns for clarity

### Database Structure
- Created ERD of sample database on QuickDBD

# Segment 2

For Segment 2, I was responsible for establishing a database integration. I ran into multiple technical difficulties and have not finished the integration with SQLAlchemy. However, I updated the database ERD with a new structure for our project's four data tables and completed the steps below in pgAdmin. 

Step 1: Created a database in pgAdmin
![Step_1]()

Step 2: Named database MLS_FinalProject
![Step_2]()

Step 3: Accessed Query Tool
![Step_3]()

Step 4: Created four SQL tables matching ERD structure
![Step_4]()

Step 5: Inserted data from the CSV files into the tables 
![Step_5]()

Step 6: Verified the success of the import
![Step_6]()

Step 7:
![Step_7]()

Step 8
![Step_8]()