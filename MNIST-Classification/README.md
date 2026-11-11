# MNIST Handwritten Digit Classification

Comparing K-Nearest Neighbors (KNN) and Support Vector Machines (SVM) on handwritten digit recognition using the MNIST dataset.

## Results

| Evaluation | KNN | SVM |
|---|---:|---:|
| Baseline 3-fold CV accuracy (20,000 images) | 95.22% | 96.30% |
| Tuned 3-fold CV accuracy (20,000 images) | 95.54% | **96.94%** |

The SVM was selected using cross-validation and retrained on the full 60,000-image training set. Its final accuracy on the separate 10,000-image test set was **98.37%** (9,837 correct classifications).

A separate image-resolution experiment in the notebook reported **98.52%** test accuracy for 16×16 images, compared with **98.37%** at 28×28. These are the saved notebook outputs, not newly reproduced runs.

## Method

- Dataset: MNIST, 70,000 grayscale images of digits 0–9.
- Model selection: KNN vs. RBF SVM with GridSearchCV and stratified 3-fold cross-validation.
- Hyperparameter search on 20,000 images, followed by fitting the selected model on 60,000 images.
- Evaluation: accuracy, precision, recall, F1 score, confusion analysis, ROC/precision–recall analyses, and resolution comparison.

## Run in Google Colab

[Open the original notebook in Google Colab](https://colab.research.google.com/drive/1PAhheyD3YDmFUvoGRRiExVcRpNGoLKok?usp=sharing)

Install packages from requirements.txt, then run the cells in order. Training the SVM can be CPU intensive.

## Project files

- `MNIST_KNN_vs_SVM.ipynb` — source code and saved output charts (not yet uploaded)
- `results/` — 16 selected plots (not yet uploaded)
- `requirements.txt` — Python package dependencies

## Note on robustness experiments

The notebook also includes separate robustness tests. One of those cells reports a different original accuracy (97.55%) from the main final evaluation (98.37%), so those results should be reviewed and rerun before being used as headline performance claims.
