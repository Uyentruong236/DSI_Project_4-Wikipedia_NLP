# Latent Semantic Analysis
## Wikipedia Search 
**By: Uyen Truong**

### Introduction

The purpose of this project were: 
- collect page contents from the Wikipedia API from specific categories (Machine Learning and Business Software), 
- analyze the text collected with  Latent Semantic Analysis in order to find the top related articles,
- create a machine learning model to predict the probability of a new article into categories. 

Addtionally, the data collected was uploaded and stored in a MongoDB.

I completed the project in in the steps outlined in each Jupyter notebook described below: 

**01_Collect-store_data_on_MongoDB.ipynb**

In this notebook, I created functions to call the Wikipedia API to pull every page content, page ID, page title from a specific category, including all of the pages found in its subcategories. The final search function include a max-depth limit in order to limit the numer of sub-categories pages due to some sub-categories irrelevance to the main category(such as was the case for "Business Software"). Within the search function, the data collected from Wikipedia is automatically uploaded to and stored in MongoDB.


**02_LSA.ipynb**

In this notebook, I used the combination of text vectorization TF_IDF and Truncated SVD to produce representative matrices of the text documents.  Then, I created a function to implement cosine similarity to measure the distance between two documents principal components in order to search over a corpus of text to predict the top 5 related articles. In this function, the top five articles are printed. 

**03_Model_prediction.ipynb**

A Logistic Regression and BernoulliNB model were trained on the Wikipedia corpus to predict which major category a body of text is derived from. The text documents are broken into train and test groups, and the model performs surprisingly well with the Logistic Regression model having accuracy score of 0.98 and precision, recall and f1-scores all above 0.96. The BernoulliNB model performed slightly worse with classification report scores just abouve 0.95.


