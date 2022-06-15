# AMLS Wine Type and Wine Quality Prediction
_Hello! :) I am Lisbora Likaj (SEM) and this is my project submission for AMLS exercise. This is my second ML related 
project and unfortunately I couldn't find a group to divide the workload, so I am aware that these solutions needs some improvements:) 
Besides the struggles , I enjoyed working on this project and learnt a lot of new stuff. I think this exercise is a really
nice approach to getting my hands "dirty" and try out some projects on my own._

Please note that I used some helpful sources online while working on this exercise which I will list below:

[MarceloMarques Article](https://www.kaggle.com/code/mgmarques/wines-type-and-quality-classification-exercises#notebook-container)
[MayurBadole Article](https://www.analyticsvidhya.com/blog/2021/04/wine-quality-prediction-using-machine-learning/)
[NivyasreeAvula Article](https://medium.com/analytics-vidhya/predicting-red-wine-quality-using-machine-learning-model-34e2b1b8d498)

**Please find below a short description of each task**



**1) Data Preparation**


**General description of the approach:** 

1. [Files](https://archive.ics.uci.edu/ml/datasets/wine+quality):
* winequality-red.csv
* winequality-white.csv
2. Both csv-s are read into separate datasets. I have added a new column "type" for white/red wine and then fused the 
   datasets together.
3. Then I added a  numerical quality label based on the quality column:
* Low: <=5
* Medium: 6>= x =<7
* High: >7
4. There are no null values in this dataset. Then I have performed some summary data descriptive statistics. (You can 
   find further comments in the respective Notebook)
5. I have split the data for the Wine Type Prediction Model and for Wine Quality prediction model separately into train 
   and test, then the train datasets further into train and validation sets.
6. Then these datasets are exported to csv-s, these csv-s can be found in the 01_DataPrep folder and will be used for
   the other subtasks.
7. Jupyter Notebook is saved as 01_DataPrep.ipynb inside 01_DataPrep folder.



In order to run the O1_DataPrep.ipynb file, you need to download both input files and then follow the commands in the 
notebook.


**Presenting Results:**

All the results, the split train, test and validation sets for both prediction models can be found as csv-s in the 
DataPrep folder.


**2) Modeling**


**General description of the approach:** 

1. I am using the train and test csv-s files previously saved from 01_DataPrep and that can be found in 01_DataPrep.zip 
   file.
2. For wine type prediction model, I am using a classification model - decision tree.
3. For wine quality prediction model, I am using a regression model - logistic regression
4. I am using a function from an article [MarceloMarques Article](https://www.kaggle.com/code/mgmarques/wines-type-and-quality-classification-exercises#notebook-container)
   called get_results to simplify getting the results from training the models. This fuction returns back the results on 
   performance metrics, the model reports and the confusion matrices.
5. After running the models separately, I have applied normalization and pca and then run them again.
6. Jupyter Notebook is saved as 02_Modeling.ipynb inside 02_Modeling folder.



In order to run the O2_Modeling.ipynb file, you need to download the files from 01_DatPrep folder and then follow the 
commands in the notebook.


**Presenting Results:**

All the results, can be found as images inside the 02_Modeling folder. You will see the results (performance metrics, 
model report and confusion matrix) for the classification and regression tasks, both before and after applying normalization 
and PCA.



**2) Tuning**


**General description of the approach:** 

1. I am using the train and test csv-s files previously saved from 01_DataPrep and that can be found in 01_DataPrep.zip 
   file, then applying normalization on them.
2. Firstly, I checked for correlation between features based on wine type and based on wine quality separately. - There 
   were no significant correlations that need to be fixed. (You can see more comments inside the Notebook)
3. Secondly, I transformed non-normal data distribution into a normal shape using box cox transform
4. Then I checked for multicollinearity and kept note on two columns that can be removed to see if they improve the results: 
   residual sugar and total sulfur dioxide.
5. Then I run the models again, this time using the validation set instead of test set, with and without the columns mentioned before. Removing the columns didn't improve the results.
6. Jupyter Notebook is saved as 03_Tuning.ipynb inside 02_Tuning folder.



In order to run the O3_Tuning.ipynb file, you need to download the files from 01_DatPrep folder and then follow the 
commands in the notebook.


**Presenting Results:**

All the results, can be found as images inside the 03_Tuning folder. You will see the results (performance metrics, 
model report and confusion matrix) for the classification and regression tasks, after applying tuning, and after removing
some columns from the multicollinearity analysis: residual sugar and total sulfur dioxide.