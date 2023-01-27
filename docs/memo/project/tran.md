---
comments: true
---

# 最优运输与蒙日-安培方程

## 项目概况
!!! note ""
    - **类型** 🎓 数学科学学院（国际化课程）
    - **时段** 🕙 2022-2023 秋冬（线上）
    - **教师** 🧑‍🏫 Jiakun Liu（白圣,李玉婷）
    - **内容** 🗞️ 本课程旨在简要介绍最优运输问题以及它在其他领域中的应用。包括最优运输映射的存在唯一性和正则性，蒙日-安培方程的正则性理论。
    - **考核** 📝 到课率+结课作业
    - **回放** 🔗 无
    - **教材** 📙 参考书目包括
    > Cedric Villani. 2003. Topics in Optimal Transportation. Graduate Studies in Mathematics 58, American Mathematical Society, Providence, Rhode Island.
    > 
    > Villani, C., 2009. Optimal Transportation, Old and New, Grundlehren der Math. Wiss. 338. Springer-Verlag, Berlin.
    > 
    > Figalli, A., 2017. The Monge-Ampere equation and its applications, Zurich Lectures in Advanced Mathematics. European Mathematical Society (EMS).
    > 
    > Gilbarg, D. and Trudinger, N. S., 1983. Elliptic partial differential equations of second order. Springer-Verlag, Berlin.```

## 大纲
!!! note ""
    - **CH0.** 内容简介
    - **CH1.** Kantorovich对偶泛函
    - **CH2.** 最优运输的几何性质
    - **CH3.** Brenier的极化分解定理
    - **CH4.** Monge-Ampere方程
    - **CH5.** 严格凸与C1正则性
    - **CH6.** 自然边值条件与C1,alpha正则性 
    - **CH7.** C2,alpha与高阶正则性
    - **CH8.** 整体正则性


## 课程论文

!!! tip "作业要求"
    分别选取范围内的部分题目进行解答.

???+ abstract "Course Report"

    ### Problem 1.

    > Discuss the relationship between Kantorovich's problem:
    > 
    > $$
    > \inf\limits_{\gamma\in\Gamma(\mu\times v)} \mathscr{C}_k(\gamma)=\int_{U\times V}c(s,y)d\gamma(x,y)
    > $$
    > 
    > and Monge'sproblem:
    > 
    > $$
    > \inf\limits_{t_{\#}\mu=v}\mathscr{C}_M(t)=\int_{\mu}c(x,t(x)d\mu(x).
    > $$
    > 
    > Both two problems are related to the existence and uniqueness of the function $t$ and $\gamma$ given the cost function $c$.

    **Answer.**

    First, we let $t$ be a measure preserving function, which satisfying that 

    $$t_{\#} \mu=v,$$

    $$\int_U c(x,t(x))d\mu(x)=\inf\limits_{t_{\#}\mu=v}\mathscr{C}_M(t).$$

    From above, we now construct a corresponding function $\mu_t\in\Gamma(\mu \times v)$, where for $\forall E\subset U\times V$, we have

    $$\gamma_t(C):=\mu(\{x|(x,t(x))\in E\}).$$

    It's easy to observe that for $\forall A\subset U$, by the measure language definition of the measure preserving mapping, we have

    $$\gamma_t(A\times V)=\mu(\{x|(x,t(x))\in A\times V\})=\mu(A).$$

    Additionally, for $\forall B\subset V$, we have

    $$v(B)=\mu(\{x|(x,t(x))\in U\times B\}),$$

    as

    $$t_{\#}\mu=v.$$

    Meanwhile

    $$\gamma_t(U\times B)=\mu(\{x|(x,t(x))\in U\times B\})=v(B).$$

    Hence, for the constructed function $\gamma_t$, we know it is product on linear space. Then, by

    $$\int_{U\times V} c(x,y)d\gamma_t (x,y)\ge \inf\limits_{\gamma\in\Gamma(\mu\times v)} \mathscr{C}_k(\gamma),$$

    we get that

    $$\inf\limits_{t_{\#}\mu=v} \mathscr{C}_M(t)\ge \inf\limits_{\gamma\in\Gamma(\mu\times v)}\mathscr{C}_k(\gamma).$$

    Finally, as we know, the limitation of the Monge's problem is more strict, requiring that 

    1. $t$ is a mapping of preserving measurability, 
    2. $\gamma$ is just limited on linear space. 

    Thus more freedom on the product space means more choices of function $\gamma$, thus there is going to have smaller total cost for Kantorovich's problem.

    ### Problem 2.

    > Choose the Problem in subject: a mapping $T$ is a measure preserving ($T_\# f=g)$ iff $\forall h\in C(V), \int_V h(y)g(y)dy=\int_U h(T(x))f(x)dx.$
    >
    > (The definition of the measure preserving given by measure language and analysis language is equivalent.)

    **Answer.**

    If $T$ is a mapping of preserving measurablity, then for $\forall E\subset V,$ always $\exists T^{-1}(E)\subset U$ s.t.

    $$\int_{T^{-1}(E)} f(x)dx=\int_E g(y)dy=\int_{T^{-1}(E)}g(Tx)|J|dx.$$

    where $J$ means the Jacobian $\displaystyle\frac{\partial y}{\partial x}$, i.e. 

    $$f(x)=g(Tx)|J|, x\in T^{-1}(E)a.s..$$

    Let $E=V$, for $\forall$ continuous function $h$ over $V$, we have

    $$h(Tx)f(x)dx=h(Tx)g(Tx)|J|,x\in T^{-1}(V)a.s..$$

    Then, we can conclude that

    $$\int_U h(Tx)f(x)dx=\int_U h(Tx)g(Tx)|J|dx=\int_V h(y)g(y)dy.$$

    Additionally, we have assumpted that $\forall \in C(V),$ thus we have

    $$\int_V h(y)g(y)dy=\int_U h(T(x)f(x))dx.$$

    Now, for $\forall E\subset V$,  we let

    $$h(y)=\mathbb{I}\{y\in E\},y\in V,$$

    then we have

    $$\int_E g(y)dy=\int_{U\cap T^{-1(E)}}f(x)dx=\int_{T^{-1}(E)}f(x)dx.$$

    Therefore, we get

    $$T_\# f=g.$$

    ### Problem 3.

    > Explain the background of Brenier polar factorise.

    **Answer.**

    The problem of Monge has stayed with no solution until progress was made in the 1940s. Indeed, only with the work by Kantorovich, it was inserted into a suitable framework which gave the possibility to attack it and, later, to provide solutions and study them. 

    Back to the 20 century, the Monge problem was asked, which is difficult to solve. after that, Kantoroich relaxes the optimal transfer problem into the optimal transmission solution, and instead of the Euclidean distance $|x-y|$ and more general measures and spaces, the problem was generalized with very general cost functions $c(x,y)$.

    Kantorovich use the idea of regarding the Monge problem as connected to linear programming, where the cost to be minimized becomes simply $\int_{X\times Y}c d\gamma$. Which means, this linear problem under linear constraints, is possible to prove existence of a solution. Then, by using techniques from convex optimization like duality, we could characterize the optimal solution. 

    Now, there is some special cases, particularly if we let the cost $c(x,y)=|x-y|^2$, which is natural and has many application in physical models, for Bernier, who works to prove that the optimal $\gamma$ does not allow this splitting of masses and particles at $x$ are only sent to a unique destination $T(x)$, thus providing a solution to the original problem by Monge. Additionally, he proves a special form for the optimal map:

    For or a convex function $u$, the optimal $T$ is of the form $T(x)=\Delta u(x)$. 

    Which makes a strong connection with the Monge-Ampère equation.

    $$|D^2u(x)|=\displaystyle\frac{f(x)}{g(\Delta u(x))}$$

    To the equation above, it is an degenerate, nonlinear, elliptic equation and is in the class of convex functions. Brenier uses result above to conclude the fact that matrices can be written as the product of a symmetric positive-definite matrix and an orthogonal one by prove that vector fields can be written as the composition of the gradient of a convex function and of a measure preserving map. It is the polar factorization theorem for vector maps, and the above narrative is the background to this theory.

