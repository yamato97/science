---
mathjax: true
---

# Density of States

Nov. 22, 2021
T. Yamato@NU

## Phase space (p, q)

The density of states, DOS, describes the number density of possible available states as a function of energy. According to the uncertainty principle, $\Delta p \Delta q > h$, where $h$ is Plank's constant. Let us consider a free particle with energy $\epsilon = \frac{p^2}{2m}$ moving in 3D space of volume $V$. Then, the number of states can be obtained by dividing the (available phase space volume) by $h^3$. Note that the phase space volume is obtained by the product of (momentum space volume) and (real space volume). 

Since this Hamiltonian does not depend on $\rm \bf{q}$, the avilable real space volume for this particle is simply $V$. On the other hand, we need to consider the $p$-dependence of $\epsilon = p^2 / 2m$ for the momentum space. The volume of the spherical shell of radius $p$ to $p + dp$ is $4 \pi p^2 dp$ in the momentum space. Using $d\epsilon = \frac{p}{m}dp$, we obtain the density of states as 
$$
D(\epsilon) = \frac{V}{h^3}\cdot 4\pi p^2 dp = \frac{Vm^{3/2}}{\sqrt 2 \pi^2 \hbar^3}\epsilon^{1/2} \tag{1}
$$

## Phase space (k, q)

We can reproduce the previous result Eq (1) in a similar manner using $p = \hbar k$.

## Particle confined in a square well

Let us consider a particle confined in one-dimensional space, $x=[0, L]$, with an infinite square well potential. We can easily get the eigenstates and eigenenergies as 
$$
\Psi (x) = \sqrt{\frac{２}{L}}\sin\left(\frac{n\pi x}{L}\right), \;(n=1, 2, 3, \cdots)
$$  
and $E = \frac{n^2 \pi^2 \hbar^2}{2mL^2}$, respectively. If you extend this to three dimsions, then the energy eigenvalues becomes, 
$$
E = \frac{\pi^2 \hbar^2}{2mL^2}(n_x^2+n_y^2+n_z^2).
$$
We can rewrite this as
$$
(n_x^2 + n_y^2 + n_z^2) = \frac{2mEL^2}{\pi^2 \hbar^2}.
$$

The volume of the number space $(n_x, n_y, n_z)$ available for the system corresponds to the number of states because the allowed positions in the number space is only those at grid points. The number of available grid points is obtained by dividing the volume of availale space by the volume of the cubic element with a volume of 1 x 1 x 1 = 1. 

We define the total number of states, $N(E)$, with energies less than $E$. Then we can get $D(E)$ by taking the derivative of $N(E)$ with respect to $E$.

The distance between the grid point $(n_x, n_y, n_z)$ and the origin is $\sqrt{n_x^2 + n_y^2 + n_z^2}$. Note that we only consider positive intergers for $n_x$, $n_y$, and $n_z$. Then, we obtain $N(E)$ as
$$
N(E) = \frac{1}{8}\frac{4\pi}{3}\sqrt{\frac{2mEL^2}{\pi^2 \hbar^2}}^3=\frac{L^3}{6\pi^2\hbar^3}(2m)^{3/2}E^{3/2}
$$
Finally, we reproduce Eq. (1) by taking the derivative of $N(E)$ with respect to $E$.