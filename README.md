# Fruit Ripeness Classification Using Custom CNN and MobileNetV2 Transfer Learning

## Overview

This repository contains the implementation of an automated fruit ripeness classification system using deep learning. The project compares a custom Convolutional Neural Network (CNN) trained from scratch with a MobileNetV2 transfer learning model on the Fresh and Rotten Fruits dataset (six classes: fresh and rotten apples, bananas, and oranges). The project includes data preprocessing, data augmentation, model training, evaluation, and comparison between the two approaches.

---

## Project Structure

```
├── fruit_ripeness_classification.ipynb   # Main project notebook
├── README.md                             # Project documentation
├── requirements.txt                      # Required Python packages
├── outputs/                              # Saved figures, metrics, and trained models
└── dataset/                              # Dataset directory (not uploaded to GitHub)
```

---

## Requirements

### Software

- Python 3.9+
- Jupyter Notebook or Kaggle Notebook
- Git

### Python Libraries

```
tensorflow
keras
numpy
pandas
matplotlib
seaborn
scikit-learn
opencv-python
pillow
```

Install all dependencies:

```
pip install -r requirements.txt
```

---

## Dataset Setup

### Option 1: Kaggle Dataset

1. Download the dataset from:

```
https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification
```

2. Add the dataset to your Kaggle notebook.

3. Update the dataset path if necessary.

Example:

```
dataset_path = "/kaggle/input/fruits-fresh-and-rotten-for-classification"
```

### Option 2: Local Machine

Create the following directory structure:

```
dataset/
├── freshapples/
├── freshbanana/
├── freshoranges/
├── rottenapples/
├── rottenbanana/
└── rottenoranges/
```

Update the dataset path inside the notebook:

```
dataset_path = "dataset/"
```

---

## Running the Project

### Using Kaggle

1. Upload `fruit_ripeness_classification.ipynb`
2. Attach the Fruits Fresh and Rotten for Classification dataset
3. Run all notebook cells

### Using Jupyter Notebook

Start Jupyter:

```
jupyter notebook
```

Open:

```
fruit_ripeness_classification.ipynb
```

Run all cells sequentially.

---

## Project Workflow

The notebook performs the following tasks:

### 1. Dataset Loading

- Load fruit images from the six class folders
- Assign class labels automatically from folder names using `ImageDataGenerator`

### 2. Data Preprocessing

- Resize images to 128 × 128 pixels
- Normalize pixel values to the range [0, 1]

### 3. Data Splitting

- Training set (10,886 images)
- Validation set (20% of training data, 2,177 images)
- Test set (2,698 images)

### 4. Data Augmentation

- Rotation (20°)
- Zoom (0.2)
- Horizontal flip
- Width and height shifts (0.2)

### 5. Custom CNN Development

- Three convolutional blocks (32, 64, 128 filters)
- MaxPooling after each block
- Dense layer (256 neurons) with Dropout (0.5)
- Softmax output layer (6 classes)

### 6. Transfer Learning (MobileNetV2)

- Frozen MobileNetV2 backbone pretrained on ImageNet
- Global Average Pooling layer
- Dense layer (128 neurons) with Dropout (0.5)
- Softmax output layer (6 classes)

### 7. Model Training

- Adam optimizer, learning rate 0.001
- Categorical cross-entropy loss
- Batch size 16, 10 epochs

### 8. Model Evaluation

- Accuracy, precision, recall, F1-score
- Confusion matrices
- ROC curves and AUC
- Classification reports

### 9. Visualization

- Accuracy and loss curves (training and validation)
- Confusion matrices for both models
- Model comparison bar chart
- ROC curves
- Sample and misclassified predictions

---

## Output Files

The notebook generates:

| File                                   | Description                                |
| --------------------------------------- | ------------------------------------------- |
| cnn_accuracy_curve.png                  | Custom CNN training and validation accuracy |
| cnn_loss_curve.png                      | Custom CNN training and validation loss     |
| mobilenet_accuracy_curve.png            | MobileNetV2 training and validation accuracy|
| mobilenet_loss_curve.png                | MobileNetV2 training and validation loss    |
| cnn_confusion_matrix.png                | Confusion matrix for the custom CNN         |
| mobilenet_confusion_matrix.png          | Confusion matrix for MobileNetV2            |
| model_comparison.png                    | Accuracy comparison bar chart               |
| roc_curves.png                          | ROC curves for all six classes              |
| classification_report_cnn.txt           | Custom CNN evaluation metrics               |
| classification_report_mobilenet.txt     | MobileNetV2 evaluation metrics              |
| custom_cnn_model.h5                     | Trained custom CNN model                    |
| mobilenetv2_model.h5                    | Trained MobileNetV2 model                   |

---

## Reproducibility

To reproduce the results:

1. Download the Fruits Fresh and Rotten for Classification dataset.
2. Install all dependencies from `requirements.txt`.
3. Update dataset paths if required.
4. Run the notebook from start to finish.
5. Generated figures and metrics will be saved automatically to the `outputs/` folder.

---

## Results

| Model             | Accuracy | Precision | Recall  | Weighted F1-score |
| ----------------- | -------- | --------- | ------- | ------------------ |
| Custom CNN        | 95.44%   | 95.52%    | 95.44%  | 95.42%              |
| MobileNetV2        | 98.52%   | 98.53%    | 98.52%  | 98.51%              |

MobileNetV2 outperformed the custom CNN by approximately 3.08 percentage points in test accuracy, while using fewer trainable parameters (164,742 vs. 6,517,574).

---

## Author

Arkesha Lalitha Annajappa

Fruit Ripeness Classification Project

Deep Learning and Computer Vision Coursework
