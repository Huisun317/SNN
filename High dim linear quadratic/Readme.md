This second example is a classical linear quadratic problem. 
\[
\begin{cases}
    dx_t=(-\frac{1}{4} x_t +u_t) dt + ( \frac{1}{5} x_t +u_t) dW_t \\
    x_0=x_0,              & x \in \bR^d
\end{cases}
\]
The cost functional takes the following form:
$$J(u(\cdot)) = \mathbb{E} [ \frac{1}{2} \int^T_0 \langle \frac{1}{2} x_t, x_t \rangle dt -\frac{1}{2} \langle Qx_T, x_T\rangle ]$$
