$$f(x)=xe^x-1=0$$
$$x_{k+1}=F(x_k)$$
$$E-0.8sinE-2\pi/10=0$$
$$E_{k+1}=0.8E_k+2\pi/10$$

If matrix $U\in R^{n\times n}$ is an upper triangular matrix, $U=(u_{ij}),i=1,2,...,n;j=1,2,...,n.$ We solve the equation in $Ux=b$ for $x_i$. Prove that:
$$x_i=(b_i-\sum_{j=i+1}^nu_{ij}x_j)/u_{ii}$$
Start by writing U as:
$$U=
\begin{pmatrix} 
u_{11} & u_{12} & ... & u_{1i} & ... & u_{1j} & ... & u_{1n} \\ 
0 & u_{22} & ... & u_{2i} & ... & u_{2j} & ... & u_{2n} \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & ... & u_{ii} & ... & u_{ij} & ... & u_{in} \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & ... & 0 & ... & 0 & ... & u_{un} \\
\end{pmatrix}
$$


