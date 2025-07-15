
# Drug–Target Binding Prediction Using MACCS & ProtBERT with Ensemble Learning

## Overview
This project aims to predict drug–target binding interactions using machine learning models trained on chemical and protein sequence features.

## Dataset
- Source: BindingDB_Kd (from [TDC](https://tdcommons.ai))
- Samples: 52,274 drug–target pairs
- Target Variable: Binding affinity (converted to binary: bind vs. not bind)

## Feature Engineering
- Drug Features: MACCS molecular fingerprints (167-dim)
- Protein Features: ProtBERT embeddings (1024-dim)
- Final Input: 1191 features per pair

## Models Used
- Logistic Regression
- Random Forest
- XGBoost
- Voting Ensemble (Soft Voting)

## Improvements & Techniques
- SMOTE for class imbalance
- Threshold tuning (e.g., 0.4 for XGBoost)
- Class weights in LR & RF
- ROC AUC + Recall-focused optimization

## Results (Test Set)
| Model         | Recall | F1 Score | ROC AUC |
|---------------|--------|----------|---------|
| Logistic Reg  | 0.07   | 0.13     | 0.87    |
| Random Forest | 0.58   | 0.53     | 0.93    |
| XGBoost       | 0.70   | 0.40     | 0.94    |
| **Ensemble**  | **0.69** | **0.51** | **0.945** |

## ROC Curves
Included in `results/roc_curve.png`

## Authors
- Varshitha
- Tools used: Google Colab, scikit-learn, XGBoost, ProtBERT, SMOTE, RDKit, PyTDC

## License
MIT License
