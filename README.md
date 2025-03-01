# Fake-News-Detection

### 1.0 Introduction
We've all read and been misled by fake news before, whether it’s a sensational headline or a misleading article shared on social media. The rapid spread of misinformation can influence public opinion, financial markets, and even political decisions. This growing concern has motivated us to explore methods for detecting fake news using machine learning. For this project, we are using the ISOT Fake News Dataset, sourced from Kaggle, which contains both real and fake news articles. 

The dataset consists of two CSV files: True.csv, which contains over 12,600 verified news articles from Reuters.com, and Fake.csv, which includes more than 12,600 articles from unreliable sources flagged by Politifact and Wikipedia. The dataset primarily covers political and world news from 2016 to 2017, with each article including attributes such as title, text, type, and publication date. While the data has been cleaned, punctuation and errors in fake news articles have been preserved for authenticity. 

This project aims to first develop a clustering model to uncover patterns in the dataset, followed by classification models to predict whether an article is fake or real. By leveraging machine learning and natural language processing techniques, this project contributes to improving information integrity and helping businesses, social media platforms, and news organizations combat misinformation.

### 2.0 Exploratory Data Analysis (EDA)  

#### 2.1 Visualization  
We conducted data visualization on both the **text** and **title**, including:  
- Histograms of the most frequently occurring words  
- Word clouds for key term representation  
- Dissimilarity matrix analysis for both fake and real news articles  

Detailed insights from these visualizations can be found in **1.2.3 Insights Drawn from Data Visualization and Comparison Between Title and Text** in the code file.  

### 3.0 Unsupervised Model  
We applied **LDA (Latent Dirichlet Allocation)**, **K-Means clustering**, and **NMF (Non-Negative Matrix Factorization)** to analyze patterns in both the title and text of fake and real news articles.  

Insights from the clustering models are documented in **2.1 Insights for Unsupervised Models**.  

### 4.0 Supervised Model  

#### 4.1 Feature Engineering  
For supervised learning, we engineered additional numerical features to improve prediction accuracy.  

##### **Lexical Analysis**  
- **Word count & sentence count** – Fake news tends to be more exaggerated and lengthy.  
- **Readability score** – Fake news may use simpler language to attract a broader audience.  
- **Average word length & sentence length** – Helps distinguish between writing styles.  

##### **N-grams & TF-IDF Analysis**  
- Identification of frequently used words in fake vs. real news.  
- Presence of specific keywords such as *“video”*, *“trump”* are commonly found in misleading headlines.  


 #### 4.2 Model Selection
 Using the numerical variables, we performed classification using random forest, logistics regression, and gradient boosting models

 ### 6.0 Conclusion
In summary, the model serves these three potential stakeholders, which are news viewer who are interested in political news, legislators, and news publishers.  Our model proactively identifies and intercepts fake news, preventing its spread before it reaches a wide audience, minimizing the impact of misleading information and protecting public opinion and ensuring electoral fairness. It may be applied in the following scenarios:
1. False rumors about a candidate’s criminal history
2. Fake voting instructions
3. A fabricated diplomatic incident
The reputation of a news publisher is correlated with their attitude to accuracy, while enhanced user retention and improved conversion rates directly contribute to revenue. Our model can consistently filter out low-quality or deceptive articles for platforms. This not only alleviates user frustration but also boosts engagement, as users are more likely to stay longer and consume more content. 
