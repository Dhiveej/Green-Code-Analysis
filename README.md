# 🍃 Green Code: An Analysis of Python's Energy Efficiency

> An exploratory data analysis and machine learning project to uncover the hidden energy and carbon costs of Python code.

![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3-F7931E?logo=scikit-learn)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-882B89?logo=seaborn)

---

## 1. Project Overview

In a world driven by software, every line of code has an invisible environmental cost. From the energy consumed by data centers to the processing power on our local machines, the efficiency of our code matters. This project aims to make that cost visible.

By analyzing the "Python Energy Microscope" dataset, this project performs a full data science workflow, including **Exploratory Data Analysis (EDA)**, **unsupervised clustering**, and **supervised classification** to investigate the performance and energy differences between various Python execution methods.

---

## 2. Key Questions Explored

1.  Which execution method is the most energy-efficient?
2.  Is the fastest method also the most energy-efficient?
3.  Can we automatically group methods into performance tiers using unsupervised learning?
4.  Can we train a supervised model to accurately **predict** the execution method from its performance data?

---

## 3. The Workflow

This project followed a comprehensive data science workflow:
1.  **Data Exploration:** Initial analysis using Pandas to understand the dataset's structure.
2.  **Data Visualization:** Creating charts with Seaborn & Matplotlib to uncover patterns.
3.  **Unsupervised Learning:** Implementing a **K-Means Clustering** model to automatically find performance tiers. This model was successfully validated with a high Silhouette Score.
4.  **Supervised Learning:** Training both a **Decision Tree** and a **Random Forest** classifier to attempt to predict the execution method.
5.  **Model Evaluation:** Assessing the models based on their **accuracy scores**.

---

## 4. Exploratory Findings & Visualizations

The initial analysis revealed a dramatic difference in performance between the methods.

#### Insight 1: Energy & Time Consumption Vary Drastically
The choice of execution method is not a minor optimization. The least efficient methods (`cpython`, `pycompile`) consume over **3 times more energy** and are **4 times slower** than the most efficient method (`ctypes`).

#### Insight 2: Visualizing the Performance Tiers
The scatter plot clearly shows distinct performance groups, with `ctypes` as the clear champion and `cpython`/`pycompile` as the least performant.

---

## 5. 🤖 Machine Learning Models & Results

Two types of machine learning models were implemented to analyze the data from different perspectives.

### Unsupervised Clustering (K-Means)
To validate the visual findings, a K-Means Clustering model was trained.
- The **Elbow Method** determined the optimal number of clusters was **2**.
- The model successfully grouped the methods into a **"High-Performance Tier"** and a **"Low-Performance Tier"**.
- The model's quality was confirmed with an excellent **Silhouette Score of 0.88**.

### Supervised Classification (Random Forest)
To test if the execution method could be predicted, supervised models were trained.
- A baseline **Decision Tree** model achieved a low accuracy of **13.33%**.
- A more powerful **Random Forest** model was then trained but also resulted in **13.33% accuracy**.
- This key result proves that while the performance differences are clear to see, the dataset is **too small** to train a reliable predictive model.

---

## 6. Conclusion

The analysis proves that the way Python code is executed has a significant and measurable impact on its speed and energy consumption. The EDA and clustering successfully identified clear performance tiers. Furthermore, the supervised learning phase provided a critical insight: it demonstrated that the dataset, while excellent for analysis, is insufficient for building a reliable predictive model, a crucial finding in any real-world data science project.
