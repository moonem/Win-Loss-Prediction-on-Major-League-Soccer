# This Readme file is to highlight the project team contribution as per the rubric for Segment-2.

## Presentation

[google slides](https://docs.google.com/presentation/d/1b0U9tTp1LIhrh8zkYAMvX0BZqA8qRPFrOiRTJiwtGKI/edit?usp=sharing)

### Selected Topic

The topic has been selected as **"Win/Loss Prediction in Major League Soccer using Deep Learning model"**.

### Reason behind choosing this topic

Our team decided on this project because our home city, Austin, Texas, recently got its first MLS soccer club. **Austin FC**, a new member of the Western Conference, has had a hot start to the 2021 season. We wanted to dig into the historic perforamance of rival clubs and develop a **machine learning model** to predict outcomes for our home team's first season. 

### Description of the Source of Data

**Data Source** is the **Kaggle** data, Major League Soccer Dataset - by Joseph Mohr, last updated 11th July, 2021; version 34. The weblink: https://www.kaggle.com/josephvm/major-league-soccer-dataset

  This dataset contains player, game, event, and table data from Major League Soccer (MLS).

  There is currently information on over 6000 matches and almost 420,000 events from those matches.

### Questions we hope to answer with the data

![image](https://user-images.githubusercontent.com/58155187/127813723-fc574beb-701c-4300-a891-fe95db09245a.png)

## Machine Learning Model
In order to predict a team's outcome in a game we chose **Neural Network** based **Deep Learning** algorithm. As the decision is kind of binary *yes / no*, we could choose other simpler *regression* based prediction algorithm also. Since neural network based algorithm provides better accuracy even with non-linear data relationship, *we preferred Deep Learning Model* over other prediction models.

  ### Data Preprocessing
  
  The data on matches is imported to a jupyter notebook for preprocessing. Following image screeshots of the **MajorLeagueSoccer_NN.ipynb** link: [jupyter notebook](https://github.com/moonem/FinalProject/blob/main/Resources/all_ipynb/MLS_players_NN.ipynb) shows the steps of data preprocessing.
  
  ![image](https://user-images.githubusercontent.com/58155187/127307165-06180638-ea58-446e-b0a9-ff51f62de6b7.png)
  
  ![image](https://user-images.githubusercontent.com/58155187/127307317-6a13b6dd-d543-4882-a1d8-547921702711.png)

![image](https://user-images.githubusercontent.com/58155187/127307583-6f43715e-663b-419c-8c6f-851b1389c52b.png)

![image](https://user-images.githubusercontent.com/58155187/127307662-2b4e52d3-c2bc-4ea2-8761-3708d982523f.png)

![image](https://user-images.githubusercontent.com/58155187/127307738-3dc706ea-2e40-4251-b28a-9b62d3e9a992.png)

### Training and Testing dataset

We need to **split** our **training** and **testing** data *before* fitting our **StandardScaler** instance. This <u> prevents testing data from influencing the standardization </u> function.

To build our training and testing datasets, we need to separate two values:

input values (which are our *independent variables* commonly referred to as **model features or "X"**) and **target output** ( *dependent variable* commonly referred to as **target or "y"** in TensorFlow documentation).

![image](https://user-images.githubusercontent.com/58155187/127308070-7a56ff26-f0ac-4241-ba23-b86ec43f806a.png)

![image](https://user-images.githubusercontent.com/58155187/127308168-95e5d5d0-8770-4bab-8dda-010d76d2ff66.png)

## GitHub

- The `main` branch has all data and codes in **Resources** folder. A copy of files relevant to *Segment-2* of the project, have been kept inside the **Segment_2** folder under the **FinalProject** folder.
- A separate **MLS_matches_NN.ipynb** file is created to design the machine learning model; [file url:](http://localhost:8888/notebooks/UT_DataScience/UTA-VIRT-DATA-PT-02-2021-U-B/FinalProject/Segment_2/MLS_matches_NN.ipynb)
- Communication protocols are defined in the **Readme.md** file for the project team.
- Outline of the project is described in the Readme.md which is updated regularly as the teamwork is progressing every week.
- Each of 4 team members have their individual brances. 
- Each team member is uploading their commits to their respective branch and/or to the `main` project folder.

## Database

[Database snapshots are in the Readme @ Sean Tyson branch](https://github.com/moonem/FinalProject/tree/seantyson_branch/SeanTyson)

## Dashboard

We will be presenting our analysis on Tableau, an interactive data visualization tool. The presentation will be in the form of a multi-dashboard Tableau story hosted online on Tableau Public. 

Our dashboards will incorporate historical data in the form of various team and player statistics from previous MLS seasons. We will be filtering our data by team and using team logo images as part of our filter-selection features. After selecting a team logo, the dashboard will present statistics like last year's top scorer, the team's record over the years, and data on average stadium attendance rates, among others.
