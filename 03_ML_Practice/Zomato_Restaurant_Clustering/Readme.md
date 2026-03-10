<img width="790" height="590" alt="08_review_length_vs_rating" src="https://github.com/user-attachments/assets/0b80fdef-7c2a-4304-ae73-1a41899d8d7b" /><img width="790" height="590" alt="08_review_length_vs_rating" src="https://github.com/user-attachments/assets/01517e0a-27db-405b-9a11-dc5a9d0890ca" /># **🍽️ Zomato Restaurant Clustering & Customer Behavior Analysis**

**📌 Project Overview**

The restaurant industry in India has seen rapid growth, with thousands of restaurants listed on platforms such as Zomato. With such a large number of options, it becomes difficult for both customers and businesses to understand restaurant performance patterns.

This project focuses on segmenting restaurants into meaningful groups using clustering techniques by analyzing:

*  Restaurant metadata

*  Customer reviews

*  Pricing patterns

*  Customer engagement metrics

The goal is to uncover hidden patterns in restaurant data that can help understand restaurant performance and customer preferences.

---

**🎯 Project Objectives**

The main objectives of this project were:

*  Analyze restaurant data and customer reviews

*  Identify factors influencing restaurant popularity

*  Segment restaurants into meaningful clusters

*  Compare multiple clustering algorithms

*  Extract business insights from restaurant segments

---

**📂 Dataset Description**

The dataset consists of two main components:

**1️⃣ Restaurant Metadata**
``
Feature	Description
Restaurant	
Restaurant Name
avg_rating
Average customer rating
review_count	
Number of customer reviews
avg_review_length	
Average length of reviews
cost	
Average cost for two people
``


**2️⃣ Customer Reviews**

The dataset also includes text reviews, which provide valuable information about:

```
Food quality

Service experience

Ambience

Customer satisfaction
```

These reviews were processed using Natural Language Processing (NLP) techniques.

---

**🔎 Exploratory Data Analysis (EDA)**

Exploratory Data Analysis was performed to understand the distribution and relationships between important restaurant features.

Key insights explored

*  Distribution of restaurant ratings

<img width="790" height="390" alt="01_rating_distribution" src="https://github.com/user-attachments/assets/ed67e258-7e67-4fa4-a54c-8ee5643b8719" />

*  Pricing distribution across restaurants

<img width="790" height="490" alt="02_cost_distribution" src="https://github.com/user-attachments/assets/aacd0d94-fa93-4656-b16b-35d0afb986dd" />
 

*  Customer review behavior

 <img width="790" height="490" alt="03_review_length_distribution" src="https://github.com/user-attachments/assets/ebf4aa24-bf7b-4559-b7e8-1810e0b03389" />


*  Relationship between ratings and review length

<img width="790" height="590" alt="08_review_length_vs_rating" src="https://github.com/user-attachments/assets/5143459a-f78e-4850-ae57-5556127406f8" />



---

**🧠 Text Processing (NLP)**

Customer reviews were processed using several NLP techniques:

*  Lowercasing

*  Removing punctuation

*  Removing stopwords

*  Lemmatization

*  Part-of-Speech tagging

*  To convert text into numerical features, TF-IDF vectorization was used.

*  TF-IDF generated ~999 features, which required dimensionality reduction.

---

**📉 Dimensionality Reduction**

*  Principal Component Analysis (PCA) was applied to reduce the TF-IDF features.

*  Original TF-IDF features → ~999

*  Reduced to 20 principal components

*  Retained ~67.9% variance

This helped reduce noise and improve clustering performance.

---

**⚙️ Feature Scaling**

Before applying clustering algorithms, the dataset was standardized using:

**StandardScaler**

This ensured that features like cost and review_count did not dominate the clustering process.

---

**🤖 Machine Learning Models**

Three clustering models were implemented and compared:

**Model	Purpose**

1. **KMeans Clustering**	- Partition-based clustering
2. **Agglomerative Hierarchical Clustering** - 	Hierarchical grouping
3. **Gaussian Mixture Model**	- Probabilistic clustering

**Models were evaluated using the Silhouette Score.**

---

**📊 Model Comparison**

**Model	Silhouette Score**

1. KMeans	**0.2168**
2. Hierarchical Clustering	**0.5566**
3. Gaussian Mixture Model	**0.4457**

**The Agglomerative Hierarchical Clustering model achieved the best performance.**

---

**📈 Clustering Visualizations**

<img width="833" height="542" alt="image" src="https://github.com/user-attachments/assets/abf8ddf6-e9f1-4ffc-b608-d83740fec766" />

<img width="1156" height="451" alt="image" src="https://github.com/user-attachments/assets/1e590dbc-0ab5-4373-ae94-3e2803aa12ba" />

<img width="695" height="465" alt="image" src="https://github.com/user-attachments/assets/6282aaf6-5457-42ff-b177-0135c2a83ea0" />

<img width="671" height="547" alt="image" src="https://github.com/user-attachments/assets/449c2267-d4a7-431e-9230-b81239fd1648" />

---

**📊 Cluster Profiling**

Cluster profiling was performed to understand the characteristics of each restaurant segment.

*  Feature	Cluster 0	Cluster 1
*  Average Rating	Higher	Moderate
*  Cost	Higher	Lower
*  Review Count	Higher	Lower
*  Review Length	Longer	Shorter

---

**💡 Business Insights**

Premium Restaurants

*  Higher cost

*  Higher ratings

*  More detailed reviews

*  Higher customer engagement

  Budget Restaurants

*  Lower cost

*  Moderate ratings

*  Shorter reviews

*  Lower engagement

**🏆 Final Model**

The Agglomerative Hierarchical Clustering model was selected as the final model because it achieved the highest silhouette score (0.5566), indicating well-separated and meaningful clusters.

---

**📌 Project Conclusion**

This project successfully applied clustering techniques and NLP analysis to identify meaningful restaurant segments in Zomato data.

By combining restaurant metadata with customer review patterns, the analysis revealed distinct restaurant categories based on pricing, customer engagement, and perceived quality.

The results demonstrate how machine learning can help uncover hidden patterns in customer behavior and restaurant performance, providing valuable insights into restaurant segmentation.


---

**🛠️ Tech Stack**

*  Python

*  Pandas

*  NumPy

*  Scikit-learn

*  NLTK

*  Matplotlib

*  Seaborn

