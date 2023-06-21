# Solving-Burger-s-Equation-using-Physics-Informed-Neural-Networks

Solution to Burger's Equation using Physics Informed Neural Network

The differential equation along with it's domain of definition and boundary conditions is already given in the notebook with a brief introduction to Physics Informed Neural Networks and how they are used to solve Burger's Equation.

Here, I will be covering some details regarding Data Generating Process:

When we talk about data here, We just mean the points that we are sampling in order to use for training the Neural Network.

As the Neural Network NN(x,t) ~ u(x,t) and u(x,t) is just the solution of our differential equation.

So we are sampling some boundary condition points, some general points in the domain of definition in order to impose the rules governed by our PDE(including boundary conditions) to our Neural Network.

How sampled points for boundary/initial conditions look like:


  X_u     | t_u        | U_train
	       |	           |
  +1      | [0,1]      | 0
  -1      | [0,1]      | 0
  [-1,1]  | 0          | -sin(pie(X_u)
  
How general sampled points look like:

  X_f     |   t_f
	       |  
  [-1,1]  |  [0,1]
  
