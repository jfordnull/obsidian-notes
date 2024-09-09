If $U\in R^{n\times n}$ 
$$x_1 = \frac{b_1}{u_{11}}-\frac{u_{12}x_2}{u_{11}}-\frac{u_{13}x_3}{u_{11}}$$

---

Goal of Gaussian Elimination: do the permutation to make A to a U (upper triangular matrix)
$$a_{11}x_1+a_{12}x_2+...+a_{1n}xn=b_1$$
Leave line 1 untouched
$$a_{21}x_1+a_{22}x_2+...+a_{2n}x_n=b_2$$
Line 2 eliminate 1st element utilizing 1st line: Line 2 - $\frac{a_{21}}{a_{11}}\times$ Line 1

That is,
Line 2 - Line* ; Where Line* := 
$$a_{21},\frac{a_{21}}{a_{11}}\times a_{12},...,\frac{a_{21}}{a_{11}}\times a_{1n}$$
```
for i=1:n-1
	for k=i+1:n
		{new Eq. # k} = {Eq. # k} - (a_ki/a_ii) {Eq # i}
	end
end
```