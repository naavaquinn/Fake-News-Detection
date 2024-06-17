# Make Believe

The main goal of this project is to create a Celebrity Fake News detection model based on the linguistic differences between true and fake news. The dataset used to develop the model is Web Celebrity, a database introduced by Verónica Rosas-Pérez et al. in her 2018 paper "Automatic Detection of Fake News".

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Project Development Summary](#project-development-summary)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Description

"Make Believe" aims to detect fake news related to celebrities by analyzing linguistic features. The project utilizes the Text Characterization Toolkit (TCT) to extract various text features and employs machine learning algorithms to build a robust fake news detection model.

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/make-believe.git
    ```
2. Navigate to the project directory:
    ```sh
    cd make-believe
    ```
3. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. Prepare your dataset and place it in the `data` directory.
2. Run the feature extraction script:
    ```sh
    python extract_features.py
    ```
3. Train the model using the extracted features:
    ```sh
    python train_model.py
    ```
4. Evaluate the model:
    ```sh
    python evaluate_model.py
    ```

## Features

- Extracts discursive, syntactic, lexical, and descriptive characteristics from text using TCT.
- Computes sentiment scores using NLTK and Textblob.
- Implements feature selection techniques like correlation analysis, Kolmogorov-Smirnov test, and recursive feature elimination.
- Trains multiple machine learning models and selects the best performing model based on F1 score and ROC AUC.
- Fine-tunes the selected model using GridSearchCV.

## Project Development Summary

1. **Feature Extraction and Sentiment Analysis**:
    - Used TCT, NLTK, and Textblob to extract features and sentiment scores.
    - Scaled the features for better interpretability.
  
2. **Feature Selection**:
    - Filtered features based on correlation with Polarity.
    - Performed Kolmogorov-Smirnov test to check feature distribution differences between true and fake news.
    - Used Recursive Feature Elimination (RFE) to select important features.
    - Created feature sets: correlation-based, Kolmogorov-Smirnov-based, RFE-based, and all features.

3. **Model Training**:
    - Trained SVC, Random Forest, K-Neighbors, and Logistic Regression models on each feature set.
    - Evaluated models using F1 score to determine the best performing combination.

4. **Model Fine-Tuning**:
    - Used GridSearchCV to optimize Random Forest hyperparameters (depth, number of estimators, split criterion).
    - Selected the final model based on performance stability and complexity.
    - The final model had a maximum depth of 8, 150 estimators, and used the Gini index for splitting.

5. **Final Model Evaluation**:
    - Achieved a final F1 score of ~91% and ROC AUC of ~90% on the training set.
    - Validated the model on an external Kaggle dataset, achieving an F1 score of ~70%.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch:
    ```sh
    git checkout -b feature/YourFeature
    ```
3. Commit your changes:
    ```sh
    git commit -m 'Add some feature'
    ```
4. Push to the branch:
    ```sh
    git push origin feature/YourFeature
    ```
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Thank you for checking out the project, and I hope you find something interesting or useful in it!
