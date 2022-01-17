---
title: 'Stock Price Simulator'
excerpt: "We developed a real time stock price prediction tool implementing machine learning algorithms like Linear regressor, KNN, CART and Support Vector Regressors. Implemented the REST API to extract real time stock price data and analyzed the interdependency of different stock prices using LSTM networks.
<br/><img src='/images/stock_prediction.png'>"
collection: portfolio 
tags:
  - Rest-API
  - LSTM
  - Linear regressor 
  - KNN 
  - CART 
  - Support Vector Regressors
---


## Overview
<p align="justify">Prediction of future movement of stock prices has been an area that attracted the attention of the researchers over a long period of time. With the choice of appropriate variable and suitable modeling, it is possible to predict the future stock prices and stock price movement patterns, with a fairly high level of accuracy. Highly robust and reliable predictive framework for stock price prediction can be built by combining the power of text mining and natural language processing in machine learning models like regression and classification.</p>


## Methodology
<p align="justify">Hybrid models for stock price prediction were built using different machine learning and deep learning-based models. Built four machine learning regression models using the training data that consisted of NIFTY 50 index records. Further augmented the predictive power of our forecasting framework by building deep learning based regression models using long-and short-term memory (LSTM) networks with a novel approach of walk-forward validation. Using the grid-searching technique, the hyperparameters of the LSTM models are optimized.</p>

  
## Technical Details
The following five variables are derived and used in the forecasting models:

○ high_norm: it refers to the normalized values of the variable high. I used minmax normalization to normalize the values. Thus, if the maximum and the minimum values of the variable high are Hmax and Hmin respectively, then the normalized value high_norm is computed as: high_norm = (high - Hmin)/(Hmax – Hmin). After the normalization operation, all values of high_norm lie inside the interval [0, 1].

○ low_norm: this normalized variable is computed from the variable low in a similar way as high_norm is computed: low_norm = (low – Lmin)/(Lmax - Lmin). The values of low_norm also lie in the interval [0, 1].

○ close_norm: it is the normalized version of the variable close, and is computed as: close_norm = (close - Cmin) / (Cmax – Cmin). The interval in which the values of this variable lie is [0, 1].

○ volume_norm: this variable is the normalized value of the variable volume. It is computed in a similar way as high_norm, low_norm, and the close_norm, and its values also lie in the interval [0, 1].

○ range_norm: this variable is the normalized counterpart of the variable range. The range for a given index record is computed as the difference between the high and the low values for that index record and it’s values lies in the closed interval [0, 1].


## Results

The RMSE values on test data for different machine learning & deep learning models is -

○ Boosting regression: 1.87

○ Random forest regression: 0.42

○ ANN regression: 19.31

○ SVM regression: 8.40

○ univariate LSTM: 0.036
