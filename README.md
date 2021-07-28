# FinalProject

  ## Win/Loss Prediction in Major League Soccer using Deep Learning model
  An overvall summary of our project and Segment 1 deliverables can be found here. Outside of joint efforts accomplishing the below, individual contributions are outlined in README files located within each team member's individual branches. 
  
## Project Goal 

Predict win/loss outcomes of a specified team in the **Major League Soccer (MLS)** through a machine learning model that utilizes match statistics from the **2001-2021** seasons. 

Multiple variables, such as **player** and **team performance**, **home/away status**, and **stadium attendance**, will be analyzed to gauge their impact and **predict potential match outcomes**.

In addition to a machine learning model that predicts future match outcomes, the team will develop a Tableau dashboard that provides additional insight into the historical performance of MLS franchises, including data on win/loss records and top scorers.

Our team decided on this project because our home city, Austin, Texas, recently got its first MLS soccer club. Austin FC, a new member of the Western Conference, has had a hot start to the 2021 season. We wanted to dig into the historic perforamance of rival clubs and develop a model to predict outcomes for our home team's first season. 

## Teamwork

  ## Segment 1
  
Our team has 4 members. Coincidentally our data source has also 4 key *.csv* files for the analysis. Each team-member cleaned one *.csv* data using **ETL** process and pushed to their respective branches as shown below. 

1. Sean Tyson - all_tables_cleaned.csv, QuickDBD-export.png; [SeanTyson_Branch](https://github.com/moonem/FinalProject/tree/seantyson_branch/SeanTyson)
2. M A Moonem - all_players_clean.csv; [Moonem_Branch](https://github.com/moonem/FinalProject/tree/moonem_branch/Resources)
3. Daniel Gonzalez - matches_2004to2021.csv; [Daniel_Branch](https://github.com/moonem/FinalProject/tree/Daniel_Project/DanielGonzalez)
4. Ben Reed - all_goalkeepers_clean.csv; [Ben Reed Branch](https://github.com/moonem/FinalProject/tree/main/BenReed)

## Communication Protocols

Team communication and project planning has been conducted through live video calls over **Zoom** and asynchronously through a project-specific **Slack** channel. The team also supplied contact details in the form of *cell phone* numbers and *emails* for any urgent tasks/questions.  

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
  
  ![MLS data quality](/Resources/MLS_data_quality.png)
  
  Fig. 1. MLS data sufficiency and adequacy information provided by the data source.
  
  From Fig. 1, we see that data on all relevant items is available for the period 2012-2020. Two key features - *Results* and *Player Stats* - are also fully available from 1996-2020, which should provide more data if required.

  ### Sample Database

A sample dataset and ERD can be seen below. This dataset will be supplemented with additional datasets that are still currently being cleaned that cover topics such as goalkeeper performance, top goal scorers, and stadium details.

![Sample_Dataset](https://github.com/moonem/FinalProject/blob/main/Resources/Sample_Dataset.png)
![Sample_Dataset_ERD](https://github.com/moonem/FinalProject/blob/main/Resources/Sample_ERD.png)
