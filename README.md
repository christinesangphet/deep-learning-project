# Song Recommendation System Based on Mood and Preferences

## Overview
This project features a song recommendation system that suggests songs based on a user's mood or preference. Using a Fine-Tuned Feedforward Neural Network (FFNN) model, the system predicts song topics based on their lyrics and provides personalized recommendations. Gradio is used for interactive user input.

## How It Works
### Model Training:
The Fine-Tuned Feedforward Neural Network (FFNN) model was trained on a dataset of song lyrics from the "Music Dataset: 1950 to 2019" from Kaggle. The model predicts topics such as sadness, violence, romance, etc., based on the lyrics of the song.

### Song Recommendation System:
User Input: The user selects a mood or topic, such as "sadness."
Topic Conversion: The system converts the selected topic into a numeric label.
Prediction: The lyrics of all songs are passed through the trained model, which outputs a probability distribution of topics for each song.
Confidence Threshold: Songs with a probability above 0.5 for the selected topic are recommended.
Fallback: If there are not enough songs with high confidence for a topic, the system will fall back and recommend songs from that topic without applying the confidence threshold.

### Gradio Interface:
The system is built using Gradio, a Python library that creates interactive user interfaces. The user can easily select a mood or topic, and the system will provide five recommended songs matching that topic.

## Model Evaluation
The model was evaluated using the following metrics:
Overall Metrics: Accuracy, weighted precision, and weighted recall were calculated to provide an overview of the model's performance across all topics.
Detailed Performance: A classification report was generated for each song topic, showing accuracy, precision, recall, F1-score, and support for each.
Confusion Matrix: A confusion matrix was visualized to identify where the model had difficulty distinguishing between similar topics.
Key Findings: The Fine-Tuned FFNN model outperformed other models with an accuracy of around 93%. The best-performing topics were the most frequent ones, while less frequent topics faced challenges.

## Song Recommendation System
The recommendation system provides song suggestions based on the user's selected mood or topic:
The user picks a mood or topic.
The system processes song lyrics through the model, which outputs a prediction for each song.
Only songs with a confidence score above 0.5 are recommended.
If there aren't enough confident predictions, songs from the selected topic are still recommended without applying the confidence threshold.
