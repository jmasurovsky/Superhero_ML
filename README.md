# Superhero_ML

## Project Topic

Comic books and superheroes from Marvel and DC publishers have been around since the 1930s. In the past decade, The DC and Marvel universe has exploded into being adapted into the film and tv industry, more so than it had before. Only in recent years, datasets have been created for public use about Marvel and DC character abilites and physical characteristics, which have impacted an emergence of using data analytic and visualization methodologies on the datasets. I chose this topic because I thoroughly enjoy reading comic books, graphic novels, and watching adapted films/tv-shows.  Datasets for this project were found on Kaggle, a data science community website that hosts a wide range of datasets and tooltips.

Research questions that will be explored in this project are:

- Can we classify a superhero as good or evil based off their physical characteristics and abilities? 
- Assuming all other variables equal, can a character's alignment be better explained through the classification of an individual ability?
     - Are intelligence, strength, power, combat, durability, or speed bias towards an alignment?

## Technologies Used

### Data Cleaning and Analysis
Pandas, Matplotlib, and Seaborn packages will be used to clean, explore, and visualize the data. Python will be used to conduct further analysis.

### Database Storage
PostgreSQL will be used as database storage and will integrate with Python.

### Machine Learning
Python's ScikitLearn package will be used to perform machine learning methodologies. R studio will be used to perform multi-linear regressions.

### Dashboard
Tableau will be used to create an interactive dashboard.


## ML Model(s)

To answer the first research question, classification model(s) will be used such as logistic regression, SVM, Naive Bayes, and/or decision trees. The target variables will be the "Alignment" field, which contains values of 'good' and 'bad' represented as '1' and '0'. Below is a sample testing data. Training data will be abilities, characteristics, and superpowers.

![img_1](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/Alignment.png)

Using clustering methods, such as K-means, will help explore similarities between all characters. Linear regression will be performed to explore how abilities of characters influence eachother.


## Database
PostgreSQL database has been set up and will be used as storage for final-stage cleaned, analyzed, and outputted results from ML models. A connection to Python has been created in the 'superhero_cleaning' notebook.


## Data preprocessing

Before running any machine learning algorithms, the data needed to be preprocessed. Alignment and Gender were converted to binary as 0 and 1. Dummy values were created from superpower, physical characterstics, and publisher fields. Superhero ability matrix stats were label encoded into bins using adaptive binning. Adaptive binning uses the IQR ranges as bin values.
-The target variable is the 'Alignment' field.

## Results

Multiple models were ran and compared accuracy scores to decide which was best suitable to replicate for each character ability (intelligence, power, etc..). Modles chosen were logistic regression, random forests, decision trees, and support vector machine. Model data was split 75% training and 25% testing and with a random state = 1. Results of random forest feature importance yielded a high importance for height, weight, and bmi accounted for 16% of the weight. I decided to remove these columns and run the models over again. Logistic regression showed an accuracy score of 73.1%, random forest classifier showed an accuracy score of 75.4%, decision tree showed an accuracy score of 66%, and svm showed an accuracy score of 64%. The table below displays results for accuracy, precision and recall scores. Random forests classifier came out strongest in comparison to the other model results. 

![img_2](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/all_model_results.png)



## Dashboard

Still in development

[Superheroes Dashboard](https://public.tableau.com/profile/jason.masurovsky#!/vizhome/Superheroes_Villains_Dashboard/Prototype)
