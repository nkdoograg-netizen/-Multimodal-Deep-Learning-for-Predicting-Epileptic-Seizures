# Multimodal Deep Learning for Predicting Epileptic Seizures

An interactive, browser-based **Seizure Risk Monitor** plus a machine-learning
pipeline for predicting epileptic seizures from multimodal signals (EEG + ECG).

## Live demo

Open the deployed app: see the GitHub Pages link in the repository **About** section
(`index.html` is the entry point).

The UI runs fully in the browser - no backend. The trained model weights
(logistic regression, RBF SVM with Platt scaling, and a 100-tree random forest)
are exported and embedded directly inside `index.html`.

## Repository contents

| File | Description |
|------|-------------|
| `index.html` | Interactive Seizure Risk Monitor (deployed app) |
| `Seizure risk monitor (1).html` | Original UI file |
| `epileptic_seizure_prediction.ipynb` | ML pipeline notebook (EDA, training, evaluation) |
| `epileptic_seizure_prediction_executed.ipynb` | Notebook with saved outputs |
| `synthetic_seizure_demo_100_patients.csv` | Demo dataset (100 patients, EEG + ECG features) |

## Dataset

100 synthetic patients, 8 features, balanced target (`seizure_label`):

| Feature | Description |
| --- | --- |
| `EEG_mean`, `EEG_std` | EEG mean voltage and variability |
| `EEG_delta_power`, `EEG_theta_power`, `EEG_alpha_power`, `EEG_beta_power` | Band powers |
| `ECG_heart_rate_bpm` | Heart rate |
| `ECG_RMSSD_ms` | Heart-rate variability (RMSSD) |

## Pipeline

1. Load and inspect data (`synthetic_seizure_demo_100_patients.csv`).
2. Feature/target split, stratified 80/20 train-test split.
3. Standardise features.
4. Train and evaluate **Logistic Regression**, **Random Forest** and **SVM (RBF)**.
5. Report accuracy, precision, recall, F1, ROC-AUC and 5-fold cross-validation.
6. Export model parameters into the self-contained HTML monitor.

## Disclaimer

Demo only. Models were trained on synthetic data and have **not** been validated on
real recordings. Not for diagnosis or treatment.
