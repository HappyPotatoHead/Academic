---
aliases:
tags:
  - Notes
  - Assignment
Date: 2026-02-27
Completion: true
obsidianUIMode: preview
---
# Initialisation

## Xavier Initialisation

This is a weight initialiser created to solve the problem of vanishing and exploding gradients. 

> This method aims to address the issue of maintaining variance in the forward and backward passes of a neural network, specifically when using certain activation functions like hyperbolic tangent and the logistic sigmoid. 

Essentially, the aforementioned exploding and vanishing gradients in forward and backward passes. 

>[!REMINDER] Exploding and Vanishing Gradients
>Exploding gradient happens when the gradients become explosively massive that it hinders the model from making any meaningful changes. 
>
>Vanishing gradient happens when the gradients become so small that the model is unable to learn anything, and the weights and biases remain effectively static. 

According to the paper, regardless of the amount of input connections a neuron in a layer has, the variance of its output should be approximately similar.

The goal is maintaining such variance within a boundary that enables effective learning with different activation functions. 

They proposed a compromise - the connection weights of each layer must be initialised randomly, where $fan_{\text{avg}} = \frac{fan_{\text{in}} + fan_{\text{out}}}{2}$, as described in the following equation. 

$$
\begin{align}
\text{Normal distribution with mean } 0 \text{ and variance } \sigma^2 = \frac{1}{fan_{\text{avg}}}  \\
\text{Or a uniform distribution between } -r \text{and} + r, \text{with} r = \sqrt{ \frac{3}{fan_{\text{avg}}} }
\end{align}
$$

### Uniform Xavier Initialisation

$$
\begin{align}
x = \sqrt{ \frac{6}{n_{\text{inputs}} + n_{\text{outputs}}} }
\end{align}
$$

Where:
- $n_{\text{inputs}}$ is the features from the previous layer
- $n_{\text{outputs}}$ is the features from the current layer

The values are drawn from a uniform distribution in the range $[-x, x]$.

Generally, this subtype is the default in frameworks such as Keras or Tensorflow. The original paper also used this with tanh activation function. 

### Normal Xavier Initialisation

$$
\begin{align}
\sigma = \sqrt{ \frac{2}{n_{\text{inputs}}+ n_{\text{outputs}}} }
\end{align}
$$

Where:
- $n_{\text{inputs}}$ is the features from the previous layer
- $n_{\text{outputs}}$ is the features from the current layer

A value is drawn randomly from a normal distribution with mean 0 and standard deviation calculated from the equation. This random value serves as the initial weight for that connection. 

By limiting the standard deviation to be dependent on the number of inputs and outputs, the scale of the weights remain reasonable, regardless of size of the layer. 

This initialiser keeps the weights nearer to 0, allowing deeper networks to stabilise.  

### Why this shift? 

1. Exploding and Vanishing Gradient
2. Overfitting
	- Deeper models are more prone to overfitting, unless there is sufficient data to train the model.
	- However, in the event of a lack of data, proper weight initialisation starts training with properly-scaled weights, preventing vanishing gradients and saturation
3. Saturation
	- The output of the selected activation function becomes too close to its minimum or maximum value for a wide range of input. 
	- This causes the activation function to not be as sensitive to changes input and its gradient approaches zero.  

Xavier initialisation works best with sigmoid activation and hyperbolic tangent activation

### Code

```python
import torch 
import torch.nn as nn
import torch.nn.init as init

class Model(nn.Module):
	def __init__(self) -> None:
		super().__init__()
	
		self.flatten = nn.Flatten()
		
		self.fc1 = nn.Linear(784, 128)
		self.fc2 = nn.Linear(128, 64)
		self.fc3 = nn.Linear(64, 10)
		self.relu = nn.ReLU(inplace=True)
		
		self.apply(self._init_weights)
	
	def forward(self, x: torch.Tensor) -> torch.Tensor:
		x = self.flatten(x)
		
		x = self.fc1(x)
		x = self.relu(x)		
		
		x = self.fc2(x)
		x = self.relu(x)
		
		x = self.fc3(x)
		return x
		
	def _init_weights(m):
		if isinstance(m, nn.Linear):
			init.xavier_uniform_(m.weight)
			if m.bias is not None: 
			init.constant_(m.bias, 0.01)
```

> The code above only serves as an example. By default PyTorch handles initialisation with `Kaiming` which works best with `ReLU` and its variants. (which is also often the default one)
> 
> You generally only need to manually configure the weights if you wish to have a different one. 

## Other Initialisers

The initialisation strategy proposed for the ReLU activation function and its variants is called *He initialisation* or *Kaiming initialisation*. For SELU, *Yann LeCun's initialisation* method is used instead, preferably with a normal distribution.

| Initialisation | Activation functions                     | $\sigma^2(\text{Normal})$    |
| -------------- | ---------------------------------------- | ---------------------------- |
| Glorot         | None, tanh, sigmoid, softmax             | $\frac{1}{fan_{\text{avg}}}$ |
| He             | ReLU, Leaky ReLU, ELU, GELU, Swish, Mish | $\frac{1j}{fan_{\text{in}}}$ |
| LeCun          | SELU                                     | $\frac{1}{fan_{\text{in}}}$  |

# Forward Pass

In any neural network, the forward pass generally looks as follows: 
$$
\text{Summation} \rightarrow \text{Activation phase} \rightarrow \text{Cost Function}
$$

Coding the forward in PyTorch is relatively simple. 

```python
import torch 
import torch.nn as nn
import torch.nn.init as init

class Model(nn.Module):
	def __init__(self) -> None:
		super().__init__()
		# Define the layers and activation function here
	
	def forward(self, x: torch.Tensor) -> torch.Tensor:
		x = self.flatten(x)
		
		x = self.fc1(x)
		x = self.relu(x)		
		
		x = self.fc2(x)
		x = self.relu(x)
		
		x = self.fc3(x)
		return x
```

The implementation of the cost function happens in the training function.

```python
for epoch in range(epochs):
	running_loss = 0.0
	for data_for_the_model_to_process, labels in train_loader:
	
		optimiser.zero_grad()
		
		outputs = model(data_for_the_model_to_process)
		
		# Loss calculation happens here
		loss = loss_function(outputs, labels)
		
		# Backward pass
		loss.backward()
		
		# Updating Gradient
		optimiser.step()
		
		running_loss += loss.item()
		
```

However, outside of PyTorch, implementation usually follows this format:
$$
\text{Function for a single layer} \rightarrow \text{Function for all the layers} \rightarrow \text{Cost function}
$$

## Function for a single layer

This function will perform the summation phase and the activation phase. The results are kept in cache for quicker retrieval.

It's important to note that matrix size is king. If the sizes are not compatible, the model will not be able to learn anything. 

```python
# "@" is dot product
Z = A_prev @ W + b.T

# Assuming sigmoid act
A = 1 / (1 + np.exp(-Z))

# Storing it in cache
cache = (W, A_prev, A)

return A, cache
```

## Function for all the layers

This is essentially a for loop

```python
A = X
for l in range(1, L+1)
	A, cache = forward_linear(A, weights[l], biases[l])
	caches[i] = cache
```

Gradient clipping is generally not needed, lest you use RNNs/LSTMs or you observe vanishing/exploding gradient. 

## Cost function

The cost function that you choose is dependent on the problem that you are trying to solve. 

*Classification*

| Hyperparameter          | Binary classification                          | Multilabel binary classification | Multiclass classification                                                                                                         |
| ----------------------- | ---------------------------------------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| \# hidden layers        | Typically 1 to 5 layers, depending on the task | <                                | <                                                                                                                                 |
| \# output nuerons       | 1                                              | 1 per binary label               | 1 per class                                                                                                                       |
| Output layer activation | Sigmoid                                        | Sigmoid                          | Softmax                                                                                                                           |
| Loss function           | Binary Cross Entropy Loss                      | Binary Cross Entropy Loss        | Cross Entropy (if this used, softmax in the activation function is not needed)<br><br>Negative Log Likelihood (used with softmax) |


*Regression*

| Hyperparameter              | Typical Value                                                                     |
| --------------------------- | --------------------------------------------------------------------------------- |
| \# hidden layers            | Typically 1 to 5                                                                  |
| \# neurons per hidden layer | Typically 10 to 100                                                               |
| \# output neurons           | 1 per prediction dimension                                                        |
| Hidden activation           | ReLU                                                                              |
| Output activation           | None, or ReLU/softplus (if positive outputs) or sigmoid/tanh (if bounded outputs) |
| Loss function               | MSE, or Huber if outliers                                                         |
# Backward Pass

In any neural network, the backward pass generally looks as follows with emphasis on derivation: 
$$
\text{Cost Function} \rightarrow  \text{Activation phase}  \rightarrow  \text{Summation phase} 
$$

In PyTorch, the implementation is as easy as:

```python
# Backward pass
loss.backward()

# Updating Gradient
optimiser.step()
```

Under the hood, backward propagation in each phase follows very similar steps,

$$
\text{Current Upstream Gradient} = \text{Local Gradient} \times \text{Previous Upstream Gradient}
$$

Under summation phase, there are three upstream gradient that has to be calculated:
1. Weight
2. Bias
3. Input Feature (layers succeeding layer 1)

Again, outside of pytorch, implementation still involves heavy abstraction.

$$
\text{Function for a cost layer} \rightarrow \text{Function for summation and activation layer} \rightarrow \text{Wrapper function}
$$

The wrapper function is still just a for loop but backwards

```python
L = len(caches) - 1
weights_grad = [None for i in range(len(caches))]
biases_grad = [None for i in range(len(caches))]

# Backpropagate the cost function
dA = backprop_cost(y_pred, y)

# Backprop linear layers
for l in range(L, 0, -1):
	curr_cache = caches[l]
	# The output layer has a different activation function
	# Hidden layers all have the same activation function
	curr_act = act_functions[l]
	
	dA, dW, db = backprop_linear(dA, curr_cache, curr_act)
	
	weights_grad = [None for i in range(len(caches))]
	biases_grad = [None for i in range(len(caches))]

return weights_grad, biases grad
```

# Updating Hyperparameters

Once gradient descent has happened, the weights and biases in the model are updated. 

In PyTorch, this is done with a single line

```python
# Updating Gradient
optimiser.step()
```

Outside of any framework, it is implemented with a for loop

```python
for l in range(1, L+1):
	weights[l] -= lr * weights_grad[l]
	biases[l] -= lr * weights_grad[l] 
```

# PyTorch Implementation

Model implementation

```python
import torch 
import torch.nn as nn
import torch.nn.init as init

class Model(nn.Module):
	def __init__(self) -> None:
		super().__init__()
	
		self.flatten = nn.Flatten()
		
		self.fc1 = nn.Linear(13, 20)
		self.fc2 = nn.Linear(20, 1)
		
		self.tanh = nn.Tanh()
		self.sigmoid = nn.Sigmoid()
		
		self.apply(self._init_weights)
	
	def forward(self, x: torch.Tensor) -> torch.Tensor:
		
		x = self.fc1(x)
		x = self.tanh(x)		
		
		x = self.fc2(x)
		x = self.sigmoid(x)
		
		return x
		
	def _init_weights(m):
		if isinstance(m, nn.Linear):
			init.xavier_uniform_(m.weight)
			if m.bias is not None: 
			init.constant_(m.bias, 0.01)
```

Training

```python
lr: float = 0.5
epochs: int = 100

loss_function = nn.BCELoss()

# Basically how the values are updated
optimiser = torch.optim.SGD(model.parameters(), lr=lr)

running_loss: float = 0.0

for epoch in range(epochs):
	optimiser.zero_grad()
	
	output = model(X)
	loss = loss_function(output, y)
	
	loss.backward()
	optimiser.step()
	
	running_loss += loss	
```