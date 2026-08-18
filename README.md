# MNIST-Neural-Network-Classification
MNIST handwritten digit classification using feedforward neural networks in Keras, comparing architectures, epochs, L2 regularization, and dropout

This project uses **feedforward neural networks in Keras** to classify handwritten digits from the MNIST dataset. Multiple neural network architectures are compared by varying the number of hidden layers, hidden units, training epochs, and regularization methods.

## Dataset

The MNIST dataset contains grayscale images of handwritten digits from **0 to 9**.

* Training images: **60,000**
* Test images: **10,000**
* Image size: **28 × 28 pixels**
* Number of classes: **10**

Each image was normalized by scaling pixel values from **0–255 to 0–1** and reshaped from a 28 × 28 matrix into a vector of **784 input features**.

## Neural Network Architecture

The models were developed using **TensorFlow/Keras**.

For all models:

* **ReLU** activation was used in the hidden layers.
* **Softmax** activation was used in the 10-unit output layer.
* **Adam** was used as the optimizer.
* **Categorical cross-entropy** was used as the loss function.
* A mini-batch size of **128** was used.

Different models were compared using:

* 1 or 2 hidden layers
* 256 or 512 hidden units
* 5 or 10 epochs
* L2 regularization
* 50% dropout

## Model Comparison

| Model       | Architecture  | Epochs | Regularization | Training Error | Test Error |
| ----------- | ------------- | -----: | -------------- | -------------: | ---------: |
| Model 1     | 512           |      5 | None           |          0.70% |      2.00% |
| Model 2     | 512           |     10 | None           |          0.15% |      1.83% |
| Model 3     | 256           |      5 | None           |          1.26% |      2.32% |
| Model 4     | 256           |     10 | None           |          0.15% |      1.99% |
| Model 5     | 512 → 512     |      5 | None           |          0.94% |      2.39% |
| **Model 6** | **512 → 512** | **10** | **None**       |      **0.14%** |  **1.71%** |
| Model 7     | 256 → 256     |      5 | None           |          1.03% |      2.42% |
| Model 8     | 256 → 256     |     10 | None           |          0.53% |      2.18% |
| Model 9     | 512           |      5 | L2 (λ = 0.001) |          2.10% |      2.61% |
| Model 10    | 512           |      5 | 50% Dropout    |          1.28% |      2.36% |

## Results

The best-performing model was **Model 6**, which contained:

* Two hidden layers
* 512 units in each hidden layer
* ReLU activation
* 10 training epochs
* Mini-batch size of 128

Model 6 achieved a **test error of approximately 1.71%**, corresponding to a **test accuracy of approximately 98.29%**.

Increasing the number of epochs from 5 to 10 generally improved performance. Under the settings evaluated, L2 regularization and 50% dropout did not improve test performance.

## Visualizations

The project includes:

* Comparison of training and test error across all neural network models
* Example MNIST test images with predictions from the best-performing model

Figures are stored in the `Figures` directory.

## Tools and Libraries

* Python
* Jupyter Notebook
* TensorFlow
* Keras
* NumPy
* Pandas
* Matplotlib

## Repository Structure

```text
MNIST-Neural-Network-Classification/
│
├── MNIST_Neural_Network_Classification.ipynb
├── README.md
│
└── Figures/
    ├── model_error_comparison.png
    └── model6_predictions.png
```

## Conclusion

Multiple feedforward neural network architectures were successfully developed and evaluated for MNIST handwritten digit classification. The results demonstrate how network depth, hidden-layer size, training duration, and regularization can influence classification performance.

Among the evaluated models, the network with **two 512-unit hidden layers trained for 10 epochs** achieved the lowest test error and was selected as the best-performing model.
