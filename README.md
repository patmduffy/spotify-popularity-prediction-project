# Spotify Popularity Predition Project

## **PROJECT OVERVIEW**
### This project analyzes numerical and categorical features of Spotify data set of random songs to best predict the popularity of songs based off their features (such as "loudness", "energy", and "playlist_genre") to see how an artist can create a song that becomes popular on Spotify. In doing this, I employed exploratory data analysis (EDA), predictive modeling, and clustering, among other steps and processes. These steps are utilized to determine the most influential features in song popularity, what model and variable combination best estimates this popularity, as well as what "type" (or cluster) of song most consistently produces top hits.

## **DATASET DESCRIPTION**
#### -Source: Kaggle
#### -Size: 4,389 total tracks x 29 features per track
#### -Target: track_popularity (scale from 0-100, which is a measure based off how popular the song is according to Spotify's statistics)

## **METHODS AND PROCESS**
### <ins>Import Data</ins>
#### -Data was inintially stored in two csv files: 'high_popularity_spotify_data.csv' and 'low_popularity_spotify_data.csv'
#### -Combined datasets into a single dataframe named 'data_all'
### <ins>Data Preprocesssing</ins>
#### -Remove missing values, check unqiue number of unqiue values, change the 'key' column, and remove irrelevant columns
#### -Transformed data for more desirable distributions, including: 
##### -Removed 'key' column for high frequency at 4 value
##### -Removed upper outliers in 'duration_ms' column
##### -Log-transformed 'speechiness' and 'loudness' distributions to reduce skew
##### -Transform 'instrumentalness' into a binary column
### <ins>Exploratory Data Analysis (EDA)</ins>
#### -Display cleaned data and check for correlation and multicolinearity
#### -Identify features that are could be more influential in predicting popularity
### <ins>Numerical Model</ins>
#### -Test linear regression and random forest regression models to reach highest accuracy
#### -Calculate relevant statistics, compare residuals vs predictons (for linear regression), and evalutate feature importance (for random forest regression)
### <ins>Categorical Model</ins>
#### -Split features into "low", "medium", and "high" bins, in hopes of being more usable for artists in estaimting the values of features
#### -Use linear regression and random forest regression to achieve the greatest accuracy
#### -Use most accurate model to create function that utilizes the top 7 influential features low/medium/high values to estimate song popularity
### <ins>Classification Model</ins>
#### -Use elbow and sillhouette method to determing number of clusters for data grouped based off top 5 features used in previous classification function
#### -Analyze results and which clusters result in more/less popular songs

## **RESULTS**
#### -Numeric Model: Achieve a mean absolute error of 11.086 using the random forest regression incorporating all variables
#### -Categorical Model: Achieve a mean absolute error of 15.111 using a linear regression model for a usable function which bases its estimation of the answers to 7 yes or no questions regarding song charactersitics
#### -Classification model: Split songs in 6 categories, with songs with high energy, low acousticness, and low instrumentalness consistently having the highest popularity (clusters 0 and 3)

