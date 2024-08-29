A differential equation (DE) relates one or more unknown functions and their derivatives. An Ordinary Differential Equation (ODE) is a DE with only one independent variable (in contrast to PDEs). Obviously, a nonlinear ODE is one in which the unknowns appear as variables of a polynomial of degree higher than one.
# Computing Nonlinear ODEs

A few methods to solve for $x$, $f(x)=0$, sometimes labelled $s$ (for solution):

**Bisection Method:**

Root-finding method applicable to any continuous function for which one knows two values with opposite signs. Repeatedly bisect the interval, each time selecting the subinterval in which the function changes sign, and therefore must contain a root. (Similar to binary search in CS.)

