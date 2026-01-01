🎯 Comparative Analysis — ML vs DL on Images

<p align="center">
	<a href="https://www.python.org/"><img src="https://img.shields.io/badge/python-3.8%2B-blue" alt="Python"/></a>
	<a href="https://jupyter.org/"><img src="https://img.shields.io/badge/jupyter-notebook-orange" alt="Jupyter"></a>
	<a href="https://www.kaggle.com/code/muhammadhassnain11/comparative-analysis-of-ml-vs-dl-models-on-images"><img src="https://img.shields.io/badge/Kaggle-Notebook-20BEFF?logo=kaggle" alt="Kaggle Notebook"></a>
</p>

This repository contains a notebook comparing classical machine learning (ML) models and deep learning (DL) models for image classification (MNIST-style Digit Recognizer).

Kaggle notebook (original project):

https://www.kaggle.com/code/muhammadhassnain11/comparative-analysis-of-ml-vs-dl-models-on-images

Files
- `comparative-analysis-of-ml-vs-dl-models-on-images.ipynb` — Main notebook with data preprocessing, model training, evaluation, and visualizations.

Quick Usage
- Open the notebook in Jupyter and run cells sequentially. See the first cells for environment and dataset instructions.

✨ Extracted details (from the notebook)
- **Dataset:** Kaggle Digit Recognizer CSVs (`/kaggle/input/digit-recognizer/train.csv`, `/kaggle/input/digit-recognizer/test.csv`).
- **Sampling:** `n_samples_per_label = 3000` (per-class balanced sampling).
- **Preprocessing:** pixel scaling `/255.0`, CNN reshape `(28,28,1)`, ML features scaled with `StandardScaler()`.
- **Classical ML models:** `KNN`, `RandomForest`, `SVM` (trained on scaled features).
- **DL models & key hyperparams:**
	- **`CNN_V2`** — optimizer: `adam`, loss: `sparse_categorical_crossentropy`, epochs: `50`, batch_size: `64`, EarlyStopping(monitor=`val_loss`, patience=`4`), dropout: `0.3/0.4/0.5`, dense: `256` units.
	- **`LeNet-5`** — optimizer: `adam`, epochs: `50`, batch_size: `64`.
	- **`Custom DNN`** — dense layers `[512,256,128]`, optimizer: `adam`, epochs: `50`, batch_size: `51`.
- **Evaluation:** accuracy, macro F1, classification reports, confusion matrices; aggregated into `ml_results` (`acc`, `f1`, `time`).
- **Inference:** notebook runs predictions on the unlabeled test CSV and computes agreement/confidence across models.

📸 Results (preview)
Here are representative result images produced by the notebook and saved in the `Results/` folder. Thumbnails are shown — click to open full-size.

-- Overall comparison

<p align="center">
	<a href="Results/all_comp.png"><img src="Results/all_comp.png" width="720" alt="Overall comparison"></a>
	<br/>
	<strong>Figure 1</strong> — Overall accuracy & training-time trade-off
</p>

<p align="center">
	<a href="Results/all_comp_ta.png"><img src="Results/all_comp_ta.png" width="720" alt="Comparison table"></a>
	<br/>
	<strong>Figure 2</strong> — Detailed comparison table
</p>

-- Learning curves (examples)

<p align="center">
	<a href="Results/lc_cnn.png"><img src="Results/lc_cnn.png" width="340" alt="CNN learning curve"></a>
	<a href="Results/lc_dnn.png"><img src="Results/lc_dnn.png" width="340" alt="DNN learning curve"></a>
	<a href="Results/lc_ln.png"><img src="Results/lc_ln.png" width="340" alt="LeNet learning curve"></a>
	<br/>
	<strong>Figure 3</strong> — Learning curves (CNN | DNN | LeNet)
</p>

-- Confusion matrices (examples)

<p align="center">
	<a href="Results/cf_cnn.png"><img src="Results/cf_cnn.png" width="300" alt="CNN confusion matrix"></a>
	<a href="Results/cf_dnn.png"><img src="Results/cf_dnn.png" width="300" alt="DNN confusion matrix"></a>
	<a href="Results/cf_knn.png"><img src="Results/cf_knn.png" width="300" alt="KNN confusion matrix"></a>
	<br/>
	<strong>Figure 4</strong> — Confusion matrices (CNN | DNN | KNN)
</p>

-- Per-model metric charts (examples)

<p align="center">
	<a href="Results/m_cnn.png"><img src="Results/m_cnn.png" width="280" alt="Metrics CNN"></a>
	<a href="Results/m_dnn.png"><img src="Results/m_dnn.png" width="280" alt="Metrics DNN"></a>
	<a href="Results/m_knn.png"><img src="Results/m_knn.png" width="280" alt="Metrics KNN"></a>
	<br/>
	<strong>Figure 5</strong> — Per-model metric charts
</p>

> Note: Filenames are renamed to use underscores for cleaner links. If you prefer different thumbnail sizes or captions, tell me which style you like and I will adjust.
