# Coursera-Reviews-Sentiment-Analysis-using-DistillBERT

## Overview

The Coursera Reviews Sentiment Analysis project aims to analyze and categorize user reviews of Coursera courses based on their sentiments.Leveraging natural language processing techniques and a DistillBERT-based sentiment analysis model from the Transformers library by Hugging Face, this project classifies reviews into positive, neutral, or negative sentiments, Providing valuable insights into the overall satisfaction of users with Coursera courses by identifying the best course choice for each user.

## Dataset

The dataset used in this project is publicly available on Kaggle since 2017. The dataset contains 2 files reviews.tsv and reviews_by_course.csv. The reviews.tsv file has 107018 review with no grouping, just the review id and their corresponding label. For the reviews_by_course.csv, they are 140320 review and their label grouped by the CourseId.
The project focuses on the `reviews_by_course.csv` file, which contains a structured set of course reviews with the following details:

- **Number of Rows:** 140,320
- **Columns:**
  - `CourseId`: The course tag, which corresponds to the course tag in the URL of the Coursera website.
  - `Review`: The text of the course review.
  - `Label`: The rating of the course review, ranging from 1 to 5, where 5 represents the most positive rating and 1 represents the most negative rating.


## Project Implementation

#### Identifying Data Imbalance

Upon initial exploration of the dataset, it was observed that the distribution of sentiments was imbalanced. To address this, a thorough data exploration was conducted to understand the distribution of sentiment labels.

### Data Cleaning

To ensure the model's training on meaningful data, a data cleaning process was implemented. This involved the removal of non-English reviews using the langid library, ensuring that the model is trained on relevant and linguistically consistent data.

### Model Selection

#### Base Model

The project selected `distilbert-base-uncased` from the Transformers library as the base model due to its remarkable speed and high-performance capabilities. This distilled version of BERT maintains impressive accuracy while significantly reducing computational requirements, making it an optimal choice for efficient sentiment analysis.

### Model Fine-Tuning

The base model was fine-tuned on the preprocessed dataset using TensorFlow. The fine-tuning process involved training the model on the Coursera reviews data, considering the imbalanced distribution of sentiments.

### Handling Data Imbalance

Given the imbalanced nature of the data, class weights were incorporated during model training to address bias and ensure the model effectively learned from minority classes.

### Model Evaluation

#### Baseline Comparison

The model's performance was evaluated on validation data and compared against a baseline model. The baseline model yielded a loss of 1.0833, while the fine-tuned model achieved a significantly improved loss of 0.63.

#### Metrics Consideration

Considering the imbalanced nature of the data, metrics such as recall, precision, and F1 score were employed for evaluation. These metrics provide a more comprehensive understanding of the model's performance across different sentiment classes.

#### Model Publication

The trained model was published and shared on the Hugging Face Model Hub. You can access the model using the following link: [Coursera Sentiment Analysis using DistillBERT](https://huggingface.co/NourhanAbosaeed/Coursera_Reviews_Sentiment_Analysis_DistillBERT).


