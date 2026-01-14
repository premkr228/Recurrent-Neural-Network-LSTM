# Recurrent-Neural-Network-LSTM  Credit Card Fraud Detection Using LSTM Recurrent Neural Networks
A Recurrent Neural Network (RNN) processes sequential data by maintaining a hidden state that carries information from previous time steps. LSTM, a specialized RNN, uses input, forget, and output gates to retain important information over long sequences, overcoming vanishing gradient issues and enabling effective learning of long-term dependencies.


Project Overview

This project implements a credit card fraud detection system using a Long Short-Term Memory (LSTM)–based Recurrent Neural Network. The primary objective is to accurately classify transactions as normal or fraudulent by learning patterns from historical transaction data, with a strong focus on capturing temporal and behavioral characteristics inherent in financial transactions.

Research Motivation and Paper Selection

The project is based on the research paper “Credit Card Fraud Detection Model Based on LSTM Recurrent Neural Networks” (2021). The motivation for selecting this paper lies in the sequential nature of fraud detection, where past transaction behavior strongly influences future outcomes. LSTM networks are well-suited for this task as they are designed to model time-dependent data and retain important historical information over long sequences, unlike conventional feedforward models.

Dataset Description

The dataset used for this project is the widely recognized Kaggle Credit Card Fraud dataset, which contains real-world transaction data collected by European cardholders. It includes numerical features obtained through PCA transformation, along with Time, Amount, and a binary target variable indicating fraud. A key challenge of this dataset is its extreme class imbalance, with fraudulent transactions representing a very small fraction of the total data.

Data Preprocessing and Feature Engineering

To prepare the data for modeling, the target variable is separated from the features, and any missing values are removed to ensure label consistency. The Time and Amount features are normalized using standard scaling to improve training stability. A stratified train–test split is applied to preserve class distribution, and SMOTE is used on the training data to address class imbalance by synthetically generating fraud samples.

Data Reshaping for Sequential Learning

Since LSTM models require sequential input, the preprocessed feature vectors are reshaped into a three-dimensional format suitable for RNNs. Each transaction is represented in a time-step format compatible with LSTM input requirements, enabling the model to process the data in a recurrent learning framework.

Model Architecture Design

The neural network architecture consists of an LSTM layer with 64 units to capture temporal dependencies, followed by a dropout layer to reduce overfitting. A final dense layer with sigmoid activation produces the binary classification output. The model is trained using binary cross-entropy loss, which is appropriate for two-class classification problems.

Training Strategy and Optimization

To evaluate optimizer effectiveness, the model is trained separately using Adam, RMSprop, and SGD with momentum. Each optimizer is tested under identical training conditions, including the same number of epochs and batch size, ensuring a fair comparison of convergence speed, stability, and overall performance.

Model Evaluation Metrics

Model performance is evaluated using multiple metrics, including accuracy, precision, recall, F1-score, and confusion matrices. Special emphasis is placed on the fraud class, as minimizing false negatives and controlling false positives are critical in financial fraud detection systems.

Results and Performance Analysis

The experimental results show that the Adam optimizer achieves the best overall performance, with superior F1-score and a balanced trade-off between precision and recall. RMSprop performs reasonably well but generates more false positives, while SGD demonstrates poor precision despite high recall, making it less suitable for this task.

Conclusion and Key Takeaways

This project demonstrates that LSTM-based Recurrent Neural Networks are highly effective for credit card fraud detection when combined with proper data preprocessing and imbalance handling techniques. The findings validate the research paper’s approach and highlight the importance of sequential modeling in detecting fraudulent behavior in real-world financial systems.
