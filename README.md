# Explainable Machine Learning for Parkinson’s Disease Detection Using Vocal Biomarkers
This repository contains a machine learning project that uses vocal biomarkers to detect Parkinson’s Disease. By analyzing subtle vocal impairments using explainable AI methods, the project aims to provide a non-invasive and accessible screening tool for early-stage Parkinson’s detection.

# Overview
Parkinson’s Disease (PD) is a progressive neurological disorder characterized by motor and non-motor symptoms. Early diagnosis is challenging since traditional methods rely on clinical observations and in-person assessments. This project focuses on using voice recordings—which capture PD-related features like dysphonia, hypophonia, and monotone speech—as an efficient screening mechanism.

The project uses a variety of machine learning models, including Logistic Regression, K-Nearest Neighbors, and Decision Trees. Explainability tools such as SHAP (SHapley Additive exPlanations) help interpret the model’s decisions.

# Dataset
The dataset consists of voice recordings from both Parkinson’s patients and healthy individuals. Each sample includes several features derived from the voice signal:

| Feature                      | Description                                                                                                      |
|------------------------------|------------------------------------------------------------------------------------------------------------------|
| MDVP:Fo(Hz)                  | Average vocal fundamental frequency.                                                                           |
| MDVP:Fhi(Hz)                 | Maximum vocal fundamental frequency.                                                                           |
| MDVP:Flo(Hz)                 | Minimum vocal fundamental frequency.                                                                           |
| MDVP:Jitter(%)               | Percentage variation in fundamental frequency.                                                                 |
| MDVP:Jitter(Abs)             | Absolute jitter measurement.                                                                                     |
| MDVP:RAP                     | Relative average perturbation.                                                                                   |
| MDVP:PPQ                     | Pitch perturbation quotient.                                                                                     |
| Jitter:DDP                   | Differences between consecutive jitter values.                                                                   |
| MDVP:Shimmer                 | Amplitude variation in the voice.                                                                                |
| MDVP:Shimmer(dB)             | Shimmer in decibels.                                                                                             |
| Shimmer:APQ3 & Shimmer:APQ5   | Amplitude perturbation quotients over different time windows.                                                    |
| MDVP:APQ                     | Averaged amplitude perturbation quotient.                                                                        |
| Shimmer:DDA                  | Difference of differences in shimmer.                                                                            |
| NHR & HNR                    | Noise-to-harmonics and harmonics-to-noise ratios, respectively.                                                  |
| RPDE                         | Recurrence period density entropy, measuring signal complexity.                                                  |
| DFA                          | Detrended fluctuation analysis for long-range correlations.                                                      |
| Spread1 & Spread2            | Measures of variability in the voice signal.                                                                     |
| D2                           | Correlation dimension indicating the complexity of the underlying dynamical system.                                |
| PPE                          | Pitch period entropy, reflecting pitch irregularity.                                                             |

The target variable, status, indicates the presence (1) or absence (0) of Parkinson’s Disease.

# Methodology
                         |
| **Explainability**      | - Use SHAP to generate global and local explanations, showing which features most strongly influence the predictions.<br>- Visualize SHAP summary and dependence plots to interpret model behavior.                                                                              |














# Data Preprocessing
- Remove non-essential columns (e.g., patient name) to focus on acoustic features.
- Explore feature distributions using violin plots and kernel density estimates.
- Scale features with StandardScaler

 Distribution of each vocal feature in the dataset, it shows how values are spread and where they concentrate.

 <div align="center">
<img src="https://github.com/user-attachments/assets/e568d520-9cc2-432d-beec-6e73e32d66da" alt="Untitled" width="600" height="500" />
<\div>

Correlation of features:

<div align="center">
<img src="https://github.com/user-attachments/assets/afe929ed-4808-4dce-8da5-d2562412bf8c" alt="Untitled" width="600" height="500" />
<\div>


# Model Building
- Train multiple models (Logistic Regression, K-Nearest Neighbors, Decision Tree).
- Evaluate performance with metrics such as accuracy, precision, recall, F1 score, and AUC.

# Future Work
* **Integration of Multi-Modal Data:** Incorporate additional data sources (e.g., gait analysis, neuroimaging) to improve diagnostic accuracy.
* **Uncertainty Quantification:** Implement Bayesian methods or Monte Carlo dropout to quantify prediction uncertainty.
