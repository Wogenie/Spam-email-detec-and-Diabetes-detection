# Spam Email Detection and Diabetes Prediction

This repository contains two machine learning projects:

1. Spam Email Detection — a classifier to detect spam vs ham emails.
2. Diabetes Prediction — a model to predict diabetes risk from clinical features.

Both projects include code for data preprocessing, model training, evaluation, and example usage.

---

## Project Overview

This repository contains two separate but related ML demos demonstrating common classification workflows:

- Spam Email Detection: preprocesses email text (tokenization, vectorization), trains one or more classifiers (e.g., Naive Bayes, Logistic Regression, or a simple neural network), evaluates with precision/recall/F1, and provides a script for predicting new messages.

- Diabetes Prediction: preprocesses tabular clinical data, trains models (e.g., Logistic Regression, RandomForest, XGBoost), evaluates with ROC/AUC and other metrics, and includes scripts/notebooks to reproduce experiments.

The code is organized so you can run either project independently.

## Repository Structure

Note: exact file names may vary. Adjust commands below for the filenames present in this repo.

- spam_detection/
  - data/                  — sample datasets or download scripts
  - notebooks/             — exploratory notebooks

- diabetes_prediction/
  - data/
  - notebooks/

- README.md               — this file

## Requirements

- Python 3.8+
- pip
- Recommended virtual environment (venv, conda)

The repository may include component-specific requirements files. To install general dependencies:

python -m pip install -r spam_detection/requirements.txt
python -m pip install -r diabetes_prediction/requirements.txt

If the repo has a single top-level requirements.txt, use that instead.

## Setup

1. Clone the repo:

   git clone https://github.com/Wogenie/Spam-email-detec-and-Diabetes-detection.git
   cd Spam-email-detec-and-Diabetes-detection

2. (Optional) Create a virtual environment and activate it:

   python -m venv .venv
   source .venv/bin/activate  # macOS/Linux
   .\.venv\Scripts\activate  # Windows PowerShell

3. Install dependencies (see Requirements above).

4. Prepare datasets (see Datasets section).

## Usage

Adjust paths and filenames to match the code in this repository.

### Spam Email Detection

1. Prepare or download the dataset and place it in `spam_detection/data/` (common datasets: SpamAssassin, SMS Spam Collection).

2. Preprocess data:

   python spam_detection/src/preprocess.py --input spam_detection/data/raw.csv --output spam_detection/data/processed.csv

3. Train a model:

   python spam_detection/src/train.py --data spam_detection/data/processed.csv --model-out spam_detection/models/spam_model.pkl

4. Evaluate:

   python spam_detection/src/evaluate.py --model spam_detection/models/spam_model.pkl --test-data spam_detection/data/test.csv

5. Predict on new messages:

   python spam_detection/src/predict.py --model spam_detection/models/spam_model.pkl --message "Free money!!!"

### Diabetes Prediction

1. Place the diabetes dataset (e.g., Pima Indians Diabetes Dataset) in `diabetes_prediction/data/`.

2. Preprocess data:

   python diabetes_prediction/src/preprocess.py --input diabetes_prediction/data/raw.csv --output diabetes_prediction/data/processed.csv

3. Train a model:

   python diabetes_prediction/src/train.py --data diabetes_prediction/data/processed.csv --model-out diabetes_prediction/models/diabetes_model.pkl

4. Evaluate:

   python diabetes_prediction/src/evaluate.py --model diabetes_prediction/models/diabetes_model.pkl --test-data diabetes_prediction/data/test.csv

5. Predict:

   python diabetes_prediction/src/predict.py --model diabetes_prediction/models/diabetes_model.pkl --features "5,116,74,0,0,25.6,0.201,30"

## Datasets

Common datasets used for these projects (not included unless present in the repo):

- Spam datasets: SMS Spam Collection, SpamAssassin public corpus.
- Diabetes dataset: Pima Indians Diabetes Dataset (UCI / Kaggle).

If you need to download datasets automatically, look for download scripts in `data/` directories or add URLs and instructions to the relevant component.

## Models & Evaluation

Typical model choices:

- Spam detection: Multinomial Naive Bayes, Logistic Regression, SVM, simple neural networks. Use TF-IDF or word embeddings as features.
- Diabetes prediction: Logistic Regression, RandomForest, XGBoost, and calibration/feature importance analysis.

Evaluation metrics:

- Classification accuracy, precision, recall, F1-score, ROC AUC. For imbalanced spam detection, prefer precision/recall and PR AUC.

## Results

Add any model performance results, confusion matrices, or example outputs here. If notebooks exist, they likely contain experimental results and visualizations.

## Contributing

Contributions are welcome. Suggested workflow:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/my-feature`.
3. Add tests and documentation for new code.
4. Open a pull request describing your changes.

Please follow standard Python code style and include dependency updates in requirements files.

## License

If this repository does not already include a LICENSE file, only for learning purpose
## Contact

For questions, open an issue or contact the repository owner: https://github.com/Wogenie

---
