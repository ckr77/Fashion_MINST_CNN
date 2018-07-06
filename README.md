# Fashion_MNIST_CNN
My first foray into CNN for Visual Recognition using Fashion MNIST dataset.
This repo consists of 3 different jupyter notebooks which have been developed using Colaboratory.

First Notebook (FirstCNN.ipynb) used the Keras sequential model from this blog post

https://colab.research.google.com/github/margaretmz/deep-learning/blob/master/fashion_mnist_keras.ipynb#scrollTo=aFe4wHGRFKle

Keras provide higher level abstraction framework for Tensorflow backend and simplifies the creation of NN model. Checkout the above blog for more details. To summarize the CNN model consists of two convolution layers with ReLU as the activation function and Adam as the the optimizer used and Dropout layer added as Regularization technique.The pooling layer uses maxpooling technique to downsample. The model achieves around 92% accuracy on training dataset and around 91% accuracy in validation dataset, to check if dropout layer really helped in avoiding overfitting in this case, I removed the dropout layer in my next notebook FirstCNN_NoRegularization.ipynb.

On removing the dropout layer the training accuracy increased to 96%, but on validation data set it still gives 91% accuracy. So looks like dropout layer did help in narrowing the gap, but looking at the results of FirstCNN_NoRegularization.ipynb it looked like the model didn't suffer from too much overfitting.

In my 3rd notebook, just tinkered with the optimizer used for the model from Adam to SGD and the results on using SGD did degrade compared to Adam and the time to train the dataset was also a tad on higher side. So using the optimizer and activation functions recommended by industry experts like Andrej Karpathy does help.

These are my first baby steps to unravel the blackbox of Deeplearning and Neural Nets. Still need to understand how experts decide on the hyperparameters (like no of conv layers, what should be filter size, Stride etc) of their networks for particular dataset or is it trial and error process.

In the above CNN model I have used ReLU as activation function which suffers from "dying ReLU" problem, but not sure how can I figure out if neurons in the network are activating and what percentage of network is dead on using ReLU activation function.