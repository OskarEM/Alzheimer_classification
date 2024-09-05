# Alzheimer's MRI Classification Project

This repository contains the code and documentation for classifying different stages of Alzheimer's disease using MRI scans. The models trained in this project classify MRI scans into four categories: Mild Demented, Moderate Demented, Non-Demented, and Very Mild Demented. Various deep learning techniques and preprocessing steps were applied to improve classification accuracy and handle dataset imbalances.

## Project Overview

- **Dataset**: Alzheimer's MRI dataset with four classes:
  - `Mild Demented`
  - `Moderate Demented`
  - `Non Demented`
  - `Very Mild Demented`
  
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
    git clone https://github.com/yourusername/Alzheimer-MRI-Classification.git
    cd Alzheimer-MRI-Classification
    ```

2. Create and activate a virtual environment (optional but recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use venv\Scripts\activate
    ```

3. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Download the Alzheimer's MRI dataset and place it in the `data/` directory:
    ```
    data/
      |-- MildDemented/
      |-- ModerateDemented/
      |-- NonDemented/
      |-- VeryMildDemented/
    ```

## Usage

1. **Training Models**:
   - To train individual models (e.g., DenseNet-121 or ResNet), use the respective script:
     ```bash
     python train_densenet.py  # To train DenseNet
     python train_resnet.py    # To train ResNet
     ```

2. **Data Augmentation**:
   - Augmentations like rescale, rotation, zoom, and brightness adjustments are applied in the `augmentation.py` file:
     ```bash
     python augmentation.py
     ```

3. **Handling Class Imbalance**:
   - SMOTE oversampling and class weighting are handled in `imbalance.py`:
     ```bash
     python imbalance.py
     ```

4. **Voting System**:
   - Combine the DenseNet and ResNet models using the ensemble voting system:
     ```bash
     python voting_system.py
     ```

## Model Performance

| Model                           | Accuracy  |
|----------------------------------|-----------|
| CNN                              | 66-68%    |
| Inception v3                     | 60-62%    |
| DenseNet-121                     | 98.6%     |
| ResNet                           | 88%       |
| **Voting (DenseNet + ResNet)**   | **98.9%** |

## Contributing

We welcome contributions! If you have suggestions or improvements, please fork the repository and submit a pull request. Ensure your code follows the project guidelines.

### Steps to Contribute:
1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Open a pull request

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
