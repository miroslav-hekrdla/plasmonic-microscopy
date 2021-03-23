# Fourier Transform of Rotationally Symetric Function in 2D

MH, v1.0, 2021_03_23

[toc]

### FT Definition

* $$S(f_x,f_y)=\mathrm{FT}[s(x,y)]=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} s(x,y) \, \mathrm{e}^{-\mathrm{j}2\pi(f_x x + f_y y)} \mathrm{d}x\mathrm{d}y,$$

   $$s(x,y)=\mathrm{FT}^{-1}[S(f_x,f_y)]=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} S(f_x,f_y) \, \mathrm{e}^{\mathrm{j}2\pi(f_x x + f_y y)} \mathrm{d}x\mathrm{d}y.$$

* Finite signal energy condition $$E_s=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} |s(x,y)|^2\mathrm{d}x\mathrm{d}y<\infty$$.

### FT of Separable Function

* Separable function can be written as  $s(x,y) = s_x(x) s_y(y)$.

* 2D FT of separable function is a product of corresponding 1D FTs:

   $$\mathrm{FT}[s(x,y)]=\mathrm{FT}[s_x(x)] \mathrm{FT}[s_y(y)],$$ 

  due to $S(f_x,f_y)=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} s_x(x)s_y(y) \, \mathrm{e}^{-\mathrm{j}2\pi(f_x x + f_y y)} \mathrm{d}x\mathrm{d}y=\int_{\infty}^{\infty} s_x(x) \, \mathrm{e}^{-\mathrm{j}2\pi f_x x} \mathrm{d}x\cdot \int_{-\infty}^{\infty} s_y(y) \, \mathrm{e}^{-\mathrm{j}2\pi f_y y} \mathrm{d}y$.

### Rotationally Symmetric Function

* Describe $s(x,y)$  in polar coordinates as $\tilde{s}(r,\theta)\triangleq s(r\cos\theta, r\sin \theta)$. We use tilde notation to emphasize that function $s$ and $\tilde{s}$ are not strictly identical, though there is a simple one-to-one correspondence.

* Rotationally symmetric function is separable function in polar coordinates independent on rotational angle, i.e. $ \tilde{s}(r,\theta)=s_r(r) s_\theta(\theta) = s_r(r)$.

### FT of Rotationally Symmetric Function

$$S(f_x,f_y)=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} s(x,y) \, \mathrm{e}^{-\mathrm{j}2\pi(f_x x + f_y y)} \mathrm{d}x\mathrm{d}y = \left|\begin{array}{c} x=r\cos\theta\\ y=r\sin\theta\\ \mathrm{d}x\mathrm{d}y=r\mathrm{d}r\mathrm{d}\theta \end{array}\right|=$$

$$=\int_{0}^{2\pi} \int_{0}^{\infty} s(r\cos\theta,r\sin\theta) \, \mathrm{e}^{-\mathrm{j}2\pi r (f_x \cos\theta + f_y \sin\theta)} r\mathrm{d}r \mathrm{d}\theta  = \int_{0}^{2\pi} \int_{0}^{\infty} s_r(r) \mathrm{e}^{-\mathrm{j}2\pi r (f_x \cos\theta + f_y \sin\theta)} r\mathrm{d}r \mathrm{d}\theta.  $$

Let denote FT spectrum in polar coordinates as $\tilde{S}(\rho,\phi)\triangleq S(\rho\cos\phi,\rho\sin\phi)$ and so

$$\tilde{S}(\rho,\phi)=\int_{0}^{2\pi} \int_{0}^{\infty} s_r(r) \mathrm{e}^{-\mathrm{j}2\pi r \rho (\cos\phi \cos\theta + \sin\phi \sin\theta)} r\mathrm{d}r \mathrm{d}\theta  = \int_{0}^{\infty} s_r(r) r \left( \int_{0}^{2\pi} \mathrm{e}^{-\mathrm{j}2\pi r \rho  \cos (\theta - \phi)}  \mathrm{d}\theta \right) \mathrm{d}r = $$

$$= 2\pi \int_{0}^{\infty} s_r(r) r J_0(2\pi r \rho) \mathrm{d}r $$,

where for the zero order Bessel function of the first kind holds  $J_0(x) = \frac{1}{2\pi} \int_{0}^{2\pi} \mathrm{e}^{-\mathrm{j} x  \cos (\theta - \phi)}  \mathrm{d}\theta, $ for any $\phi\in\mathbb{R}$.

### Summary

FT of rotationally symmetric function in polar coordinates is also rotationally symmetric and it equals to 

$$\tilde{S}(\rho,\phi) = S_\rho(\rho) = 2\pi \int_{0}^{\infty} s_r(r) r J_0(2\pi r \rho) \mathrm{d}r$$, 

where $r=\sqrt{x^2+y^2}$ and $ \tilde{s}(r,\theta)= s_r(r)$ is the function $ s(x,y)$ described in polar coordinates.

### Example

Let us consider a disc function $s(x,y)=\mathrm{circ}(x,y)\triangleq\begin{cases} 1, & \sqrt{x^{2}+y^{2}}\leq1\\ 0, & \mathrm{otherwise} \end{cases}$ for which $s_r(r)= 1$ for $r \leq 1$ and $0$ otherwise.

$$\tilde{S}(\rho,\phi) = 2\pi \int_{0}^{1} r J_0(2\pi r \rho) \mathrm{d}r = \left|\begin{array}{c} 2\pi r\rho=x\\ r=\frac{x}{2\pi\rho}\\ 2\pi\rho\mathrm{d}r=\mathrm{d}x \end{array}\right| = \int_{0}^{2\pi\rho} \frac{x}{\rho} J_0(x) \frac{\mathrm{d}x}{2\pi\rho} = \frac{J_1(2\pi\rho)}{\rho}$$, where for the first order Bessel function of the first kind holds $x J_1(x) = \int_{0}^{x} \xi J_0(\xi) \mathrm{d}\xi$.

### Reference

- [Blahut_1990], Lecture notes in radar/sonar: Theory of remote surveillance algorithms, IMA Preprint Series # 659, 1990
- [Blahut_2004], Theory of remote image formation, Cambridge University Press, 2004

- [Goodman_2005], Introduction to Fourier optics, Roberts and Company Publishers, 2005



