# goodreads

Goodreads Books Rating Prediction Model

***Python version***

Python 3.7.13 (default, Mar 28 2022, 08:03:21) [MSC v.1916 64 bit (AMD64)] :: Anaconda, Inc. on win32

***environment***
This project was coded with anaconda and Jupyter notebook

***Packages used***

pandas as pd

numpy as np

matplotlib inline

pyplot as plt

seaborn as sns

datetime, date, time

plotly.express as px

***Data***

One file for the data : "books.csv", at the root the directory


***Description of the project***

With this project I tried to build a model to predict the average rating of books in a Goodreads Dataset I was provided with.

The dataset was loaded in a Jupyter Notebook. 

Then I started to explore the data, and though I didn’t find NAs at first, I rapidly saw that some columns had “0” values typed in, so I checked column by column.

I did some pruning of the dataset on :
- the average_rating column
- the text_reviews_count column 
- the num_pages column (for this one I also replaced some values by the mean of the column)
- the language_code column

For the publication_date column I converted it into date format

I added some answers to questions I was asking myself :
- What are the 10 years with the most books published?
-	What are the 10 most represented Publishers in the dataset?
-	What are the 10 most represented Authors in the dataset?
-	In average which language has the books with the more pages ?

Then came the moment to prepare the dataset for Machine Learning:
- I transformed language_codes in dummies variables
- for the date part I only kept the years as integers
- I dropped the unuseful columns

I did a short graphic analysis of the main relationships through the dataset

After all I began the Machine Learning part and loaded regression models.
I tried Linear Regression, Decision Tree and Random Forest from the scikit learn library.

For evaluating those models, I choosed:
-	 MAE / Mean Absolute error : to have a simple and intuitive metric
-	 MSE / Mean Squared error : to have a better understanding of the large errors
-	 ME /Maximum Error : this one is less relevant but it was to know what was the largest error in the predictions

All three did a fairly great job, the Random Forest one was clearly the best.

At last I tried to improve those results with the exclusion of the books with the less ratings.

The results were a little better, again the random forest was the best model.
 
