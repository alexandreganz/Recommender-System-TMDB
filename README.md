# **Recommender-System-IMDB**
This repository explains in depth optimization functions and a step by step how to set up a movie recommendation system using base inputs to promote similar movies to users

# Use Case

- Use Case Summary:
- Objective Statement:
  * Gain insights on how to produce a recommendation system for users.
  * Understand best practices for analyzing a dataset and consequently functions to make the recommendation model possible.
  * Make sure the system is consistent, following a standard for similar movies to be recommended to users.
  
 - Challenges:
  * Large size of data, with many features (+ 26 ratings and 45k+ movies).
  * Lack of a test section to prove if the recommendations were a success.
  * Due to the volume of the data a specific approach was determined for its processing in order not to deteriorate the productivity of the analysis.
  
- Methodology / Analytic Technique:
  * Descriptive analysis
  * Graph analysis
  * Recommender systems
  * Prediction
  * Ensemble
  * Random Forest
  
 - Expected Outcome:
  * Make a coherent prediction and recommendation of the movies involved for users.
  * No data leakage to harm the model.
  
 # Data Understanding
  - Source Data: The Movie Database (TMDB) API, a public dataset containing more than 26 million ratings and 45 thousand movies. [link](https://developers.themoviedb.org/3/getting-started/introduction)
  - The dataset contains more than 45k rows with 24 columns
  - The Data Dictionary can be found inside of the jupyter [notebook](https://github.com/alexandreganz/Recommender-System-IMDB/blob/main/Python%20Functions%20and%20Recommender%20System.ipynb)

# Data Preparation
  - Code Used:
  - Python Version 3.9.7
  - Packages: Pandas, numpy, ast, sklearn, seaborn, matplotlib

# Data Cleansing

- Adult filters and missing values were removed from the analysis, leaving more than 45,000 lines to analyze.
- In general, as it is a very popular database in the data community, little cleaning was required and to focus on the main theme (recommendation system) the emphasis will be more on how the modeling was done to show that all steps were accomplished.

# Exploratory Data Analysis

- What are the most popular generics in databases?

![genres](https://i.imgur.com/KzLSgbP.png)

As we can see, the drama genre is very popular in the addiction base, having the largest number of movies produced. As our goal is not specifically to analyze the different movies or any other feature in the data, we want to transform the categorical columns we already have and make a movie prediction containing the test part of the dataset

- First Attempt of Prediction

![first_matrix](https://i.imgur.com/5gOjs9Z.png)

After doing all the data treatment (numerical features, binary features, etc) we can notice for the first prediction attempt that the confusion matrix came out extremely high, and as we should always be suspicious of such data, approximately the specificity was **1** and the sensitivity **0.25**. Most likely our model has a leak that must be treated.

- Second Attempt of Prediction

![second_matrix](https://i.imgur.com/rRhG1hP.png)

It was possible to notice that the columns containing genera in or the quantity of genera was an indicator that harmed the prediction, removing them the accuracy fell to **90%** and the sensitivity to **25%**.


- Building a Simple Recommender System
![recommender](https://i.imgur.com/xjZqgS1.png)

To perform the first stage of the recommendation, we will use the Pearsons correlation between movies and filter by the number of ratings given so as not to harm the final result of the recommendation (a few ratings may imply a high correlation and thus harm the output).


  
  
  
  
  
  
  
