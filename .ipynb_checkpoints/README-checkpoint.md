# Disaster Response Pipeline Project
## Table of Contents
1. [Project Overview](#project-overview)
2. [Project Components](#project-components)
3. [File Description](#file-description)
4. [Installation](#installation)

## Project Overview
This project is part of the [Udacity Data Science Nano Degree Program](https://www.udacity.com/course/data-scientist-nanodegree--nd025)and supported by [Appen](https://appen.com/). This project will analyze a [data set](https://github.com/petitblue/Udacity_Data_Science/tree/main/Project%202%20Disaster%20Response%20Pipeline/data) containing real messages that were sent during disaster events. Those messages are sent from social media or from disaster response organizations. This project will build a ETL pipeline to load and process data, and a machine learning pipeline to classify those messages so as to send them to an appropriate disaster relief agency.
## Project Components
There are three components in the project.
### 1. ETL Pipeline
- Loads the message.csv and categories.csv files 
- merges two datasets
- clean data 
- stores it in a SQLite database
### 2. ML Pipeline
- Load cleaned data from database
- Build a test processing and maching learning pipline
- Used different models and evaluate accuracy
- Apply feature union to improve model 
- Train and tunes a model using GridSearchCV
### 3. Flask Web App
There is a web app where an emergency worker can input a new message and get classification results in several categories. The web app will also display visualizations of the data.


## File Description
```sh
- README.md: read me file
- ETL Pipeline Preparation.ipynb: ETL pipeline preparation code
- ML Pipeline Preparation.ipynb: ML pipeline preparation code
- \app
	- run.py: flask file to run the app
   	- \templates
		- master.html: main page of the web application 
		- go.html: result web page
- \data
	- disaster_categories.csv: categories dataset
	- disaster_messages.csv: messages dataset
	- DisasterResponse.db: disaster response database
	- process_data.py: ETL process to clean up data
- \model
	- train_classifier.py: classification code
   	- custom_extractor.py: python package that build a class to extract disaster related words
	- classifier.pkl: model saved as a pickle file
```

## Installation
### Devendencies :
   - [python (>=3.6)](https://www.python.org/downloads/)  
   - [pandas](https://pandas.pydata.org/)  
   - [numpy](https://numpy.org/)  
   - [sqlalchemy](https://www.sqlalchemy.org/)  
   - [nltk](https://www.nltk.org/)  
   - [sys](https://docs.python.org/3/library/sys.html)  
   - [plotly](https://plotly.com/python/)  
   - [sklearn](https://sklearn.org/)  
   - [joblib](https://joblib.readthedocs.io/en/latest/)  
   - [flask](https://flask.palletsprojects.com/en/2.0.x/)  
   
 ### Download and Installation
 ```sh
git clone https://github.com/petitblue/disaster-response-pipeline.git
```
 
 While in the project's root directory disaster-response-pipeline run the ETL pipeline that cleans and stores data in database.
 
 ```sh
python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db
```

 Next, run the ML pipeline that trains the classifier and save it.
```sh
python model/train_classifier.py data/DisasterResponse.db model/classifier.pkl
```
Next, change directory into the app directory and run the Python file run.py.
```sh
cd app
python run.py
```
Finally, go to http://0.0.0.0:3001/ or http://localhost:3001/ in your web-browser.
Type a message input box and click on the Classify Message button to see the various categories that your message falls into.

#### Screenshot of the web app
![Alt text](https://github.com/petitblue/disaster-response-pipeline/blob/main/web_message_classifier.png)
![Alt text](https://github.com/petitblue/disaster-response-pipeline/blob/main/genre_cts.png)
![Alt text](https://github.com/petitblue/disaster-response-pipeline/blob/main/distribution_message_by_genre.png)