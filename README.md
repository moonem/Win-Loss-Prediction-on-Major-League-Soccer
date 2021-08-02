# FinalProject

  ## Win/Loss Prediction in Major League Soccer using Deep Learning model
  An overvall summary of our project and Segment 1 deliverables can be found here. Outside of joint efforts accomplishing the below, individual contributions are outlined in README files located within each team member's individual branches. 
  
  #### Reason to choose this topic
  
  After forming the team for the Final Project, we explored few other topics to choose from but most team members showed passion to work on **Major League Soccer** data and thought this would be interesting to predict a team's outcome using Deep Learning model. 
  
## Project Goal 

Predict win/loss outcomes of a specified team in the **Major League Soccer (MLS)** through a machine learning model that utilizes match statistics from the **2001-2021** seasons. 

Multiple variables, such as **player** and **team performance**, **home/away status**, and **stadium attendance**, will be analyzed to gauge their impact and **predict potential match outcomes**.

In addition to a machine learning model that predicts future match outcomes, the team will develop a Tableau dashboard that provides additional insight into the historical performance of MLS franchises, including data on win/loss records and top scorers.

Our team decided on this project because our home city, Austin, Texas, recently got its first MLS soccer club. Austin FC, a new member of the Western Conference, has had a hot start to the 2021 season. We wanted to dig into the historic perforamance of rival clubs and develop a model to predict outcomes for our home team's first season. 

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

  ## Segment 1
  
Our team has 4 members. Coincidentally our data source has also 4 key *.csv* files for the analysis. Each team-member cleaned one *.csv* data using **ETL** process and pushed to their respective branches as shown below. 

1. Sean Tyson - all_tables_cleaned.csv, QuickDBD-export.png; [SeanTyson_Branch](https://github.com/moonem/FinalProject/tree/seantyson_branch/SeanTyson)
2. M A Moonem - all_players_clean.csv; [Moonem_Branch](https://github.com/moonem/FinalProject/tree/moonem_branch/Resources)
3. Daniel Gonzalez - matches_2004to2021.csv; [Daniel_Branch](https://github.com/moonem/FinalProject/tree/Daniel_Project/DanielGonzalez)
4. Ben Reed - all_goalkeepers_clean.csv; [Ben Reed Branch](https://github.com/moonem/FinalProject/tree/main/BenReed)

  ## Segment 2
  
  ### Data Exploration
  
  In the data exploration stage, each member worked on their own .csv file to **understand the data content** i.e., columns, empty or null values. The key task in exploration was to understand most of the abbreviated column headers using Google search and **match key columns** (e.g., Team / CLub) with all 4 .csv files.
  
  ### Forming a Database
  
  As we're working on 4 separate datasets an **entity relations diagram (ERD)** has bee formed to explore potential relations among the datasets across commmon columns.
  
 ![ERD](https://github.com/moonem/FinalProject/blob/main/Resources/Images/QuickDBD-export.png)
  
The MLS_FinalProject database was then created in pgAdmin. The following four tables were created to conside with our four csv files. 
- Season_Tables
- Matches
- Players
- Goalkeepers

![Step_4](https://github.com/moonem/FinalProject/blob/main/SeanTyson/Step_4.png)

![Step_5](https://github.com/moonem/FinalProject/blob/main/SeanTyson/Step_6.png)

  ### Data Analysis
  
  This has been a time-consuming task to analyze the datasets. Since the data was in the **.csv** format, we didn't have to do any *RegEX* operation on the data, rather it took a good effort to clean some anomaly in a few column entry's **datatype**, clean **scrambled data**, matching **club names** among multiple .csv files.
  
  For example, the *all_players_2004to2020.csv* file was imported to **Pandas** dataframe for further analysis. The following figure shows that the source data has abbreviated *column headers* and a lot of **NaN** values under certain columns.
  
  ![image](https://user-images.githubusercontent.com/58155187/127281715-63f86cfe-f99d-408a-974f-3d679be579a5.png)

All the abbreaviated column headers have been **renamed** by replacing them with more elaborative and meaningful terms, as shown below,

![image](https://user-images.githubusercontent.com/58155187/127282186-fef000f5-dce5-4088-80bd-f1cf073ce508.png)

Next, **null values** under the **Club** column have been removed. Since our goal is to predict a team/club outcome in a game, we need **Club Names** without any null values in this column. So we **dropped** null values as shown below,

![image](https://user-images.githubusercontent.com/58155187/127282878-0250d836-128a-40af-8394-75e2dfed0ccc.png)

The abbreviated Club names have been **replaced** with the full name of the club, e.g., 'MIA':'Inter Miami CF'. Finally, a **cleaned** dataset having **25 columns** and **691 rows** of non-null data with consistent **DataType** has been achieved as shown below,

![image](https://user-images.githubusercontent.com/58155187/127283879-6e1311c6-9413-4b35-a5ac-10e9cb9e4348.png)

Similar data analysis steps have been taken by all 4 team members to clean respective data sets.

### Machine Learning Model

[MLS_matches_NN.ipynb](https://github.com/moonem/FinalProject/blob/main/Segment_2/MLS_matches_NN.ipynb)

In order to predict a team's outcome in a game we chose **Neural Network** based **Deep Learning** algorithm. As the decision is kind of binary *yes / no*, we could choose other simpler *regression* based prediction algorithm also. Since neural network based algorithm provides better accuracy even with non-linear data relationship, *we preferred Deep Learning Model* over other prediction models.

  #### Data Preprocessing
  
  The data on matches is imported to a jupyter notebook for preprocessing. Following image screeshots of the **MajorLeagueSoccer_NN.ipynb** link: [jupyter notebook](https://github.com/moonem/FinalProject/blob/main/Resources/all_ipynb/MLS_players_NN.ipynb) shows the steps of data preprocessing.
  
  ![image](https://user-images.githubusercontent.com/58155187/127307165-06180638-ea58-446e-b0a9-ff51f62de6b7.png)
  
  ![image](https://user-images.githubusercontent.com/58155187/127307317-6a13b6dd-d543-4882-a1d8-547921702711.png)

![image](https://user-images.githubusercontent.com/58155187/127307583-6f43715e-663b-419c-8c6f-851b1389c52b.png)

![image](https://user-images.githubusercontent.com/58155187/127307662-2b4e52d3-c2bc-4ea2-8761-3708d982523f.png)

![image](https://user-images.githubusercontent.com/58155187/127307738-3dc706ea-2e40-4251-b28a-9b62d3e9a992.png)


#### Training and Testing dataset

We need to **split** our **training** and **testing** data *before* fitting our **StandardScaler** instance. This <u> prevents testing data from influencing the standardization </u> function.

To build our training and testing datasets, we need to separate two values:

input values (which are our *independent variables* commonly referred to as **model features or "X"**) and **target output** ( *dependent variable* commonly referred to as **target or "y"** in TensorFlow documentation).

![image](https://user-images.githubusercontent.com/58155187/127308070-7a56ff26-f0ac-4241-ba23-b86ec43f806a.png)

![image](https://user-images.githubusercontent.com/58155187/127308168-95e5d5d0-8770-4bab-8dda-010d76d2ff66.png)

### Dashboard

We will be presenting our analysis on Tableau, an interactive data visualization tool. The presentation will be in the form of a multi-dashboard Tableau story hosted online on Tableau Public. 

Our dashboards will incorporate historical data in the form of various team and player statistics from previous MLS seasons. We will be filtering our data by team and using team logo images as part of our filter-selection features. After selecting a team logo, the dashboard will present statistics like last year's top scorer, the team's record over the years, and data on average stadium attendance rates, among others.




