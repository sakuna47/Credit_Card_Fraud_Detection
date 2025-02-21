# Credit Card Fraud Detection

This project uses an **autoencoder** model for fraud detection in credit card transactions. The model detects fraud by comparing the reconstruction error of transaction data with a predefined threshold. 

## Features

- **Fraud Detection**: Classifies transactions as "Fraud" or "Legitimate" based on input features.
- **User-Friendly Interface**: A simple web interface to input transaction details and get fraud predictions.
- **Model**: The model is an autoencoder, trained on transaction data using the **Keras** library.

## Input Details

To make predictions, you need to input 29 features. These include `V1` to `V28` (which represent transformed features from the original dataset) and `Amount` (the transaction amount). Here's an overview of the inputs:

- **V1 to V28**: These are abstract numerical features derived from the dataset. These features are not easily interpretable by humans, and users are not expected to know what to input for them.
- **Amount**: This is the transaction amount (in dollars or the relevant currency).

### Known Input Issue

Since the features `V1` to `V28` are derived from PCA or other transformation techniques and are not directly related to the raw transaction data, **users will not know what values to enter** for these fields. Here are a few options for users to interact with the application:

1. **Auto-Fill Random Values (For Testing)**: 
   If you're testing the application and don't know what to input, you can use the **Auto-Fill** button on the web form to automatically fill random values for `V1` to `V28`, along with the `Amount`.

2. **Upload a CSV File**: 
   Instead of manually entering values, you can upload a CSV file containing the transaction data. The CSV must have exactly 29 columns (one for each of `V1` to `V28` and one for `Amount`). The application will read the CSV and use the values to make a prediction.

3. **Example Values (Static Testing)**: 
   For easier testing, you can modify the input fields with example values for `V1` to `V28` and `Amount`. This allows users to quickly test the functionality without knowing the exact values to enter.

### How to Use

1. **Run the Flask Application**:
   ```bash
   python app.py
