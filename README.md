# BBC News Text Classification

## Overview

This project focuses on automatically classifying news articles into their respective categories using Natural Language Processing (NLP) and machine learning techniques.

The project uses the **BBC News dataset**, which contains news articles from five categories:

- Business
- Entertainment
- Politics
- Sport
- Tech

The text data is processed using several Natural Language Processing techniques before being transformed into numerical representations using **TF-IDF (Term Frequency-Inverse Document Frequency)**.

Two classification algorithms are then implemented and compared:

- **Multilayer Perceptron (MLP)**
- **K-Nearest Neighbors (KNN)**

The models are evaluated using classification metrics including **accuracy, precision, recall, and F1-score**.

---

## Objectives

The objectives of this project are to:

- Classify news articles automatically based on their content.
- Apply Natural Language Processing techniques to raw news text.
- Transform textual data into numerical features using TF-IDF.
- Build a text classification model using Multilayer Perceptron.
- Build a text classification model using K-Nearest Neighbors.
- Determine an appropriate K value for the KNN model using cross-validation.
- Compare the performance of MLP and KNN for news classification.
- Test the trained models on new unseen text.

---

## Dataset

The project uses the **BBC News Text Dataset**.

The dataset contains news articles categorized into five topics:

| Category | Description |
|---|---|
| `business` | Business and financial news |
| `entertainment` | Entertainment and media news |
| `politics` | Political news |
| `sport` | Sports-related news |
| `tech` | Technology-related news |

The dataset is stored as:

```text
data/bbc-text.csv
```

# Exploratory Data Analysis

The initial exploratory analysis was performed to understand the structure and characteristics of the BBC News dataset before applying text preprocessing and machine learning models.

The analysis included:

- Inspecting the dataset structure.
- Checking the number of observations and variables.
- Checking data types.
- Checking missing values.
- Analyzing the distribution of news categories.
- Examining the characteristics of the text data.

The distribution of news articles across the five categories was visualized to understand the class composition of the dataset.

The five news categories are:

- Business
- Entertainment
- Politics
- Sport
- Tech

---

# Text Preprocessing

Before feature extraction, the raw news text was processed using several Natural Language Processing techniques.

## Tokenization

Tokenization was performed using NLTK's `word_tokenize` to split each news article into individual words or tokens.

This allows the text to be processed at the word level.

## Text Normalization

The text was normalized through several steps:

- Converting text to lowercase.
- Removing unnecessary symbols and characters.
- Removing duplicated whitespace.
- Reconstructing the processed text.

These steps help reduce variations in text representation before feature extraction.

## Stopword Removal

English stopwords were removed using NLTK's English stopword list.

Stopwords are common words that generally provide limited information for text classification.

Removing these words helps the feature representation focus on terms that are more relevant to distinguishing between news categories.

---

# Feature Extraction

## TF-IDF

The preprocessed news text was transformed into numerical features using **Term Frequency-Inverse Document Frequency (TF-IDF)**.

TF-IDF represents each document as a numerical feature vector based on the importance of individual terms within the document and across the collection of documents.

Words that occur frequently within a document but less frequently across the dataset receive relatively higher weights.

This transformation allows the textual data to be used as input for machine learning algorithms.

## Feature Analysis

The resulting TF-IDF feature matrix was further analyzed to understand the characteristics of the extracted features.

The project also calculated the **Gini Index** for TF-IDF features and visualized the resulting values to examine their distribution.

---

# Model Development

Two supervised machine learning algorithms were developed for news classification:

- **Multilayer Perceptron (MLP)**
- **K-Nearest Neighbors (KNN)**

## Multilayer Perceptron

The first classification model uses a **Multilayer Perceptron (MLP)** classifier.

MLP is a neural-network-based algorithm that learns relationships between the TF-IDF feature representation and the corresponding news categories.

The model was configured with:

```text
hidden_layer_sizes = (6, 5)
random_state = 5
learning_rate_init = 0.01
```

## Model Evaluation

The MLP and KNN models were evaluated to measure their classification performance.

The evaluation included:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

### Accuracy

Accuracy measures the proportion of correctly classified news articles among all evaluated articles.

A higher accuracy indicates that a larger proportion of the test observations were assigned to their correct news categories.

### Precision

Precision measures the proportion of articles predicted as a particular category that actually belong to that category.

### Recall

Recall measures the proportion of articles belonging to a particular category that were successfully identified by the model.

### F1-score

F1-score combines precision and recall into a single metric.

It provides a balanced measure of the model's ability to correctly identify each news category.

### Confusion Matrix

A confusion matrix was generated to examine the classification performance across the five news categories.

The matrix compares the actual categories with the categories predicted by the model.

This allows correctly classified articles and misclassification patterns between categories to be examined in more detail.

---

## Text Prediction

After the models were trained and evaluated, they were used to classify new and previously unseen news articles.

The new text was processed using the same preprocessing steps and TF-IDF transformation applied during model development.

The prediction workflow was:

```text
New News Article
        ↓
Text Preprocessing
        ↓
TF-IDF Transformation
        ↓
Trained Classification Model
        ↓
Predicted News Category
```

## Prediction Results

The trained models were tested using new news articles that were not part of the original training observations.
The prediction examples covered sports, entertainment, politics, and cricket-related texts.
Each input text was transformed into the TF-IDF representation before being passed to the trained classification model.
The model then returned a predicted news category for each text sample.

## Conclusion

This project demonstrates the application of Natural Language Processing and supervised machine learning for automatic BBC News classification.

The workflow includes exploratory data analysis, text preprocessing, TF-IDF feature extraction, model development, model evaluation, and prediction on unseen text.

Two classification algorithms were implemented:

- Multilayer Perceptron (MLP)
- K-Nearest Neighbors (KNN)

For KNN, 10-fold cross-validation was used to determine the number of neighbors, resulting in K = 4 as the selected configuration.
The models were evaluated using accuracy, precision, recall, F1-score, and confusion matrices.
The trained models were also applied to new news articles to demonstrate their ability to classify previously unseen text into predefined news categories.

Overall, the project demonstrates how Natural Language Processing and supervised machine learning can be combined to build an automated news text classification system.

## Project Context

This project was developed as an academic project focusing on Natural Language Processing, text mining, and supervised machine learning.
The project applies text classification techniques to automatically categorize BBC News articles based on their textual content.
