# Thesis-Ecommerce-Price-Prediction
  
## Deadline : 15/04/2024

  **Team member**
   * Nguyen Ha Phuong
   * Nguyen Minh Tu
   * Vu Trong Manh
   * Tran Hai Nam

# Our Work

## Summary Table Results All Models 

+------------------------------------------+-----------------------------------+-----------------------------+------------+
|                  Model                   |           Featurizations          |       Hyperparameters       | Test RMSLE |
+------------------------------------------+-----------------------------------+-----------------------------+------------+
|              Baseline Ridge              |                BOW                |           alpha=10          |   0.472    |
|              Baseline LGBM               |                BOW                | nest=1500,lr=0.05,leaves=50 |    0.47    |
| Baseline Ensemble=(50% Ridge + 50% LGBM) |                BOW                |              --             |    0.46    |
|               Baseline MLP               |  Concatenate Text, OneHotEncoding |         batch = 512         |    0.42    |
|             ----------------             |          ---------------          |       ---------------       |   ------   |
|                 Ridge 1                  |                BOW                |           alpha=10          |   0.471    |
|                 Ridge 2                  |               TFIDF               |           alpha=10          |   0.467    |
|                  LGBM 1                  |                BOW                | nest=1500,lr=0.05,leaves=50 |   0.471    |
|                  LGBM 2                  |               TFIDF               | nest=1500,lr=0.05,leaves=50 |    0.47    |
|                  MLP 1                   |            256-64-64-32           |       Adam,Batch=4096       |   0.418    |
|                  MLP 2                   |       1024-512-256-128-64-32      |       Adam,Batch=4096       |   0.413    |
|                  MLP 3                   |        MLP2 + BN + dropout        |       Adam,Batch=4096       |   0.415    |
|             ----------------             |          ---------------          |       ---------------       |   ------   |
|          Final Model - Ensemble          | MLP 1 + MLP 2 + Ridge 1 + Ridge 2 |     0.9 MLP + 0.1 Ridge     | **0.404**  |
+------------------------------------------+-----------------------------------+-----------------------------+------------+