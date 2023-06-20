# Solving-Burger-s-Equation-using-Physics-Informed-Neural-Networks
Solved Burger's Equation using Physics Informed Neural Network in PyTorch

Refer to the presentation in the repository for better understanding of the problem statement

Procedure Used to implement PINNs for Solving Burger’s Equation

1. Data Preparation:
   - Boundary training data (X_u_train) is collected as pairs of (x, t) coordinates.
   - Boundary solution data (u_train) is collected.
   - Collocation points (X_f_train) are collected as pairs of (x, t) coordinates.

2. PINN Initialization:
   - The data arrays are transformed into torch tensors.
   - The neural network (PINN) is defined as a class inheriting from torch.nn.Module.
   - The PINN architecture consists of multiple fully connected layers with a hyperbolic tangent activation function.

3. PINN Forward Pass:
   - The forward method in the NeuralNetwork class defines the forward pass of the PINN.
   - The input (x, t) is passed through the fully connected layers with the activation function.
   - The output represents the function u(x, t).
4. Physics-Informed Neural Network:
   - The PhysicsInformedNN class is defined to handle the PINN operations.
   - The class takes boundary and collocation data as inputs.
   - The class initializes the necessary tensors, the PINN model, and the optimizer (LBFGS).
   - The class defines methods to compute the predicted solution (u) and the residual (f) using automatic differentiation.
5. Training the PINN:
   - The closure method is defined to compute the loss and update the gradients during each optimization step.
   - The train method is called to start the training loop.
   - The closure method is repeatedly called by the optimizer to update the PINN's weights and biases.
   - The loss consists of two components: the boundary condition loss (u_loss) and the PDE loss (f_loss).
   - The sum of these losses is minimized using the LBFGS optimizer.

6. Data Visualization:
   - The plot method is defined to visualize the solution on new data.
   - It generates a meshgrid of (x, t) points and evaluates the PINN's output.
   - The solution is reshaped and plotted using matplotlib.

7. Data Generation:
   - The generate_data function is defined to generate training points for boundary conditions and collocation points.
   - It samples points for boundary conditions (X_u_train) and collocation points (X_f_train).
   - The corresponding solution values (u_train) for the boundary conditions are also generated.

8. Training the Model:
   - The generate_data function is called to obtain the training data.
   - An instance of the PhysicsInformedNN class is created with the training data.
   - The train method is called to train the PINN and find the optimal weights.
