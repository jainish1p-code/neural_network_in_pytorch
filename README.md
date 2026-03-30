# PyTorch_1
## Rice Type Classification

### Model Architectures:

1.  **MyModel1 (Single Layer - 5 Neurons):**
    *   **Testing Accuracy:** 98.42%

2.  **MyModel2 (Single Layer - 10 Neurons):**
    *   **Testing Accuracy:** 98.35%

3.  **MyModel3 (Two Layers - 5, 5 Neurons):**
    *   **Testing Accuracy:** 98.35%

All models were trained for 10 epochs using Adam optimizer and Binary Cross-Entropy Loss (`BCELoss`). The models show very similar and high testing accuracies, indicating that even simple architectures perform well on this dataset after normalization.


# PyTorch2
## Animal Face Classification

### Model Architecture

A custom Convolutional Neural Network (CNN) with 4.28M parameters is used, comprising 3 convolutional layers, ReLU activations, max-pooling layers, and fully connected layers for classification.

### Accuracy

The model achieved a test accuracy of approximately 94.75% after 10 epochs of training. The training and validation loss/accuracy plots are available in the notebook for detailed analysis.
