# Cryptocurrency Trader Performance Analysis Using Fear & Greed Index

## Project Overview

This project investigates the relationship between cryptocurrency trader performance and market sentiment using historical trading data and the Crypto Fear & Greed Index.

The objective is to understand how market psychology influences trading outcomes, identify hidden behavioral patterns, and build machine learning models capable of predicting profitable trades.

The analysis combines trader-level transaction data with daily market sentiment indicators to uncover actionable insights that can support smarter trading strategies and risk management decisions.

---

# Business Problem

Cryptocurrency markets are highly influenced by investor emotions such as fear and greed. Market participants often make irrational decisions during periods of extreme optimism or pessimism.

This project aims to answer the following questions:

* Does market sentiment affect trader profitability?
* Are traders more successful during Greed or Fear periods?
* How does trading behavior change under different market conditions?
* Can trader profitability be predicted using market sentiment and trading activity?
* Which machine learning model performs best for profitability prediction?

---

# Dataset Description

## Dataset 1: Historical Trading Data

The historical trading dataset contains detailed information about trader activities.

### Features

* Account
* Coin
* Execution Price
* Size Tokens
* Size USD
* Side
* Timestamp IST
* Start Position
* Direction
* Closed PnL
* Transaction Hash
* Order ID
* Crossed
* Fee
* Trade ID
* Timestamp

### Target Variable

Profit_Flag

Created using:

Profit_Flag = 1 if Closed PnL > 0

Profit_Flag = 0 if Closed PnL ≤ 0

---

## Dataset 2: Fear & Greed Index

The Fear & Greed Index measures market sentiment on a scale from extreme fear to extreme greed.

### Features

* timestamp
* value
* classification
* date

### Sentiment Categories

* Extreme Fear
* Fear
* Neutral
* Greed
* Extreme Greed

---

# Project Workflow

## Step 1: Data Loading

Both datasets are loaded using Pandas.

---

## Step 2: Data Understanding

Performed:

* Dataset inspection
* Missing value analysis
* Data type analysis
* Statistical summary generation

---

## Step 3: Data Preprocessing

Tasks performed:

* Timestamp conversion
* Duplicate removal
* Missing value handling
* Dataset merging using date information

---

## Step 4: Feature Engineering

Additional features created:

### Profit_Flag

Binary classification target.

### Trade_Size_Category

Categorizes trades into:

* Small
* Medium
* Large
* Very Large

### Daily_Trading_Volume

Aggregated trading volume per day.

### Time Features

* Trade_Hour
* Trade_DayOfWeek
* Trade_Month

### Fee_Percent

Fee relative to trade size.

### PnL_to_Size

Profitability ratio relative to trade volume.

---

## Step 5: Exploratory Data Analysis

EDA was performed to investigate:

* Profitability distribution
* Market sentiment distribution
* Sentiment vs trader performance
* Trading volume trends
* Correlation between variables

Visualizations include:

* Histograms
* Boxplots
* Heatmaps
* Countplots
* Feature importance plots

---

## Step 6: Machine Learning Models

Three classification models were developed.

### Logistic Regression

Advantages:

* Simple
* Fast
* Interpretable

Purpose:

Provides a baseline model for comparison.

---

### Decision Tree Classifier

Advantages:

* Easy to interpret
* Captures nonlinear relationships

Purpose:

Identify rule-based decision patterns.

---

### Random Forest Classifier

Advantages:

* High predictive power
* Reduced overfitting
* Handles nonlinear relationships

Purpose:

Production-grade predictive model.

---

# Model Evaluation Metrics

The following metrics are used:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix

These metrics help evaluate classification performance and model generalization ability.

---

# Key Business Insights

## 1. Market Sentiment Influences Trading Outcomes

The analysis demonstrates that trader profitability is closely associated with market sentiment.

Periods of Greed often show higher trading activity and improved profitability compared to Fear periods.

---

## 2. Fear and Greed Affect Trading Behavior

Traders tend to:

* Increase position sizes during Greed
* Trade more aggressively during bullish sentiment
* Reduce activity during Fear periods

This suggests that trader behavior is significantly influenced by market psychology.

---

## 3. Trade Size Impacts Profitability

Larger trade sizes generally contribute more to profits but also increase risk exposure.

Trade size is one of the most influential predictive features.

---

## 4. Sentiment Can Be Used as a Predictive Signal

Fear & Greed scores provide useful information for predicting profitable trades.

Market sentiment should be incorporated into trading strategy development and risk management systems.

---

## 5. Time-Based Patterns Exist

Trading performance may vary by:

* Hour of the day
* Day of the week
* Market cycle

Time-related features improve model performance.

---

## 6. Random Forest Typically Performs Best

Among the evaluated models:

* Logistic Regression provides interpretability.
* Decision Tree provides rule-based explanations.
* Random Forest generally achieves the best balance between accuracy and generalization.

Therefore, Random Forest is recommended for production deployment.

---

# Production Recommendation

Recommended Model: Random Forest Classifier

Reasons:

* Strong predictive performance
* Handles complex feature interactions
* Robust against overfitting
* Supports feature importance analysis
* Suitable for large datasets

---

# Future Improvements

Potential enhancements include:

* Hyperparameter tuning using GridSearchCV
* XGBoost implementation
* LightGBM implementation
* SMOTE for class imbalance handling
* Real-time sentiment integration
* Trading strategy backtesting
* Deep learning approaches

---

# Technologies Used

Programming Language

* Python

Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

Machine Learning Models

* Logistic Regression
* Decision Tree
* Random Forest

---

# Conclusion

This project successfully combines trader transaction data with market sentiment indicators to understand the relationship between trader behavior and market psychology.

The results demonstrate that sentiment-based features provide valuable predictive information and can be leveraged to improve trading decisions, optimize risk management, and develop more intelligent cryptocurrency trading strategies.
