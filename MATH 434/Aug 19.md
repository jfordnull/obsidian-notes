Midterm - October 16
- Look into Matlab
# Floating Point

A real machine number consists of two parts:
- *m* is the mantissa (or significant) 
- *e* is an exponent; (*B* is our base, ex. *B*=2 in binary)

$$\tilde{a}=\pm{m}\times{B}^{e}$$
$m = D.D...D$
$B = D...D$
${D}\in\{0,1,...,B-1\}$

eps := smallest possible number : ${eps}+{1}\neq{1}$

ex. MATLAB Precision (IEEE Double Precision) is 64 bits:
- 0: S (sign)
- 1-11: e
- 12-63: m
	
In binary, ${eps}={2}^{-t}$, where t = mantissa bits

Iterative method: $x_{k+1}=F(x_k)$

Stopping criteria:
$|x_{k+1}-x_k|<tol$

ODE := Ordinary Differential Equation
- Kepler's equation
- Pendulum equation
- Bass diffusion model
(PDE := Partial Differential Equation)

$$u^Tv= u_1v_1+...+u_nv_n$$






