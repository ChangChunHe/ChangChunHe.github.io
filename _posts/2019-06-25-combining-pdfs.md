---
title: 'Basel问题和圆周率的关系'
date: 2023-06-26
permalink: /posts/2023/06/basel-pi/
excerpt_separator: <!--more-->
toc: true
tags:
  - 数学
  - 圆
---

1734年Euler给出了Basel 问题的解答, 也就是所有正整数的平方的倒数和:

$$\sum\_{i=1}^{\infty}\frac{1}{i^2} = \frac{\pi^2}{6}$$

<!--more-->

相信很多人会对这个等式很着迷的, 一个相当漂亮的等式, 当时Euler给出的证明其实并不完全严谨, 当然也无伤大雅, 而且对于所有的偶数次方都是有解析解的, 跟[伯努力数](https://en.wikipedia.org/wiki/Bernoulli_number)有关, 这里就不展开讲了. 一般的高数书会用Fourier transform来证明这个等式, 也有其他的例如
帕塞瓦尔恒等式, 留数定理, 柯西还给过一个初等的证明, [维基百科](https://en.wikipedia.org/wiki/Basel_problem)都有记录.这里介绍一种几何方法的证明. 证明原文来自[这里](http://www.math.chalmers.se/~wastlund/Cosmic.pdf).

首先给出一个很简单的引理, 在直角三角形中, 两个直角边和斜边上的高构成一组倒勾股数. 也即为

$$\frac{1}{a^2}+\frac{1}{b^2}=\frac{1}{h^2}$$

下面用这个等式就可以巧妙的构造出Basel问题的解答了.

如下图所示, 我们先画一个小圆$OA_1$, 周长为2, 那么直径$OA_1$也就是$\frac{\pi}{2}$, 利用上面的等式我们就可以得到:

$$\frac{\pi^2}{4}=\frac{1}{A\_1A_2^2}+\frac{1}{A\_1A_3^2}$$

<img height="380" src="https://raw.githubusercontent.com/ChangChunHe/Sundries/master/basel_iter_1.png">

这里看起来并没有什么用处, 但是注意到如果我们再画一个更大的圆就可以有新的发现了.

<img height="400" src="https://raw.githubusercontent.com/ChangChunHe/Sundries/master/basel_iter_2.png">

这里我们连接大圆的圆心和$A_2$可以交大圆于两点分别为$B_1, B_3$, 那么很明显三角形$B_1A_1B_3$是一个以$A_1$为直角顶点的三角形, 那么我们就可以对$\frac{1}{A_1A_2^2}$进行分解, 即为:

$$\frac{1}{A\_1A_2^2}=\frac{1}{A\_1B_1^2}+\frac{1}{A\_1B_3^2}$$

所以直径$OA_1^2$可以改写为:

$$\frac{\pi^2}{4}=\frac{1}{A\_1B_1^2}+\frac{1}{A\_1B_3^2}+\frac{1}{A\_1B_2^2}+\frac{1}{A\_1B_4^2}$$

留意到这里的$B_1-B_4$都在在圆周上均匀分布的. 原因其实很简单, 例如弧$A_1A2$在中等圆中对的圆周角角$A_1O_1B_1=\pi/4$, 但是在更大的圆中, 这个角刚好是这个大圆的圆心角, 所以圆周角$A_1B_3B_1$是圆心角$A_1O_1B_1$的一半, 相应地$A_1B_1$弧所占大圆的比例也就是$A_1A_2$弧占中等圆比例的一半, 所以依旧是均匀分布的. 注意到这里弧$A_1A_2$, $A_1B_1$都是等于1的, 因为圆都是等分的, 这一点很重要..., 而且我们可以迭代下去就会有8个$C_i$, 16个$D_i$,32个$E_i$...

下面就是见证奇迹的时刻, 我们设想我们迭代了无穷多次, 那么弧长和线段长是等价的, 那么就有

$$2*(\frac{1}{1^2}+\frac{1}{3^2}+...+\frac{1}{(2n-1)^2}+...)=\frac{1}{OA_1^2}=\frac{\pi^2}{4}$$

这里乘以2是因为有左右两边的线段. 那么Basel问题

$$S = \frac{1}{1^2}+\frac{1}{2^2}+\frac{1}{3^2}+\frac{1}{4^2}+\frac{1}{5^2}+... = \frac{1}{1^2}+\frac{1}{3^2}+\frac{1}{5^2}+...+\frac{1}{2^2}(1+\frac{1}{1^2}+\frac{1}{2^2}+...)$$

所以

$$S = \frac{4}{3}\frac{\pi^2}{8} = \frac{\pi^2}{6}$$
