# Sql-injection-detection-using-Machine-Learning-Techniques

## Objective
SQL injection is a code injection technique in which malicious SQL statements are inserted into an entry field for execution (e.g. to dump the database contents to the attacker).The objective of this project is to train ensemble machine learning models. Both injected and normal sql queries to form a dataset along with plain text as we also want our model to differentiate between query and plaint text and from them required queries and queries-based features are extracted. The performance level of each model is measured and compared.
We have implemented the model prescribed by the research paper which would be cited in refercences.
This research paper didn't specify any dataset ehich is used and no implementation is given.So we resort to an attempt to try getting the best accuracy from the trained model.

## Data Collection
The set of normal and injected queries are collected from opensource service called **Kaggle**. This service provide a set of sql injection queries(which consitsts of normal queries,injected queries and plain text) in the csv format.To download the data: https://www.kaggle.com/datasets/syedsaqlainhussain/sql-injection-dataset.The dataset however had only two labels 1 for injected queries ,0 for normal queries, so we gave third lable 2 for plain text to the dataset which have plain text as queries.  From this dataset, 30000 random queries are collected to train the ML models.

From this dataset, 10000 random normal(legitimate) queries,about 5000 injected queries and 800 plain queries are collected are collected to train the ML models.

The dataset are uploaded to the '(https://github.com/ankitkumarhello20/sql-injection-detection-using-Machine-Learning-Techniques/blob/main/sqlqueriesdata.csv)'to this repository.

## Feature Extraction
The below mentioned category of features are extracted from the URL data:

1.   Keywords based Features <br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this category 9 features are extracted.
2.   Character based Features<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this category 4 features are extracted.

*The details pertaining to these features are mentioned in the [SQL injected queries Feature Extraction.ipynb.](https://github.com/ankitkumarhello20/sql-injection-detection-using-Machine-Learning-Techniques/blob/main/Sql_injected_queries_features_extraction.ipynb)[![Open In Colab]](https://colab.research.google.com/github/ankitkumarhello20/sql-injection-dataset/blob/main/Sql_injected_queries_features_extraction.ipynb)*

So, all together 21 features are extracted from the 10,000 URL dataset and are stored in '[sqlqueriesdata.csv](https://github.com/ankitkumarhello20/sql-injection-detection-using-Machine-Learning-Techniques/blob/main/sqlqueriesdata.csv)' file in the DataFiles folder.<br>
The features are referenced from the research paper.'[Ensemble Machine Learning Approaches for Detection of SQL Injection Attack --By Umar Farooq](https://hrcak.srce.hr/file/367636)'

## Models & Training 

Before stating the ML model training, the data is split into 80-20 . From the dataset, it is clear that this is a supervised machine learning task. There are two major types of supervised machine learning problems, called classification and regression.

This data set comes under classification problem, as the input Sql queries is classified as injected (1), legitimate (0) and plain text(2). The supervised machine learning models (classification) considered to train the dataset in this project are:

* Decision Tree
* Random Forest
* Adaboost
* XGBoost
* Gradient Boosting Machine
* Light Gradient Boosting Machine
* Autoencoder Neural Network
* Support Vector Machines

All these models are trained on the dataset and evaluation of the model is done with the test dataset. The elaborate details of the models & its training are mentioned in [Sql_injection_detection_by_Machine_Learning_Techniques.ipynb](https://github.com/ankitkumarhello20/sql-injection-detection-using-Machine-Learning-Techniques/blob/main/Sql_injection_detection_by_Machine_Learning_Techniques.ipynb)[![Open In Colab](https://colab.research.google.com/github/ankitkumarhello20/sql-injection-dataset/blob/main/Sql_injection_detection_by_Machine_Learning_Techniques.ipynb)

## Presentation

The poster presentation for this project is![1650043290330](https://user-images.githubusercontent.com/79505467/163601525-736edaaf-452a-4cb4-8fbb-b30bf4f67994.png) which is made possible with the great endeavor of my project partner Amrutha.All credits goes to her from idea to implementaion.

## End Results
From the obtained results of the above models, Random Forest Classifier has highest model performance of 94.2%. So the model is saved to the file '[ForestClassifier.pickle.dat](https://github.com/ankitkumarhello20/sql-injection-detection-using-Machine-Learning-Techniques/blob/main/ForestClassifier.pickle.dat)'

### Next Steps

This project can be further extended to creation of browser extention or developed a GUI which takes the URL and predicts it's nature i.e., legitimate of phishing. *As of now, I am working towards the creation of browser extention for this project. And may even try the GUI option also.* The further developments will be updated at the earliest. 

