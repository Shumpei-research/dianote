# 1ディア 摩擦あり リリース有り

## 1. 摩擦の導入

$$
\begin{align}
(\boldsymbol{x}_{1}, \boldsymbol{x}_{2}, \boldsymbol{x}_{3}) &\Leftrightarrow (L, \Delta l, \phi_{3}, \theta, x_{3x}, x_{3y}) \dots \boldsymbol{X} \\
(\phi_{3}, \theta), (\boldsymbol{u}_1, \boldsymbol{u}_2, \boldsymbol{u}_3) &\Leftrightarrow (\phi_{3}, \theta), (U_{l}, \Delta u_{l}, U_{v}, \Delta u_{v}, u_{3l}, u_{3v}) \dots \boldsymbol{U} \\
(\phi_{3}, \theta),  (\boldsymbol{a}_1, \boldsymbol{a}_2, \boldsymbol{a}_3) &\Leftrightarrow  (\phi_{3}, \theta), (A_{l}, \Delta a_{l}, A_{v}, \Delta a_{v}, a_{3l}, a_{3v}) \dots \boldsymbol{A} \\
\end{align}
$$

$$
\begin{align}
L &= L_0 \; (constraint)\\
u_{3v} &= \frac{U_{v}}{\cos \theta} \; (constraint) \\
a_{3v} &= a_{3v}(\Delta l , \theta , U_{l} , \Delta u_{l} , U_{v} , u_{3l}, A_{v}) \; (constraint)\\
&= \frac{A_{v}}{\cos \theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} \\
&=
\frac{A_{v}}{\cos\theta} + \frac{2L}{\cos\theta \left( L^2 - \Delta l^2 \right)}
\left[
\left( u'_{l} + u'_{v} \right)^{2}-
2\left( \frac{L+\Delta l}{L} \right) u'_{l} u'_{v}
\right] \\
u'_{l} &:= u_{3l}\cos\theta-U_{l} = \frac{L \dot{\phi}_{3} + \Delta l \dot{\theta}}{2}\\
u'_{v} &:= u_{3v}\sin\theta - \Delta u_{l} = \frac{\Delta l \dot{\phi}_{3} + L \dot{\theta}}{2}\\
\end{align}
$$

$ x_1 $ を右手とする。(鏡写し)

$$
\begin{align}
a_{3l} &=  \frac{\sin\theta(T_2 - T_1)}{m} - g\sin\phi_{3} \\
a_{3v} &=  \frac{\cos\theta(T_1+T_2)}{m} - g\cdot \cos{\phi_3} \\
\theta' &:= \pi - 2\theta (\theta< \pi/2) \\
\theta' &:= 2\theta - 3\pi (\theta> 3\pi/2) \\
T_2 &= e^{-c\theta'}T_1 \; \left( \frac{\dot{\Delta l}}{2} > w \right) \\
T_1 &= e^{-c\theta'}T_2 \; \left( \frac{\dot{\Delta l}}{2} < w \right) \\
\dot{w} &= \frac{m(T_1 - T_2)}{R}
\end{align}
$$

スティックを質量Mの質点とみなすと、スティックリリース時には

$$
i = 1,2 \\
a_{il} = -g\sin\phi _i \\
a_{iv} = - \frac{T_i}{M} \\
$$

ただし

$$
a_{1l} = A_l + \Delta a_l \\
a_{2l} = A_l - \Delta a_l \\
a_{1v} = A_v + \Delta a_v \\
a_{2v} = A_v - \Delta a_v \\
$$


以上で拡張できた。L, c, R, m, M が道具固有の量。
スティックリリース時にはAvが未知量になり、a3vをa1vなどの方程式と連立して解く必要がある。1(右手)のみをリリースしている場合には、

