# Analysis of the Internet Movie Database (IMDb)
## Advanced Data Mining, Machine Learning and Time Series Analysis

Project for the course ‘Data Mining: Advanced’. The syllabus revolved around the following concepts: Outlier Detection, Dimensionality Reduction, Regression, Advanced Classification and Regression, Time Series Analysis, Transactional Clustering, Explainability.

### Project Overview

This project focuses on the analysis of the **Internet Movie Database (IMDb)** through a comprehensive application of advanced data mining and machine learning techniques.

The main objective is to investigate the characteristics of movies, TV series, and other entertainment content by exploring their metadata, predicting relevant attributes, and identifying patterns in their box office performance.

The project combines **Advanced Data Preprocessing, Imbalanced Learning, Classification, Regression, Explainable AI (XAI), Time Series Analysis, and Sequential Pattern Mining** to extract meaningful insights from IMDb data.

The analysis is divided into seven main areas, covering both traditional machine learning tasks and more advanced temporal data mining techniques.

### Dataset

The project uses two datasets:

1. IMDb Metadata Dataset (`imdb.csv`): The dataset contains **149,531 titles**, covering different forms of visual entertainment, originally described by 32 attributes. After preprocessing and feature engineering, the dataset was reduced to a set of relevant variables used throughout the subsequent analyses.

2. IMDb Time Series Dataset (`imdb_ts.csv`): This dataset contains **1,134 univariate time series**, each representing the domestic daily box office gross of a movie, from its release date up to the following 100 days.This dataset is used to investigate temporal patterns, cluster similar revenue trajectories, and classify movies according to their rating categories.

### Methodology

The project is structured into seven analytical sections.

1. Data Understanding and Preparation. The preprocessing pipeline includes:

- Feature engineering and removal of redundant variables.
- Duplicate record identification and handling.
- Missing value analysis and imputation.
- Multi-label encoding of genres and geographical information.
- Logarithmic transformations of highly skewed numerical variables.
- Creation of stratified training and test sets using a 70/30 split.

2. Advanced Data Preprocessing This section investigates two important challenges in machine learning: class imbalance and outlier detection.
3. Advanced Classification

The classification analysis focuses on two different target variables:
  A. Title Type Classification. The first task aims to predict the type of an IMDb title across ten different categories, including movies, TV series, TV episodes, shorts, videos,       and video games. The following models were implemented and compared:
    
    - Logistic Regression
    - Support Vector Machine (SVM)
    - Bagging
    - AdaBoost
    - Gradient Boosting
    - XGBoost
    - Neural Networks

    In particular, XGBoost achieved:
    - Accuracy: 93%
    - Macro F1-score: 0.72
    - Weighted F1-score: 0.93

  B. Rating Classification. The second classification task aims to predict IMDb rating categories, ranging from 1 to 10. The same families of machine learning algorithms were evaluated.

    However, this task proved considerably more challenging due to:
    - Strong class imbalance.
    - The limited representation of extreme ratings.
    - The subjective nature of user ratings.
    - The difficulty of distinguishing between neighboring rating categories.

    Bagging and XGBoost achieved the best overall results, with approximately 46% and 45% accuracy, respectively, and a macro F1-score of 0.31 for both models. These findings highlight the limitations of predicting subjective ratings using only structural IMDb metadata.

4. Explainable AI (XAI). To improve model interpretability, **SHAP (SHapley Additive exPlanations)** was applied to the Neural Network developed for title type classification.

5. Advanced Regression. The regression task focuses on predicting the continuous variable `averageRating`. To avoid target leakage, the ordinal `rating` variable was excluded from the input features. Although Random Forest achieved the best results, the task remains challenging, suggesting that user ratings depend on subjective factors that cannot be fully captured by the available metadata.

  Three models were evaluated:
  - Support Vector Regressor (SVR)
  - Random Forest Regressor
  - Neural Network implemented with PyTorch

6. Time Series Analysis. The time series analysis investigates the temporal evolution of domestic box office revenues for 1,134 movies. Several techniques were applied to extract meaningful temporal information.

7. Sequential Pattern Mining. The final section investigates recurring temporal sequences in movie box office performance. The **Generalized Sequential Patterns (GSP)** algorithm was applied to identify frequent sequences of revenue categories. The results show that movies tend to maintain high or medium-high revenue levels during the first days following their release. Conversely, recurring long sequences of low or medium revenue were not identified, suggesting that lower-revenue periods are generally more sporadic.

### Technologies and Libraries

The project was developed in Python and relies on several data science and machine learning libraries.

| Area | Technologies |
|---|---|
| Programming Language | Python |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Gradient Boosting | XGBoost |
| Deep Learning | PyTorch |
| Imbalanced Learning | imbalanced-learn |
| Explainable AI | SHAP |
| Time Series Feature Extraction | catch22 |
| Dimensionality Reduction | PCA, t-SNE |
| Time Series Analysis | Motifs, Shapelets, DTW |
| Sequential Pattern Mining | GSP |

### Main Results and Conclusions

The project provides a comprehensive comparison of different data mining approaches applied to IMDb metadata and movie box office time series.

The main findings can be summarized as follows:

- **Title type prediction:** machine learning models achieved strong predictive performance, with XGBoost reaching 93% test accuracy.
- **Rating prediction:** predicting user ratings proved considerably more difficult, with the best models achieving approximately 45–46% accuracy.
- **Class imbalance:** minority classes significantly affect classification performance, making macro F1-score an essential evaluation metric.
- **Outlier detection:** different anomaly detection strategies provide complementary perspectives on unusual observations.
- **Model explainability:** SHAP identified runtime and geographical distribution as particularly informative features for title type classification.
- **Rating regression:** Random Forest achieved the best regression performance, with a test R² of 0.45.
- **Time series clustering:** four distinct temporal patterns were identified, highlighting different box office revenue dynamics.
- **Motifs and shapelets:** recurring revenue structures can also provide useful information for distinguishing between movie categories.
- **Sequential pattern mining:** high and medium-high revenues frequently occur during the initial days following a movie's release.

Overall, the project demonstrates how combining traditional machine learning, explainable AI, and temporal data mining can provide a deeper understanding of complex entertainment datasets.

### Project Information

**Course:** Data Mining: Advanced Topics and Applications

**University:** University of Pisa

**Academic Year:** 2024/2025

**Authors:**
- Gaia Federica Francesca Ferrara
- Lavinia Rotellini
- Luca Santolillo

---

*This project was developed as part of the Data Mining: Advanced Topics and Applications course at the University of Pisa.*
