# Privacy-Preserving and Explainable Federated Learning for Outcome Prediction in Primary Biliary Cirrhosis

## 1. Project Overview

This research project investigates privacy-preserving and explainable federated learning (FL) for predicting death or survival in patients with Primary Biliary Cirrhosis (PBC).

The project compares federated learning algorithms under independent and identically distributed (IID) and non-IID data settings. It also investigates privacy mechanisms, communication efficiency, and model interpretability.

The federated learning environment is simulated on a single machine using five clients.

## 2. Research Objectives

- Develop a federated learning pipeline for PBC outcome prediction.
- Compare FedAvg, FedProx, and FedNova aggregation methods.
- Evaluate performance under IID and non-IID data distributions.
- Investigate update clipping, quantisation, secure aggregation simulation, and differential privacy noise.
- Reduce communication costs through update quantisation.
- Explain model predictions using SHAP, LIME, and permutation feature importance (PFI).
- Evaluate model performance using accuracy, precision, recall, F1-score, and AUC.

## 3. Dataset Description

The study uses the Mayo Clinic Primary Biliary Cirrhosis dataset described in the research paper.

- **Total patients:** 418
- **Prediction task:** Binary classification
- **Target:** Death or survival
- **Input features:** 18 numerical features
- **Training/validation/test split:** 70% / 15% / 15%

Follow-up time (`N_Days`) is excluded from the input features because it is measured after baseline and is related to the outcome.

Add the exact dataset source used by the notebook before publishing. Do not upload patient-level data unless redistribution is permitted.

## 4. Methodology

### Data Preprocessing
- Convert age from days to years.
- Encode categorical and ordinal variables.
- Transform selected skewed laboratory variables.
- Handle missing values and standardise features.
- Split the data before fitting preprocessing statistics.

### Federated Learning
Five simulated clients participate in federated training.

The algorithms compared are:
- Federated Averaging (FedAvg)
- Federated Proximal (FedProx)
- Federated Normalised Averaging (FedNova)

### Privacy and Communication
The research investigates:
- Update clipping
- 8-bit update quantisation
- Simulated secure aggregation using pairwise masks
- Gaussian noise for differential privacy experiments

### Explainable Artificial Intelligence
Three methods are used to investigate model behaviour:
- SHAP (SHapley Additive exPlanations)
- LIME (Local Interpretable Model-agnostic Explanations)
- Permutation Feature Importance (PFI)

## 5. Main Results

The paper reports the following mean test accuracy across five random seeds.

| Experimental Setting | Method | Mean Accuracy |
|---|---|---:|
| IID | FedAvg | 0.730 ± 0.045 |
| IID | FedProx | 0.724 ± 0.053 |
| IID | FedNova | 0.730 ± 0.045 |
| Non-IID | FedAvg | 0.667 ± 0.076 |
| Non-IID | FedProx | 0.667 ± 0.076 |
| Non-IID | FedNova | 0.689 ± 0.044 |

The paper reports that centralised reference models achieved accuracies between approximately 0.775 and 0.787.

Differential privacy noise accounted for much of the observed performance reduction, while quantisation reduced communication requirements without a measurable accuracy loss in the reported experiments.

These values are reported results from the paper and have not been independently reproduced by this README.

## 6. Repository Structure

Update the filenames below to match the files uploaded to GitHub.

- `FL_Cirrhosis_Colab.ipynb` — Google Colab notebook containing the implementation.
- `Paper_FL_Cirrhosis.pdf` — Research paper in PDF format.
- `Research_Paper.docx` — Editable Word version, if included.
- `README.md` — Project description and instructions.
- `requirements.txt` — Required Python packages, if included.

## 7. How to Run the Project

1. Open the notebook in Google Colab.
2. Obtain the required dataset from its original source.
3. Install any required packages that are missing from the runtime.
4. Run the notebook cells in order.
5. Review the generated evaluation metrics, plots, and explainability results.

For reproducibility, record the dataset version and the Python package versions used.

## 8. Limitations

- The dataset contains only 418 patients.
- The federated environment is simulated on a single machine.
- Secure aggregation is simulated rather than implemented as a complete cryptographic protocol.
- The paper does not establish a formally accounted end-to-end differential privacy guarantee.
- External validation is needed before any clinical application.

**Disclaimer:** This project is intended for academic research and educational purposes. It is not a validated clinical decision-making tool.

## 9. Research Paper

The full research paper is available as a PDF in this repository. An editable Word version can also be included.

