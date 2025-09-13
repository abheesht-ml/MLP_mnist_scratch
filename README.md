# NumPy-MLP: MNIST Classifier from Scratch ✍️

This is a simple two-layer neural net (MLP) for classifying MNIST digits, built using **only NumPy**.

It's a classic textbook exercise to show how backpropagation works from the ground up, without any magic from libraries like PyTorch or TensorFlow. Everything—the forward pass, the chain rule for the backward pass, and the gradient descent updates—is written out manually.

## Get Started

You just need `numpy`, `scikit-learn`, and `matplotlib`. `scikit-learn` is only used to fetch the data and split it, not for the model itself.
