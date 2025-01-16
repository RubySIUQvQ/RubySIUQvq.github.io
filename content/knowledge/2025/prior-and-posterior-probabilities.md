---
title: 'Prior and Posterior Probabilities'
date: 2025-01-15T20:36:06+08:00
draft: False
ShowToc: true
TocOpen: true
typora-root-url: ..\..\..\static\
---









**已知** ：

人群中某个人患癌的概率是 1%，现在我们有一个测试某个对象是否患癌的机器，但是机器并不完美。对于确定患癌的人，机器有 10% 的概率给出不患癌的判断，对于确定不患癌的人，机器有 3% 的概率给出患癌的判断。我们使用 0 表示患癌，使用 1 表示不患癌。使用事件 C 表示是否患癌，使用事件 T 表示机器的判断，所以我们有以下概率分布：
$$
\begin{align*}
P(C=1)&=0.01 \newline
P(C=0)&=0.99 \newline
P(T=1|C=1)&=0.9 \newline
P(T=0|C=1)&=0.1 \newline
P(T=1|C=0)&=0.03 \newline
P(T=0|C=0)&=0.97
\end{align*}
$$

### 先验概率与后验概率

在某个人使用机器做测试之前，我们希望得知这个人患癌的概率。这被称之为**先验概率**，因为这个概率在我们观察到测试结果之前得到。如果某个人使用机器进行了测试，并观测到了测试结果，我们问这个人实际患癌的概率。这被称之为**后验概率**，因为我们观察到了测试的结果。

先验概率我们可以理解为事先估计的概率分布。后验概率则是给定了一些信息而确定下的概率，可以理解为条件概率，即某个因素确定发生了，在该因素影响下事件发生的概率。

在上面提到的事件中，一个人患癌的概率就是先验概率就是 $P(C)$，而一个人在经过机器测试后患癌概率就是$P(C|T)$。

在不经过测试时，患癌的先验概率$P(C=1)=0.01$，那么假设测试结果为患癌，其确定患癌的后验概率可由公式
$$
\begin{align*}
P(C=1|T=1)&=\frac{P(C=1,T=1)}{P(T=1)} \newline
&=\frac{P(T=1|C=1)P(C=1)}{P(T=1)} \newline
&=\frac{P(T=1|C=1)P(C=1)}{P(T=1|C=1)P(C=1)+P(T=1|C=0)P(C=0)}
\end{align*}
$$
得出$P(C=1|T=1)\simeq0.23$。

这里出现了一种非常反直觉的情况。即对于没有患癌的人，机器给出误判为患癌的概率只有 3%，这是说明机器具有非常准确的判断。但是当机器给出患癌的判断时，人实际患癌的概率却只有 23%。这是因为患癌的先验概率非常低。