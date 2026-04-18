**Deep Sequence Modeling: LSTM vs. Transformer**

A Comparative Study on Electricity Demand Forecasting

This repository explores the performance trade-offs between Recurrent Neural Networks (RNNs) and Attention-based Transformers for univariate time series forecasting. The study utilizes historical daily electricity consumption data from India to benchmark accuracy, computational efficiency, and convergence behavior.

**📌 Project Architecture **
**
The project implements two distinct Deep Neural Network (DNN) approaches:**

**1. Stacked LSTM (RNN)**: Leverages gated memory cells to maintain a hidden state across time steps, capturing sequential dependencies and daily seasonality.
**2. Transformer (Self-Attention):** Utilizes Multi-Head Attention and Sinusoidal Positional Encoding to process temporal sequences in parallel, bypassing the vanishing gradient issues of standard recurrence.

**🚀 Key Technical Features**

Time Series Pipeline: Stationarity testing (ADF Test), MinMaxScaler normalization, and sliding window sequence generation ($T=30$).Custom Transformer Implementation: Built from scratch using Keras/TensorFlow, featuring a dedicated Positional Encoding layer and Multi-Head Attention blocks.Advanced Metrics: Evaluation via Mean Absolute Percentage Error (MAPE) and Coefficient of Determination ($R^2$) to assess forecast reliability.

**📊 Benchmark Results**

Metric                Stacked LSTM          Transformer

$R^2$ Score               0.9004            0.7356

MAPE (%)                  1.87%             3.36%

Model Parameters          49,985            166,593

Training Time (s)         203.9s            444.9s

**🧠 Technical Analysis & Findings**

**1. Efficiency vs. Complexity:** The LSTM architecture achieved superior performance with 70% fewer parameters and 2.1x faster training time compared to the Transformer.

**2. Inductive Bias:** For univariate data with strong local dependencies (daily electricity patterns), the sequential inductive bias of the LSTM proved more effective than the global attention mechanism.

**3. Error Distribution:** Residual analysis shows that while the Transformer captures the general trend, the LSTM follows peak demand fluctuations with significantly higher precision (85.46 MAE vs 151.12 MAE).

**🛠️ Tech Stack**

Frameworks: TensorFlow, Keras

Data Science: NumPy, Pandas, Scikit-learn

Visualization: Matplotlib, Seaborn

Environment: Python 3.x
