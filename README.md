# Thesis-Ecommerce-Price-Prediction
  
It can be hard to know how much something’s really worth. Small details can mean big differences in pricing. For example, one of these sweaters cost $335 and the other cost $9.99. Can you guess which one’s which?

<img src='https://storage.googleapis.com/kaggle-media/competitions/mercari/mercari_comparison.png'>

Product pricing gets even harder at scale, considering just how many products are sold online. Clothing has strong seasonal pricing trends and is heavily influenced by brand names, while electronics have fluctuating prices based on product specs.

Mercari, Japan’s biggest community-powered shopping app, knows this problem deeply. They’d like to offer pricing suggestions to sellers, but this is tough because their sellers are enabled to put just about anything, or any bundle of things, on Mercari's marketplace.

In this competition, Mercari’s challenging you to build an algorithm that automatically suggests the right product prices. You’ll be provided user-inputted text descriptions of their products, including details like product category name, brand name, and item condition.

<!-- ##
  **Team member**
   * Nguyen Ha Phuong
   * Nguyen Minh Tu
   * Vu Trong Manh
   * Tran Hai Nam -->

<hr><div>

## Table of Contents

 **All Experimentation and Models are in .ipynb files. Table of Contents and sections in .ipynb files as below :** 

| S.No: | Section  | Notebook(.ipynb) |
| ----  | --------- | ------------- |
| 1.    | Business Problem|  1_eda.ipynb |
| 2.    | Exploratory Data Analysis|  1_eda.ipynb |
| 3.    | Data Processing|  2_process.ipynb |
| 4.    | Feature Engineering|  2_process.ipynb |
| 5.    | Correlation heatmap|  2_process.ipynb |
| 6.    | Final Data Preparation|  3_baseline_machine_learning_models.ipynb |
| 7.    | Evaluation Metiric|  3_baseline_machine_learning_models.ipynb |
| 8.    | Baseline Ridge Model|  3_baseline_machine_learning_models.ipynb |
| 9.    | Baseline LGBM Model|  3_baseline_machine_learning_models.ipynb |
| 10.    | Baseline Ensemble Model|  3_baseline_machine_learning_models.ipynb |
| 12.    | Baseline MLP (Colab)|  4_baseline_mlp(colab).ipynb |
| 13.    | Final Models|  5_final_ensemble_models(colab) |
| 14.    | Final Summary|  5_final_ensemble_models(colab) |

<hr><div>

## Experimental Results

**Summary Table Results Of All Models**

| Model | Featurizations | Hyperparameters | Test RMSLE | Test RMSE|
|---|---|---|---|
| Baseline Ridge | BOW | alpha=10 | 0.472 |
| Baseline LGBM | BOW | nest=1500, lr=0.05, leaves=50 | 0.47 |
| Baseline Ensemble (50% Ridge + 50% LGBM) | BOW | -- | 0.46 |
| Baseline MLP | Concatenate Text, OneHotEncoding | batch = 512 | 0.42 |
||
| Ridge 1 | BOW | alpha=10 | 0.471 |
| Ridge 2 | TFIDF | alpha=10 | 0.467 |
| Ridge 1 + Ridge 2| 0.4 Ridge1 + 0.6 Ridge2|-- |0.462|
||
| LGBM 1 | BOW | nest=1500, lr=0.05, leaves=50 | 0.471 |
| LGBM 2 | TFIDF | nest=1500, lr=0.05, leaves=50 | 0.47 |
| MLP 1 | 256-64-64-32 | Adam, Batch=4096 | 0.418 |
| MLP 2 | 1024-512-256-128-64-32 | Adam, Batch=4096 | 0.413 |
| MLP 3 | MLP2 + BN + dropout | Adam, Batch=4096 | 0.415 |
| MLP 1 + MLP 2| 0.45 MLP1 + 0.55 MLP2|-- |0.407|
||
| Final Model - Ensemble | MLP 1 + MLP 2 + Ridge 1 + Ridge 2 | 0.9 MLP + 0.1 Ridge | **0.404** |
