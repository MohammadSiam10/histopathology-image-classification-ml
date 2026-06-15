# Histopathology Image Classification using Machine Learning

This project explores machine learning and deep learning approaches for classifying colon cell histopathology image patches from a modified CRCHistoPhenotypes-style dataset.

The project was completed as part of my Computational Machine Learning coursework and has been converted into a portfolio-friendly version. The original processed assessment dataset, label files, image files, and submission materials are not included in this repository.

## Project Overview

The project involved two supervised image classification tasks:

1. **Cancer classification**
   Predict whether a colon cell image is cancerous or non-cancerous.

2. **Cell-type classification**
   Predict the cell type as fibroblast, inflammatory, epithelial, or others.

The images were small 27×27 RGB histopathology patches. This made the task challenging because the visual differences between classes were subtle and depended on colour, texture, staining patterns, and local cellular morphology.

## Evaluation Design

A key part of the workflow was patient-level splitting. Instead of randomly splitting individual images, the data was split by patient ID so that validation and test patients were unseen during training.

This reduced the risk of data leakage and provided a more realistic estimate of model generalisation to new patients.

## Methods Used

The workflow included:

* dataset inspection and quality checks
* image availability checking
* class distribution analysis
* patient-level train/validation/test splitting
* image normalisation
* flattened pixel features for classical models
* RGB tensor inputs for CNN models
* PCA-based exploratory visualisation
* classical ML baselines
* convolutional neural networks
* hyperparameter tuning
* data augmentation
* ensemble modelling
* threshold tuning
* accuracy, macro-F1, weighted-F1, classification reports, and confusion matrices
* responsible AI and clinical limitations discussion

## Models Explored

The project compared several approaches, including:

* Logistic Regression
* Support Vector Machine
* Random Forest
* Convolutional Neural Network
* Augmented CNN
* Ensemble models

## Key Findings

PCA visualisation showed strong overlap between classes, especially for the cell-type task. This suggested that simple low-dimensional separation was not sufficient and that more expressive supervised models were needed.

For the cancer classification task, combining a tuned Random Forest with an augmented CNN improved validation performance. Threshold tuning further improved macro-F1.

For the cell-type classification task, CNN checkpointing was important because validation performance fluctuated across epochs.

## Final Test Summary

The final models were evaluated once on unseen patients after validation-based model selection.

* Cancer classification: tuned Random Forest + augmented CNN ensemble
* Cell-type classification: CNN with checkpointing

The models were useful for exploratory machine learning analysis, but they are not suitable for clinical deployment without expert validation, larger datasets, external testing, and clinical governance.

## Skills Demonstrated

* Python
* pandas
* NumPy
* scikit-learn
* PyTorch
* computer vision
* medical image analysis
* CNN modelling
* image preprocessing
* PCA visualisation
* patient-level evaluation
* model comparison
* hyperparameter tuning
* data augmentation
* ensemble learning
* threshold tuning
* macro-F1 evaluation
* responsible AI discussion

## Data Availability

The processed assessment dataset and image files are not included in this repository. This repository is intended to document the machine learning workflow and project learning outcomes without redistributing restricted coursework data.
