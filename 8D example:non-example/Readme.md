## An 8D example.
We construct an eight dimensional example and apply the proposed algorithm to learn the designed function. 

We show that when each layer (drift) is approximated by

$$
   \sum a_l \sigma_l( W X +B) , \ \ -A \leq s_l \leq A
   $$

where $\sigma$ is a Sigmoid function, the algorithm converges. 

However, when ReLu is used in place, the control parameters blow up (NAN or are demonstrated to be very large) since this function is non-smooth and unbounded. 
