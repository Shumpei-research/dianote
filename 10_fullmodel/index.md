# Generalized diabolo model and analytical solution

## 1. Definitions and Preparations

### 1-1. Geometry

Let N diabolos on the string. We number the objects from left to right, left stick being 0 and right stick being N+1, diabolos being 1,...,N.
With these numberings, position $\boldsymbol{x_i} \: (i=0,...,N+1)$
 and their time-differentials velocity $\boldsymbol{u_i}$ and acceleration $\boldsymbol{a_i}$ are defined.

Let $\boldsymbol{l_i}$ the string segment vector between $\boldsymbol{x_i, x_{i+1}}$, and $l_i$ the length of it.
Unit vector $\boldsymbol{e_i}$ is also defined

$$
\begin{align}
&\boldsymbol{l_i} := \boldsymbol{x_{i+1}} - \boldsymbol{x_i} \:(i=0,...,N) \\
&l_i := |\boldsymbol{l_i}| \\
&\boldsymbol{e_i} := \frac{\boldsymbol{l_i}}{l_i}
\end{align}
$$

Rotating coordinate system $(\boldsymbol{\alpha_i} , \boldsymbol{\beta_i})$ (unit vectors) is defined for each object as shown in the figure below.
Let $\phi_i$ the rotaion angle.
$\phi_i$ is determined so that $\boldsymbol{\beta_i}$ is the bisector of two adjacent string segments.
Let $\theta_i$ the angle between two adjacent string segments.
$\phi_0, \phi_{N+1}$ at the sticks are defined so that $\boldsymbol{\beta_0},\boldsymbol{\beta_{N+1}}$ is parallel to the terminal string segment.

![fig10_1](./fig/fig-01.png)

Here, these angles have a redundancy of $2n\pi$ .
This redundancy is utilized to naturally express the string wrapping around the axes of diabolos.
In the simplest situation where all the diabolos are simply sitting on the string without wrapping, 
$\theta_i$ are defined so that $0 \le\theta_i < 2\pi$ .
In this case, especially $\pi \le \theta_i < 2\pi$ , since diabolos are not flying.
Additionally, define so that $0 \le \phi_0 < 2\pi$ .
Then $\phi_i \: (i=1,...,N+1)$ is intuitively defined as shown below so that you tilt the coordinates as you go from left to right.

$$
\begin{equation}
\begin{gathered}
\phi_i := \phi_{i-1} + \frac{\theta_{i-1} - \pi}{2} + \frac{\theta_{i} - \pi}{2}\\
(\theta_0 , \theta_{N+1} := 0 \text{ just for simplicity})
\end{gathered}
\end{equation}
$$

In the time-dependent context, $0 \le \phi_0 < 2\pi$ at time 0.
Then all angles are allowed to change continuously.
The wrapping is introduced by the extension of this simplest situation.
As you wrap a diabolo i, you increase $\theta_i$ from $0-2\pi$ regime to $2\pi - 4\pi$ regime.
Also $\phi_i$ increase by about $\pi$.

To provide the language, "knot degree" $k_i$ is defined:
0 for zero-wrapped state, 
1 for single-wrapped state,
2 for double-wrapped state,
and so on.
Also k is
-1 for zero-wrapped recaptured state, 
-2 for single-wrapped recaptured state,
-3 for double-wrapped recaptured state,
and so on.

Accordingly, redundancy of $\theta_i$ can be determined based on the knot degree, $2k_i\pi \le \theta_i < 2(k_i+1)\pi$

Note that $-\pi \le \theta_i < \pi$ means that the diabolo would be flying and is not physically allowed.
This "flying regime" might provide useful boundaries 
when the diabolos actually detach from and attach to the string.
Now that all $\theta_i$ and $\phi_0$ is non-arbitrarily defined, 
$\phi_i$ is also non-arbitrarily defined by the definition above.

We define another angle $\psi_i$ as a simple derivative of $\theta_i$, 
which will be useful to simplify the equations later.

$$
\begin{gather}
\psi_i := \frac{\theta_i - \pi}{2}\\
\psi_0, \psi_{N+1} := - \frac{\pi}{2}\\
\end{gather}
$$

We adopted the system where we first define $\phi_0$ and $\theta_i$ , 
then secondarily defined $\phi_i$. 
But it is also possible to first define $\phi_{0,...,N}$ , 
then secondarily define $\phi_{N+1}$ and $\theta_i$.
Also $\theta$ and $\psi$ is completely interchangeable.
There is some arbitrariness in what is chosen for the state variable.


$\boldsymbol{u_i, a_i}$ can be expressed using the rotating coordinate system $(\boldsymbol{\alpha_i}, \boldsymbol{\beta_i}) \: (i=0,...,N+1)$ .

$$
\begin{gather}
\boldsymbol{u_i} = 
u_i^{\alpha}\boldsymbol{\alpha_i} + u_i^{\beta}\boldsymbol{\beta_i} =
\begin{pmatrix} u_{i}^{\alpha} \\ u_{i}^{\beta} \end{pmatrix} =
\begin{bmatrix}
    \cos{\phi_i} & -\sin{\phi_i} \\
    \sin{\phi_i} & \cos{\phi_i}
\end{bmatrix} 
\begin{pmatrix} u_{i}^{x} \\ u_{i}^{y} \end{pmatrix} \\
\boldsymbol{a_i} = 
a_i^{\alpha}\boldsymbol{\alpha_i} + a_i^{\beta}\boldsymbol{\beta_i} =
\begin{pmatrix} a_{i}^{\alpha} \\ a_{i}^{\beta} \end{pmatrix} =
\begin{bmatrix}
    \cos{\phi_i} & -\sin{\phi_i} \\
    \sin{\phi_i} & \cos{\phi_i}
\end{bmatrix} 
\begin{pmatrix} a_{i}^{x} \\ a_{i}^{y} \end{pmatrix} \\
\end{gather}
$$

Given the above definitions, the interchangeable expressions of the system are obtained:

$$
\begin{align}
(\boldsymbol{x}_i, k_{1,...,N}, u_i^{x,y}) \Leftrightarrow (\boldsymbol{x}_0, l_{0,...,N}, \phi_0, \theta_{1,...,N}, u_i^{\alpha,\beta})
\end{align}
$$

The left side is a more intuitive expression with Cartesian coordinates, 
which will be useful when dealing with real data, or visualizing simulation results.
The right side is useful when dealing with analytical solutions.

Here are simple time-derivative that are geometrically derived.

$$
\begin{gather}
\begin{pmatrix}
    \dot{u_i^\alpha} \\ \dot{u_i^\beta}
\end{pmatrix}
=\begin{pmatrix}
    a_i^\alpha - u_i^\beta \dot{\phi_i} \\
    a_i^\beta + u_i^\alpha \dot{\phi_i}
\end{pmatrix} \\
\dot{l_i} = - u_{i}^\alpha \cos \psi_{i}
-u_{i}^\beta \sin \psi_{i}
+u_{i+1}^\alpha \cos \psi_{i+1}
-u_{i+1}^\beta \sin \psi_{i+1} \\
\begin{gathered}
\dot{\phi_i} = 
\frac{1}{2}(
\frac{
u_{i+1}^\alpha \sin\psi_{i+1} +
u_{i+1}^\beta \cos\psi_{i+1} +
u_{i}^\alpha \sin \psi_{i} -
u_{i}^\beta \cos \psi_{i}
}
{l_{i}} \\+
\frac{
u_{i}^\alpha \sin\psi_{i} +
u_{i}^\beta \cos\psi_{i} +
u_{i-1}^\alpha \sin \psi_{i-1} -
u_{i-1}^\beta \cos \psi_{i-1}
}
{l_{i-1}}
)
\end{gathered} \\
\dot{\phi_0} = 
\frac{
u_{1}^\alpha \sin\psi_{1} +
u_{1}^\beta \cos\psi_{1} -
u_{0}^\alpha 
}
{l_{0}} 
\\
\dot{\phi}_{N+1} = 
\frac{
u_{N}^\alpha \sin\psi_{N} -
u_{N}^\beta \cos\psi_{N} -
u_{N+1}^\alpha 
}
{l_{N}} 
\\
\begin{gathered}
\dot{\theta_i} = 
(
\frac{
u_{i+1}^\alpha \sin\psi_{i+1} +
u_{i+1}^\beta \cos\psi_{i+1} +
u_{i}^\alpha \sin \psi_{i} -
u_{i}^\beta \cos \psi_{i}
}
{l_{i}} \\-
\frac{
u_{i}^\alpha \sin\psi_{i} +
u_{i}^\beta \cos\psi_{i} +
u_{i-1}^\alpha \sin \psi_{i-1} -
u_{i-1}^\beta \cos \psi_{i-1}
}
{l_{i-1}}
)
\end{gathered}\\
\dot{\psi_i} = \frac{\dot{\theta_i}}{2}
\end{gather}
$$

### 1-2 Frictions

One of the forces is the string tension.
Due to frictions at diabolos, tension is different among string segments.
Thus, the tension is defined for each string segment as $T_i$ .
Tension vector is defined as

$$
\begin{align}
\boldsymbol{T_i} := T_i \boldsymbol{e_i}
\end{align}
$$

In order to handle the frictions, rotation of diabolo is introduced.
Let $r$ the radius of diabolo axis,
$I$ the rotational inertia,
and $m$ the mass of diabolo.
Then let $\omega_i$ the angular velocity of diabolo $i$, positive value of which means the rotation from left to right (clockwise).
The surface velocity of the axis is $w_i = r\omega_i$ .
Let $J$ the normalized rotational inertia (see below).
The surface-integrated friction is equal to the loss of string tension $S_i = T_{i-1} - T_{i}$ .
In the context of solving the system behavior, we only need $w$ and $J$ rather than $\omega, r, I$.
With simple rigid-body mechanics,

$$
\begin{align}
J := \frac{I}{mr^2} \\
I\dot{\omega_i} = rS_i \\
\text{Thus, }\dot{w_i} = \frac{S_i}{mJ}
\end{align}
$$

If you account for aerodynamic drag $D>0$,
so that the rotational velocity is not accelerated limitlessly, 

$$
\begin{align}
\dot{w_i} = \frac{S_i}{mJ} - D(w_i)
\end{align}
$$

Physically, the friction occurs at the interface of axle surface and the string.
Thus it should be determined by the relative speed of axle surface against the string.
This means the comparison between $w_i$ and the speed of diabolo movement against the string.
The latter is equal to the change in the summed string segment lengths on the left side of a given diabolo.
Then, the relative volocity $w_i'$ is,

$$
\begin{equation}
\begin{gathered}
w_i' := w_i - \sum_{j=0}^{i-1}{\dot{l_j}} \\
=w_i - (
u_0^\beta + u_i^{\alpha} \cos \psi_i - u_i^{\beta} \sin \psi_i -
2\sum_{j=1}^{i-1} u_j^{\beta} \sin \psi_j
) 
\end{gathered}
\end{equation}
$$

Here, the term $\dot{\phi_i}r$ should also be included if rigorous 
(imagine you spin the entire system without any other motion).
But this term is practically very small, 
and can be ignored as a limit case of $r \rightarrow 0$.

The direction of friction is determined by the sign of $w_i'$,
here refered to as "acceleration state",
which can take "accelerating" state or "decelerating" state.

$$
\begin{cases}
\text{accelerating if } w_i' < 0\\
\text{decelerating if } w_i' > 0\\
\end{cases}
$$

In the linear friction regime, the friction is determined by 
friction coefficient $c$, 
wrapping angle $\theta'$, 
and the acceleration state.
The effective friction coefficient $c_i'$ is introduced to simplify the expression. 
With capstan equation,

$$
\begin{align}
\theta' &= 
    \begin{cases}
        \theta - \pi & (\theta >\pi)\\
        \theta + \pi & (\theta <-\pi)\\
    \end{cases} \\
c_i'(w_i') &:= 
    \begin{cases}
        -c &  w_i'<0 \\
        c  &  w_i'>0 \\
    \end{cases} \\
T_i &= T_{i-1} \times e^{c_i' \theta_i'}
\end{align}
$$

Here, the effective friction coefficient becomes a step function, ignoring the zero-velocity condition. 
Modifying $c_i'(w_i')$, such that it is zero when decelerating, easily accounts for bearing diabolos.
Additionally, this implies the possibility of extending to generalized continuous function, such as $c_i'(w_i') \approx \tanh$. 
And the step function would be represented as a certain limit case.

In a little bit more generalized linear approximation, 
tension ratio is determined by a function f:

$$
\begin{equation}
T_i = T_{i-1}  \times f(w_i',\theta_i')
\end{equation}
$$

Further, when the friction is not assumed linear, 
$f$ needs to be

$$
\begin{equation}
T_i = f(T_{i-1} ; w_i',\theta_i')
\end{equation}
$$

Only the linear regime is considered in the following.

### 1-3. Equations of motions and constraints
Suppose the system where the input is the force applied from hands to sticks. 
Let $\boldsymbol{F_0, F_{N+1}}$ the force applied to each stick. Let $M$ the mass of a stick. 
Let $\boldsymbol{g}$ the standard acceleration of gravity.
Then the equations of motions are,

$$
\begin{align}
M\boldsymbol{a_0}     &= \boldsymbol{T_0} + M\boldsymbol{g} + \boldsymbol{F_0} \\
M\boldsymbol{a_{N+1}} &= -\boldsymbol{T_N} + M\boldsymbol{g} + \boldsymbol{F_{N+1}} \\
m\boldsymbol{a_i}     &= \boldsymbol{T_i} - \boldsymbol{T_{i-1}} + m\boldsymbol{g}
\end{align}
$$

The constraint of the system is that the total length of string is a constant. 
Let $L$ the total length of string.
Then,

$$
\begin{align}
&L(t) = \sum_{i=0}^{N} l_i = L\\
&\Leftrightarrow \dot{L} = \sum_{i=0}^{N} \dot{l_i}  = 0 \text{ and } L(t=0)=L\\
&\Leftrightarrow \ddot{L} = \sum_{i=0}^{N} \ddot{l_i}  = 0\text{ and } L(t=0)=L\text{ and } \dot{L}(t=0)=0\\
\end{align}
$$

The goal is to solve these equations to get $\boldsymbol{a}$ as a function of $\boldsymbol{F}$.
Once $\boldsymbol{a}$ is obtained, 
the differential equations for the state of system $(\boldsymbol{x,u})$ are set, 
ready for numerical calculations.
($w$ should also be included, 
but they can be easily derived as secondary results.)


## 2. Solution

### 2-1. Deriviation of Accelerations

First, tensions are compressed to $T_0$ .

$$
\begin{gather}
T_i = T_0 \times d_i \\
d_i := \prod_{j=1}^{i} f(w_j',\theta_i') = \exp(\sum_{j=1}^{i} c_j' \theta_j') \;\;\; (d_0 := 1)
\end{gather}
$$

The constraint is solved geometrically,

$$
\begin{gather}
\dot{L} = \sum_{i=0}^{N} \dot{l_i}
= u_0^\beta + u_{N+1}^\beta - 2\sum_{i=1}^{N} u_i^\beta \sin\psi_i 
=0\\
\ddot{L} = (a_0^\beta + a_{N+1}^\beta) + 
(u_0^\alpha \dot{\phi_0} +
u_{N+1}^\alpha \dot{\phi_{N+1}} ) -
2\sum_{i=1}^{N} (
a_i^{\beta}\sin \psi_i +
u_i^{\alpha} \dot{\phi_i} \sin \psi_i +
u_i^\beta \frac{\dot{\theta_i}}{2} \cos \psi_i)
=0
\end{gather}
$$

The equations of motions are rewritten in rotating coordinates,

$$
\begin{gather}
\begin{pmatrix}
a_0^{\alpha} \\ a_0^{\beta}
\end{pmatrix}
=\frac{1}{M}\begin{pmatrix}
0 \\ -T_0
\end{pmatrix}
-g\begin{pmatrix}
\sin \phi_0 \\ \cos \phi_0
\end{pmatrix}
+\frac{1}{M}
\begin{pmatrix}
F_0^\alpha \\ F_0^\beta
\end{pmatrix} \\
\begin{pmatrix}
a_{N+1}^{\alpha} \\ a_{N+1}^{\beta}
\end{pmatrix}
=\frac{1}{M}\begin{pmatrix}
0 \\ -T_{0} d_{N}
\end{pmatrix}
-g\begin{pmatrix}
\sin \phi_{N+1} \\ \cos \phi_{N+1}
\end{pmatrix}
+\frac{1}{M}\begin{pmatrix}
F_{N+1}^\alpha \\ F_{N+1}^\beta
\end{pmatrix} \\
\begin{pmatrix}
a_{i}^{\alpha} \\ a_{i}^{\beta}
\end{pmatrix}
=\frac{T_0}{m} \begin{pmatrix}
(d_{i} - d_{i-1}) \cos\psi_i \\ (d_{i} + d_{i-1}) \sin\psi_i
\end{pmatrix}
-g\begin{pmatrix}
\sin \phi_{i} \\ \cos \phi_{i}
\end{pmatrix}
\; (i=1,...,N)
\end{gather}
$$


With this,

$$
\begin{equation}
\begin{aligned}
\ddot{L} = &(a_0^\beta + a_{N+1}^\beta) + 
(u_0^\alpha \dot{\phi_0} +
u_{N+1}^\alpha \dot{\phi_{N+1}} ) \\
&-2\sum_{i=1}^{N} (
(
    \frac{T_0}{m} (d_i + d_{i-1})\sin\psi_i)
    -g\cos\phi_i
)
\sin \psi_i +
u_i^{\alpha} \dot{\phi_i} \sin \psi_i +
u_i^\beta \frac{\dot{\theta_i}}{2} \cos \psi_i) \\
= &(a_0^\beta + a_{N+1}^\beta) + 
(u_0^\alpha \dot{\phi_0} +
u_{N+1}^\alpha \dot{\phi_{N+1}} ) \\
&-2\sum_{i=1}^{N}
(-g\cos\phi_i\sin\psi_i + u_i^\alpha \dot{\phi_i} \sin\psi_i + u_i^\beta \frac{\dot{\theta_i}}{2}\cos\psi_i)
-\frac{2T_0}{m}\sum_{i=1}^{N}
(d_i + d_{i-1})\sin^2\psi_i  \\
&= 0
\end{aligned}
\end{equation}
$$

Then,

$$
\begin{equation}
\begin{gathered}
T_0 = 
(a_0^\beta + a_{N+1}^\beta) \frac{1}
{\frac{2}{m}\sum_{i=1}^{N}
(d_i + d_{i-1})\sin^2\psi_i} \\
+\frac{
    (u_0^\alpha \dot{\phi_0} +
    u_{N+1}^\alpha \dot{\phi_{N+1}} )
    -2\sum_{i=1}^{N}
    (-g\cos\phi_i\sin\psi_i + u_i^\alpha \dot{\phi_i} \sin\psi_i + u_i^\beta \frac{\dot{\theta_i}}{2}\cos\psi_i)
}
{\frac{2}{m}\sum_{i=1}^{N}
(d_i + d_{i-1})\sin^2\psi_i} \\
=(a_0^\beta + a_{N+1}^\beta)A_1 + A_2
\end{gathered}
\end{equation}
$$

Both $A_1,A_2$ are determined by state variables,

$$
\begin{gather}
A_1 = A_1(w_{0,...,N},\theta_{1,...,N},u_{0,...,N+1}^\beta,u_{1,...,N}^{\alpha}) \\
A_2 = A_2(w_{0,...,N},\theta_{1,...,N},l_{0,...,N},u_{0,...,N+1}^{\alpha,\beta})
\end{gather}
$$

Lastly,

$$
\begin{gather}
\begin{cases}
a_0^\beta = 
-\frac{1}{M}((a_0^\beta + a_{N+1}^\beta)A_1 + A_2) - 
g\cos\phi_0 + 
\frac{1}{M}F_0^{\beta}
\\
a_{N+1}^\beta = 
-\frac{1}{M} d_{N} ((a_0^\beta + a_{N+1}^\beta)A_1 + A_2) - 
g\cos\phi_{N+1} + 
\frac{1}{M}F_{N+1}^{\beta}
\end{cases} \\
(a_0^{\beta} + a_{N+1}^{\beta}) =
-\frac{A_1}{M}(1+d_N) (a_0^{\beta} + a_{N+1}^{\beta})
+\frac{A_2}{M}(1+d_N)
-g(\cos \phi_0 + \cos \phi_{N+1})
+\frac{F_0^\beta + F_{N+1}^\beta}{M} \\
(a_0^{\beta} + a_{N+1}^{\beta}) = 
\frac{(F_0^\beta + F_{N+1}^\beta) }
{M + A_1(1+d_N)} +
\frac{A_2(1+d_N) - Mg (\cos \phi_0 + \cos \phi_{N+1})}
{M + A_1(1+d_N)} \\
= A_3(F_0^\beta + F_{N+1}^\beta) + A_4 \\
\begin{cases}
a_0^\beta = 
-\frac{1}{M}((A_3(F_0^\beta + F_{N+1}^\beta) + A_4)A_1 + A_2) - 
g\cos\phi_0 + 
\frac{1}{M}F_0^{\beta}
\\
a_{N+1}^\beta = 
-\frac{1}{M} d_{N} ((A_3(F_0^\beta + F_{N+1}^\beta) + A_4)A_1 + A_2) - 
g\cos\phi_{N+1} + 
\frac{1}{M}F_{N+1}^{\beta}
\end{cases} \\
\begin{cases}
a_0^\beta = 
\frac{1 - A_1 A_3}{M} F_0^\beta - \frac{A_1 A_3}{M}F_{N+1}^\beta
-(g\cos\phi_0
+\frac{A_1 A_4 + A_2}{M})
\\
a_{N+1}^\beta = 
-\frac{d_N A_1 A_3}{M} F_0^\beta + \frac{1 - d_N A_1 A_3}{M}F_{N+1}^\beta
-(g\cos\phi_{N+1}
+d_N\frac{A_1 A_4 + A_2}{M})
\end{cases} \\
A_5 := A_1 A_3 \\
A_6 := A_1 A_4 + A_2 \\
\begin{pmatrix}
a_0^\beta \\ a_{N+1}^\beta
\end{pmatrix}
= \begin{bmatrix}
\frac{1 - A_5}{M}  & - \frac{A_5}{M} \\
-\frac{d_N A_5}{M} & \frac{1 - d_N A_5}{M}
\end{bmatrix}
\begin{pmatrix}
F_0^\beta \\ F_{N+1}^\beta
\end{pmatrix}
+\begin{pmatrix}
-(g\cos\phi_0 +\frac{A_6}{M}) \\
-(g\cos\phi_{N+1} +d_N\frac{A_6}{M})
\end{pmatrix} \\
\end{gather}
$$

Additionally,

$$
\begin{gather}
T_0 = A_5(F_0^\beta + F_{N+1}^\beta) + A_6 \\
\begin{cases}
a_0^\alpha = \frac{1}{M} F_0^\alpha -g\sin\phi_0 \\
a_{N+1}^\alpha =\frac{1}{M} F_{N+1}^\alpha -g\sin\phi_{N+1}   
\end{cases} \\
\begin{pmatrix}
a_{i}^{\alpha} \\ a_{i}^{\beta}
\end{pmatrix}=
\frac{A_5}{m} 
\begin{pmatrix}
(d_{i} - d_{i-1}) \cos\psi_i \\ (d_{i} + d_{i-1}) \sin\psi_i
\end{pmatrix}
(F_0^\beta + F_{N+1}^\beta)+
(
\frac{A_6}{m}
\begin{pmatrix}
(d_{i} - d_{i-1}) \cos\psi_i \\ (d_{i} + d_{i-1}) \sin\psi_i
\end{pmatrix}
-g\begin{pmatrix}
\sin \phi_{i} \\ \cos \phi_{i}
\end{pmatrix}
)\\
\end{gather}
$$

Therefore,

$$
\begin{gather}
\begin{pmatrix}
a_0^\alpha \\ 
a_0^\beta\\ 
a_{N+1}^\alpha \\ 
a_{N+1}^\beta \\ 
a_i^\alpha\\ a_i^\beta \\ 
...\\ ... \\ 
\end{pmatrix}
= \begin{bmatrix}
\frac{1}{M} & 0 & 0 & 0\\
0 & \frac{1 - A_5}{M} & 0 & - \frac{A_5}{M} \\
0 & 0 & \frac{1}{M} & 0\\
0 & -\frac{d_N A_5}{M} & 0 & \frac{1 - d_N A_5}{M}\\
0 & \frac{A_5 (d_{i} - d_{i-1}) \cos\psi_i }{m} & 0 & \frac{A_5 (d_{i} - d_{i-1}) \cos\psi_i }{m} \\
0 & \frac{A_5 (d_{i} + d_{i-1}) \sin\psi_i }{m} & 0 & \frac{A_5 (d_{i} + d_{i-1}) \sin\psi_i }{m} \\
... \\
... \\
\end{bmatrix}
\begin{pmatrix}
F_0^\alpha \\ 
F_0^\beta \\ 
F_{N+1}^\alpha \\
F_{N+1}^\beta
\end{pmatrix}
+\begin{pmatrix}
-g\sin\phi_0\\
-(g\cos\phi_0 +\frac{A_6}{M}) \\
-g\sin\phi_{N+1}\\
-(g\cos\phi_{N+1} +d_N\frac{A_6}{M})\\
\frac{A_6}{m}(d_{i} - d_{i-1}) \cos\psi_i -g \sin \phi_{i} \\
\frac{A_6}{m}(d_{i} + d_{i-1}) \sin\psi_i -g \cos \phi_{i} \\
...\\
...\\
\end{pmatrix}
\end{gather}
$$

Adding the equations for the rotational motions will complete the solution,

$$
\begin{gather}
\dot{w_i} = \frac{S_i}{mJ} - D(w_i) = \frac{- T_0(d_{i}-d_{i-1})}{mJ} -D(w_i) \\
= - \frac{A_5 (d_i - d_{i-1})}{mJ}(F_0^\beta+F_{N+1}^\beta) - 
(\frac{A_6(d_i-d_{i-1})}{mJ} + D(w_i))
\end{gather}
$$

There are some physical consequences we can see. 
The forces diabolos feel are only the tension and gravity.
And the ratio of each tension is predetermined by the state.
Only $T_0$, the magnitude of tensions can be modulated by input forces.
Thus, only one degree of freedom, $F_0^\beta + F_{N+1}^\beta$ is used for all the diabolos.
The direction of $\boldsymbol{a}_i$ is predetermined and cannot be modulated.
The stick movements in $\beta$ direction are determined by another degree of freedom,
say $F_0^\beta - F_{N+1}^\beta$.
The stick movements in $\alpha$ direction are affected only by gravity and input forces.
Thus, these movements are independent and uses $F_0^\alpha, F_{N+1}^\alpha$ each,
freely controlable.

A useful conversion of the solution is, using two-dimensional rotation matrix $\boldsymbol{R}$,

$$
\begin{gather}
\boldsymbol{B}
:= \begin{bmatrix}
\frac{1}{M} & 0 & 0 & 0\\
0 & \frac{1 - A_5}{M} & 0 & - \frac{A_5}{M} \\
0 & 0 & \frac{1}{M} & 0\\
0 & -\frac{d_N A_5}{M} & 0 & \frac{1 - d_N A_5}{M}
\end{bmatrix} \\
\det(\boldsymbol{B}) =
M^{-4} (1-(1+d_N)A_5) =
M^{-4} \frac{1}{1 + \frac{A_1(1+d_N)}{M}}
\ne 0 \text{ (except special cases)}
\\
\boldsymbol{C}
:= \begin{pmatrix}
-g\sin\phi_0\\
-(g\cos\phi_0 +\frac{A_6}{M}) \\
-g\sin\phi_{N+1}\\
-(g\cos\phi_{N+1} +d_N\frac{A_6}{M})
\end{pmatrix} \\
\boldsymbol{R}_2 (a,b) := 
\begin{bmatrix}
\boldsymbol{R}(a) & 0 \\
0 & \boldsymbol{R}(b)
\end{bmatrix}\\
\boldsymbol{B'} :=
\boldsymbol{R}_2^{-1}(\phi _0, \phi _{N+1})
\boldsymbol{B}
\boldsymbol{R}_2(\phi _0, \phi _{N+1})\\
\boldsymbol{C'} :=
\boldsymbol{R}_2^{-1}(\phi _0, \phi _{N+1})
\boldsymbol{C}
\end{gather}
$$

Then,

$$
\begin{gather}
\begin{pmatrix}
a_0^x \\ 
a_0^y\\ 
a_{N+1}^x \\ 
a_{N+1}^y
\end{pmatrix} =
\boldsymbol{B'}
\begin{pmatrix}
F_0^x \\ 
F_0^y \\ 
F_{N+1}^x \\
F_{N+1}^y
\end{pmatrix} +
\boldsymbol{C'} \\
\begin{pmatrix}
F_0^x \\ 
F_0^y \\ 
F_{N+1}^x \\
F_{N+1}^y
\end{pmatrix} =
\boldsymbol{B'}^{-1}
\begin{pmatrix}
a_0^x \\ 
a_0^y\\ 
a_{N+1}^x \\ 
a_{N+1}^y
\end{pmatrix} -
\boldsymbol{B'}^{-1}\boldsymbol{C'} \\
\end{gather}
$$

This means that the input forces and the acceleration of sticks are linearly convertible in a given state.
Suppose you simulate the system with input forces,
it may be difficult to find the proper $\boldsymbol{F}$ so that the objects move intuitively.
But it is also possible to use $\boldsymbol{a}_{0,N+1}$ as the input, 
and internally determine the necessary input forces,
which allows you to just intuitively move the sticks.

### 2-2 (Re-stating) Formula for Numerical Calculation

The system is expressed as:

$$
\begin{align}
\boldsymbol{X_0} (t): (\boldsymbol{x}_i, k_{1,...,N}, u_i^{x,y}, w_i) 
\Leftrightarrow 
\boldsymbol{X} (t): (\boldsymbol{x}_0, l_{0,...,N}, \phi_0, \theta_{1,...,N}, u_i^{\alpha,\beta}, w_i)
\end{align}
$$

with the parameters $(L, m, M, c, J, D)$ and a physical constant $g$.
We focus on $\boldsymbol{X} (t)$ since the conversion is easy. 
Due to constraints, the state variables can be reduced:

$$
\begin{gather}
\boldsymbol{X} (t): (\boldsymbol{x}_0, l_{0,...,N-1}, \phi_0, \theta_{1,...,N}, u_{0,...,N}^{\alpha,\beta}, u_{N+1}^\alpha, w_i)
\end{gather}
$$

And $l_N, u_{N+1}^\beta$ are determined by constraints.
The goal is to obtain the incremental time evolution for the given input:

$$
\begin{gather}
\boldsymbol{X} (t=t+dt) = \boldsymbol{X} (t=t) + dt \times \dot{\boldsymbol{X}} |_{t=t} \\
\dot{\boldsymbol{X}} |_{t=t} = \dot{\boldsymbol{X}} |_{t=t} (\boldsymbol{X}(t=t), \boldsymbol{F}(t=t)) \\
= (
    \dot{\boldsymbol{x_0}}, 
    \dot{l}_{0,...,N-1},
    \dot{\phi}_0, 
    \dot{\theta}_{1,...,N},
    \dot{u}_{0,...,N}^{\alpha,\beta},
    \dot{u}_{N+1}^\alpha,
    \dot{w_i}
)
\end{gather}
$$

Only from the state $\boldsymbol{X} (t=t)$, the following is determined as seen above.

$$
\begin{gather}
\boldsymbol{X} (t=t)
\Rightarrow
(
    \dot{\boldsymbol{x_0}}, 
    \dot{l}_{0,...,N-1},
    \dot{\phi}_0, 
    \dot{\theta}_{1,...,N},
) (t=t) \\
\dot{\boldsymbol{x}}_0 = \boldsymbol{R}(-\phi_0)(u_0^\alpha, u_0^\beta)^T \\
\dot{l_i} = - u_{i}^\alpha \cos \psi_{i}
-u_{i}^\beta \sin \psi_{i}
+u_{i+1}^\alpha \cos \psi_{i+1}
-u_{i+1}^\beta \sin \psi_{i+1} \\
\dot{\phi_0} = 
\frac{
u_{1}^\alpha \sin\psi_{1} +
u_{1}^\beta \cos\psi_{1} -
u_{0}^\alpha 
}{l_{0}}  \\
\begin{gathered}
\dot{\theta_i} = 
(
\frac{
u_{i+1}^\alpha \sin\psi_{i+1} +
u_{i+1}^\beta \cos\psi_{i+1} +
u_{i}^\alpha \sin \psi_{i} -
u_{i}^\beta \cos \psi_{i}
}
{l_{i}} \\-
\frac{
u_{i}^\alpha \sin\psi_{i} +
u_{i}^\beta \cos\psi_{i} +
u_{i-1}^\alpha \sin \psi_{i-1} -
u_{i-1}^\beta \cos \psi_{i-1}
}
{l_{i-1}}
)
\end{gathered}\\
\end{gather}
$$

With $\boldsymbol{X, F}$, the rotational accelerations $\dot{w}_i$ is determined,
and all the accelerations $a_i^{\alpha,\beta}$ is determined as seen above. 
Then, as we saw above, $\dot{u}_i^{\alpha,\beta}$ is easily obtained.

$$
\begin{gather}
\boldsymbol{X} (t=t), \boldsymbol{F} (t=t)
\Rightarrow
(
    \dot{u}_{0,...,N}^{\alpha,\beta},
    \dot{u}_{N+1}^\alpha,
    \dot{w_i}
) (t=t)\\
(
F_0^\alpha 
F_0^\beta 
F_{N+1}^\alpha
F_{N+1}^\beta
)^T = 
\boldsymbol{R}_2 (\phi_0, \phi_{N+1}) \boldsymbol{F}
\\
\dot{w_i}
= - \frac{A_5 (d_i - d_{i-1})}{mJ}(F_0^\beta+F_{N+1}^\beta) - 
(\frac{A_6(d_i-d_{i-1})}{mJ} + D(w_i))\\
\begin{pmatrix}
a_0^\alpha \\ 
a_0^\beta\\ 
a_{N+1}^\alpha \\ 
a_{N+1}^\beta \\ 
a_i^\alpha\\ a_i^\beta \\ 
...\\ ... \\ 
\end{pmatrix}
= \begin{bmatrix}
\frac{1}{M} & 0 & 0 & 0\\
0 & \frac{1 - A_5}{M} & 0 & - \frac{A_5}{M} \\
0 & 0 & \frac{1}{M} & 0\\
0 & -\frac{d_N A_5}{M} & 0 & \frac{1 - d_N A_5}{M}\\
0 & \frac{A_5 (d_{i} - d_{i-1}) \cos\psi_i }{m} & 0 & \frac{A_5 (d_{i} - d_{i-1}) \cos\psi_i }{m} \\
0 & \frac{A_5 (d_{i} + d_{i-1}) \sin\psi_i }{m} & 0 & \frac{A_5 (d_{i} + d_{i-1}) \sin\psi_i }{m} \\
... \\
... \\
\end{bmatrix}
\begin{pmatrix}
F_0^\alpha \\ 
F_0^\beta \\ 
F_{N+1}^\alpha \\
F_{N+1}^\beta
\end{pmatrix}
+\begin{pmatrix}
-g\sin\phi_0\\
-(g\cos\phi_0 +\frac{A_6}{M}) \\
-g\sin\phi_{N+1}\\
-(g\cos\phi_{N+1} +d_N\frac{A_6}{M})\\
\frac{A_6}{m}(d_{i} - d_{i-1}) \cos\psi_i -g \sin \phi_{i} \\
\frac{A_6}{m}(d_{i} + d_{i-1}) \sin\psi_i -g \cos \phi_{i} \\
...\\
...\\
\end{pmatrix} \\
\begin{pmatrix}
    \dot{u_i^\alpha} \\ \dot{u_i^\beta}
\end{pmatrix}
=\begin{pmatrix}
    a_i^\alpha - u_i^\beta \dot{\phi_i} \\
    a_i^\beta + u_i^\alpha \dot{\phi_i}
\end{pmatrix} \\
\end{gather}
$$

where

$$
\begin{gather}
\begin{gathered}
\phi_i := \phi_{i-1} + \frac{\theta_{i-1} - \pi}{2} + \frac{\theta_{i} - \pi}{2}\\
(\theta_0 , \theta_{N+1} := 0)
\end{gathered} \\
\psi_i := \frac{\theta_i - \pi}{2}\\
\begin{gathered}
\dot{\phi_i} = 
\frac{1}{2}(
\frac{
u_{i+1}^\alpha \sin\psi_{i+1} +
u_{i+1}^\beta \cos\psi_{i+1} +
u_{i}^\alpha \sin \psi_{i} -
u_{i}^\beta \cos \psi_{i}
}
{l_{i}} \\+
\frac{
u_{i}^\alpha \sin\psi_{i} +
u_{i}^\beta \cos\psi_{i} +
u_{i-1}^\alpha \sin \psi_{i-1} -
u_{i-1}^\beta \cos \psi_{i-1}
}
{l_{i-1}}
)
\end{gathered} \\
\dot{\phi}_{N+1} = 
\frac{
u_{N}^\alpha \sin\psi_{N} -
u_{N}^\beta \cos\psi_{N} -
u_{N+1}^\alpha 
}
{l_{N}} 
\\
w_i' := w_i - \sum_{j=0}^{i-1}{\dot{l_j}}
=w_i - (
u_0^\beta + u_i^{\alpha} \cos \psi_i - u_i^{\beta} \sin \psi_i -
2\sum_{j=1}^{i-1} u_j^{\beta} \sin \psi_j
)\\ 
\theta_i' := 
    \begin{cases}
        \theta_i - \pi & (\theta_i >\pi)\\
        \theta_i + \pi & (\theta_i <-\pi)\\
    \end{cases} \\
c_i'(w_i') := 
    \begin{cases}
        -c &  w_i'<0 \\
        c  &  w_i'>0 \\
    \end{cases} \\
d_i := \prod_{j=1}^{i} f(w_j',\theta_i') = \exp(\sum_{j=1}^{i} c_j' \theta_j') \;\;\; (d_0 := 1) \\
A' := \sum_{i=1}^{N} (d_i + d_{i-1})\sin^2 \psi_i\\
A'' := \sum_{i=1}^{N}
(-g\cos\phi_i\sin\psi_i + 
u_i^\alpha \dot{\phi_i} \sin\psi_i + 
u_i^\beta \frac{\dot{\theta_i}}{2}\cos\psi_i) \\
A_2 := \frac{m}{2A'}((u_0^\alpha \dot{\phi_0} +u_{N+1}^\alpha \dot{\phi_{N+1}} )-2A'')\\
A_5 := \frac{1}{(1+d_N) + \frac{2M}{m} A'} \\
A_6 :=
\frac{A_2 (\frac{2M}{m}A' + 2(1+d_N)) - Mg(\cos\phi_0 + \cos\phi_{N+1})}{\frac{2M}{m}A'+(1+d_N)} \\
\\\\\\
\end{gather}
$$

So far $D(w_i)$ has been treated as a general function for aerodynamic drag,
but in the simplest approximation of viscous drag,
$D(w_i) = D \times w_i$ with a constant $D$.