#How to Train a Deep Neural Network (DNN) Optimally

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
- Notebook 2: Concolutional Neural Networks or CNNs

The vanishing/exploding gradient problem of the Backpropagation algorithm is attributed to the weight initialization technique and the activation function. The slow convergence issue of SGD is caused by its learning rate. Thus, we inestigate the role of these three factors in training a DNN optimally:

- Weight Initializer
- Activation Function
- Learning Rate Optimizer for SGD

We use the following following variants of the above three factors:

- Initializers: LeCun, Glorot, He and Orthogonal
- Activation function: Sigmoid, Tanh, ReLU, ELU
- Learning Rate Optimizer: 1cycle (learning rate schedule) to tune global scalar LR & NAdam (adaptive LR) to tune LRs per dimension.

In addition to this, we experiment with the Batch Normalization (BN) technique that addresses the vanishing/exploding gradient poblem as well as acts as a regularizer.

For a fair comparison with the BN based approach, we add l2 regularizer with other models where we see overfitting happens. The regularization parameter alpha is tuned optimally.

