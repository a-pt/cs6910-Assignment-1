# CS6910 Deep Learning [CS20M005,CS20M016]

-Gradient_Descent_Solution[1-7].iypnb
-
Question 1-7 is implemented in the single file Gradient_Descent_Solution[1-7].iypnb<br/>
The code implements backpropogation algorithm for feed forward neural network in with the following functionalities.
```
Optimizers               :Stochastic,NAG,Momentum,RMSPorp,Adam,Nadam
Activation Fucntions     :Sigmoid, Tanh, ReLu
Initialization           :Random, Xavier
```
-Functions:
-
*prep_pixels(test_data,train_data)* - Datapreprocessing [Normalization]<br/><br/>
initialize(string,no_of_input, no_of_hidden_layer, no_of_output,neurons_in_hidden_layer) - Initialize weights and biases with either one of the option(random or xavier) according to the first argument.<br/><br/>
*activation(string,list)* - returns output of a hidden layer after applying activation function(argument-1) on weighted sum of inputs specified in the 2nd positional argument.</br>*softmax(list)*- implements softmax output function applied at the output layer of neurons.<br/><br/>      
*feed_forward(input,weights,bias,layers,activation_fn)* - Takes images from the fashion-mnist data as input and outputs a probability distribution over the 10 classes.<br/><br/>
*back_propogation(H,A,y_hat,label,W,L,actfn)* - Implements back propogation algorithm for diffrent optimisations. Arguments for this funtion is as follows: H- Gradients wrt hidden layer outputs, A- Gradients wrt pre activation, y_hat- Predicted probabiity distribution ouput by feed forward function, W- weights, L-no of layes, actfn- Activation fucntion.<br/><br/>
*stochastic(Layers,No_of_hidden_neurons,learning_rate,epoch,activation_function,initialization,decay_factor)* - Implementation of SGD.</br><br/>
*momentum(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - MomentumGD. </br><br/>
*nesterov(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - NAG. </br><br/>
*rmsprop(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - RmsProp. </br><br/>
*adam(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - Adam. </br><br/>
*nadam(Layers,No_of_hidden_neurons,learning_rate,batch_size,epoch,activation_function,initialization,decay_factor)* - Nadam. </br><br/>



       
