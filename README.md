Dutch Electricity Consumption Forecasting: Hybrid CNN-LSTM Approach
This repository contains a deep learning pipeline designed to predict electricity consumption patterns in the Netherlands. Using a decade of historical data from various Dutch energy grid operators (Stedin, Liander, Enexis, etc.), the project implements a Hybrid CNN-LSTM model to perform time-series forecasting.

📊 Dataset
The project utilizes the Dutch Energy Dataset, which provides historical electricity and gas consumption data.

Time Range: 2009 – 2020.

Grid Operators: Stedin, Liander, Enduris, Enexis, Westland-Infra, Rendo, and Coteq.

Features: The model specifically processes yearly consumption metrics and smart meter data to predict future demand.

🏗️ Model Architecture
The core of this project is a Convolutional Neural Network (CNN) combined with Long Short-Term Memory (LSTM) networks.

CNN Layer (Conv1D): Extracts local patterns and features from the input sequences (e.g., sudden spikes or drops in usage).

MaxPooling: Reduces the dimensionality of the features while retaining the most important information.

LSTM Layers: Captures long-term dependencies and seasonal trends inherent in energy consumption.

TimeDistributed Wrapper: Allows the model to apply the CNN layers to every temporal slice of the input.

Model Summary
Optimizer: Adam

Loss Function: Mean Squared Error (MSE)

Input Sequence Length: 120 time steps

Architecture: TimeDistributed(Conv1D) -> MaxPooling1D -> LSTM -> Dense

🚀 Key Features
Automated Data Ingestion: Includes scripts to programmatically download and organize Kaggle datasets.

Robust Preprocessing: Custom normalization functions and sliding window sequence generation (load_data).

Multi-Company Support: The pipeline is built to handle data from multiple energy providers across the Netherlands.

Visualization: Integrated plotting for training history and prediction vs. actual results.

🛠️ Requirements
Python 3.x

TensorFlow / Keras

Pandas

NumPy

Scikit-learn

Matplotlib

📈 Future Improvements
Expansion to include Gas consumption forecasting.

Hyperparameter tuning for the seq_len and CNN filter sizes.

Implementation of Attention mechanisms to improve long-range forecasting.
