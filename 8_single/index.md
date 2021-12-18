# 1ディア 摩擦あり リリース有り

## 1. 摩擦の導入

紐長一定の束縛条件から導いた以下の関係式は、摩擦があっても常に成立する。

$$
\begin{align}
(\boldsymbol{x}_{1}, \boldsymbol{x}_{2}, \boldsymbol{x}_{3}) &\Leftrightarrow (L, \Delta l, \phi_{3}, \theta, x_{3x}, x_{3y}) \dots \boldsymbol{X} \\
(\phi_{3}, \theta), (\boldsymbol{u}_1, \boldsymbol{u}_2, \boldsymbol{u}_3) &\Leftrightarrow (\phi_{3}, \theta), (U_{l}, \Delta u_{l}, U_{v}, \Delta u_{v}, u_{3l}, u_{3v}) \dots \boldsymbol{U} \\
(\phi_{3}, \theta),  (\boldsymbol{a}_1, \boldsymbol{a}_2, \boldsymbol{a}_3) &\Leftrightarrow  (\phi_{3}, \theta), (A_{l}, \Delta a_{l}, A_{v}, \Delta a_{v}, a_{3l}, a_{3v}) \dots \boldsymbol{A} \\
\end{align}
$$

$$
\begin{gather}
L = L_0 \; (constraint)\\
u_{3v} = \frac{U_{v}}{\cos \theta} \; (constraint) \\
\begin{aligned}
a_{3v} &= a_{3v}(\Delta l , \theta , U_{l} , \Delta u_{l} , U_{v} , u_{3l}, A_{v}) \; (constraint)\\
&= \frac{A_{v}}{\cos \theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} \\
&=
\frac{A_{v}}{\cos\theta} + \frac{2L}{\cos\theta \left( L^2 - \Delta l^2 \right)}
\left[
\left( u'_{l} + u'_{v} \right)^{2}-
2\left( \frac{L+\Delta l}{L} \right) u'_{l} u'_{v}
\right]
\end{aligned} \\
\left(
\begin{aligned}
u'_{l} := u_{3l}\cos\theta-U_{l} = \frac{L \dot{\phi}_{3} + \Delta l \dot{\theta}}{2}\\
u'_{v} := u_{3v}\sin\theta - \Delta u_{l} = \frac{\Delta l \dot{\phi}_{3} + L \dot{\theta}}{2}\\
\end{aligned} 
\right) \\
\end{gather}
$$

摩擦を導入する場合には、運動方程式の部分を修正する必要がある。
巻き数 $ \theta ' $ , 摩擦係数c, 軸表面速度w, 正規化慣性モーメントRを用いる。
$ x_1 $ を右手とする。(鏡写し)

$$
\begin{gather}
a_{3l} =  \frac{\sin\theta(T_2 - T_1)}{m} - g\sin\phi_{3} \\
a_{3v} =  \frac{\cos\theta(T_1+T_2)}{m} - g\cdot \cos{\phi_3} \\
\theta' := \left(
    \begin{aligned}
    &\pi - 2\theta (\theta< \pi/2) \\
    &2\theta - 3\pi (\theta> 3\pi/2) \\
    \end{aligned}
    \right. \\
T_2 = \left(
    \begin{aligned}
    e^{-c\theta'}T_1 \; \left( \frac{\dot{\Delta l}}{2} \gt w \right) \\
    e^{c\theta'}T_1 \; \left( \frac{\dot{\Delta l}}{2} \lt w \right) \\
    \end{aligned}
\right. \\
\dot{w} = \frac{m(T_1 - T_2)}{R}
\end{gather}
$$

以上で摩擦ありの場合に拡張できた。L, c, R, m が道具固有の量。

## 2. スティックリリースの導入

スティックを質量Mの質点とみなすと、スティックリリース時には

$$
\begin{gather}
\begin{gathered}
a_{il} = -g\sin\phi _i \\
a_{iv} = - \frac{T_i}{M} - g\cos\phi _{i} \\
\end{gathered}
\; (i = 1,2)
\end{gather}
$$

ただし

$$
\begin{alignat}{4}
a_{1l} = A_l + \Delta a_l
&\qquad a_{2l} = A_l - \Delta a_l 
&\qquad a_{1v} = A_v + \Delta a_v 
&\qquad a_{2v} = A_v - \Delta a_v \\
\end{alignat}
$$



スティックリリース時にはavが未知量になり、a3vをa1vなどの方程式と連立して解く必要がある。
1(右手)のみをリリースしている場合には、回転減速時であれば

$$
\begin{gather}
\mu := \frac{M}{m} \\
T_1 = -M(a_{1v} + g\cos\phi _1) \\
T_2 = -e^{-c\theta '}M(a_{1v}+g\cos\phi _1) \\
\begin{gathered}
a_{3v} = -\mu\cos\theta (1+e^{-c\theta '})(a_{1v}+g\cos\phi _1)-g\cos\phi _3 \\
= \frac{a_{1v}+a_{2v}}{2\cos \theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta}
\end{gathered}
\end{gather}
$$

$$
\begin{gather}
\begin{gathered}
-a_{1v}(\mu\cos\theta (1+e^{-c\theta '})+\frac{1}{2\cos\theta})= \\
\frac{a_{2v}}{2\cos\theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} + 
g\cos\phi _3 + \mu\cos\theta (1+e^{-c\theta '})g\cos\phi _1
\end{gathered} \\
\begin{gathered}
a_{3v}\left( \frac{1}{\mu\cos\theta(1+e^{-c\theta '})}+2\cos\theta \right) = \\
-g\cos\phi _1 -\frac{1}{\mu\cos\theta(1+e^{-c\theta '})}g\cos\phi _3 + a_{2v} +
2\left( \cos \theta u_{3l} - U_{l} \right) \dot{\phi}_{3} + 
2\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos \theta} \dot{\theta}
\end{gathered} \\
\end{gather}
$$


のように汚い式になるが、a1vとa3vを保持しているスティック側の加速度a2vの関数として求められる。
ただしスティックの相対質量 $ \mu $ を定義し用いた。
摩擦が逆方向の場合はcの符号を反転させればよい。
摩擦を無視した場合はc=0とすればよく、

$$
\begin{gather}
T_1 = T_2 = -M(a_{1v} + g\cos\phi _1) \\
\begin{aligned}
& -a_{1v}\left(2\mu\cos\theta +\frac{1}{2\cos\theta}\right) \\
& = \frac{a_{2v}}{2\cos\theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} + 
g\cos\phi _3 + 2\mu g \cos\theta \cos\phi _1 
\end{aligned} \\
\begin{aligned}
& a_{3v}\left( \frac{1}{2\mu\cos\theta}+2\cos\theta \right) \\ 
& = -g\cos\phi _1 -\frac{1}{2\mu\cos\theta}g\cos\phi _3 + a_{2v} +
2\left( \cos \theta u_{3l} - U_{l} \right) \dot{\phi}_{3} + 
2\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos \theta} \dot{\theta}
\end{aligned} \\
\end{gather}
$$

のように汚いが計算可能である。
a1lは重力のみの寄与であり、a3lはT1,T2に各式を代入することで計算できる。

次に両手をリリースしている場合、

$$
\begin{gather}
\left(
    \begin{aligned}
    T_1 &= -M(a_{1v} + g\cos\phi _1) \\
    T_2 &= e^{-c\theta '}T_1 = -M(a_{2v} + g \cos \phi _2) \\
    \end{aligned}
\right. \\
\left(
    \begin{aligned}
    a_{1v} = e^{c\theta '}a_{2v} + g(e^{c\theta '} \cos\phi _2 - \cos\phi _1)\\
    a_{2v} = e^{-c\theta '}a_{1v} + g(e^{-c\theta '} \cos\phi _1 - \cos\phi _2)\\
    \end{aligned}
\right. \\
\begin{gathered}
a_{1v} + a_{2v} = \frac{e^{-c\theta '} + e^{c\theta '}}{2}(a_{1v} + a_{2v}) +
\frac{e^{-c\theta '} - e^{c\theta '}}{2}(a_{1v} - a_{2v}) + \\
g\left( (e^{-c\theta '}-1)\cos\phi _1 + (e^{c\theta '}-1)\cos\phi _2 \right)
\end{gathered} \\
\begin{gathered}
(1-\cosh(-c\theta '))A_v = \sinh(-c\theta ')\Delta a_v +  \\
g((\cosh(-c\theta ') -1)\cos\theta\cos\phi _3 - \sinh(-c\theta ')\sin\theta\sin\phi _3) \\
\end{gathered} \\
\Delta a_v = \tanh(\frac{c\theta '}{2})A_v + 
g(\tanh(\frac{c\theta '}{2})\cos\theta\cos\phi _3 + \sin\theta\sin\phi _3) \\
\begin{aligned}
T_1 + T_2 &= -M(a_{1v} + a_{2v} + g(\cos\phi _1 + \cos \phi _2)) \\
&= -M(2A_v + g(\cos(\phi_3 + \theta) + \cos(\phi_3 - \theta)) \\
&= -2M(A_v + g\cos \phi _3 \cos \theta) 
\end{aligned} \\
\end{gather}
$$

のように対称性を利用できる。

$$
\begin{align}
a_{3v} &=  \frac{\cos\theta(T_1+T_2)}{m} - g\cdot \cos{\phi_3} \\
&= -2\mu\cos\theta(A_v + g\cos \phi _3 \cos \theta) - g\cos\phi _3 \\
&= \frac{A_{v}}{\cos \theta} +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} \\
-\left(2\mu\cos\theta + \frac{1}{\cos\theta}\right)A_v
&= g\cos\phi _3(2\mu\cos ^2\theta + 1) +
\left( u_{3l} - \frac{U_{l}}{\cos \theta} \right) \dot{\phi}_{3} + 
\frac{U_{v}\sin \theta - \Delta u_{l} \cos \theta }{\cos ^{2} \theta} \dot{\theta} \\
\end{align}
$$

直感的にもわかるように、張力比が決まるため、a1vとa2vに線形な関係が制約として課されることになる。
また張力がAvで書けるため、比較的簡単にAvやa3vを解くことができる。
あとは順次解いていけば求まるはず。

このようにスティックリリースの導入は、微分方程式そのものの段階では煩雑だが容易い。
また直感的にも明らかなように、その運動は相対質量 $ \mu $ によって記述できる。
しかし、スティックリリース時の運動はおそらくカオス的になり、その解析は私には難しい。