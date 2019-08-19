# Udacity Data Scientist Nanodegree program
## Disaster response pipelines

## Table of Contents
1. [Description](#description)
2. [How to Use](#how_to_use)
    1. [Dependency](#dependency)
    2. [Installation](#installation)
    3. [Run](#run)
3. [File Descriptions](#file_description)
4. [Results](#results)
    1. [Web app](#web_app)
    2. [Things to be improved](#things_to_be_improved)
5. [License](#license)
6. [Acknowledgements](#acknowledgements)

## Description <a name="description"></a>

This is one of 2nd term projects of Data Science Nanodegree Program by Udacity. The goal of the project is to create a model using a data set containing real messages given by [Figure Eight](https://www.figure-eight.com) to classify disaster messages. To complete this, three process were used in order as follows.

1. ETL Pipeline : Original messages are preprocessed(extraction, transformation, and loading) to be fed for a machine learning pipeline.
2. ML pipeline : a model is built and trained with data from ETL pipeline to calssify text messages.
3. Flask Web App : A web app contains the visual summary of a dataset used training a model and a section that a user can input a message to get the result of classification.


## How to Use<a name="how_to_use"></a>
### Dependency<a name="dependency"></a>
The code should run with no issues using Python versions 3.* with the libararies as follows.
- Numpy, Pandas, Sqlite3, SQLalchemy, Scikit-Learn, Pickle, NLTK  for ETL and ML pipelines.
- Flask, Plotly for Flask web app.

### Installation<a name="installation"></a>
Clone the repositor below.
`https://github.com/dalpengholic/Udacity_Disaster_response_project.git`

### Run<a name="run"></a>
1. Run the following commands in the project's root directory to set up your database and model.

- To run ETL pipeline that cleans data and stores in database
`python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
- To run ML pipeline that trains classifier and saves
`python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
`python run.py`

3. Open http://0.0.0.0:3001/ 
        

## File Descriptions<a name="file_description"></a>
```
├── app
│   ├── run.py
│   └── templates
│       ├── go.html
│       └── master.html
├── data
│   ├── disaster_categories.csv
│   ├── disaster_messages.csv
│   ├── DisasterResponse.db
│   ├── process_data.py
├── models
│   ├── classifier.pkl
│   └── train_classifier.py
├── notebooks
│   ├── ETL Pipeline Preparation.ipynb
│   ├── ML Pipeline Preparation.ipynb
├── README.md
```

## Results<a name="results"></a>
### Web App<a name="web_app"></a>
1. Main page of the web app. It contains the two plots, which are the summary of statistic of a training dataset. 
The first plot shows the distribution of message genre. The second plot shows frequency of categories
![main page](https://github.com/dalpengholic/Udacity_Disaster_response_project/blob/master/sample/main.png)

2. Result of input new message on the web app. When a user input a new message about disaster, the trained model classifies where the message belongs to.
![search page](https://github.com/dalpengholic/Udacity_Disaster_response_project/blob/master/sample/search.png)

### Things to be improved<a name="things_to_be_improved"></a>
The model used in the web app was trained with an imbalanced dataset. For example, the training dataset did not have any messages beloning 'child alone' category. In addition, messages about categories like 'offer', 'fire', and 'hospitals' were also rare. One solution for this imbalanced case is to add new messages related to minority categories to reduce imbalance. The other workaround solution could be using other libraries such as 'imbalanced-learn' for advanced sampling methods like SMOTE (Synthetic Minority Over-Sampling Technique) and ADASYN (Adaptive Synthetic sampling approach). 

## License<a name="license"></a>
This source code is made available under the [MIT License](https://github.com/dalpengholic/Udacity_ML_Titanic_survivors/blob/master/LICENSE).

## Acknowledgements<a name="acknowledgements"></a>
This project is given by the result of collaboration between [Udacity](https://www.udacity.com) and [Figure Eight](https://www.figure-eight.com)
