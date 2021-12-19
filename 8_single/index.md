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
\right] \\
&= \frac{A_v}{\cos\theta} + B
\end{aligned} \\
\left(
\begin{aligned}
u'_{l} := u_{3l}\cos\theta-U_{l} = \frac{L \dot{\phi}_{3} + \Delta l \dot{\theta}}{2}\\
u'_{v} := u_{3v}\sin\theta - \Delta u_{l} = \frac{\Delta l \dot{\phi}_{3} + L \dot{\theta}}{2}\\
\end{aligned} 
\right) \\
\end{gather}
$$

ただしa3vの第二項以下をBとおいた。
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
具体的にはa3vは既知であるため、そこからT1T2を求め、a3lに代入することで加速度がすべて求められる。
加速時には、

$$
\begin{gather}
a_{3v} = \frac{A_v}{\cos\theta}+B = 
\frac{\cos\theta(T_1+T_2)}{m} - g\cdot \cos{\phi_3} \\
T_1 + T_2 = \frac{m}{\cos\theta} \left(
    \frac{A_v}{\cos\theta}+B+g\cos\phi_{3}
\right) \\
T_1+T_2 = (1+e^{-c\theta'})T_1 \\
T_1-T_2 = (1-e^{-c\theta'})T_1 = -\tanh \left(\frac{c\theta'}{2}\right)(T_1+T_2) \\
a_{3l} =  \frac{\sin\theta}{m}(T_2 - T_1) - g\sin\phi_{3} \\
= \tanh\left(\frac{c\theta'}{2}\right)\tan\theta \left(
    \frac{A_v}{\cos\theta}+B+g\cos\phi_{3}
\right) - g\sin\phi _{3}
\end{gather}
$$


## 2. スティックリリースの導入

そもそもスティックを保持していることによる制約はなんら課していないのだから、
これまでの式はすべてスティックリリース時にも成立する。
ただしスティックリリース時には $ a_{iv}, a_{il} $ が未知量になるため、
Avなどを含む多変数関数のこれまでの式は役に立たない。
スティックが新たに張力と重力に基づく運動方程式に従うため、
これを解くことでスティックの運動を記述する必要がある。
スティックを質量Mの質点とみなすと、

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
\begin{alignat}{2}
a_{1l} = A_l + \Delta a_l
&\qquad a_{2l} = A_l - \Delta a_l \\
a_{1v} = A_v + \Delta a_v 
&\qquad a_{2v} = A_v - \Delta a_v \\
\end{alignat}
$$

$ a_{il} $ についてはこの運動方程式そのもので完結しており、$ a_{iv} $ を解けばよい。
例えば1(右手)のみをリリースしている場合には、a2 をプレイヤーからの入力とみなし、
a1vとa3v, a3lを解く必要がある。
回転加速時であれば

$$
\begin{gather}
\mu := \frac{M}{m} \\
T_1 = -M(a_{1v} + g\cos\phi _1) \\
T_2 = -e^{-c\theta '}M(a_{1v}+g\cos\phi _1) \\
\begin{gathered}
a_{3v} = -\mu\cos\theta (1+e^{-c\theta '})(a_{1v}+g\cos\phi _1)-g\cos\phi _3 \\
= \frac{a_{1v}+a_{2v}}{2\cos \theta} +B
\end{gathered}
\end{gather}
$$

$$
\begin{gather}
\begin{aligned}
& -a_{1v}(\mu\cos\theta (1+e^{-c\theta '})+\frac{1}{2\cos\theta}) \\
& =\frac{a_{2v}}{2\cos\theta} + B + 
g\cos\phi _3 + \mu\cos\theta (1+e^{-c\theta '})g\cos\phi _1
\end{aligned} \\
a_{1v} = 
-\frac{a_{2v} + 2\cos\theta (B + g\cos\phi _3) + 2\mu\cos^2\theta (1+e^{-c\theta '})g\cos\phi _1}
{1+2\mu\cos^2\theta (1+e^{-c\theta '})} \\
\begin{aligned}
& a_{3v}\left( \frac{1}{\mu\cos\theta(1+e^{-c\theta '})}+2\cos\theta \right) = \\
& a_{2v} -g\cos\phi _1 -\frac{1}{\mu\cos\theta(1+e^{-c\theta '})}g\cos\phi _3 + 
2\cos\theta B
\end{aligned} \\
a_{3v} = \frac{\mu\cos\theta(1+e^{-c\theta '})(a_{2v} - g\cos\phi _1 +2\cos\theta B) -g\cos\phi _3}
{1+2\mu\cos^2\theta (1+e^{-c\theta '})} \\
T_{1} = M\left(
\frac{a_{2v} + 2\cos\theta (B + g\cos\phi _3) - g\cos\phi _1}
{1+2\mu\cos^2\theta (1+e^{-c\theta '})} 
\right) \\
a_{3l}
= \tanh\left(\frac{c\theta'}{2}\right)\tan\theta \left(
    a_{3v}+g\cos\phi_{3}
\right) - g\sin\phi _{3}\\
=(代入省略) \\
\end{gather}
$$


のように汚い式になるが、a1vとa3vを保持しているスティック側の加速度a2vの関数として求められる。
ただしスティックの相対質量 $ \mu $ (ふつう0.2くらい)を定義し用いた。
摩擦が逆方向の場合はcの符号を反転させればよい。
摩擦を無視した場合はc=0とすればよく、

$$
\begin{gather}
a_{1v} = 
-\frac{a_{2v} + 2\cos\theta (B + g\cos\phi _3) + 4\mu\cos^2\theta g\cos\phi _1}
{1+4\mu\cos^2\theta} \\
a_{3v} = 
\frac{2\mu\cos\theta(a_{2v} - g\cos\phi _1 +2\cos\theta B) -g\cos\phi _3}
{1+4\mu\cos^2\theta} \\
T_{1} = T_2  = M\left(
\frac{a_{2v} + 2\cos\theta (B + g\cos\phi _3) - g\cos\phi _1}
{1+4\mu\cos^2\theta} 
\right) \\
a_{3l} = - g\sin\phi _{3} \\
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

直感的にもわかるように、張力比が決まるため、a1vとa2vに線形な関係が制約として課されることになる。
また対称性を利用できる。

$$
\begin{gather}
\begin{aligned}
a_{3v} &=  \frac{\cos\theta(T_1+T_2)}{m} - g\cdot \cos{\phi_3} \\
&= -2\mu\cos\theta(A_v + g\cos \phi _3 \cos \theta) - g\cos\phi _3 \\
&= \frac{A_{v}}{\cos \theta} +B
\end{aligned} \\
-\left(2\mu\cos\theta + \frac{1}{\cos\theta}\right)A_v
= g\cos\phi _3(2\mu\cos ^2\theta + 1) +B \\
A_v = -g\cos\theta\cos\phi _3 - \frac{\cos\theta }
{1+2\mu\cos^2\theta}B \\
a_{3v} = -g\cos\phi _3 + \frac{2\mu\cos^2\theta }
{1+2\mu\cos^2\theta}B\\
T_1 + T_2 = 2M\frac{\cos\theta }{1+2\mu\cos^2\theta}B \\
\Delta a_v = \tanh(\frac{c\theta '}{2})A_v + 
g(\tanh(\frac{c\theta '}{2})\cos\theta\cos\phi _3 + \sin\theta\sin\phi _3) \\
=-\tanh(\frac{c\theta '}{2})\frac{\cos\theta }
{1+2\mu\cos^2\theta}B  + g\sin\theta\sin\phi _3\\
a_{3l}
= \tanh\left(\frac{c\theta'}{2}\right)\tan\theta \left(
    a_{3v}+g\cos\phi_{3}
\right) - g\sin\phi _{3} \\
=\tanh\left(\frac{c\theta'}{2}\right)\tan\theta \frac{2\mu\cos^2\theta }
{1+2\mu\cos^2\theta}B - g\sin\phi _{3} \\
\end{gather}
$$

張力の和がAvで書けるため、比較的簡単に解くことができる。
摩擦は $ a_{3l}, \Delta a_{v} $ のみに影響するのは面白い。

このようにスティックリリースの導入は、微分方程式そのものの段階では煩雑だが容易い。
また直感的にも明らかなように、その運動は相対質量 $ \mu $ によって記述できる。
しかし、スティックリリース時の運動はおそらくカオス的になり、
例えばこれらを数値的に解いたとして、
どれだけの時間スケールにわたって妥当な結果を得られるのかは別問題と思われる。