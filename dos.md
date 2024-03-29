---
mathjax: true
mermaid: true
---

# Density of States

Nov. 22, 2021
Nov. 23, 2021
Nov. 25, 2022

T. Yamato@NU

## Particle under periodic boundary condition

Let us consider a free particle under periodic boundary condition in one-dimensional space, $x=[0, L]$. If we assume the wavefunction of the form, $\psi_k (x) = Ce^{ikx}$, where $C$ is constant, then $\psi(x) = \psi(x+L)$. Accordingly, we obtain:
$$
k = \left(\frac{2\pi}{L}\right)n, \; (n=0, \pm1, \pm2, \cdots ),
$$
and we see that the state space $n = \frac{L}{2\pi}k$, which is easily extended to three-dimensional state space as $(n_x, n_y, n_z) = \left( \frac{L}{2\pi} \right)^3 (k_x, k_y, k_z)$. Consequently, we can represent the summation over all discrete states in the 3D state space in terms as integral with respect to wavenumber vector $\rm{\bf k}$: $\sum_{\rm\bf{k}_n} \rightarrow \left(\frac{L}{2\pi} \right)^3 \int d{\rm\bf k}$.

## Particle in a square well

Let us consider a particle confined in one-dimensional space, $x=[0, L]$, with an infinite square well potential. 

<img src="img/1Dwell-2.svg" title="1D square well potential">

We can easily get the eigenstates and eigenenergies as 
$$
\begin{align}
\Psi (x) &= \sqrt{\frac{２}{L}}\sin\left(\frac{n\pi x}{L}\right), \\ \epsilon &= \frac{n^2 \pi^2 \hbar^2}{2mL^2} \;(n=1, 2, 3, \cdots) \tag{1}
\end{align}
$$  

If you extend this to three dimensions, then the energy eigenvalues become, 
$$
\epsilon = \frac{\pi^2 \hbar^2}{2mL^2}(n_x^2+n_y^2+n_z^2). \tag{2}
$$
We can rewrite this as
$$
(n_x^2 + n_y^2 + n_z^2) = \frac{2m\epsilon L^2}{\pi^2 \hbar^2}. \tag{3}
$$
Let us consider the state space $(n_x, n_y, n_z)$. The L.H.S. of (Eq. 3) represents the squared distance, $r^2$, of the grid point $(n_x, n_y, n_z)$ from the origin. In this space, we find one grid point per each cubic element of volume 1 (= 1 x 1 x 1). Accordingly, the one-eighth of the volume of the sphere of radius $r$ represents the number of states, $N(\epsilon)$, with energy $< \epsilon$. Note that that the factor of 1/8 is needed because only positive integers $n_x, n_y, n_z$, are allowed.
$$
N(\epsilon) = \frac{1}{8}\frac{4\pi}{3}\left( \frac{2m \epsilon L^2}{\pi^2 \hbar^2} \right)^{3/2} \tag{4}
$$
Then the density of states, $D(\epsilon)$, is obtained by taking the derivative of $N(\epsilon)$ with respect to $\epsilon$, where $V=L^3$ is the real space volume of this system.
$$
D(\epsilon) = \frac{Vm^{3/2}}{\sqrt 2 \pi^2 \hbar^3}\epsilon^{1/2} \tag{5}
$$
