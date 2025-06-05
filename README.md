# Cloud Cost Prediction using Machine Learning

This project focuses on predicting and optimizing the cost of cloud computing instances based on input parameters like CPU, memory, and storage using different machine learning models. It includes:

- Feedforward Neural Networks
- LSTM-based Recurrent Neural Networks
- Hybrid DNN + LSTM models
- A variant with Genetic Algorithm-style input optimization

---

## 📁 Dataset

The dataset used is `cloud_data.csv`, containing the following features:

- `cpu`: Number of CPUs
- `memory`: Memory in GB
- `storage`: Storage in GB
- `cost`: Cost associated with the configuration

---

## 🔧 Models Implemented

### 1. Feedforward Neural Network
- Multiple dense layers with dropout for regularization.
- Evaluates using MSE, MAE, and MAPE.
- Saves the model as `dnn_model.h5`.

### 2. LSTM (Bidirectional)
- Processes inputs as sequences for better temporal pattern capture.
- Uses EarlyStopping and RMSprop optimizer.
- Saves the model as `lstm_model.h5`.

### 3. Hybrid DNN + LSTM (Multi-Input Model)
- Combines the strengths of both dense and sequential modeling.
- Requires reshaping inputs accordingly for LSTM layers.
- Saves as `combined_dnn_lstm_model.h5`.

### 4. Implicit Genetic Algorithm Optimization
- Randomly generates instance configurations.
- Predicts cost for each and outputs top optimized setups.

---

## 📈 Evaluation Metrics

Each model is evaluated using:
- **MSE** (Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **MAPE** (Mean Absolute Percentage Error)

Visualizations include:
- Training vs Validation Loss curves
- Actual vs Predicted scatter plots

---

## 📊 Sample Output

```text
Optimized instances:
CPU: 2, Memory: 8 GB, Storage: 16 GB, Predicted Cost: $0.43
CPU: 3, Memory: 12 GB, Storage: 24 GB, Predicted Cost: $0.67
...
