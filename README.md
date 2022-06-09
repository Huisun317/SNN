# SNN
This repository contains code/implementation results of our novel Stochastic Maximum principle approach for solving control problems using the SGD optimization procedure.

The goal of this paper/project (under review in SIAM Journal of Numerical Analysis) is to solve the stochastic optimal control problem through the stochastic maximal principle (SMP) where the control is assumed to be time deterministic. 

As usual, SMP replies on constructing the "adjoint process" $(Y_t, Z_t)$ which will in turn requires finding the numerical solution of these two processes. Solving these two 'functions' (Feyman-Kac) is not very efficient especially in high dimensions. Noticing that the true goal is to find the optimal contrl $u_t$ (or $u_{n}$ in the discretized case), we approximate $(Y_t, Z_t)$ with the one-trajectory solution, and rely on the SGD algorithm to reach convergence in expectation.

When the problem is convex, we show that the decay rate (under sqaured norm) is:
$$\sim (C_1 \frac{1}{N} + C_2 \frac{N}{K})$$
where N is the total time discretization and $K$ is the iteration number. 

An eight-dimensioanl example is constructed for numerical demonstration. 
![high_dim_decay](https://user-images.githubusercontent.com/107137651/172748641-ae492a7f-a47d-4e6c-a046-8b6ec7af7439.png)



