# Federated Learning with Simulated Update Loss

This project simulates a federated learning environment with data loss to study its effects on model performance. It uses the MNIST dataset and a simple CNN model.

## Project Overview

Federated learning (FL) is a machine learning technique that enables multiple clients to collaboratively train a shared model without sharing their raw data. However, real-world FL systems often face challenges like unreliable communication, leading to data loss or corruption during model updates.

This project aims to:

1. Simulate a federated learning environment using the MNIST dataset.
2. Introduce data loss during the model update process with varying loss rates.
3. Analyze the impact of data loss on the accuracy of the global model.

## Methodology

1. **Federated Learning Setup:** The project divides the MNIST dataset among multiple clients, each training a local model on its data.

2. **Data Loss Simulation:** A function is implemented to randomly discard or corrupt some model updates based on a given probability (loss rate).

3. **Federated Averaging:** The server aggregates local model updates using federated averaging, but only those updates that pass the loss simulation.

4. **Evaluation:** The global model's accuracy is evaluated on the MNIST test set after each round of communication.

## Results and Observations

The results are presented in a graph showing the test accuracy of the global model over communication rounds for different loss rates. Key observations include:

* **Accuracy Degradation:** Test accuracy generally decreases with increasing communication rounds, particularly at higher loss rates.
* **Impact of Loss Rate:** Higher loss rates lead to more severe accuracy degradation.
* **Sensitivity to Loss:** Even minor data loss can negatively affect model performance.

## Conclusion

This project demonstrates the adverse effects of data loss on federated learning systems. It highlights the importance of robust communication protocols and error handling mechanisms in real-world FL applications.

## Future Work

* Implement more sophisticated data loss simulation scenarios.
* Investigate different aggregation methods to mitigate data loss effects.
* Explore techniques for early detection and correction of corrupted updates.

## Code Structure

* `Net`: Defines the CNN model.
* `simulate_loss`: Simulates data loss by dropping or corrupting updates.
* `train`: Trains a local model.
* `test`: Evaluates the global model's accuracy.
* `main`: Executes the federated learning process.

## Usage

To run this project in Google Colab:

1. Upload the code to a Colab notebook.
2. Install the necessary libraries (e.g., `torch`, `torchvision`).
3. Execute the code cells in order.
4. Observe the results and plotted graph.

## Dependencies

* Python 3.7 or later
* PyTorch 1.7.0 or later
* Torchvision 0.8.0 or later
* Matplotlib 3.3.0 or later
