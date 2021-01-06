# Superhero_ML

## Project Topic

Comic books and superheroes from Marvel and DC publishers have been around since the 1930s. In the past decade, The DC and Marvel universe has exploded into being adapted into the film and tv industry, more so than it had before. Only in recent years, datasets have been created for public use about Marvel and DC character abilites and physical characteristics, which have impacted an emergence of using data analytic and visualization methodologies on the datasets. I chose this topic because I thoroughly enjoy reading comic books, graphic novels, and watching adapted films/tv-shows.  Datasets for this project were found on Kaggle, a data science community website that hosts a wide range of datasets and tooltips.

Research questions that will be explored in this project are:

- Can we classify a superhero as good or evil based off their physical characteristics and abilities? Do we see a bias?
- Can we cluster superheroes by their abilities to uncover similarities between good and evil characters?
- Which superhero abilities have statistically significant influence on one another and by how much?

## Technologies Used

### Data Cleaning and Analysis
Pandas, Matplotlib, and Seaborn packages will be used to clean, explore, and visualize the data. Python will be used to conduct further analysis.

### Database Storage
PostgreSQL will be used as database storage and will integrate with Python and possibly JavaScript for dashboard integration.

### Machine Learning
Python's ScikitLearn package will be used to perform machine learning methodologies. R studio will be used to perform multi-linear regressions.

### Dashboard
JavaScript's D3.js library will be used to create an interactive dashboard.


## ML Model(s)

To answer the first research question, classification model(s) will be used such as logistic regression, SVM, Naive Bayes, and/or decision trees. The target variables will be the "Alignment" field, which contains values of 'good' and 'bad' represented as '1' and '0'. Below is a sample testing data. Training data will be abilities, characteristics, and superpowers.

![img_1](https://github.com/jmasurovsky/Superhero_ML/blob/main/Alignment.png)

Using clustering methods, such as K-means, will help explore similarities between all characters. Linear regression will be performed to explore how abilities of characters influence eachother.


## Database
PostgreSQL database has been set up and will be used as storage for final-stage cleaned, analyzed, and outputted results from ML models. A connection to Python has been created in the 'superhero_cleaning' notebook (see data_cleaning branch).


## Data preprocessing

Before running any machine learning algorithms, the data needed to be preprocessed. Alignment and Gender were converted to binary as 0 and 1. Dummy values were created from superpower, physical characterstics, and publisher fields. Superhero ability matrix stats were label encoded into bins using adaptive binning. Adaptive binning uses the IQR ranges as bin values.

### Logistic Regression Classification

The target variable is the 'Alignment' field. The data was split into ~80% training (400) and ~20% testing (117). 

