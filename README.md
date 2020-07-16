# How to Train a Deep Neural Network (DNN) Optimally

The goal of training a Deep Artificial Neural Network or DNN is two-fold:

- Achieve effectiveness (such that the model generalizes well)
- Achieve efficiency (converges faster to an effective solution)

We measure the effectiveness by using model's performance on the test dataset (e.g., test accuracy). The efficiency is measured by the training (wall) time. Some techniques enable to converge in fewer epochs, but they require more training time per epoch. For some applications these are not suitable techniques from the perspective of overall training time. 

    We prefer a technique that achieves higher test accuracy using shortest training time.

Two main issues prevent achieving effectiveness and efficiency in training DNNs.

- The vanishing/exploding gradient problem of the Backpropagation algorithm
- Slow convergenge due to the Stochastic Gradient Descent (SGD) algorithm

The first issue is deadlier than the second one. It can completely stall the training and stop learning. Even if the vanishing/exploding gradient issue is resolved, SGD could make the training painfully slow.

We present several techniques to overcome these issues in the following two notebooks designed for **two DNN architectures**:
- Notebook 1: feedforward dense DNNs
- Notebook 2: Convolutional Neural Networks or CNNs

In our investigation of the slow convergence problem of SGD, we use two techniques to determine the optimal learning rate: learning rate schedule (to determine a global constant learning rate) and adaptive learning rate (to determine learning rate per dimension).

More specifically, we compare the **1cycle learning rate schedule** with the **NAdam** adaptive learning rate based optimizer. In notebooks 1 and 2, we used the deafult learning rate for NAdam. However, it is important to determine the optimal learning rate for optimizers like NAdam. We conduct this investigation in the following notebook.
- Notebook 3: Determine the Optimal Learning Rate for NAdam

One of the key findings from the experiments done in notebooks 1 and 2 is that the **pretraining** based weight initialization technique significantly reduces the training time and achieves very high test accuracy. To implement the pretraining based initializer we need to determine what fraction of training data and classes should be used for pretraining. Generally it is beneficial to use a small subset of the training data. However, it is not clear whether we should use a small subset of the classes as well. By keeping the pretraining subset data fixed, we could either use a large fraction of the classes each with smaler instances, or a small subset of the classes each with larger number of instances. Which strategy should we use? In the following notebook we propose a strategy.

- Notebook 4: Optimal Strategy for Pretraining based Weight Initialization
