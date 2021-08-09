# Customer churn prediction of music streaming service

For this project, we work with data collected on Sparkify, a digital music platform similar to Spotify. Predicting customers who might want to cancel the service. The dataset is a fictional, generated by Udacity program of Data Science Nano-degree project. 

The main goal of this project is to use a subset of data (128MB out of 12 GB full data set), building the workflow by Spark APIs with that it is expected can be extended in big data analysis, to make the prediction for the customer churn.

## Overview of the data
This dataset contains 286,500 lines of log in 18 features. They are generated by 225 users after removing a small part of log that lack the records of userId.

<pre>
 |-- artist: string (nullable = true)
 |-- auth: string (nullable = true)
 |-- firstName: string (nullable = true)
 |-- gender: string (nullable = true)
 |-- itemInSession: long (nullable = true)
 |-- lastName: string (nullable = true)
 |-- length: double (nullable = true)
 |-- level: string (nullable = true)
 |-- location: string (nullable = true)
 |-- method: string (nullable = true)
 |-- page: string (nullable = true)
 |-- registration: long (nullable = true)
 |-- sessionId: long (nullable = true)
 |-- song: string (nullable = true)
 |-- status: long (nullable = true)
 |-- ts: long (nullable = true)
 |-- userAgent: string (nullable = true)
 |-- userId: string (nullable = true)
</pre>

## Data analysis
### Exploratory Data Analysis:
Many features are visited and explored, can be roughly divided into three categories: 
1. time-related variables, ex: days passed after the user registered, average time user spent on a session, ect
2. about the users' page access activities, ex: thumbs Up/Down, songs added to the playlist, etc
3. users' profile, ex: gender, location, etc

Some variables can be extracted directly from the data file, and some need a little processing.
All characteristics are carefully compared whether there is a difference between churn and non-churn users. 

### Modeling and Results:
Some features that are more distinguishable between churn and non-churn are selected to be included in the model. 
Logistic Regression, Random Forest, and Gradient-boosted Trees are tested as the algorithm with hyper-parameters tunning and cross-validation applied. In the test set, a preliminary F1-score is reached by Random Forest at 0.76.  

## Dependencies/Libraries:
Coding in Python3 in Jupyter Notebook IDE, the following libraries are expected: 
- PySpark
- Numpy
- pandas
- Matplotlib
- Seaborn

## Documentation:
To walk through with my process, ideas, and discussion, you can find it in my article post [here](https://kate-d.medium.com/customer-churn-prediction-of-music-streaming-service-534e4378e87b).  
The corresponding code is in `Sparkify.ipynb`, or nbviewer version [here](https://nbviewer.jupyter.org/github/yduh/Churn-Prediction/blob/main/Sparkify.ipynb).
