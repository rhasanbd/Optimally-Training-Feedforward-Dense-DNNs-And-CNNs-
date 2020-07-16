# How to Train a Deep Neural Network (DNN) Optimally

The goal of training a Deep Artificial Neural Network or DNN is two-fold:

- Achieve effectiveness (such that the model generalizes well)
- Achieve efficiency (converges faster to an optimal solution)

We measure the effectiveness by using performance on the test dataset (e.g., test accuracy). The efficiency is measured by the training time. Some techniques enable to converge faster (in fewer epochs), but they require more trining time pr epoch. These are not efficient techniques from the perspective of overall training time. We prefer a technique that achieves higher accuracy in shortest training time.

Two main issues prevent achieving effectiveness and efficiency in training DNNs.

- The vanishing/exploding gradient problem of the Backpropagation algorithm
- Slow convergenge due to the Stochastic Gradient Descent (SGD) algorithm

The first issue is deadlier than the second one. It can completely stall the training and stop learning. However, even if it is resolved, SGD could converge very slowly.

Two notebooks are created to overcome these issues:
- Notebook 1: feedforward dense DNNs
- Notebook 2: Convolutional Neural Networks or CNNs

In our investigation of the slow convergence problem of SGD, we compare the 1cycle learning rate schedule with the NAdam optimizer. We used the deafult learning rate for NAdam. However, it is important to determine the optimal learning rate for optimizers like NAdam. We conduct this investigation in another notebook.
- Notebook 3: Determine the Optimal Learning Rate for NAdam
