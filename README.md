# SNN
This repository contains the code/implementation results of our novel Stochastic Maximum principle approach for solving control problems using the SGD optimization procedure.

The goal of this paper/project (under review in SIAM Journal of Numerical Analysis) is to solve the stochastic optimal control problem through the stochastic maximal principle (SMP) where the control is assumed to be time deterministic. 

As usual, SMP relies on constructing the "adjoint process" $ (Y_t, Z_t)$ to find the optimal control which will in turn requires finding the numerical solution of these two processes. Solving these two 'functions' (Feyman-Kac) is not very efficient especially in high dimensions. Noticing that the true goal is to find the optimal control $u_t$ (or $u_{n}$ in the discretized case), we approximate $(Y_t, Z_t)$ with the one-trajectory approximation, and rely on the SGD algorithm to reach convergence in expectation.

When the problem is convex, we show that the decay rate (under sqaured norm) is:
$$\sim (C_1 \frac{1}{N} + C_2 \frac{N}{K})$$
where N is the total time discretization and $K$ is the iteration number. 

An eight-dimensioanl example is constructed for numerical demonstration. 
![high_dim_decay](https://user-images.githubusercontent.com/107137651/172748641-ae492a7f-a47d-4e6c-a046-8b6ec7af7439.png)

When the strong convexity assumption is relaxed, one can only show convergence of the algorithm (with the martingale trick), but not convergence in the global minimum sense. 


## High dimension
This idea can be generated to higher dimensions to train stochastic neural networks. Notice that under our stochastic framework, the diffusion process 
$$dX_t = b(u_t, X_t) dt + \sigma (u_t,X_t) dW_t $$
can be treated with ResNet adding a noise at each forward process. Then, it is natural to train the SNN in the SMP setting since taking derivatives with respect to controls related to diffusion will require Ito's formula.

The addition of the noise term in building stochastic neural networks brings a few benefits, and a few observations are in order. 
1. Removing the noise term (or setting the noise to be constant) will result in the standard Maxium Principle framework for solving $Y_n$(Qianxiao Li etal, https://arxiv.org/abs/1710.09513) We give here an example of training such NN on CIFAR10 and obtain 93%~94% accuracy on the test set without much fine tuning. 
2. Adding a noise term can increase the robustness of the neural network compared to the standard feedforward neural network trained to achieve the same level of accuracy (on test set.) This observation echos the findings of the paper (Bao Wang etal. https://arxiv.org/abs/1811.10745). Instead of running a large volume of ResNet code to prove this fact, we train both the standard FFNN and SNN to the same level of accuracy on both the MNIST and FASHION MNIST dataset and perform adversial attack on the trained neural networks. We show that SNN is more robust when facing such attack. 
3. Since our work is under the framework of stochastic control which is intimately related to the HJB equation, we show that it is natural to solve the HJB equation through our approahch. We use the standard HJB example in the classical paper (Jiequn Han, Arnulf Jentzen Weinan E https://arxiv.org/pdf/1707.02568.pdf)
4. The HJB example has a constant diffusion term. To show that the diffusion term can be approximated by a nural network whose parameters can be optimized through our procedure, we solve a high dimensional linear quadratic problem. (Example and exact solution borrowed from https://arxiv.org/abs/2007.02227)
5. Fixing an input $X_0$ and passing it through a stochastoc neural net will produce a random variable. Thus, learning from noisy data through controling the diffusion term will help us in quantifying the uncertainity of the dataset. This is a very interesting idea/direction that the author is exploring.   










