# Fruit Freshness Classification using Deep Learning

## Project Description

This project classifies fruits into six categories:

* Fresh Apples
* Fresh Bananas
* Fresh Oranges
* Rotten Apples
* Rotten Bananas
* Rotten Oranges

A custom Convolutional Neural Network (CNN) was developed and compared with MobileNetV2.

---

## Dataset

Dataset:Fruits Fresh and Rotten for Classification

Kaggle Dataset:https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification

---

## Methodology

* Image resizing (128 × 128)
* Normalization
* Data augmentation
* Custom CNN architecture
* MobileNetV2 comparison
* Confusion matrix
* Classification report
* Accuracy and loss curves

---

## Results

The custom CNN achieved high classification accuracy and outperformed MobileNetV2 under the current environment settings.

---

### Notebook

Fruit_Freshness_Classification.ipynb

---

### Models

* cnn_model.h5
* mobilenet_model.h5

---

### Figures

* cnn_accuracy_curve.png
* cnn_loss_curve.png
* cnn_confusion_matrix.png
* model_comparison.png

---

## How to Run

1. Clone the repository.

2. Install dependencies:

pip install -r requirements.txt

3. Open the notebook and run all cells.

---

## Libraries Used

* TensorFlow
* Keras
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

---

## Author

Arkesha Lalitha Annajappa
