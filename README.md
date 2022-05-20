# Win/Loss Prediction in Major League Soccer using Deep Learning model
    
## Project Goal 

Predict win/loss outcomes of a specified team in the **Major League Soccer (MLS)** through a machine learning model that utilizes match statistics from the **2001-2021** seasons. 

Multiple variables, such as **player** and **team performance**, **home/away status**, and **stadium attendance**, have been analyzed to gauge their impact and **predict potential match outcomes**.

In addition to a machine learning model that predicts future match outcomes, the team develops a Tableau dashboard that provides additional insight into the historical performance of MLS franchises, including data on win/loss records and top scorers.

We chose this project because our home city, Austin, Texas, recently got its first MLS soccer club. Austin FC, a new member of the Western Conference, has had a hot start to the 2021 season. We want to dig into the historic perforamance of rival clubs and develop a model to predict outcomes for our home team's first season. 

 [Dashboard link in Tableau Public:](https://public.tableau.com/app/profile/sean3063/viz/MLSDashboard/Dashboard1)
  
  ![MLS Dashboard](https://user-images.githubusercontent.com/58155187/129308899-1269408f-0b52-46cf-9040-b3c36d24474a.png)

## Dataset Overview

  ### Data Source
  
  Major League Soccer Dataset - by Joseph Mohr, last updated 11th July, 2021; version 34. The weblink: https://www.kaggle.com/josephvm/major-league-soccer-dataset

  This dataset contains player, game, event, and table data from Major League Soccer (MLS).

  There is currently information on over 6000 matches and almost 420,000 events from those matches.

   ### Player Data
  
   **all_goalkeepers.csv** - all goalkeeper data from every season of MLS through 2020; 19 Columns, 2,007 Rows.
  
   **all_players.csv** - all outfield player data from every season of MLS through 2020; 28 Columns, 15,768 Rows.

   ### Game Data

   **matches.csv** - match data from the 2001-2021 seasons; 122+ Columns, 6,698 Rows.

   ### Event Data

   **events.csv** - events from games from the 2008-2021 seasons; 3 Columns, 442,178 Rows.

   ### Tables

   **all_tables.csv** - end of season / current standing of tables for every season through 2021; 17 Column, +/- 789 Rows.
  
  ### Data Quality
  
  In the Kaggle webpage, this dataset is rated with a score of **8.8** for **Data Usability** which seems good.
  
  ![MLS data quality](/Resources/Images/MLS_data_quality.png)
  
  Fig. 1. MLS data sufficiency and adequacy information provided by the data source.
  
  From Fig. 1, we see that data on all relevant items is available for the period 2012-2020. Two key features - *Results* and *Player Stats* - are also fully available from 1996-2020, which should provide more data if required.

  ### Sample Database

A sample dataset and ERD can be seen below. This dataset will be supplemented with additional datasets that are still currently being cleaned that cover topics such as goalkeeper performance, top goal scorers, and stadium details.

![Sample_Dataset](https://github.com/moonem/FinalProject/blob/main/Resources/Images/Sample_Dataset.png)

## Communication Protocols

Team communication and project planning has been conducted through live video calls over **Zoom** and asynchronously through a project-specific **Slack** channel. The team also supplied contact details in the form of *cell phone* numbers and *emails* for any urgent tasks/questions.  


## Teamwork

Our team has 4 members. Coincidentally our data source has also 4 key *.csv* files for the analysis. Each team-member cleaned one *.csv* data using **ETL** process and pushed to their respective branches as shown below. 

1. Sean Tyson - all_tables_cleaned.csv, QuickDBD-export.png; 
2. M A Moonem - all_players_clean.csv; 
3. Daniel Gonzalez - matches_2004to2021.csv; 
4. Ben Reed - all_goalkeepers_clean.csv; 

## Presentation

[google slides](https://docs.google.com/presentation/d/1b0U9tTp1LIhrh8zkYAMvX0BZqA8qRPFrOiRTJiwtGKI/edit?usp=sharing)

### Selected Topic

The topic has been selected as **"Win/Loss Prediction in Major League Soccer using Deep Learning model"**.

### Reason behind choosing this topic

Our team decided on this project because our home city, Austin, Texas, recently got its first MLS soccer club. **Austin FC**, a new member of the Western Conference, has had a hot start to the 2021 season. We wanted to dig into the historic perforamance of rival clubs and develop a **machine learning model** to predict outcomes for our home team's first season. 

### Questions we hope to answer with the data

The following figure shows the column headers which are essentially the input FEATURES (X) and the last “outcome” column is the OUTCOME (y) for the Machine Learning Model.
As the headers say, we expect to relate a good prediction of outcome based on the feature columns.

![image](https://user-images.githubusercontent.com/58155187/127813723-fc574beb-701c-4300-a891-fe95db09245a.png)

### Data Exploration

In the data exploration stage, each member worked on their own .csv file to understand the data content i.e., columns, empty or null values. 

The key task in exploration was - 
- To **understand** most of the abbreviated column headers using Google search and match key columns (e.g., Team / CLub) with all 4 .csv files;
- **Deciding** which columns seem insignificant in decision making and may be dropped; 
- **Identify**ing columns with data anomaly which needed to be cleaned.
- Since we’re targeting to predict game outcome for our home team Austin FC and **Austin FC** has only data from 2020 onward, we decided to drop most of the “home-” related columns to make the prediction more meaningful.
- Decided to use only those data that can be **known prior** to the game starts, e.g., **team, venue, date, day, time, attendance**, and previous average performance of away teams (calculated).

### Data Analysis and Cleaning

Following steps summarize the process of data analysis including data cleaning where necessary,

1. Data **Exploration** - datatype, useful columns, deciding on NULL values
2. Data **Cleaning**:
  - Updated column titles for clarity
  - Removed all data prior to 2004 (due to most of the columns having null values)
  - Removed seemingly insignificant data column
  - Renamed mismatching club names, venue names
  - Removed duplicate entries, e.g., venue names, team names
  - Applied **regex** on a date column with anomaly in entry
  - Created **functions** to fill in NULL values
  - Reordered columns for clarity
3. **Created** Database - ERD with matches, players, goalkeepers and tables data
4. **Exported** the cleaned **.csv files to** the project folder and **major_league_soccer DB**
5. **Imported** / read clean files **from DB** for ML processing phases
6. **Neural Network model**:
  - **Preprocessing**: Binning/bucketing of categorical variables > OneHotEncoding > StandardScaler
  - Defining NN model > **Compile > Train > Evaluate**.


The following figure shows an example of **data cleaning** process,

Initially the imported `.csv` file had 6693 rows of data with `Null` values in key columns as shown in the following figure:

![Null data before](https://user-images.githubusercontent.com/58155187/128642249-b8ffb1da-8e66-4869-bde1-e2a6c182a301.png)

As we can see there are 2355 `Null` entries under the `attendance` column. This columns is a key-column for our analysis and we can't drop almost one-third of the rows because of it. So we decided to fill the null values using the **average attendance** of the same `venue` for all other matches. This is not an easy task to do manually for more than 100 unique venues. Therefore, we've deveoped an functional code using `for-if` statements, as shown below, to fill in the empty `attendance` rows.

![average_attendace_code](https://user-images.githubusercontent.com/58155187/128642423-f42476f3-6c32-4852-9529-5f258429746b.png)

The `venue` column had some duplicate venues having a slight difference in naming, e.g., both *'Cotton Bowl', "Cotton Bowl, Dallas"* are the same venue. We had to identify duplicates from 115 venues and cleaned them down to 80 unique venues, as shown below:

![duplicate venues](https://user-images.githubusercontent.com/58155187/128642572-9ef6cf5c-2c86-4b22-ae6e-4e8ea25ff07d.png)

There were 467 entries of `Null` values under `venue` column. We assumed the `home` team should play in their *home venue*, and based on this assumption we created two lists `key_teams` and `value_venues` to create a mapping **dictionary** to fill in the null venues using followin code block:

![team-venue dictionary](https://user-images.githubusercontent.com/58155187/128642735-786b86b0-f151-48a9-9cc3-ed6534c9bf39.png)

![code to fillin venue](https://user-images.githubusercontent.com/58155187/128642772-e3162015-efc6-41eb-aefc-e7a705e1b894.png)

After cleaning these 2 key-columns the dataset became almost free of `Null` values except the `time (utc)` column which later we decided to drop.

![Null data After](https://user-images.githubusercontent.com/58155187/128642842-eb7e8e42-074c-4da2-bb76-a1b4aceddf32.png)

There have been a few more cleaning steps required to get data with consistent data types.

![data_cleaning](https://user-images.githubusercontent.com/58155187/128083380-48edef5c-7b45-4041-a0ee-ace6d8f3e168.png)

### Creating an ERD for PostgreSQL Database

![QuickDBD-export](https://user-images.githubusercontent.com/58155187/128083646-835b9c1a-edad-449f-acd3-142afd558732.png)

### Creating an empty Database named "major_league_soccer" in PostgreSQL

![empty_db_mls](https://user-images.githubusercontent.com/58155187/128083845-81a91eac-7b79-478e-bbe8-fd5275f11f40.png)

### Export data from pandas DataFrame to PostgreSQL database

Exported 6 cleaned DataFrames to SQL tables and 2 tables are joined using SQL Query, as shown in the following figure,

![six_tables_to_mls_db_join](https://user-images.githubusercontent.com/58155187/128083949-ec90384f-0e70-41d9-a3b8-429acbe90cb4.png)

### Reading data from SQL Database

For Deep Learning preprocessing, data tables are imported from the SQL database as shown below,

![read_from_sql](https://user-images.githubusercontent.com/58155187/128084232-7f776d13-8a9b-482f-83b8-cf7fc510bb69.png)


## Machine Learning Model

[match_clean_NN.ipynb](https://github.com/moonem/FinalProject/blob/main/Resources/all_ipynb/match_clean_NN.ipynb)

In order to predict a team's outcome in a game we chose **Neural Network** based **Deep Learning** algorithm. As the decision is kind of binary *yes / no*, we could choose other simpler *regression* based prediction algorithm also. Since neural network based algorithm provides better accuracy even with non-linear data relationship, *we preferred Deep Learning Model* over other prediction models.

### Data Preprocessing
  
  The data on matches is imported from SQL localhost server to a jupyter notebook for preprocessing. Following image screeshots of the **MLS_matches_NN.ipynb** link: [jupyter notebook](https://github.com/moonem/FinalProject/blob/main/Resources/all_ipynb/MLS_matches_NN.ipynb) shows the steps of data preprocessing.
  
### Read data from SQL database:
  
  ![read_from_sql](https://user-images.githubusercontent.com/58155187/128084656-1c9a7470-1087-4df3-8c46-aa1b6107f6a8.png)

### Check categorical variables for OneHotEncoding:
 
 ![image](https://user-images.githubusercontent.com/58155187/128084901-7e709ac0-3058-4508-b525-374349d752c2.png)

### **OneHotEncoder** to encode categorical variables:

![image](https://user-images.githubusercontent.com/58155187/128085043-f220b549-e1c9-4a49-b9bf-3f5e07dfa03a.png)

### **Merging** `encode_df` with original `game_df`:

![encoded merge](https://user-images.githubusercontent.com/58155187/128643610-044eb88d-d5eb-4fe0-ad75-6713232c4071.png)

### Define **features (X)** and **output (y)** in the *training* and *test* dataset :

We need to **split** our **training** and **testing** data *before* fitting our **StandardScaler** instance. This <u> prevents testing data from influencing the standardization </u> function.

To build our training and testing datasets, we need to separate two values:

input values (which are our *independent variables* commonly referred to as **model features or "X"**) and **target output** ( *dependent variable* commonly referred to as **target or "y"** in TensorFlow documentation).

![image](https://user-images.githubusercontent.com/58155187/128085484-825a5f7e-f654-47b5-b776-d1ec9e284bf2.png)

### **Scaling** training and testing dataset:

![image](https://user-images.githubusercontent.com/58155187/128085568-5a33f838-9187-48a2-b463-2c0bbd8afee9.png)

### Choice of the Machine Learning Model:

Since we're working on major league soccer match data to predict the outcome whether **Win or Not**; the scope of outcome is known. Therefore, **Supervised ML Model** is a good fit for our prediction. Also, our prediction type falls under **Binary Classification**, so we chose to build a Neural Network based **Deep Learning** model for our project.

 #### Pros:

**Neural Network** based **Deep Learning Model** is a popular choice among maching learning model because of its 

- better **accuracy** in evaluating test data, and 
- ability to model **non-linear** relationship. 

#### Cons:

- Although Neural Network model is like a **blackbox and hard to explain**.
- Needs very good quality **clean data**;
- **Prone to over-fitting** model which affects the performance in matching model with real test dataset.

### Define Neural Network model

For our **input layer**, we must add the **number of input features equal to the number of variables in our feature** DataFrame.

In our **hidden layers**, we'll add **three hidden layers** with only a few neurons in each layer. To create the *second hidden layer*, we'll add another **Keras Dense class** while defining our model. All of our hidden layers will use the **relu activation** function to identify nonlinear characteristics from the input values.

In the **output layer**, we'll use the `sigmoid` activation function that will help us predict the probability that a team is winning or not.
  
  We've tried different activation functions, such as `tanh` and `linear` in middle layers and but `relu` provided slightly better result in model fitting and evaluation. Since, our intended outcome is **Win** or **Not Win**, a binary classifier, we've chosen `sigmoid` in the output layer.

![NN model match_clean](https://user-images.githubusercontent.com/58155187/128643651-8aaf2017-3f2e-4194-a4ed-61164e565467.png)

### **Compile** and **Evaluate** the NN model:

During compilation, we've tried both `binary_crossentropy` and `mean_squared_error` to measue loss in model evaluation. We found `mean_squared_error` provides almost 10 times  **lower loss** metric for almost similar percentage of accuracy.

For **optimizer** `adam` is widely used and effective for NN model.

**loss** with `binary_crossentropy`:

![loss(binaryEntropy)](https://user-images.githubusercontent.com/58155187/128643751-89434ee1-f379-4300-ab13-3938fc753675.png)

**loss** with `mean_squared_error`:

![loss(mse)](https://user-images.githubusercontent.com/58155187/128643879-f47d41a9-b14b-4cb5-8984-eb34ae0f0d9e.png)

### Model Evaluation:

It looks like the model is fit pretty well in 100 epochs with less than **1% loss**.

While running on **test-data** the model is evaluated to predict the **Win** outcome of a game **57.6% times accurate**. We got an accuracy of 51% and 53% in our previous models. We went back to our dataset and added some more features prepared from "average grouped" data. This addition along with **optimization** of the model brough us a good increase in accuracy.

This is not a high accuracy metric, but based on our available realistic input data prior to a game starts, this prediction seems to be **fair enough**

## GitHub

- The `main` branch has all data and codes in **Resources** folder. A copy of files relevant to *Segment-4* of the project, have been kept inside the **Segment_4** folder under the **FinalProject** folder; url: [Segment_4](https://github.com/moonem/FinalProject/tree/main/Segment_4).
- A separate **match_clean_NN.ipynb** file is created to design the machine learning model; [file url:](https://github.com/moonem/FinalProject/Resources/all_ipynb/match_clean_NN.ipynb)
- Communication protocols are defined in the **Readme.md** file for the project team.
- Outline of the project is described in the Readme.md which is updated regularly as the teamwork is progressing every week.
- Each of 4 team members have their individual brances. 
- Each team member is uploading their commits to their respective branch and/or to the `main` and 'Segment_4' project folders.

## Database

Details of PostgreSQL database creation, exportin files to database, importing from database, joining files using SQL Query - have been discussed in the previous sections.

## Dashboard

We are presenting our analysis on Tableau, an interactive data visualization tool. The presentation is in the form of a multi-dashboard Tableau story hosted online on [Tableau Public.](https://public.tableau.com/app/profile/sean3063/viz/MLSDashboard/Dashboard1) 

Our dashboards incorporates historical data in the form of various team and player statistics from previous MLS seasons. We filtered our data by team and using team logo images as part of our filter-selection features. After selecting a team logo, the dashboard will present statistics like last year's top scorer, the team's record over the years, and data on average stadium attendance rates, among others.

[dashboard image 1](https://drive.google.com/file/d/1rbAqDhGwEDbDec6BgJ0yeLay89Pw2nre/view?usp=sharing)

[dashboard image 2](https://drive.google.com/file/d/1jx0aIF-jvOsZPLnrrDvHEjhoXfBbam2q/view?usp=sharing)

[dashboard image 3](https://drive.google.com/file/d/1I_BacWb6ySUhYBZGA913LTiOZdxV3r2-/view?usp=sharing)

[dashboard Movie](https://drive.google.com/file/d/1tDt5H8qEujCfAFWTHFXx7RLfz_4uyTQe/view?usp=sharing)

