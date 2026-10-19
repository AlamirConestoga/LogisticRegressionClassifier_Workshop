# Logistic Regression Classifier Workshop

## Overview

This project demonstrates how to build a **binary Logistic Regression classifier from scratch** using Python and NumPy. The model predicts whether a student will **Pass (1)** or **Fail (0)** based on the number of hours studied.

The notebook walks through the main steps of logistic regression, from calculating probabilities to training and evaluating the model.

## Objectives

- Represent student study hours and Pass/Fail outcomes as NumPy arrays.
- Use the sigmoid function to convert a linear score into a probability.
- Calculate Binary Cross-Entropy loss.
- Train the model using Gradient Descent.
- Evaluate predictions using a 0.5 classification threshold and accuracy.
- Visualize the training loss and predicted probabilities.

## Dataset

The notebook uses a small, manually defined example dataset stored directly in the notebook. It contains **19 observations** with two variables:

| Variable | Description |
|---|---|
| `X` | Number of hours studied |
| `y` | Actual outcome: `1` = Pass, `0` = Fail |

No external dataset file is required.

> **Note:** This is a small illustrative dataset for learning purposes, not a validated model for making real academic decisions.

## Technologies

- Python
- NumPy
- Matplotlib
- Jupyter Notebook

## Project Structure

```text
.
├── logisticRegression_workshop.ipynb
└── README.md
```

## Requirements

Install the required libraries:

```bash
pip install numpy matplotlib notebook
```

If you use Anaconda or another environment that already includes NumPy, Matplotlib, and Jupyter, you may not need to install them again.

## How to Run

1. Clone or download this repository.
2. Open a terminal in the project folder.
3. Install the required libraries.
4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `logisticRegression_workshop.ipynb`.
6. Run the notebook cells from top to bottom.

## Methodology

### 1. Prepare the data

The notebook defines the study-hour values (`X`) and the actual Pass/Fail labels (`y`) in NumPy arrays.

### 2. Calculate probabilities with the sigmoid function

The model first calculates a linear score:

\[
z = wx + b
\]

It then applies the sigmoid function:

\[
p = \frac{1}{1 + e^{-z}}
\]

The resulting probability is between 0 and 1.

### 3. Calculate Binary Cross-Entropy loss

Binary Cross-Entropy measures the difference between the actual labels and predicted probabilities. The implementation clips probabilities slightly away from 0 and 1 to avoid taking the logarithm of zero.

### 4. Train with Gradient Descent

The notebook initializes the weight and bias, then updates them iteratively to reduce the loss. The training configuration is:

- Learning rate: `0.1`
- Epochs: `1000`
- Initial weight: `0.5`
- Initial bias: `-1`

### 5. Make predictions and evaluate

The trained model calculates a probability for each observation. It classifies an observation as:

- **Pass (1):** predicted probability is greater than or equal to `0.5`
- **Fail (0):** predicted probability is less than `0.5`

Accuracy is calculated by comparing predictions with the actual labels.

### 6. Visualize the results

The notebook creates two plots:

- **Training loss curve:** Binary Cross-Entropy loss over the training epochs.
- **Classification plot:** Actual Pass/Fail observations, the sigmoid probability curve, and the 0.5 decision threshold.

## Expected Outputs

When the notebook is run, it prints sigmoid test values, example predictions, training progress, the learned weight and bias, final loss, and classification evaluation results. It also displays the two visualizations described above.

Exact numerical results are generated when the notebook runs; this README does not assume a particular accuracy or final loss.

## Limitations

- The example dataset is small and is defined manually in the notebook.
- The model uses only one input feature: hours studied.
- The notebook evaluates the model on the same observations used for training; it does not include a separate test set or cross-validation.
- Accuracy on this example should not be interpreted as evidence of performance on other students or datasets.

## Learning Outcomes

After completing the notebook, a learner should be able to explain how logistic regression converts a linear score into a probability, how Binary Cross-Entropy measures prediction error, how Gradient Descent updates model parameters, and how a threshold converts probabilities into binary predictions.
