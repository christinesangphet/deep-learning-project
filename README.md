# Deep Learning Approach on Music Recommendation System

## Overview

This project features a song recommendation system that suggests songs based on a user's mood or preference. Using a Fine-Tuned Feedforward Neural Network model, the system predicts song topics based on their lyrics and provides personalized recommendations. Gradio is used for interactive user input, allowing users to easily select topics and receive song recommendations.

The system is trained on a dataset from Kaggle: "Music Dataset: 1950 to 2019" (https://www.kaggle.com/datasets/saurabhshahane/music-dataset-1950-to-2019/data). The dataset contains a variety of songs and their corresponding lyrics, which are used to predict topics such as sadness, romantic, and violence.

## Process

### Preprocessing

The preprocessing stage involves cleaning and preparing the song lyrics data for model training. Key tasks include:
- Removing irrelevant information (e.g., stopwords, special characters).
- Tokenizing song lyrics into words.
- Converting text data into a format suitable for machine learning, such as transforming words into numerical representations.

### Exploratory Data Analysis (EDA)

During the exploratory data analysis (EDA) phase, we used feature engineering, clustering, and visualization techniques to identify patterns in musical attributes and group songs into distinct clusters. This helps us understand the data and ensures we address any imbalances before training the model.

### Model Training

We trained and evaluated three different models:
- Feedforward Neural Network
- Fine-Tuned Feedforward Neural Network
- Transformer-based model

### Model Evaluation

The model was evaluated using the following metrics to assess its performance:

- Overall Metrics: Accuracy, weighted precision, and weighted recall were used to summarize the model's performance across all topics.
  
- Detailed Performance: A classification report was generated for each song topic, showing metrics like accuracy, precision, recall, F1-score, and support for each class.
  
- Confusion Matrix: We visualized the confusion matrix to identify where the model had difficulty distinguishing between similar topics.

- Key Findings: Best and worst performing classes were identified and most frequently confused topic labels were highlighted.

After assessing the performance of all three models, the Fine-Tuned Feedforward Neural Network performed the best, with an overall accuracy of approximately 93%. As a result, we chose this model to power the song recommendation system.

## Song Recommendation System

### How It Works

1. User Input: The user selects a mood or topic (e.g., "sadness").
2. Topic Conversion: The selected topic is converted into a numeric label using label encoding.
3. Prediction: The lyrics of all songs are passed through the trained Fine-Tuned Feedforward Neural Network model, which outputs a probability distribution of topics for each song.
4. Confidence Threshold: Songs with a probability greater than 0.5 for the selected topic are recommended.
5. Fallback: If there aren't enough songs with a high confidence score, songs from the selected topic are still recommended, even without applying the confidence threshold.

### Gradio Interface

The song recommendation system is built using Gradio, which allows users to easily interact with the model. Through the Gradio interface, users can select a mood or topic, and the system will recommend up to 10 random songs that match the chosen topic.

Link: https://5f450278c027cde988.gradio.live/ (NOTE: public URL expires after one week after launch)

## Repository Structure

Each component of the project is organized into a dedicated folder. Most folders include their own `README.md` for detailed descriptions:

```
deep-learning-project/
│
├── data preprocessing and EDA/          # Data cleaning and exploratory analysis
│   ├── music_data_preprocessing.ipynb
│   ├── EDA.ipynb
│   └── README.md
│
├── data/                                # Raw data and dataset description
│   ├── music_data.csv
│   └── README.md
│
├── model evaluation/                    # Model evaluation and metrics
│   ├── model_evaluation_NN_v1.ipynb
│   ├── model_evaluation_NN_v2.ipynb
│   ├── model_evaluation_NN_v3.ipynb
│   └── README.md
│
├── modeling/                            # Model training notebooks
│   ├── mood_prediction_NN_v1.ipynb
│   ├── mood_prediction_NN_v2.ipynb
│   ├── mood_prediction_NN_v3.ipynb
│   └── README.md
│
├── song recommendation system/          # Song Recommendation System: Code Implementation and final interface 
│   ├── song_recommendation_system_1.ipynb
│   └── README.md
│
├── .gitattributes                       # Git LFS tracking for CSV files
├── README.md                            # Main project overview and guide
└── requirements.txt                     # Project dependencies
```

