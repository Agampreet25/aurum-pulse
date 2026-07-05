# AurumPulse Insights
Sentiment-Aware Financial Forecasting System for Gold Price Prediction
AurumPulse Insights is an end-to-end machine learning system for short-horizon gold price forecasting under noisy market conditions. The project integrates LSTM–Autoencoder–based representation learning with sentiment-aware decision logic to generate actionable buyer/seller insights, bridging predictive modeling and human-centric decision support.

The project is copyrighted under UPES IS Cell.

🔍 Motivation

Financial time series such as gold prices exhibit non-stationarity, noise, and temporal dependencies, making reliable forecasting challenging. While deep learning models can capture temporal structure, raw predictions alone are often insufficient for decision-making.

AurumPulse Insights addresses this gap by:
Learning robust latent representations using an Autoencoder
Forecasting future prices with LSTM-based sequence modeling
Translating predictions into interpretable, user-aware signals (buyer vs seller)

🧠 Methodology Overview

The system follows a three-stage architecture:

Sequence Encoding (Autoencoder)

A stacked LSTM Autoencoder learns compressed representations of 30-day gold price windows.

Helps denoise input sequences and stabilize downstream forecasting.

Forecasting (LSTM Regressor)

The encoded sequence is passed to an LSTM forecaster to predict the next closing price.

Trained using Mean Squared Error (MSE) loss.

Sentiment-Aware Decision Logic

Forecasts are contextualized based on user intent (buyer or seller).

Outputs actionable guidance (e.g., “Good time to buy” or “Consider holding off”).

🏗️ System Architecture
Raw Gold Prices (30-day window)
        ↓
LSTM Autoencoder (Representation Learning)
        ↓
LSTM Forecaster (Next-Day Prediction)
        ↓
Sentiment Logic (Buyer / Seller Context)
        ↓
Actionable Insight + Predicted Price

📊 Model & Evaluation

Input Window: 30 historical closing prices

Models Used:

LSTM Autoencoder (denoising & representation learning)

LSTM Regression Model (forecasting)

Evaluation Metrics:

RMSE

MAE

Directional Accuracy

Achieves 98–99% directional accuracy with 12–18% RMSE improvement over classical baselines under noisy conditions.

Note: Directional accuracy is emphasized over raw accuracy to reflect realistic decision-making performance in financial forecasting.

🌐 Web Application

The system is deployed as a Flask-based web application with:

Interactive frontend (HTML/CSS/JavaScript)

Real-time prediction via REST API

Visualization-ready outputs

Users input:

A sequence of 30 closing prices

Their intent (Buyer / Seller)

The system returns:

Predicted next-day gold price

Current market price

Contextual decision guidance

⚙️ Tech Stack

Backend: Python, Flask

ML Frameworks: TensorFlow, scikit-learn

Data Processing: NumPy, Pandas

Frontend: HTML, CSS, JavaScript, Chart.js

Deployment: Docker
