# Fake-News-Detection

### 1.0 Introduction
We've all read and been misled by fake news before, whether it’s a sensational headline or a misleading article shared on social media. The rapid spread of misinformation can influence public opinion, financial markets, and even political decisions. This growing concern has motivated us to explore methods for detecting fake news using machine learning. For this project, we are using the ISOT Fake News Dataset, sourced from Kaggle, which contains both real and fake news articles. 

The dataset consists of two CSV files: True.csv, which contains over 12,600 verified news articles from Reuters.com, and Fake.csv, which includes more than 12,600 articles from unreliable sources flagged by Politifact and Wikipedia. The dataset primarily covers political and world news from 2016 to 2017, with each article including attributes such as title, text, type, and publication date. While the data has been cleaned, punctuation and errors in fake news articles have been preserved for authenticity. 

This project aims to first develop a clustering model to uncover patterns in the dataset, followed by classification models to predict whether an article is fake or real. By leveraging machine learning and natural language processing techniques, this project contributes to improving information integrity and helping businesses, social media platforms, and news organizations combat misinformation.

### 2.0 EDA
#### 2.1 Visualization
