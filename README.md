# Rice Type Classification with PyTorch

This project demonstrates a rice type classification task using different Artificial Neural Network (ANN) architectures implemented with PyTorch. The goal is to classify rice grains into one of two types based on their morphological features.

## Dataset

The dataset used for this project is the "Rice Type Classification" dataset from Kaggle. It contains various features of rice grains that are used to distinguish between different rice types.

### Data Source:
- [Kaggle: Rice Type Classification](https://www.kaggle.com/datasets/mssmartypants/rice-type-classification)

## Project Steps

1.  **Data Acquisition**: The dataset was downloaded from Kaggle using the `opendatasets` library.
2.  **Data Loading and Initial Exploration**: The `riceClassification.csv` file was loaded into a pandas DataFrame. The first few rows and basic statistics were inspected.
3.  **Data Preprocessing**: 
    *   Missing values were dropped.
    *   The 'id' column was removed as it's not relevant for classification.
    *   All numerical features were normalized by dividing by their absolute maximum values to scale them between 0 and 1.
    *   The data was split into features (X) and target (Y).
4.  **Data Splitting**: The dataset was divided into training, validation, and testing sets using `sklearn.model_selection.train_test_split` with a 70% train, 15% validation, and 15% test split.
5.  **PyTorch Dataset and DataLoader**: Custom `Dataset` and `DataLoader` classes were created to efficiently load and batch the data for training and evaluation.
6.  **Model Definition**: Three different simple feed-forward neural network (ANN) models were defined using `torch.nn.Module`:
    *   **MyModel1**: A single hidden layer with 10 neurons.
    *   **MyModel2**: A single hidden layer with 20 neurons.
    *   **MyModel3**: Two hidden layers, each with 10 neurons.
    All models use a `Sigmoid` activation function in the output layer for binary classification.
7.  **Model Training and Evaluation**: A `model_run` function was implemented to handle the training, validation, and testing loop for each model. It includes:
    *   **Loss Function**: Binary Cross-Entropy Loss (`nn.BCELoss`).
    *   **Optimizer**: Adam optimizer with a learning rate of 1e-3.
    *   **Epochs**: Each model was trained for 10 epochs.
    *   **Metrics**: Training loss, validation loss, training accuracy, and validation accuracy were tracked per epoch. Finally, testing accuracy was reported.
    *   **Visualization**: Plots showing the training/validation loss and accuracy over epochs were generated for each model.

## Results

The models achieved high testing accuracy, indicating good performance in classifying rice types:

*   **MyModel1 (1 hidden layer, 10 neurons)**: ~98.42% Testing Accuracy
*   **MyModel2 (1 hidden layer, 20 neurons)**: ~98.39% Testing Accuracy
*   **MyModel3 (2 hidden layers, 10 neurons each)**: ~98.39% Testing Accuracy

Visualizations of training and validation metrics were provided to illustrate the learning process of each model.

## Dependencies

This project requires the following Python libraries:

*   `pandas`
*   `numpy`
*   `torch`
*   `torchvision` (implicitly for `torchsummary` or related features)
*   `torchsummary`
*   `sklearn`
*   `matplotlib`
*   `opendatasets`

## How to Run

1.  **Install Dependencies**: Make sure you have all the required libraries installed (`pip install pandas numpy torch scikit-learn matplotlib opendatasets torchsummary`).
2.  **Kaggle Credentials**: Provide your Kaggle username and API key for downloading the dataset. This can be done interactively when `od.download` is called.
3.  **Execute Notebook**: Run the cells in the provided Jupyter/Colab notebook sequentially.
