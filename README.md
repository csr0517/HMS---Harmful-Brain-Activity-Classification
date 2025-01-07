# HMS - Harmful Brain Activity Classification

## Project Overview
This repository contains our solution for the Kaggle competition "HMS - Harmful Brain Activity Classification". The competition aims to predict and classify epileptic seizures and other types of harmful brain activity using EEG and spectrogram data.

## Files
- Code
  - hms-1dcnn+gru-2defficient-multi-train
  - hms-2defficient-pytorch-train
  - submit
  - These 3 above were code that submitted
- Details in PowerPoint

### Data Preprocessing
Through exploratory data analysis (EDA), we identified and addressed several key issues:
- Removed duplicate or highly similar data samples
- Handled missing values in both EEG and spectrogram data by removing affected samples

### Feature Engineering
Our feature engineering approach focused on two main strategies:

1. Spectrogram Features:
   - Created concatenated features by combining spectrograms of different durations derived from the original 10-minute recordings
   - Used various transformation methods to generate different temporal representations

2. EEG Features:
   - Generated differential EEG wave data by calculating the differences between pairs of original EEG recordings

### Model Architecture
We implemented an ensemble of 8 different models, including:
- EfficientNet V2
- EfficientNet B4
- EEG Net

Each model was trained with different combinations of input data types to ensure diversity in the ensemble.

### Training Strategy
Our training approach incorporated several key techniques:

1. Cross-Validation:
   - Implemented 10-fold cross-validation for robust model evaluation

2. Data Augmentation:
   - Applied masking techniques to both time and frequency dimensions of spectrograms

3. Two-Stage Training Process:
   - Stage 1: Initial training on a subset of the data
   - Stage 2: Fine-tuning the pre-trained models from Stage 1 using the remaining training data

4. Model Ensemble:
   - Combined predictions from all 8 models trained on different data combinations
   - Created an optimal ensemble through weighted averaging of individual model predictions

## Results
The final solution achieved competitive performance through the ensemble of diverse models and sophisticated training strategies.
