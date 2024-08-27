$$b_k - a_k = \frac{1}{2}(b_{k-1}-a_{k-1})=\frac{1}{2^k}(b-a)$$
We obtain for the error:
$$|x_k-s|\le b_k-a_k=\frac{1}{2^k}(b-a)\rightarrow 0, k \rightarrow \infty$$
# Fixed Point Iteration
Consider
$$f(x)=0$$
where f(x) is function defined and continuous in the interval [a,b]. Assume that $s\in[a,b]$ . In order to compute s, we transform function into fixed point form.
$$x=F(x)$$
where $F(x) = x\longleftrightarrow f(x)=0$. Fixed point form suggests:
$$x_{k+1}=F(x)$$
$$F(x)=f(x)+x$$
Ex. 1:
Start with function and transform it:
$$f(x) = xe^x-1=0$$
This implies:
$$x_{k+1}=F(x_k)=x_k+x_ke^{x_k}-1$$
---
We can also express the iterative relation as follows:
$$x=x+xe^x-1$$
$$1+x=x+xe^x$$
$$1+x=x(1+e^x)$$
$$F(x_k)=\frac{1+x_k}{1+e^{x_k}}$$
Second version is better because $x_ke^{x_k}$ term will grow much larger asymptotically 

**Newton's Method**
basic idea:
- approximate the function f in the neighborhood of a zero s by a simpler function h (e.g. linear function)
- replace f(x) = 0 by h(x) = 0 which should be easy to solve and one hopes that the zero of h is also an approximation of the zero of
Let $x_k$ $be an approximation of a zero s of f. We choose for h a linear function 

$$x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}$$

