Previous electric field equation useful for calculating E due to small number of charges. Often we have *continuous* distribution of electric charge rather than discrete charges.
# Electric Field, Continuous Charge Distribution

The electric field at P due to a continuous charge distribution is the vector sum of the fields $\Delta \vec{E}$ due to all the elements $\Delta q_i$ of the charge distribution:

$$\vec{E}=k_e\lim_{\Delta q_i \rightarrow 0}\sum_i\frac{\Delta q_i}{r_i^2}\hat{r}_i=k_e\int\frac{dq}{r^2}\hat{r}$$
Where integration is over entire charge distribution.

E.g. charge distributed over a line, area, and volume. Use concept of *charge density* with the following notations:

**Volume Charge Density**:
$$\rho\equiv\frac{Q}{V}$$
(SI unit $C/m^3$)

**Area Charge Density**:
$$\sigma\equiv\frac{Q}{A}$$
($C/m^2$)

**Linear Charge Density**:
$$\lambda\equiv\frac{Q}{l}$$
($C/m$)

If nonuniform distribution of charge, $dq$ is given as: $dq = \rho dV$, $dq = \sigma dA$, $dq = \lambda dl$ 
# 23.2

**Electric Flux** is the product of the magnitude of the electric field $E$ and surface area $A$ perpendicular to field:
$$\Phi_E=EA$$
(SI : $N \cdot m^2/C$)
When the surface is not perpendicular to the field, at an angle $\theta$ to a plane perpendicular to the field:
$$\Phi_E=EAcos\theta$$
General definition of electric flux is:
$$\Phi_E\equiv\int_{surface}\vec{E}\cdot dA$$
Often we evaluate flux for a *closed surface*, meaning it divides space into an inside and out (e.g. sphere). Using $\oint$ to represent an integral over a closed surface, we can write net flux through a closed surface as:
$$\Phi_E=\oint\vec{E}\cdot d\vec{A}=\oint E_ndA$$
Where $E_n$ represents component of electric field normal to the surface.
# 23.3

**Gauss's Law**
This section describes general relationship between net electric flux through a closed surface (called *gaussian surface*) and the charge enclosed by the surface - a relationship known as *Gauss's Law*:
$$\Phi_E=\oint\vec{E}\cdot d\vec{A}=\frac{q_{in}}{\epsilon_0}$$
Net flux through *any* closed surface surrounding a point charge $q$ is given by $\frac{q}{\epsilon_0}$. (Therefore, net flux $\propto$ to the charge inside surface.)

Gauss's Law is useful for determining electric fields when the charge distribution is highly symmetric.
# 23.4

**Applications of Gauss's Law to Various Charge Distributions**
(Remember: a Gaussian surface is an imaginary surface you construct)
# Example 1: A Spherically Symmetric Charge Distribution

Insulating solid sphere of radius $\alpha$ has a uniform volume charge density $\rho$ and carries total positive charge $Q$.

**Example 1.A: Electric Field at a Point Outside the Sphere** 
for ($r > \alpha$): 
$$E=\frac{Q}{4\pi\epsilon_0r^2}=k_e\frac{Q}{r^2}$$
**Example 1.B: Electric Field at a Point Inside the Sphere**
for $(r<\alpha)$:
$$E=\frac{Q/\frac{4}{3}\pi\alpha^3}{3(1/4\pi k_e)}r=k_e\frac{Q}{\alpha^3}r$$
# Example 2: A Cylindrically Symmetric Charge Distribution

Find the electric field a distance $r$ from a line of positive charge of infinite length and constant charge per unit length $\lambda$:
$$E=\frac{\lambda}{2\pi\epsilon_0r}=2k_e\frac{\lambda}{r}$$
# Example 3: A Plane of Charge

Find the electric field due to an infinite plane of positive charge with uniform surface charge density $\sigma$
$$E=\frac{\sigma}{2\epsilon_0}$$


