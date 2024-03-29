# CS6910 Deep Learning [CS20M005,CS20M016]

-Gradient_Descent_Solution[1-7].iypnb
-
Question 1-7 is implemented in the single file Gradient_Descent_Solution[1-7].iypnb<br/>
The code implements backpropogation algorithm for feed forward neural network on fashion_mnist dataset with the following functionalities.
```
Optimizers               :Stochastic,NAG,Momentum,RMSPorp,Adam,Nadam
Activation Fucntions     :Sigmoid, Tanh, ReLu
Initialization           :Random, Xavier
```
-Functions:
-

*prep_pixels(test_data,train_data)* - Datapreprocessing [Normalization]<br/>
initialize(string,no_of_input, no_of_hidden_layer, no_of_output,neurons_in_hidden_layer) - Initialize weights and biases with either one of the option(random or xavier) according to the first argument.<br/><br/>
*activation(string,list)* - returns output of a hidden layer after applying activation function(argument-1) on weighted sum of inputs specified in the 2nd positional argument.<br/><br/>
*softmax(list)*- implements softmax output function applied at the output layer of neurons.<br/><br/>
*feed_forward(input,weights,bias,layers,activation_fn)* - Takes images from the fashion-mnist data as input and outputs a probability distribution over the 10 classes.<br/><br/>
*back_propogation(H,A,y_hat,label,W,L,actfn)* - Implements back propogation algorithm for diffrent optimisations. Arguments for this funtion is as follows: H- Gradients wrt hidden layer outputs, A- Gradients wrt pre activation, y_hat- Predicted probabiity distribution ouput by feed forward function, W- weights, L-no of layes, actfn- Activation fucntion.<br/><br/>
*stochastic(Layers,No_of_hidden_neurons,learning_rate,epoch,activation_function,initialization,decay_factor)* - Implementation of SGD.<br/>
*momentum(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - MomentumGD.<br/>
*nesterov(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - NAG.<br/>
*rmsprop(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - RmsProp.<br/>
*adam(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - Adam.<br/>
*nadam(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - Nadam.<br/>

The implementation is linked with wandb and hyper parameter tuning can be done effectively by changing the values of sweep confiiguration in the script. The configuration used for parameter searching are as follows.

```
'epoch': [3,4,5,10]
'layers': [4,5,6]
'hidden_layer_size': [12,24,32,64,128]
'weight_decay': [0,0.0005,0.05,0.5]
'learning_rate': [0.001,0.0001]
'optimizer_fn': ['sgd','momentum','nesterov','rmsprop','adam','nadam']
'batch_size': [16,32,64,128]
'weight_initial':['random','xavier']
'activation_fn': ['sigmoid','tanh','relu']
```

-CE_vs_SE[8].ipynb
-
The Loss comparision for multiclass classification problem Cross Entopy vs Squared error is demostrated in [CE_vs_SE[8].ipynb] file. The comparison of train loss for Vanila Gradient descent trained on a neural network with 3 Layers having 8 neurons in each hidden layer with a learning rate 0.0001 is illustrated.[Question 8]

-Backporpogation- Python Scirpts
-

The individual pythons scripts for Vanila GD and each of the above optimisation algorithm are added in the following files. 
```
VanilaGD.ipynb
StochasticGD.ipynb
RmsProp.ipynb
NesterovGD.ipynb
Nadam.ipynb
MomentumGD.ipynb
Adam.ipynb
```

Activation function used is Sigmoid and Softmax is used for the output layer.  The parameter values such as No of Layers,Size of each hidden layer,No of classes and Learning Rate are hardcoded in these implementations to compare the loss function of each of them. These are made flexible enough to incorporate diffrent activations and optimisers in the combined solution file. [Gradient_Descent_Solution[1-7].iypnb]


-Best Models
-
The best 3 configurations got from hyper parameter search are tested on Mnist dataset for handwritten digits.<br/>

```
sgd_93.74.iypnb

Configurations-
Activation Fucntion: ReLu
Batch size: 64
Epoch: 5
Hidden layer size: 12
Learning Rate: 0.001
Optimizer: Stochastic GD
Weight Decay: 0.0005
Weight Initialisation: Xavier
Layers: 4

Test Accuracy: 93.74%
```
```
rmsprop_93.53.iypnb

Configurations-
Activation Fucntion: ReLu
Batch size: 64
Epoch: 2
Hidden layer size: 24
Learning Rate: 0.001
Optimizer: RmsProp
Weight Decay: 0
Weight Initialisation: Xavier
Layers: 3

Test Accuracy: 93.53%
```
```
momentum_85.54.iypnb

Configurations-
Activation Fuction: tanh
Batch size: 32
Epoch: 3
Hidden layer size: 8
Learning Rate: 0.001
Optimizer: Momentum
Weight Decay: 0.0005
Weight Initialisation: Xavier
Layers: 3

Test Accuracy: 85.54%

```
