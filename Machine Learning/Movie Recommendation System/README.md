# Project: Movie Recommendation with MLlib - Collaborative Filtering (implementation 3)  
## Recommendation System is a filtration program whose prime goal is to predict the “rating” or “preference” of a user towards a domain-specific item or item. This project will implement movie recommendation by Collaborative Filtering technology.
<img width="380" alt="image" src="https://user-images.githubusercontent.com/55336314/203538310-30eaf328-24c6-4118-b9b4-4d8988c696cf.png">


## Step 1: Study PySpark Collaborative Filtering with ALS (local copy pdf, html)
* Pyspark code (ipynb)
* data
  * movies.csv - movieId, title, genere
  * ratings.csv - 2.37 MB download
  * tags.csv - userId, movieId, tag, timestamp
## Step 2: Study Colab
* Getting start with Colab
* Project Falling Detection: Python + kNN + Colab
## Step 3: Experiment Pyspark code (ipynb) of PySpark Collaborative Filtering with ALS
* ### Step 3.1: Download the Pyspark code (ipynb)
* ### Step 3.2: Upload the ipynb file to your Colab
* ### Step 3.3: Experiment Pyspark code (ipynb) by modifying the ipynb file
* ### Step 3.4: Save the modified ipynb file as py format
* ### Step 3.6: Save the modified ipynb file as HTML format which can be used on Step 5 of this project
* ### Step 3.5: Run the py file saved at Step 3.4 on GCP
  * Set up PySpark on GCP
  * Prepare Data in HDFS
    * hdfs dfs -mkdir hdfs:///mydata 
    * hdfs dfs -put movies.csv hdfs:///mydata
    * hdfs dfs -put ratings.csv hdfs:///mydata
  * Prepare the program
  * Running the program with Pyspark
***
More ditals: 
[slides](https://docs.google.com/presentation/d/1QqQJ0hqs0OLTGDbJoc9eOw18vna-GHqJjsqty7JlnuE/edit?usp=sharing)
