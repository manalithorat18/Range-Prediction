# EV Range Prediction Using Artificial Neural Networks (ANN)

## Overview

This project develops an Artificial Neural Network (ANN) model to predict the remaining driving range of an Electric Vehicle (EV). The model utilizes battery and vehicle operational parameters such as State of Charge (SoC), Voltage, Power Consumption, Input Power, and Speed to estimate the remaining travel distance in kilometers.

The solution demonstrates how machine learning can be applied to improve EV range estimation, helping drivers make informed decisions and optimize energy usage.

---

## Features

* EV range prediction using Deep Learning
* Data preprocessing and cleaning
* Automatic range calculation from battery parameters
* Feature scaling using Min-Max Normalization
* Feed-Forward Neural Network implemented with TensorFlow/Keras
* Performance evaluation using MAE, MSE, and R² Score
* Actual vs Predicted Range visualization
* Real-time user input prediction system

---

## Dataset

The project uses a cleaned EV dataset (`Cleaned_Data.csv`) containing battery and vehicle telemetry data.

### Required Columns

| Feature     | Description                      |
| ----------- | -------------------------------- |
| Pack SoC    | Battery State of Charge (%)      |
| Voltage     | Battery Pack Voltage (V)         |
| PC          | Power Consumption                |
| input_power | Input Power                      |
| speed       | Vehicle Speed (km/h)             |
| E_remaining | Remaining Battery Energy         |
| E_per_km    | Energy Consumption per Kilometer |

---

## Target Variable

The remaining range is calculated using:

```math
Range\_Km = \frac{E\_remaining}{E\_per\_km}
```

Rows containing missing or zero values are removed to avoid invalid calculations.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* TensorFlow / Keras

---

## Model Architecture

The Feed-Forward Neural Network consists of:

```text
Input Layer (5 Features)
        ↓
Dense Layer (64 Neurons, ReLU)
        ↓
Dense Layer (32 Neurons, ReLU)
        ↓
Output Layer (1 Neuron)
```

### Hyperparameters

| Parameter        | Value              |
| ---------------- | ------------------ |
| Optimizer        | Adam               |
| Loss Function    | Mean Squared Error |
| Epochs           | 100                |
| Batch Size       | 32                 |
| Validation Split | 20%                |

---

## Data Preprocessing

1. Load dataset from CSV file
2. Remove invalid values from `E_per_km`
3. Calculate `Range_Km`
4. Select relevant features
5. Split data into Training (70%) and Testing (30%)
6. Apply Min-Max Scaling

---

## Training Performance

The model was trained for **100 epochs**.

### Final Training Results

| Metric                    | Value   |
| ------------------------- | ------- |
| Test Loss (MSE)           | 40.94   |
| Mean Absolute Error (MAE) | 3.55 km |
| Mean Squared Error (MSE)  | 40.94   |
| R² Score                  | 0.95    |

### Interpretation

* **MAE = 3.55 km** indicates the model's predictions are on average only 3.55 km away from the actual range.
* **R² = 0.95** shows that the model explains approximately 95% of the variance in the data.
* The low error values and high R² score demonstrate strong predictive performance.

---

## Visualization

The project generates an **Actual vs Predicted Range** scatter plot.

### Plot Description

* Blue points represent model predictions.
* Red dashed line represents perfect predictions.
* Points closer to the red line indicate higher prediction accuracy.

---

## User Prediction Module

After training, users can provide:

* SOC
* Voltage
* PC
* Input Power
* Speed

### Example

```text
Enter SOC: 85
Enter Voltage: 52
Enter PC: 4
Enter Power: 1200
Enter Speed: 40
```

### Output

```text
Predicted Range: 68.45 km
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/your-username/ev-range-prediction.git
cd ev-range-prediction
```

### Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

---

## Run the Project

Update the dataset path:

```python
data = pd.read_csv("Cleaned_Data.csv")
```

Execute:

```bash
python ev_range_prediction.py
```

---

## Future Enhancements

* Hyperparameter tuning
* Early Stopping implementation
* Cross-validation
* LSTM-based sequence prediction
* Real-time EV sensor integration
* Streamlit dashboard deployment
* Battery health prediction module

---

## Project Outcome

The developed ANN model successfully predicts EV driving range with high accuracy, achieving an R² score of 0.95 and a low prediction error of 3.55 km. The results demonstrate the effectiveness of Artificial Neural Networks for intelligent battery management and electric vehicle analytics.

---

## Author

**Manali Thorat**

B.Tech – Computer Engineering

Project: EV Range Prediction Using Artificial Neural Networks (ANN)
