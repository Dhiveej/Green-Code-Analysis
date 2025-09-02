# 🍃 Green Code: An Analysis of Python's Energy Efficiency

> An exploratory data analysis and machine learning project to uncover the hidden energy and carbon costs of Python code.

![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3-F7931E?logo=scikit-learn)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-882B89?logo=seaborn)

---

## 1. Project Overview

In a world driven by software, every line of code has an invisible environmental cost. From the energy consumed by data centers to the processing power on our local machines, the efficiency of our code matters. This project aims to make that cost visible.

By analyzing the "Python Energy Microscope" dataset, this project performs an **Exploratory Data Analysis (EDA)** and uses an **unsupervised machine learning model** to answer a key question: How significant is the performance and energy difference between various Python execution methods?

---

## 2. Key Questions Explored

1.  **Which execution method is the most energy-efficient?**
2.  **Is the fastest method also the most energy-efficient?** What are the trade-offs?
3.  **Can we automatically group methods into distinct performance tiers** using machine learning?

---

## 3. The Workflow

This project followed a standard data science workflow:
1.  **Data Exploration:** Initial analysis using Pandas to understand the dataset's structure and statistics.
2.  **Data Visualization:** Creating bar charts and scatter plots with Seaborn & Matplotlib to uncover patterns and relationships.
3.  **Machine Learning:** Implementing a K-Means Clustering model to automatically group the Python methods.
4.  **Model Evaluation:** Validating the quality of the clusters using the Silhouette Score.

---

## 4. Key Findings & Visualizations

The analysis revealed a dramatic difference in performance between the methods.

#### Insight 1: Energy & Time Consumption Vary Drastically
The choice of execution method is not a minor optimization. The least efficient methods (`cpython`, `pycompile`) consume over **3 times more energy** and are **4 times slower** than the most efficient method (`ctypes`).


#### Insight 2: Visualizing the Performance Tiers
The scatter plot clearly shows three distinct groups:
- **The Champion (`ctypes`):** In a class of its own for both speed and efficiency.
- **The Contenders (`cython`, `pypy`):** A strong middle tier, offering significant gains over the standard.
- **The Standard (`cpython`, `pycompile`):** The slowest and least energy-efficient group.



---

## 5. 🤖 Machine Learning Model: K-Means Clustering

To validate these visual findings, a K-Means Clustering model was trained on the data.

- The **Elbow Method** determined that the optimal number of clusters was **2**.
- The model successfully grouped the methods into a **"High-Performance Tier"** (`ctypes`, `cython`, `pypy`) and a **"Low-Performance Tier"** (`cpython`, `pycompile`).
- The model's performance was evaluated with a **Silhouette Score of 0.88**, indicating that the clusters are dense, well-separated, and meaningful.

This chart shows the final clusters identified by the algorithm:

---

## 6. Conclusion

The analysis proves that the way Python code is executed can have a significant and measurable impact on both its speed and its energy consumption. For developers working on performance-critical or large-scale applications, choosing an optimized execution method is a key lever for building more sustainable and efficient software.
