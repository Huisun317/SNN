This second example is a classical linear quadratic problem. 


$$
{ \begin{cases}
        dx_t=(-\frac{1}{4} x_t +u_t) dt + ( \frac{1}{5} x_t +u_t) dW_t \\
         x_0=x_0,  & x \in \mathbb{R}^d \\
    \end{cases}
}
$$

The cost functional takes the following form:
$$J(u(\cdot)) = \mathbb{E} [ \frac{1}{2} \int^T_0 \langle \frac{1}{2} x_t, x_t \rangle dt -\frac{1}{2} \langle Qx_T, x_T\rangle ]$$

The Hamiltonian is found to be accordingly
$$H(t,x,u,p,q) = \langle p, -\frac{1}{4}x +u \rangle +\langle q, \frac{1}{5}x +u \rangle -\frac{1}{4}\langle x,x \rangle -\langle u, u \rangle$$
And the optimal control is found to be $u^*= \frac{1}{2}(p+q)$.

$$
{ \begin{cases}
        dx^* _t=(-\frac{1}{4} x^* _t +u^* _t) dt + ( \frac{1}{5} x^* _t +u^* _t) dW_t \\
         -dp^* _t=(-\frac{1}{2} x^* _t -\frac{1}{4} p^* _t +\frac{1}{5} q^* _t) dt - q^* _t dW_t\\
          x^* _0 =x_0, p^* _T=-Qx^* _T, \\
          u^* _t=\frac{1}{2}(p^* _t+q^* _t)\\
    \end{cases}
}
$$


The setup:

$T=0.1,x_0=1$ $Q=I_n$, the benchmark value of $p_0$ is $p^*_0 = -0.9586$. Our new algorithm produces result that is fairly close to the benchmark. 
