# DL-SentimentAnalysis
📌 Project Title
Analysis of User Sentiment Evolution in Reviews and Interactions over Time

👥 Team Members
Dhruv Jain (202418020)
Kaustubh Wade (202418024)
Anujit Nair (202418036)
Naman Gandhi (202418038)



📖 Problem Definition
This project focuses on forecasting the evolution of user sentiments over time from Amazon product reviews, particularly in the Cell Phones & Accessories category. Traditional sentiment analysis offers static insights, missing dynamic changes due to market trends or user experience shifts. Our goal is to build a predictive framework that uses time-series modeling to uncover such sentiment patterns and trends.


📚 Dataset
Source: Amazon Reviews for Cell Phones and Accessories

Key Features:

Textual feedback (Review Body)
Star ratings (1–5 scale)
Timestamps
Helpfulness votes
Preprocessing Steps:

Filtered helpful reviews
Cleaned and normalized text
Computed sentiment scores (VADER)
Combined sentiment + rating into a unified sentiment score
Applied sliding window for time-series forecasting
🔧 Methodology
Combined sentiment score = 0.5 × (Rating Score) + 0.5 × (VADER Score)
Normalized sentiment into weekly time windows
Forecasting using:
Bi-LSTM
Temporal Convolutional Network (TCN)
Transformer



🧠 Model Architectures
1. LSTM (Main Model)
Input: Sliding window of past sentiment
LSTM (64 units)
Dense output layer for H-step forecasting
Optimized with MSE loss, early stopping
2. Baseline: Moving Average
Simple smoothing across the past L days
3. SOTA Models
TCN with dilated causal convolutions
Transformer with positional encoding & self-attention



⚙️ Training Strategy
Train/Val/Test split: 80% / 10% / 10%
Optimizer: Adam (lr = 0.001)
Epochs: Max 50 with early stopping (patience = 5)
Evaluation Metric: Mean Squared Error (MSE)



📊 Results
Model	MSE
Moving Avg	0.000112
LSTM	0.000148
TCN	0.000246
Transformer	0.000543
Insight: Moving Average and LSTM performed best in trend forecasting. Transformer captured long-term dependencies but lagged in short-term volatility.
