For the first numerical example, we reproduce the results shown in Weinan. We solve a high dimensional HJB equation of 100 dimensions.
consider the following HJB equation
\[
\begin{cases}
    \frac{\partial v}{\partial t} + \Delta_x v - \lambda |D_x v|^2 = 0 ,& (t,x) \in [0,T) \times \bR^d \\
    v(T,x)=g(x),              & x \in \bR^d
\end{cases}
\]
Notice that the equation above can be put in the following form
\[
\begin{cases}
    \frac{\partial v}{\partial t} + \Delta_x v + \lambda \inf_{a \in \bR^d} [|a|^2 + 2a \cdot D_x v ] = 0 ,& (t,x) \in [0,T) \times \bR^d \\
    v(T,x)=g(x),              & x \in \bR^d
\end{cases}
\]
