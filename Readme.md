# Heart Disease Classification with Differential Privacy

## Overview
This repository focuses on using differentially private machine learning (ML) and deep learning (DL) techniques to classify heart disease from medical datasets. By incorporating privacy-preserving algorithms, the project ensures the security of sensitive patient data while maintaining competitive performance metrics.

Key aspects of the project include:
- Binary and multi-class classification of heart disease using traditional and differentially private models.
- Addressing dataset imbalance through resampling techniques.
- Implementing adversarial attacks (e.g., Membership Inference Attack) to evaluate privacy robustness.

---

## Datasets
The dataset used includes heart disease records with features such as age, sex, cholesterol levels, and more. Classification tasks are performed for both binary (presence/absence of heart disease) and multi-class labels (different stages of heart disease).

### Dataset Variants
- **Imbalanced Dataset**: Original dataset without resampling.
- **Balanced Dataset**: Resampled dataset to address class imbalances.

---

## Results

### Binary Classification Results

#### Traditional Models (Imbalanced Dataset)
| Model             | F1 Score | Precision | Recall | Accuracy | AUC Score |
|-------------------|-----------|-----------|--------|----------|-----------|
| XGB               | 0.807692  | 0.750000  | 0.875  | 0.833333 | 0.840278  |
| GradientBoosting  | 0.745098  | 0.703704  | 0.792  | 0.783333 | 0.784722  |
| RandomForest      | 0.791667  | 0.791667  | 0.792  | 0.833333 | 0.826389  |

#### Traditional Models (Balanced Dataset)
| Model             | F1 Score | Precision | Recall | Accuracy | AUC Score |
|-------------------|-----------|-----------|--------|----------|-----------|
| XGB               | 0.800000  | 0.769231  | 0.833  | 0.833333 | 0.833333  |
| GradientBoosting  | 0.769231  | 0.714286  | 0.833  | 0.800000 | 0.805556  |
| RandomForest      | 0.840000  | 0.807692  | 0.875  | 0.866667 | 0.868056  |

#### Differentially Private Models (Balanced Dataset)
| Model              | F1 Score | Precision | Recall | Accuracy | AUC Score |
|--------------------|-----------|-----------|--------|----------|-----------|
| DP Random Forest   | 0.529412  | 0.900000  | 0.375  | 0.733333 | 0.673611  |
| DP KMeans          | 0.298507  | 0.232558  | 0.417  | 0.216667 | 0.250000  |
| DP Decision Tree   | 0.723404  | 0.739130  | 0.708  | 0.783333 | 0.770833  |

### Adversarial Attack: Membership Inference Attack
| Model Name                                  | Accuracy | Precision | Recall | F1 Score | AUC Score |
|--------------------------------------------|----------|-----------|--------|----------|-----------|
| Target RF Model - Membership Inference     | 0.484375 | 0.484375  | 1.000  | 0.652632 | 0.597752  |

### Multi-Class Classification Results

#### Traditional Models (Imbalanced Dataset)
| Model             | F1 Score | Precision | Recall | Accuracy | AUC Score |
|-------------------|-----------|-----------|--------|----------|-----------|
| XGB               | 0.516718  | 0.492800  | 0.556  | 0.555556 | 0.748553  |
| GradientBoosting  | 0.548812  | 0.534887  | 0.586  | 0.585859 | 0.743859  |
| RandomForest      | 0.518131  | 0.480825  | 0.586  | 0.585859 | 0.740038  |

#### Traditional Models (Balanced Dataset)
| Model             | F1 Score | Precision | Recall | Accuracy | AUC Score |
|-------------------|-----------|-----------|--------|----------|-----------|
| XGB               | 0.550151  | 0.548429  | 0.566  | 0.565657 | 0.739072  |
| GradientBoosting  | 0.523471  | 0.528439  | 0.525  | 0.525253 | 0.727486  |
| RandomForest      | 0.513584  | 0.503373  | 0.525  | 0.525253 | 0.678100  |

#### Differentially Private Models (Balanced Dataset)
| Model              | F1 Score | Precision | Recall | Accuracy | AUC Score |
|--------------------|-----------|-----------|--------|----------|-----------|
| DP Random Forest   | 0.556111  | 0.608007  | 0.517  | 0.516667 | 0.573057  |
| DP KMeans          | 0.483664  | 0.565302  | 0.450  | 0.450000 | 0.581287  |
| DP Decision Tree   | 0.531875  | 0.623709  | 0.483  | 0.483333 | 0.591557  |

#### Adversarial Attack: Membership Inference Attack
| Model Name                                  | Accuracy | Precision | Recall | F1 Score | AUC Score |
|--------------------------------------------|----------|-----------|--------|----------|-----------|
| Target RF Model - Membership Inference     | 0.218750 | 0.482299  | 0.219  | 0.094049 | 0.508941  |

---

## Key Features
1. **Traditional ML Models**: Implementation of models like Random Forest, Gradient Boosting, and XGBoost for both binary and multi-class classification tasks.
2. **Differentially Private ML Models**: Utilization of `diffprivlib` for privacy-preserving ML models (e.g., DP Random Forest, DP KMeans, DP Decision Tree).
3. **Adversarial Attack Evaluation**: Analysis of membership inference attacks to assess privacy vulnerabilities.
4. **Performance Analysis**: Comparison of traditional and DP models on imbalanced and balanced datasets.
