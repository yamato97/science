---
mathjax: true
---

# Navier-Stokes equation

[ver. 1. August XX, 2021] 

[ver. 2. September 03, 2021 ]

[ver.3. September 07, 2021]

Takahsia Yamato


## Lagrange derivative (material derivative)

In fluid continuum, if you measure the time evolution of physical quantity, say $A$, it changes from $A(x_0, y_0, z_0, t_0)$​ at time $t_0$​ and position $(x_0, y_0, z_0)$​​ to $A(x_0 + \Delta t v_x, y_0 + \Delta t v_y, z_0 + \Delta t v_z, t_0 + \Delta t)$​​ after $\Delta t$​. As a result, the difference of $A$​ is expressed as:
$$
\Delta A = \left (\frac{\partial A}{\partial x}v_x + \frac{\partial A}{\partial y}v_y + \frac{\partial A}{\partial z}v_z + \frac{\partial A}{\partial t}\right)\Delta t = \left ((\mathbf v \cdot \nabla) + \frac{\partial}{\partial t}\right)A \Delta t.
$$
The Lagrange derivative (material derivative) of $A$​ is represented as:
$$
\frac{DA}{Dt} = \frac{\Delta A}{\Delta t} = \left ((\mathbf v \cdot \nabla) + \frac{\partial}{\partial t}\right)A. \tag{1}
$$
The first term of the leftmost side of Eq.(1) is called convection term. 

## Incompressibl fluld

In incompressible fluid of density $\rho$, the total mass in region $V$ changes by $\frac{\partial}{\partial t}\int_{V}\rho dV$ as time evolution. This quantity is relarted with the mass flow across the surface of this region, $\int_S \rho \mathbf v \cdot \mathbf ndS = \int_V \nabla \cdot (\rho \mathbf v)dV$​​, via the continuity equation as:
$$
\frac{\partial}{\partial t}\int_{V}\rho dV = -\int_V \nabla \cdot (\rho \mathbf v)dV.
$$
Since region $V$ can be taken arbitrary, we obtain:
$$
\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \mathbf v)= 0. \tag{2}
$$
The material derivative of density $\rho$ should vanish because of incompressibility:
$$
\frac{D\rho}{Dt}= \frac{\partial \rho}{\partial t}+ \mathbf v \cdot \nabla \rho = 0 \tag{3}
$$
By using Eqs (2) and (3), we obtain:
$$
\nabla \cdot (\rho \mathbf v) = \nabla \rho \cdot \mathbf v + \rho (\nabla \cdot \mathbf v) = \mathbf v \cdot \nabla \rho.
$$
Thus, we see that the divergence of velocity is zero in this system:
$$
\nabla \cdot \mathbf v = 0. \tag{4}
$$

## Pressure term

If we consider a small volume element $dV = dxdydz$​ centered at $(x, y, z)$​, then the $x$​-compent of the force, $f_x$, acting on this element is:
$$
f_x = \left [p\left(x-\frac{dx}{2}, y, z \right) - p\left(x+\frac{dx}{2}, y, z \right) \right]dydz = -\frac{\partial p}{\partial x}dxdydz.
$$
Likewise, we obtain $f_y=-\frac{\partial p}{\partial y}dxdydz$ and $f_z=-\frac{\partial p}{\partial z}dxdydz$ for $y$- and $z$-component, respectively. Thus, the total force acting on this volume element per unit volume becomes $-\nabla p(x, y, z)$.

![NS.svg](/tips/NS.svg)

## Viscosity term

The viscous stress tensor $\tau_{ij}$ is expressed as:
$$
\tau_{ij} = \mu \left(\frac{\partial v_i}{\partial x_j} + \frac{\partial v_j}{\partial x_i} \right),
$$
where each of $(i, j)$ represents either of $(x, y, z)$. For example, $\tau_{xx}$ ($\tau_{xy}$) represents the $x$($y$)-compont of the force acting on the face parpendicular to the $x$-axis per unit area. Thus, the contributions to the $x$-component of the force, $f_x$, acting on the left and right surfaces are  $- \left(\tau_{xx}- \frac{1}{2}\frac{\partial \tau_{xx}}{\partial x}dx \right) \times dydz $  and   $\left(\tau_{xx} + \frac{1}{2}\frac{\partial \tau_{xx}}{\partial x}dx \right) \times dydz $, respectively (see below). Thus, the summation of these two terms becomes  $\frac{\partial \tau_{xx}}{\partial x}dx \times dydz $.　Likewise, the contributions from the front and back surfaces to $f_x$ are  $- \left( \tau_{yx} - \frac{1}{2}\frac{\partial \tau_{yx}}{\partial y}dy \right) \times dzdx $  and  $\left( \tau_{yx} + \frac{1}{2}\frac{\partial \tau_{yx}}{\partial y}dy \right) \times dzdx $ , and those from the top and bottom surfaces to $f_x$ are $ \left(\tau_{zx}+ \frac{1}{2}\frac{\partial \tau_{xz}}{\partial z}dz \right) \times dydx $  and   $-\left(\tau_{zx} - \frac{1}{2}\frac{\partial \tau_{zx}}{\partial z}dz \right) \times dydx $, respectively.  

![NS-viscosity](/tips/NS-viscosity.svg)

As a result,
$$
\begin{eqnarray}
\frac{f_x}{dv} &=& \left(\frac{\partial \tau_{xx}}{\partial x} + \frac{\partial \tau_{yx}}{\partial y} + \frac{\partial \tau_{zx}}{\partial z}\right) \\\\
&=& \mu \frac{\partial}{\partial x}\left(\frac{\partial v_x}{\partial x} + \frac{\partial v_x}{\partial x} \right) + \mu \frac{\partial}{\partial y}\left(\frac{\partial v_y}{\partial x} + \frac{\partial v_x}{\partial y} \right) + \mu \frac{\partial}{\partial z}\left(\frac{\partial v_x}{\partial x} + \frac{\partial v_x}{\partial z} \right) \\\\
&=& \mu \left(\frac{\partial^2 v_x}{\partial x^2} + \frac{\partial^2 v_x}{\partial y^2} + \frac{\partial^2 v_z}{\partial z^2} \right) + \mu \frac{\partial}{\partial x}\left(\frac{\partial v_x}{\partial x} + \frac{\partial v_y}{\partial y} + \frac{\partial v_z}{\partial z} \right) \\\\
&=& \left( \mu \nabla^2 \mathbf{v} \right)_x
\end{eqnarray}
$$

, where $dv = dxdydz$. Similarly, we can easily show that $f_y/dv$ and $f_z/dv$ are $\left(\mu \nabla^2 \mathbf{v} \right)_y$ and $\left(\mu \nabla^2 \mathbf{v} \right)_z$, respectively.



## Navier-Stokes Equation

Assuming that the velocity of the volume element, $dv$ is $\mathbf{v}$, the acceleration is calculated by the material derivative of $\mathbf{v}$ as:
$$
\frac{D\mathbf{v}}{Dt} = \left(\frac{\partial \mathbf v}{\partial t} + (\mathbf{v} \cdot \nabla)\mathbf{v} \right) \tag{6}
$$
The total mass of this volume element is $\rho dv$, and the total force acting on $dv$ consists of the pressure- and viscosity terms. Consequently, we obtain the Navier-Stokes equation:
$$
\rho dv \left(\frac{\partial \mathbf v}{\partial t} + (\mathbf v \cdot \nabla)\mathbf v \right) = \left(-\nabla p + \mu \nabla^2 \mathbf v \right)dv. \tag{7}
$$

