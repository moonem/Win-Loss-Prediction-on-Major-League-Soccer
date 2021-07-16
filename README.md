# FinalProject

  ## Win/Loss Prediction in Major League Soccer using Deep Learning model

## Goal 

Predict win/loss outcomes of a specified team in the **Major League Soccer (MLS)** through a machine learning model that utilizes match statistics from the **2001-2021** seasons. 

Multiple variables, such as **player** and **team performance**, **home/away status**, and **stadium attendance**, will be analyzed to gauge their impact and **predict potential match outcomes**.

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
  xzczxczxcx
  
