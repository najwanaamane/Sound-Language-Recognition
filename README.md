# Sound-Language-Recognition
Language Recognition from wav audio files Using GMM Models and MFCC parametrization
Here's the updated README to reflect that the files are Jupyter notebooks (`.ipynb`) instead of Python scripts (`.py`).

## README for Language Recognition Project

# Language Recognition Using GMM Models

## Overview

This project focuses on implementing Gaussian Mixture Models (GMM) for automatic language recognition. The objective is to develop a data processing pipeline using Python to train a machine learning model capable of recognizing spoken languages.

## Project Structure

### 1. Data Collection

- **Dataset**: Audio recordings of different languages in WAV format.
- **Data Storage**: Audio files are read and stored in lists for further processing.

### 2. Data Preprocessing

- **MFCC Extraction**: Extract Mel Frequency Cepstral Coefficients (MFCC) features from audio data.
- **Silence Removal**: Remove silent frames to improve data quality and reduce false positives.
- **Saving Features**: Save MFCC features into text files categorized by speaker gender.

### 3. Train-Test Split

- **Data Division**: Split data into training and testing sets based on a specified ratio.
- **Feature Loading**: Load MFCC features from text files for each set.

### 4. Model Training

- **GMM Initialization**: Initialize and train multiple GMM models with different numbers of components.
- **Model Saving**: Save trained models into .pkl files for future use.

### 5. Performance Evaluation

- **Likelihood Scores**: Calculate likelihood scores for each GMM model on the test set.
- **Model Selection**: Select the model with the mean score closest to zero as the best-performing model.
- **ROC Curves**: Use ROC curves to evaluate prediction performance.

## Detailed Process

### Data Collection
Audio recordings are collected from various directories containing WAV files of speakers in different languages, including:
- English
- French
- Arabic (including Moroccan dialect)
- Spanish
- Italian
- German
- Turkish
- Japanese
- Korean

### Data Preprocessing
- **MFCC Extraction**: Extract relevant features using the `python_speech_features` library.
- **Silence Removal**: Calculate the energy of vocal signals and remove silent frames based on a set threshold.
- **Saving Features**: Save MFCC features into text files categorized by gender.

### Train-Test Split
- **Function**: `train_test_split`
- **Task**: Split data based on speaker gender and load MFCC features for each set.

### Model Training
- **Functions**: `gmm16`, `gmm32`, `gmm64`, `gmm128`, `gmm256`
- **Task**: Train GMM models with different numbers of components and save them.

### Performance Evaluation
- **Function**: `score_samples`
- **Task**: Calculate likelihood scores and compare them to evaluate model performance.

### Language Prediction and ROC Analysis
- **Prediction Function**: `predict_language`
- **ROC Curve Function**: `plot_roc_curve`
- **Analysis**: Evaluate performance for different segment durations and analyze ROC curves for each language.

## Hypotheses and Results
- **Variability**: Languages with higher variability in shorter segments are easier to identify.
- **Overfitting**: Longer segments may lead to overfitting, reducing model generalization.
- **Segment Length**: Shorter segments simplify classification, improving model focus on essential features.

## Conclusion
The project demonstrates a comprehensive methodology for processing audio data and building a language recognition model. Results vary across languages, highlighting the importance of dataset quality. Improvements can be made by enhancing data quality and using more advanced hardware.

## Authors and Acknowledgments
- **Author**: Najwa Naamane
- **Supervisor**: Prof. ElKharroubi Jamal

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

## Acknowledgements
Thank you for considering this project. Your feedback and contributions are welcome.

---

### Usage Instructions
1. **Clone the Repository**: `git clone <repository_url>`
2. **Install Dependencies**: `pip install -r requirements.txt`
3. **Run Jupyter Notebooks**:
    - **Preprocessing**: Open and run `preprocess.ipynb`
    - **Model Training**: Open and run `train.ipynb`
    - **Model Evaluation**: Open and run `evaluate.ipynb`
    - **Language Prediction**: Open and run `predict.ipynb`

For detailed steps and explanations, please refer to the provided documentation in the repository.
