# Alzheimer's MRI Classification Project

This repository contains the code and documentation for classifying different stages of Alzheimer's disease using MRI scans. The models trained in this project classify MRI scans into four categories: Mild Demented, Moderate Demented, Non-Demented, and Very Mild Demented. Various deep learning techniques and preprocessing steps were applied to improve classification accuracy and handle dataset imbalances.

## Project Overview

- **Dataset**: Alzheimer's MRI dataset with four classes:
  - `Mild Demented`
  - `Moderate Demented`
  - `Non Demented`
  - `Very Mild Demented`
link to data set used: https://www.kaggle.com/datasets/tourist55/alzheimers-dataset-4-class-of-images

- **Models Implemented**:
  - **CNN**: A basic convolutional neural network (accuracy: 66-68%).
  - **Inception v3**: Pre-trained model, underperformed (accuracy: 60-62%).
  - **DenseNet-121**: Best-performing model, achieved 74-76% accuracy, improved to 98.6% with oversampling.
  - **ResNet**: Improved from 66-69% accuracy to 78% with Sobel edge detection and data augmentation.

- **Techniques**:
  - Data augmentation (rescale, rotate, zoom, brightness adjustment, etc.)
  - Oversampling (SMOTE) to handle class imbalance
  - K-fold cross-validation
  - Sobel edge detection & Gabor filtering
  - Ensemble voting system (DenseNet + ResNet)

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Model Performance](#model-performance)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/OskarEM/Alzheimer_classification.git
    cd Alzheimer_classification
    ```

2. Create and activate a virtual environment (optional but recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use venv\Scripts\activate
    ```

3. Install required dependencies:
   There are no requirment files as each file is based on diffrent models,
   so each is needed to be downloaded according to use.
    ```bash
    pip install
    ```

5. Download the Alzheimer's MRI dataset and place it in a dictonary, example the `data/` directory:
    ```
    data/
      |-- MildDemented/
      |-- ModerateDemented/
      |-- NonDemented/
      |-- VeryMildDemented/
    ```
6. Then use the preprocessing file to create the training and validation sets.
   There are some diffrent preprocesses based on which model that you want to train.
   But if you want to only train without augmentations you can make a script that just splits the
   data set in too training and validation without augmentation. 

## Usage

1. **Training Models**:
   - To train individual models (e.g., DenseNet-121 or ResNet), we use ipynb scripts,
     that both trains and analyses / gives matraixes of the diffrent results of the training and validation.
     

2. **Data Augmentation**:
   - Augmentations like rescale, rotation, zoom, and brightness adjustments are applied in the `augmentation.ipynb` file.
     

3. **Handling Class Imbalance**:
   - SMOTE oversampling and class weighting are handled in `imbalance.ipynb`.
    

4. **Voting System**:
   - Combine the DenseNet and ResNet models using the ensemble voting system is done in `voting.ipynb`.
     

## Model Performance

| Model                           | Accuracy  |
|----------------------------------|-----------|
| CNN                              | 66-68%    |
| Inception v3                     | 60-62%    |
| DenseNet-121                     | 98.6%     |
| ResNet                           | 88%       |
| **Voting (DenseNet + ResNet)**   | **98.9%** |



