
The Process to work with this code.
1. First import the dataset from yfinance. For that needed to install couple of libraries and installr. Such as import yfinance as yf

# Display the downloaded data
print(msft_data)


2. Load training/validation/test data from yfinance according to the date range.
Convert DataFrames to NumPy arrays.
Apply standard scaling to both features and labels.
Model Construction:

3. A 5-layer ( 16 neurons for the first layer, 12 neuron for the rest 4 lears) feedforward network with ReLU activations, BatchNorm after each dense layer.
A final Dense(1) for  output.
Adam optimizer with an initial LR of 1e-6 and MSE loss.
Cyclical LR Scheduler:

4. The learning rate is adjusted each epoch using the triangular method. It oscillates between 1e-6 and 1e-3 over step_size=20 epochs, then reduces the amplitude each cycle.
Training:

5. Train for 600 epochs (validation data used for real-time feedback).
The LR scheduler is applied each epoch.
Evaluation:

6. Evaluate MSE on the test set in scaled space and convert it back to the original space.
Display a few predictions vs. actual values.
Plotting & Saving:

7. Plot training and validation loss over epochs to visualize convergence.
Save the trained model to an .ipynb file for future use.
This is essentially a deep regression pipeline that uses:

8. Data splitting (train, val, test),
Scaling (important for neural networks),
A custom cyclical learning rate (for potentially better convergence),
A moderately deep architecture (5 hidden layers of 18 neurons),
Regularization ( BatchNorm),
Adam optimizer,
MSE loss.
All of these steps together constitute the full training and evaluation procedure seen in the code.
