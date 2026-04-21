Project made by me for my AI class during the 3rd course in university.

# House price prediction using neural networks


## Project description

This project solves a regression task: predicting house prices based on structured tabular data using a neural network model.

The dataset contains detailed information about residential properties, including:
- Physical characteristics of houses
- Quality and condition features
- Location-related attributes
- Additional property descriptions

The goal is to predict the final sale price of each house.

---

## Dataset

- `train.csv` — training dataset with target variable (`SalePrice`)
- `test.csv` — test dataset
- `data_description.txt` — feature descriptions

Original dataset contains 80+ features describing housing properties.

---

## Data Preprocessing

The following preprocessing steps were applied:

### Handling missing values
- Removed columns with excessive missing values:
  - `Alley`
  - `FireplaceQu`
  - `PoolQC`
  - `Fence`
  - `MiscFeature`

### Filling missing values
- Numerical features → filled with **median**
- Categorical features → converted to numeric encoding

### Feature scaling
- Applied `StandardScaler` for normalization

### Train-validation split
- 80% training / 20% validation

---

## Model Architecture

A fully connected neural network was built using TensorFlow / Keras.

General structure:


---

## Training Setup

- Framework: TensorFlow / Keras
- Loss functions:
  - Mean Squared Error (MSE)
  - Mean Absolute Error (MAE)
- Optimizers tested:
  - Adam
  - RMSprop
- Batch sizes tested: 16, 32, 64, 128, 256
- Epochs tested: 10 to 150

---

## Evaluation Metrics

Model performance was evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R² Score

---

## Results

### Best configuration:

- Architecture: `[64, 32, 32, 32, 16]`
- Optimizer: Adam
- Loss: MAE
- Batch size: 32
- Epochs: 50

### Performance:
- MAE: 18,000 – 22,000
- MSE: 6e8 – 1e9
- R² Score: 0.87 – 0.88

---

## Experiments & Observations

### Network depth
- Increasing hidden layers improves performance up to a point
- Too deep networks → overfitting

### Epochs
- Too few leads to underfitting, too many - to overfitting
- Optimal range: 50–100 epochs

### Batch size
- Best results at batch_size = 32
- Large batch sizes reduce generalization quality

### Input layer size
- Should match number of input features
- 64 neurons performed best in experiments

---

## Key Insights

- Neural networks can effectively model tabular data
- Proper preprocessing significantly improves performance
- Model tuning is crucial for avoiding overfitting
- MAE loss provided more stable results than MSE in some cases

---

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
