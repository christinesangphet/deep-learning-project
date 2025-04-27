# Song Recommendation System Based on Mood and Preferences

## Overview

This project features a **song recommendation system** that suggests songs based on a user's mood or preference. Using a **Fine-Tuned Feedforward Neural Network** model, the system predicts song topics based on their lyrics and provides personalized recommendations. **Gradio** is used for interactive user input, allowing users to easily select topics and receive song recommendations.

## Process

### Preprocessing

The preprocessing stage involves cleaning and preparing the song lyrics data for model training. Key tasks include:
- Removing irrelevant information (e.g., stopwords, special characters).
- Tokenizing song lyrics into words.
- Converting text data into a format suitable for machine learning, such as transforming words into numerical representations.

### Exploratory Data Analysis (EDA)

During the exploratory data analysis (EDA) phase, we analyze using feature engineerings, clustering and visualization to identify patterns in musical attributes and group songs into distinct clusters.. This helps us understand patterns in the data and ensures we address any imbalances or outliers before training the model.

### Model Training

We trained and evaluated **three different models**:
- **Feedforward Neural Network**
- **Fine-Tuned Feedforward Neural Network**
- **Transformer-based model**

After assessing the performance of all three, the **Fine-Tuned Feedforward Neural Network** performed the best, with an accuracy of approximately **93%**. As a result, we chose the FTNN model to power the song recommendation system.

### Model Evaluation

The model was evaluated using the following metrics to assess its performance:

- **Overall Metrics:** Accuracy, weighted precision, and weighted recall were used to summarize the model's performance across all topics.
  
- **Detailed Performance:** A **classification report** was generated for each song topic, showing metrics like accuracy, precision, recall, F1-score, and support for each class.
  
- **Confusion Matrix:** We visualized the **confusion matrix** to identify where the model had difficulty distinguishing between similar topics.

- **Key Findings:** The **FTNN** outperformed the other models by a slight margin (about 1-2%) and was selected as the final model for the recommendation system.

## Song Recommendation System

### How It Works

1. **User Input:** The user selects a mood or topic (e.g., "sadness").
2. **Topic Conversion:** The selected topic is converted into a numeric label using label encoding.
3. **Prediction:** The lyrics of all songs are passed through the trained FTNN model, which outputs a probability distribution of topics for each song.
4. **Confidence Threshold:** Songs with a probability greater than 0.5 for the selected topic are recommended.
5. **Fallback:** If there aren't enough songs with a high confidence score, songs from the selected topic are still recommended, even without applying the confidence threshold.

### Gradio Interface

The song recommendation system is built using **Gradio**, which allows users to easily interact with the model. Through the Gradio interface, users can select a mood or topic, and the system will generate five random songs that match the chosen topic.
