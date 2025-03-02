# Fake-News-Detection  

### 1.0 Introduction  

In today’s digital world, **fake news spreads rapidly**, influencing public opinion, financial markets, and even political decisions. Whether it’s a **sensational headline** or a **misleading article shared on social media**, misinformation has become a serious concern. To combat this issue, we explore **machine learning-based fake news detection**.  

#### 1.1 **Dataset Overview**  
For this project, we use the **ISOT Fake News Dataset** from Kaggle, which contains both **real** and **fake** news articles. The dataset consists of:  
- **True.csv** – Over **12,600** verified news articles from *Reuters.com*.  
- **Fake.csv** – More than **12,600** articles from unreliable sources, flagged by *Politifact* and *Wikipedia*.  
- **Content Focus** – Primarily **political and world news** from **2016–2017**.  
- **Key Attributes** – Each article includes **title, text, type, and publication date**.  
- **Data Authenticity** – While cleaned, **punctuation errors** in fake news articles have been preserved to maintain authenticity.  

#### 1.2 **Project Objective**  
Our goal is to develop a **machine learning pipeline** that:  
1. **Uncovers hidden patterns** in the dataset using **unsupervised learning (clustering)**.  
2. **Builds classification models** to predict whether an article is **fake** or **real**.  

By leveraging **machine learning** and **Natural Language Processing (NLP)**, this project aims to **enhance information integrity** and provide valuable insights for **businesses, social media platforms, and news organizations** to combat misinformation effectively.  


### 2.0 Exploratory Data Analysis (EDA)  

#### 2.1 Visualization  
We conducted data visualization on both the **text** and **title**, including:  
- Histograms of the most frequently occurring words  
- Word clouds for key term representation  
- Dissimilarity matrix analysis for both fake and real news articles  

Detailed insights from these visualizations can be found in **1.2.3 Insights Drawn from Data Visualization and Comparison Between Title and Text** in the code file.  

## 3.0 Unsupervised Model  
To uncover hidden patterns in fake and real news, we applied multiple unsupervised learning techniques:  

- **LDA (Latent Dirichlet Allocation)** – Topic modeling to identify common themes in news articles.  
- **K-Means Clustering** – Grouping articles based on textual similarity.  
- **NMF (Non-Negative Matrix Factorization)** – Decomposing text into meaningful components.  

These models were applied separately to both **titles** and **full text**, allowing us to analyze patterns at different levels.  

Key insights from the clustering models can be found in **2.1 Insights for Unsupervised Models**.  

---

## 4.0 Supervised Model  

### 4.1 Feature Engineering  
To enhance model performance, we engineered additional numerical features for classification, incorporating **title and text cluster assignments** along with other linguistic attributes.  

#### **Lexical Analysis**  
- **Word count & sentence count** – Fake news articles tend to be longer and more exaggerated.  
- **Readability score** – Fake news often uses simpler language to appeal to a broader audience.  
- **Average word length & sentence length** – Helps differentiate between formal and sensational writing styles.  

#### **N-grams & TF-IDF Analysis**  
- Identifying frequently used words in **fake vs. real news**.  
- Presence of specific keywords such as *“video”* and *“Trump”*, which frequently appear in misleading headlines.  

---

### 4.2 Model Selection  
We trained **Random Forest**, **Logistic Regression**, and **Gradient Boosting** on the engineered features. Model performance was evaluated using:  
- **Accuracy score**  
- **Confusion matrix**  
- **Feature importance analysis**  

#### **4.2.1 Random Forest**  
- **Accuracy**: **0.95**  
- **Confusion Matrix**:  
  - **229 False Negatives**  
  - **219 False Positives**  
- **Key Insight**:  
  - The **word count in the title** emerged as the most important feature, highlighting the significance of title length in distinguishing fake news.  

#### **4.2.2 Logistic Regression**  
- **Accuracy**: **0.87**  
- **Confusion Matrix**:  
  - **467 False Negatives**  
  - **688 False Positives**  
- **Key Insight**:  
  - Logistic Regression underperformed due to its inability to fully capture non-linear relationships in textual data.  

#### **4.2.3 Gradient Boosting**  
- **Accuracy**: **0.93**  
- **Confusion Matrix**:  
  - **283 False Negatives**  
  - **328 False Positives**  
- **Key Insight**:  
  - Gradient Boosting effectively captured complex patterns but slightly underperformed compared to Random Forest.  

✅ **Overall, Random Forest outperformed the other models with the highest accuracy and better handling of false positives/negatives.**  

---

## 5.0 NLP Models  
To further improve classification performance, we explored **NLP-based deep learning models**.  

### 5.1 BERT (Bidirectional Encoder Representations from Transformers)  
- **Accuracy**: **0.87**  
- **Confusion Matrix**:  
  - **498 False Negatives**  
  - **639 False Positives**  
- **Key Insight**:  
  - While BERT improved contextual understanding, it still struggled with classification accuracy, particularly in detecting false negatives.  

### 5.2 BERT + BiGRU (Bidirectional Gated Recurrent Unit)  
- **Accuracy**: **~1.00** (Near-perfect performance)  
- **Confusion Matrix**:  
  - **4 False Negatives**  
  - **13 False Positives**  
- **Key Insight**:  
  - Combining **BERT’s contextual embeddings** with **BiGRU’s sequential processing capabilities** significantly enhanced accuracy, reducing misclassification to near zero.  

🚀 **BERT + BiGRU achieved the best performance among all models, with almost perfect classification accuracy.**  


## 6.0 Conclusion  

Our model addresses the needs of three key stakeholders:  

1. **News Viewers** – Individuals interested in political news who want to consume accurate and reliable information.  
2. **Legislators** – Policymakers concerned with electoral integrity and the spread of misinformation.  
3. **News Publishers** – Media organizations seeking to maintain credibility and improve user engagement.  

By **proactively identifying and intercepting fake news**, the model helps prevent the spread of misinformation before it reaches a broad audience. This contributes to **protecting public opinion**, ensuring **electoral fairness**, and maintaining **trust in media sources**.  

### **Potential Applications**  
The model can be deployed in scenarios such as:  
- **False rumors** about a candidate’s criminal history.  
- **Fake voting instructions** designed to mislead the public.  
- **Fabricated diplomatic incidents** that could influence international relations.  

### **Impact on News Publishers**  
A publisher’s reputation is directly linked to their commitment to accuracy. By filtering out low-quality or deceptive articles, our model:  
✅ **Enhances user retention** – Readers trust the platform and engage with more content.  
✅ **Improves conversion rates** – Reliable news attracts a loyal audience, contributing to revenue growth.  
✅ **Reduces misinformation-driven frustration** – Users experience a more informative and credible news feed.  

### **Future Steps**  
While our final model achieved **near-perfect accuracy**, this may be due to the **limitations of the dataset**. The news articles used for training may not fully represent the complexity of real-world misinformation. To ensure **generalizability and robustness**, we should:  
- **Test the model on a more recent dataset** that includes evolving fake news strategies.  
- **Evaluate performance on unseen news sources** to assess its adaptability.  
- **Incorporate real-time updates** to capture new misinformation trends as they emerge.  

🚀 **In summary, our model serves as a powerful tool in combating misinformation, benefiting both individual users and the broader media ecosystem.** However, ongoing validation with fresh data is essential to maintaining its effectiveness.  

