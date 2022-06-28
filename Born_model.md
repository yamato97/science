---
mathjax: true
---

# Born model

Takahisa Yamato

July, 21, 2021



## Born model

In a dielectric medium, a scholar potential  $\phi$ occurs from a charge distribution. We consider the work, $\delta W$, needed to increase the uniform charge density throughout the distribution by $\delta\rho$. This work equals to the increase of energy:
$$
\delta W = \int_V \phi (\mathbf{r})\delta \rho dV  \tag{1}
$$
In a dielectric medium, Gauss's law is $$\nabla \cdot \mathbf{D}=\rho $$. Therefore, 
$$
\phi \delta \rho = \phi \nabla \cdot \delta \mathbf{D} = \nabla \cdot (\phi \delta \mathbf{D}) - \delta \mathbf{D} \cdot \nabla \phi    \tag{2}
$$
By substituting the integrand of (1) for (2), we obtain:
$$
\delta W = \int_V \nabla \cdot (\phi \delta \mathbf{D})dV - \int_V \delta \mathbf{D} \cdot \nabla \phi dV \tag{3}
$$
By using divergence theorem, the first term is equal to a surface integral of $$\phi \delta \mathbf{D} \cdot \mathbf{n}  $$, where $\mathbf{n}$ is the unit vector normal to the integral surface.  If we expand the volume of integration to infinity, then $$\phi$$ decreases on the order of  $$\sim \frac{1}{r}$$ for any finite charge distribution. Therefore, the first term in Eq.(3) vanishes. Substituting $$\nabla \phi$$ for $$-\mathbf{E}$$ in Eq. (3), we get: 
$$
\delta W = \int_V \delta \mathbf{D} \cdot \mathbf{E} dV \tag{4}
$$
 In a linear dielectric, $$\delta \mathbf{D} = \epsilon \delta \mathbf{E} $$. We parametrize $\mathbf{E}$ by $\lambda$ so that $\mathbf{E}$ increase from 0 to $\mathbf{E}$ as $\lambda$ 0 to 1. And, using the following relation,
$$
\mathbf{E} \cdot \delta \mathbf{E} = \mathbf{E} \cdot \frac{\partial \mathbf{E}}{\partial \lambda} \delta \lambda = \frac{1}{2}\frac{\partial E^2}{\partial \lambda} \delta \lambda
$$
we obtain the following equation by integrating (4) from $\mathbf{E}$ = 0 to $$\mathbf{E}$$:
$$
W = \frac{\epsilon}{2} \int_V E^2 dV \tag{5}
$$
If we keep the system at constant volume and temperatute, then $$dF = dU$$. Accordingly, 
$$
\Delta F = \frac{\epsilon}{2} \int_V E^2 dV \tag{6}
$$
   Next, we move on to the Born model. The free energy of solvation can be broken up as:
$$
\Delta G = \Delta G_{elec} + \Delta G_{vdw} + \Delta G_{cav}
$$
We consider the solute to be a sphere of charge $Z$ with radius $a$ embeded in a medium of dielectric constant $\epsilon$. Then, the electric field produced bythe charge at distance $r > a$ is 
$$
\mathbf{E} = \frac{Z}{4 \pi \epsilon} \frac{\mathbf{r}}{r^3}
$$
To find the free energy, we use Eq.(6) and integrate $E^2$ from $r=a$ to $r = \infty$, yielding:
$$
G = \frac{Z^2}{8 \pi \epsilon a } \tag{7}
$$
We can compare the energy of the solute in vacuum ($\epsilon = \epsilon_0$) with the energy in the solvent. This energy difference between these two states is the electrostatic contribution to the solvation free energy:
$$
\Delta G_{elec} = \frac{Z^2}{8 \pi \epsilon_0 a} \Bigl( \frac{1}{\epsilon_r}-1\Bigr) \tag{8}
$$

## Generalized Born model

The generalized Born model is an extension of Born model to a molecule with non-spherical shape. We consider that each atom in the molecule as a sphere of radius $a_i$ and charge $q_i$. The electrostaic contribution to the free energy chages as 
$$
\Delta G_{elec} = - \frac{1}{8 \epsilon_0} \Bigl(\frac{1}{\epsilon_r}-1 \Bigr) \sum_{i,j}^{N} \frac{q_iq_j}{f_{GB}} \tag{9}
$$
, where
$$
f_{GB}(i,j) = \Bigl[r_{ij}^2 + R_i R_j \exp\Bigl(\frac{-r_{ij}^2}{4R_i R_j} \Bigr) \Bigr]
$$
Here $R_i$ are called the effective Born radii. The generalized Born approach is heavily used in biophysics because of its computational ease. However, this theory typically overestimates solvation free energies. 



  

