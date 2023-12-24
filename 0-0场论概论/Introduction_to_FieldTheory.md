# Overview of Field Theory

## 0 Definition of a Field

"A Field":

Describes a physical quantity in a certain space at a given moment. Due to the existence of both vector and scalar quantities, we naturally have "vector fields" and "scalar fields."

Scalar Field:

$$ u = u(x, y, z, t) $$

$$ \text{Also written as: } u = u(\vec{r}, t) $$

Vector Field:

$$ \vec{F} = \vec{F}(x, t, z, t) $$

$$ \text{Also written as: } \vec{F} = \vec{F}(\vec{r}, t) $$

In the Cartesian coordinate system, we often represent it as:

$$ \vec{F} = P(x, y, z, t)\vec{i} + Q(x, y, z, t)\vec{j} + R(x, y, z, t)\vec{k} $$

We often focus on discussing static fields, i.e., when ${t\equiv C}$.

$$ \begin{cases}
  \text{Scalar Field: } u = u(x, y, z) \\
  \text{Vector Field: } \vec{F} = P\vec{i} + Q\vec{j} + R\vec{k}
\end{cases} $$

To describe the properties of a field, we will discuss 1. Directional Derivatives & Gradient 2. Flux & Divergence 3. Circulation & Curl.

## 1 Directional Derivatives and Gradient of a Scalar Field

### 1-1 Directional Derivatives

**Directional derivatives are used to describe how a scalar field changes along any direction.**

$$ \left. \frac{\partial f}{\partial l} \right|_{\left( x_0, y_0 \right)} \xlongequal{def} \lim_{\Delta l\rightarrow 0} \frac{u\left( x + \Delta l\cos \theta, y + \Delta l\cos \beta \right) - u\left( x, y \right)}{\Delta l} $$

$$ = \frac{\partial u}{\partial x}\cos \theta + \frac{\partial u}{\partial y}\cos \beta = \left( \nabla u \right) \cdot \vec{e}_l $$

Providing an intuitive geometric representation:

Proof:
![](Pasted%20image%2020230924140736.png)

$$
\frac{\partial u}{\partial l}
=\frac{dz}{dl}=\frac{dz_x+dz_y}{dl}
=\frac{\frac{\partial u}{\partial x}dx+\frac{\partial u}{\partial y}dy}{dl}
=\frac{\partial u}{\partial x}\frac{d x}{d l}+\frac{\partial u}{\partial x}\frac{d y}{d l}
=\frac{\partial u}{\partial x}\cos\theta+\frac{\partial u}{\partial y}\cos\beta
$$

This formula can be extended to higher dimensions.

### 1-2 Gradient

**We want to know in which direction the directional derivative is maximized and what its maximum value is.**

This is clearly a vector problem, and we will provide a definition now and a proof later.

$$ \text{grad}u \xlongequal{def} \frac{\partial u}{\partial x}\vec{i} + \frac{\partial u}{\partial y}\vec{j} + \frac{\partial u}{\partial z}\vec{k} $$

We want to know the direction in which the derivative is maximized. It seems that this linear structure can be expressed as the dot product of two vectors:

$$(\frac{\partial u}{\partial x},\frac{\partial u}{\partial y},\frac{\partial u}{\partial z})(\cos \theta,\cos \beta,\cos \gamma)=(\nabla u)\cdot \vec{e_l}=|\nabla u|\cdot|\vec{e_l}|\cos(\nabla u,\vec{e_l})=|\nabla u|\cos(\nabla u,\vec{e_l})$$

At a fixed point, $|\nabla u|$ is a constant, so the maximum value is obtained when $\nabla u$ and $\vec{e_l}$ are aligned, i.e., $\cos(\nabla u,\vec{e_l})=1$. Thus, we determine the **direction**: $\vec{e_l}$ is aligned, and we determine the **magnitude**: $|\nabla u|$. Therefore, the gradient is defined as:

$$ \text{grad}u \xlongequal{def} \frac{\partial u}{\partial x}\vec{i} + \frac{\partial u}{\partial y}\vec{j} + \frac{\partial u}{\partial z}\vec{k} = \nabla u $$

## 2 Flux and Divergence of a Vector Field

### 2-1 Flux of a Vector Field

**Describes the quantity passing through a surface in a vector field at a specific location in space.**

$$\varPhi = \iint\limits_{S}\vec{F}\cdot\mathrm{d}\vec{S}$$

In a three-dimensional Cartesian coordinate system:

$$\underset{\Sigma}{\iint}\vec{F}\cdot d\vec{S}=\underset{\Sigma}{\iint}P(x,y,z)dydz+Q(x,y,z)dxdz+R(x,y,z)dxdy$$

Taking only the $x$ direction:

$$\underset{D_{xy}}{\iint}P(x,y,z)dxdy$$

### 2-2 Divergence of a Vector Field

**Describes the rate of change of flux with respect to volume, reflecting the "strength of the source."**

We define divergence as:

$$\text{div}\vec{F} = \lim_{\Omega\to M}\frac{\iint\limits_{S}\vec{F}\cdot\mathrm{d}\vec{S}}{V}$$

Where $\Omega\to M$ represents the volume shrinking to a point M, i.e., $\Delta V \to 0$.

In a three-dimensional Cartesian coordinate system, we have the following formula:

$$\text{div}\vec{F}=\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}$$

Proof:
In a three-dimensional Cartesian coordinate system, there are three directions, and for a closed surface, it passes through six faces.

$$\varPhi = [\underset{\text{top}}{\iint} + \underset{\text{bottom}}{\iint} + \underset{\text{left}}{\iint} + \underset{\text{right}}{\iint} + \underset{\text{front}}{\iint} + \underset{\text{back}}{\iint}]\vec{F}\cdot d\vec{S}$$

Let's consider only the $x$ direction for now:

$$\underset{\text{front}}{\iint}\vec{F}\cdot d\vec{S}\approx P(x+\Delta x/2,y,z)\Delta y\Delta z$$
$$\underset{\text{back}}{\iint}\vec{F}\cdot d\vec{S}\approx -P(x-\Delta x/2,y,z)\Delta y\Delta z$$

Using Taylor expansion:

$$\begin{aligned}
F_{x}\Bigg(x+\frac{\Delta x}{2},y,z\Bigg)& =P(x,y,z)+\frac{\partial P(x,y,z)}{\partial x}\frac{\Delta x}{2}+\frac{1}{2}\frac{\partial^{2}P(x,y,z)}{\partial x^{^2}}\Bigg(\frac{\Delta x}{2}\Bigg)^{^2}+\cdots   \\
&\approx P(x,y,z)+\frac{\partial F_x(x,y,z)}{\partial x}\frac{\Delta x}2
\end{aligned}$$

This leads to:

$$\underset{\text{front}}{\iint}\vec{F}\cdot d\vec{S}\approx P(x,y,z)\Delta y\Delta z+\frac{\partial P(x,y,z)}{\partial x}\frac{\Delta x\Delta y\Delta z}{2}$$
$$\underset{\text{back}}{\iint}\vec{F}\cdot d\vec{S}\approx -P(x,y,z)\Delta y\Delta z+\frac{\partial P(x,y,z)}{\partial x}\frac{\Delta x\Delta y\Delta z}{2}$$

In summary, along the $x$ direction:

$$[\underset{\text{front}}{\iint}+\underset{\text{back}}{\iint}] \vec{F}\cdot d\vec{S}\approx \frac{\partial P(x,y,z)}{\partial x}\Delta x\Delta y\Delta z$$

Adding up for $x$, $y$, and $z$:

$$\oiint\limits_{S}\vec{F}\cdot\mathrm{d}\vec{S}\approx\left(\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}\right)\Delta x\Delta y\Delta z$$

So, we obtain the formula for divergence in Cartesian coordinates:

$$\text{div}\vec{F}=\lim_{\Delta V\to 0}\frac{\iint\limits_{S}\vec{F}\cdot\mathrm{d}\vec{S}}{\Delta V}=\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}=\nabla\cdot \vec{F}$$

### 2-3 Relationship between Flux and Divergence

**We often use Gauss's theorem to express the relationship between flux and divergence.**

$$\underset{\Omega}{\oiiint}(\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z})dV=\underset{\Sigma}{\iint}Pdydz+Qdxdz+Rdxdy$$

Shortened as:

$$\underset{\Omega}{\oiiint}\nabla \cdot \vec{F}dV = \underset{\Sigma}{\oiint}\vec{F}\cdot d\vec{S}$$

This equation shows that the **triple volume integral of divergence is equal to the flux through the closed surface**. The proof of Gauss's theorem is achieved by transforming the triple integral into a double integral.
