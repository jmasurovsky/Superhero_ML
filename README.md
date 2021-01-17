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

## Database
PostgreSQL database has been set up and will be used as storage for final-stage cleaned, analyzed, and outputted results from ML models. A connection to Python has been created in the 'superhero_cleaning' notebook.


## Data preprocessing

Before running any machine learning algorithms, the data needed to be preprocessed. Alignment and Gender were converted to binary as 0 and 1. Dummy values were created from superpower, physical characterstics, and publisher fields. Superhero ability matrix stats were label encoded into bins using adaptive binning. Adaptive binning uses the IQR ranges as bin values. The target variable is the 'Alignment' field and 'Name' of characters have been set as the index to contextualize model results.

## ML Model(s)

Multiple classification models will be run and comapared such as logistic regression, SVM, random forests, and decision trees. One model will be chosen to decide which was best suitable to replicate for each character ability (intelligence, power, etc..) The target variables will be the "Alignment" field, which contains values of 'good' and 'bad' represented as '1' and '0'. Below is a sample testing data. Training data will be the gen labels of abilities, character characteristics, and superpowers.

![img_1](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/Alignment.png)


## Results

Model data was split 75% training and 25% testing and with a random state = 1. Random forests n_estimators were set to 50. Results of random forest feature importance yielded a high importance for height, weight, and bmi accounted for 16% of the weight. I decided to remove these columns and run the models over again. Logistic regression showed an accuracy score of 73.1%, random forest classifier showed an accuracy score of 75.4%, decision tree showed an accuracy score of 66%, and svm showed an accuracy score of 64%. The table below displays results for accuracy, precision and recall scores. Random forests classifier came out strongest in comparison to the other model results with a precsion score of and a recall score of . 

![img_2](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/all_model_results.png)

*Table 1. Accuracy, precision, and recall results for all models*

Abilities such as intelligence, speed, strength, power, and combat were placed into separate dataframes and ran through random forests classifer.

#### Good

 - Combat had an accuracy score of 70%, a precision score of 77%, a recall score of 89%, and an F1 score of 83%.
 
 - Intelligence had an accuracy score of 74%, a precision score of 77%, a recall score of 89%, and an F1 score of 83%.
 
 - Power had an accuracy score of 76%, a precision score of 78%, a recall score of 91%, and an F1 score of 84%.
 
 - Speed had an accuracy score of 74%, a precision score of 77%, a recall score of 90%, and an F1 score of 83%.
 
 - Strength had an accuracy score of 74%, a precision score of 77%, a recall score of 90%, and an F1 score of 83%.
 
#### Evil

 - Combat had an accuracy score of 70%, a precision score of 50%, a recall score of 23%, and an F1 score of 32%.
 
 - Intelligence had an accuracy score of 74%, a precision score of 60%, a recall score of 38%, and an F1 score of 47%.
 
 - Power had an accuracy score of 76%, a precision score of 67%, a recall score of 41%, and an F1 score of 51%.
 
 - Speed had an accuracy score of 74%, a precision score of 61%, a recall score of 36%, and an F1 score of 45%.
 
 - Strength had an accuracy score of 74%, a precision score of 61%, a recall score of 36%, and an F1 score of 45%.
 
Results above are reflected in the tables below.

![img_3](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/.png)

*Table 2. Random forests cllasifier results for good characters' individual abilities*

![img_4](https://github.com/jmasurovsky/Superhero_ML/blob/main/images/.png)

*Table 2. Random forests cllasifier results for evil characters' individual abilities*

## Summary/Conclusion

The analysis revealed there is a an imbalance in the dataset when classifying superhero comic book characters as good or evil using ability levels, superpowers, and characteristics with over half the dataset being good characters. At the same time, about 70% of the dataset were men reiterating there has been a historical bias towards making male comic book characters. Running different classification algorithms showed that random forests was the best chosen model to use with a somewhat strong accuracy score of 75%. Analysis results showed comparing the average of individual character abilities raised a new question that evil characters were on average more likely to be intelligent and powerful. Running random forests on individual abilities, with all other variables remaining unchanged, for evil characters showed that intelligence and power had higher recall and F1 scores compared to other abilities. This supports the idea that intelligent and/or powerful, compared to other abilities, characters are more likely to be classified as evil. Abilities for good characters were evenely balanced across model results. Future work could incoporate performing k-means clustering analysis to find similarities regardless of a character's alignment, and increasing the character volume for the dataset. 

## Dashboard

Still in development

[Superheroes Dashboard](https://public.tableau.com/profile/jason.masurovsky#!/vizhome/Superheroes_Villains_Dashboard/Prototype)
