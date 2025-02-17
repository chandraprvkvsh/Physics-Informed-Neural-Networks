# Physics Informed Neural Networks (PINNs)

This project focuses on utilizing Physics Informed Neural Networks (PINNs). While the scope is currently limited to Burger's Equation, the methodology can be extended to solve various types of differential equations, including highly non-linear ones. 

## Introduction

In the provided notebook, you will find the Burger's Equation along with its domain of definition and boundary conditions. Additionally, there's a brief overview of Physics Informed Neural Networks and their application in solving Burger's Equation.

## Data Generating Process

In this section, we delve into the process of generating data for training the Neural Network. The term "data" here refers to the points sampled to train the Neural Network. Since the Neural Network, denoted as NN(x,t), approximates the solution u(x,t) of our differential equation, the sampling process is crucial.

### Boundary and Initial Conditions

We sample points for boundary and initial conditions to ensure that the Neural Network adheres to the rules dictated by our Partial Differential Equation (PDE), including the boundary conditions. 

#### Sampled Points for Boundary/Initial Conditions

| X_u   | t_u      | U_train |
|-------|----------|---------|
| +1    | [0,1]    | 0       |
| -1    | [0,1]    | 0       |
| [-1,1]| 0        | g(x)    |

Here, `g(x) = -sin(πx)` represents the prescribed function for the boundary condition.

### General Sampled Points

In addition to boundary and initial conditions, we sample general points within the domain of definition to provide more data for training.

#### Sampled General Points

| X_f   | t_f      |
|-------|----------|
| [-1,1]| [0,1]    |

These sampled points help in capturing the behavior of the solution throughout the domain.

## Conclusion

This README provides an overview of the project, focusing on the methodology of using Physics Informed Neural Networks to solve Burger's Equation and the process of generating data for training the network. For further details and implementation, refer to the provided notebook.
