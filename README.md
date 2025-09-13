NumPy-MLP: MNIST Classifier from Scratch ✍
This is a simple two-layer neural net (MLP) for classifying MNIST digits, built using only NumPy.

It's a classic textbook exercise to show how backpropagation works from the ground up, without any magic from libraries like PyTorch or TensorFlow. Everything—the forward pass, the chain rule for the backward pass, and the gradient descent updates—is written out manually.

Get Started
You just need numpy, scikit-learn, and matplotlib. scikit-learn is only used to fetch the data and split it, not for the model itself.

Bash
pip install numpy matplotlib scikit-learn
Save the code into a single .py file (like train.py) and just run it:

Bash
python train.py
What it does:

Downloads MNIST (this might take a second the first time).

Pops up a plot of sample digits.

Trains for 50 epochs, printing the live accuracy and loss to your console.

When done, it shows you two final graphs: the loss curve and the train vs. validation accuracy curve.

How It Works
This isn't a complex framework, just one script that shows the whole process.

Model Architecture: The NeuralNetMLP class defines the network. It's a simple 784 (input) -> 50 (hidden) -> 10 (output) layer stack. Both the hidden and output layers use a sigmoid activation.

Backpropagation: The core logic is in the class:

forward(): Runs a batch of images through the network to get predictions.

backward(): This is the important part. It manually computes the chain rule, starting from the derivative of the Mean Squared Error (MSE) loss and going all the way back through the output and hidden layers to get the gradients for every single weight and bias (grad_w_out, grad_b_out, grad_w_h, grad_b_h).

Training Loop:

The train() function handles the optimization (mini-batch SGD).

For each epoch, it shuffles the data and loops through it in batches using minibatch_generator.

In the loop, it just calls forward, then backward, then updates the weights: weight = weight - learning_rate * gradient.

After each epoch, it prints the performance on the full train and validation sets.

Results
The script prints the progress to the console and generates the final plots. The accuracy graph is the most useful—you can clearly see the model learn and then start to overfit when the validation accuracy (orange line) flattens out while the training accuracy (blue line) keeps climbing.
