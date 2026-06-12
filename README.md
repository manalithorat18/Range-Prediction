# EV Range Prediction Using Artificial Neural Network (ANN)

## Overview

This project predicts the driving range of an Electric Vehicle (EV) using a Feed-Forward Artificial Neural Network (ANN) built with TensorFlow/Keras. The model learns the relationship between various battery and vehicle parameters and estimates the remaining travel range in kilometers.

The prediction is based on real-world EV telemetry data, including battery state, voltage, power consumption, and vehicle speed.

---

## Features

* Data preprocessing and cleaning
* Calculation of EV driving range using battery parameters
* Feature normalization using Min-Max Scaling
* Feed-Forward Neural Network for regression
* Model evaluation using:

  * Mean Absolute Error (MAE)
  * Mean Squared Error (MSE)
  * R² Score
* Visualization of Actual vs Predicted Range
* Interactive user input for real-time range prediction

---

## Dataset

The project uses a CSV dataset named:

```text
Cleaned_Data.csv
```

### Required Columns

| Column Name | Description                      |
| ----------- | -------------------------------- |
| Pack SoC    | Battery State of Charge (%)      |
| Voltage     | Battery Pack Voltage (V)         |
| PC          | Power Consumption                |
| input_power | Input Power                      |
| speed       | Vehicle Speed (km/h)             |
| E_remaining | Remaining Battery Energy         |
| E_per_km    | Energy Consumption per Kilometer |

---

## Range Calculation

The target variable is calculated as:

```text
Range_Km = E_remaining / E_per_km
```

Rows containing missing or zero values in `E_per_km` are removed to avoid division errors.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* TensorFlow / Keras

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ev-range-prediction.git
cd ev-range-prediction
```

### 2. Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

---

## Project Workflow

### Data Preprocessing

* Load EV dataset
* Remove invalid values
* Calculate remaining range
* Select relevant features

### Feature Selection

Input Features:

```text
Pack SoC
Voltage
PC
input_power
speed
```

Target:

```text
Range_Km
```

### Data Scaling

Min-Max Normalization is applied to improve ANN training performance.

### Model Architecture

```text
Input Layer (5 Features)
        ↓
Dense Layer (64 neurons, ReLU)
        ↓
Dense Layer (32 neurons, ReLU)
        ↓
Output Layer (1 neuron)
```

### Training Parameters

```text
Optimizer : Adam
Loss      : Mean Squared Error
Epochs    : 100
Batch Size: 32
Validation Split: 20%
```

---

## Model Evaluation

The trained model is evaluated using:

### Mean Absolute Error (MAE)

Measures the average prediction error.

### Mean Squared Error (MSE)

Measures the squared difference between actual and predicted values.

### R² Score

Measures how well the model explains variance in the data.

---

## Visualization

The project generates an Actual vs Predicted Range plot.

* Blue points represent predictions.
* Red dashed line represents perfect prediction.

This visualization helps assess model accuracy.

---

## User Range Prediction

After training, users can enter:

```text
SOC
Voltage
PC
Power
Speed
```

Example:

```text
Enter SOC: 85
Enter Voltage: 52
Enter PC: 4
Enter Power: 1200
Enter Speed: 40
```

Output:

```text
Predicted Range: 68.45 km
```

---

## Running the Project

Update the dataset path in the code:

```python
data = pd.read_csv("C:/Users/Manali/Downloads/Cleaned_Data.csv")
```

Run:

```bash
python ev_range_prediction.py
```

---

## Future Improvements

* Hyperparameter tuning
* Cross-validation
* LSTM-based time-series prediction
* Real-time IoT sensor integration
* Battery health estimation
* Web dashboard deployment using Flask or Streamlit

---

## Results

The ANN model successfully predicts EV driving range using battery and operational parameters. The model demonstrates the effectiveness of machine learning in improving range estimation and supporting smarter energy management in electric vehicles.

---

## Author

**Manali Thorat**

B.Tech – Artificial Intelligence & Machine Learning

Project: EV Range Prediction using Artificial Neural Networks (ANN)
