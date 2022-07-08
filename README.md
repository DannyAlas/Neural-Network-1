# Nerual Network From Scratch

Anyone with even some cursuory knowledge in AI/ML likely knows the basics about neural networks.You connect a few of layers of nodes with weights and biases, train it on some data, and bingo, you've got a network that can recognize dogs or predict stock prices.

I've always found this high-level understanding a little wishy-washy, though. Even when working through Kaggle courses over the summer, fully building out these models in Tensorflow, I felt like I didn't understand what was going on or what I should be paying attention to in the code.

I didn't begin building this intuition though until i took Andrew Ng's Intro to ML course on Coursera, which taught ML principles and design not using Tensorflow or Keras but Matlab instead. For me, this more concrete technical understanding was a huge boost for my understanding of ML overall. To further solidify my learning, I spent a few hours over the past few days building a simple neural network from scratch, and trained it to recognize handwritten digits from the MNIST dataset.

In the [Jupyter Notebook](NN-from-scratch.ipynb) I give a more detailed walkthourgh of my process and code design. 

The dataset used is the MNIST handwritten digit dataset. It contains 28 x 28 grayscale images of handwritten digits. Each image is accompanied by a label of what digit it belongs to, from 0 to 9. The task is to build a network that takes in an image and predicts the written digit.

![learning](https://raw.githubusercontent.com/DannyAlas/Neural-Network-1/main/img/NN_Learning_Curve.png)

### Neural Network Overview
The network consists of three layers: an input layer and two parameter layers. Since the input layer has no parameters, this network would be referred to as a two-layer neural network.

The input layer has 784 nodes, corresponding to each of the 784 pixels in the 28x28 input image. Each pixel has a value between 0 and 255, with 0 being black and 255 being white. I normalized these values — between 0 and 1 - before feeding them into the network.

The second layer, or hidden layer, could have any amount of nodes, but I've kept it simple with just 10 nodes. The value of each of these nodes is calculated based on weights and biases applied to the value of the 784 nodes in the input layer. After this calculation, a ReLU activation is applied to all nodes in the layer.

The output layer also has 10 nodes, corresponding to each of the output classes (0 to 9). The value of each of these nodes will again be calculated from weights and biases applied to the value of the 10 nodes in the hidden layer, with a softmax activation applied to them to get the final output.
