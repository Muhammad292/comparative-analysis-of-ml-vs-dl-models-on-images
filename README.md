# Comparative Analysis of ML vs DL Models on Images

This repository contains a single notebook that compares classical machine learning (ML) models and deep learning (DL) models on image classification tasks.

Kaggle notebook (original project):

https://www.kaggle.com/code/muhammadhassnain11/comparative-analysis-of-ml-vs-dl-models-on-images

Files
- `comparative-analysis-of-ml-vs-dl-models-on-images.ipynb` — Main notebook with data preprocessing, model training, evaluation, and visualizations.

Usage
- Open the notebook in Jupyter and run cells sequentially. See the first cells for environment and dataset instructions.


Extracted details from the notebook
- Dataset: Kaggle Digit Recognizer (CSV files) used at `/kaggle/input/digit-recognizer/train.csv` and `/kaggle/input/digit-recognizer/test.csv`.
- Sampling: `n_samples_per_label = 3000` (balanced sampling performed per class).
- Preprocessing:
	- Pixel scaling: divide by 255.0.
	- CNN input reshape: `(28, 28, 1)`.
	- ML features scaled with `StandardScaler()`.
- Classical ML models included: `KNN`, `RandomForest`, `SVM` (trained on scaled features; hyperparameters not explicitly set in notebook excerpt).
- Deep learning models & key hyperparameters:
	- `CNN_V2` (custom): optimizer=`adam`, loss=`sparse_categorical_crossentropy`, epochs=`50`, batch_size=`64`, EarlyStopping monitor=`val_loss`, patience=`4`; dropout rates `0.3/0.4/0.5`, final dense `256` units.
	- `LeNet-5` (custom): optimizer=`adam`, epochs=`50`, batch_size=`64`.
	- `Custom DNN` (fully-connected): layers `[512, 256, 128]`, optimizer=`adam`, epochs=`50`, batch_size=`51`.
- Evaluation: accuracy, macro F1, classification reports, confusion matrices; results aggregated into `ml_results` dict with keys `acc`, `f1`, `time`.
- Test/Inference: notebook uses `/kaggle/input/digit-recognizer/test.csv` as an unlabeled test set and runs predictions for all models; also computes prediction agreement and model confidences.

If you want, I can now update the README to include a `requirements.txt` and embed exact hyperparameter values directly into `ML_PROJECT_DOCS.md`.
