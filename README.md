# RNN---Sentiment-Analysis

## Sentiment Analysis on #TheSocialDilemma Tweets

## Project Overview
This project involves classifying tweets with the hashtag #TheSocialDilemma into three sentiment categories: Positive, Neutral, and Negative. The dataset contains nearly 20,000 tweets extracted using TwitterAPI, capturing reactions from users worldwide after watching the documentary "The Social Dilemma" released on Netflix on September 9th, 2020.

## Problem Statement
Given the tweets related to "The Social Dilemma," the goal is to categorize them into three sentiment categories: Positive, Neutral, and Negative. The goal is to build a model using a Recurrent Neural Network (RNN) to accurately classify the sentiments of tweets.

## Dataset Description
The dataset contains the following attributes:

| **Attribute**       | **Description**                                                |
|---------------------|----------------------------------------------------------------|
| **user_name**       | The name of the user, as defined by them.                      |
| **user_location**   | The user-defined location for the account’s profile.           |
| **user_description**| A UTF-8 string describing the user's account.                  |
| **user_created**    | The date and time when the account was created.                |
| **user_followers**  | The number of followers the account currently has.             |
| **user_friends**    | The number of friends the account currently has.               |
| **user_favourites** | The number of favorites the account currently has.             |
| **user_verified**   | Indicates whether the user has a verified account.             |
| **date**            | UTC date and time when the Tweet was created.                  |
| **hashtags**        | All hashtags posted in the tweet along with #TheSocialDilemma. |
| **source**          | Utility used to post the Tweet (e.g., "web" for Twitter website).|
| **is_retweet**      | Indicates whether the Tweet is a retweet.                      |
| **clean_text**      | Cleaned text of the tweet.                                     |
| **Sentiment**       | Sentiment of the tweet, categorized as Positive, Neutral, or Negative. |


### Model Development

#### Text Preprocessing
- **Text Cleaning**: "Ensured all entries in the `clean_text` column were converted to strings for consistent text processing."
- **Tokenization**: The `clean_text` from the dataset was tokenized using Keras' `Tokenizer` with a vocabulary size of 20,000 words. This converts the text into sequences of integers, where each integer corresponds to a specific word in the tokenizer's vocabulary.
- **Padding**: After tokenization, the sequences were padded to a uniform length of 100 to ensure that all inputs to the RNN have the same shape. This padding adds zeros to the sequences that are shorter than the specified length.
  

#### Model Architecture
- **Embedding Layer**: Converts the tokenized integer sequences into dense vector representations, which the RNN can process.

- **SimpleRNN Layer**: Captures sequential dependencies in the text data.

- **Dense Layer**: The final layer uses softmax activation to output probabilities across the three sentiment categories: Positive, Neutral, and Negative.

#### Model Compilation
- The model was compiled using the following settings:
  - **Loss Function**: Categorical Crossentropy, which is suitable for multi-class classification problems.
  - **Optimizer**: Adam, a popular choice for training deep learning models.
  - **Evaluation Metric**: Accuracy, to measure the model's performance.

- **Compilation**: 
  - Loss Function: Categorical Crossentropy.
  - Optimizer: Adam.
  - Evaluation Metric: Validation Accuracy Score.
  
  

### Model Evaluation
- **Validation Accuracy**: The model achieved a validation accuracy of **86.29%** on the test data, indicating strong performance in classifying the sentiments of the tweets.

## Conclusion
This project demonstrates the effectiveness of using a Simple RNN model for sentiment analysis on social media data. The achieved validation accuracy of 86.29% suggests that the model can reliably categorize tweets into Positive, Neutral, and Negative sentiments. Further improvements could involve exploring different RNN architectures or fine-tuning hyperparameters.

