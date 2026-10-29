---
publishDate: 2026-10-29T22:00:00Z
author: Mobell
title: 2026级高等数学(上)期中考试试题讲解 Ⅱ
excerpt: 第二部分我们来到了大题部分，我个人感觉大题是要比选择稍难一些，但是也没有到很难的地步。
image: https://pub.mini-tools.uk/permanent/81ddf9d3-7d8f-4541-86b5-343e375c83d8.webp
imageAlt: ss
category: Host
tags:
  - 数学
  - 高数
  - 考试
  - 大学
---
在开始写这篇文章前，老师将高数成绩下发了下来，我也是毫不意外地没有考到很高的水平，100分满分只有87分，就像我前一篇文章说的，这张试卷有很多人其实是能得到满分的，目前我已知的就至少有7人高数满分。我在错了两个选择8分的情况下，大题又扣去5分。不过不可忽视的是，即使这张卷子并不是很难，依旧有60分上下的学生，我认为即使上课不听讲，我们也才学了两个月的知识，考前2天就能基本过上一边，并不至于在及格线徘徊（当然你说你全复习线代了那当我没说）。

同样网络上的回忆版于正式版有些许偏差，但是数值和算是都是相同的，只是问法稍有不同，不影响我们分析。
<div text-center>
    <img src="https://pub.mini-tools.uk/permanent/3bdb9016-7861-43e9-8a28-0b1eb0c43594.png" alt="t2">
</div>

## 三、计算题

**1. 求极限 $$\lim_{n \to \infty} \frac{1}{n^2} \left( \sqrt{1 \cdot 2} + \sqrt{2 \cdot 3} + \cdots + \sqrt{n(n+1)} \right).$$**

>其实原题应该是这样的 $\lim_{n \to \infty} \left( \frac{\sqrt{1 \times 2}}{n^2} + \frac{\sqrt{2 \times 3}}{n^2} + \cdots + \frac{\sqrt{n \times (n+1)}}{n^2} \right)$ 。不过两者等价。

典型的数列求和，用夹逼准则。对数字敏感的话可以很容易看出 $\sqrt{n \times (n+1)}$ 可以缩小为 $\sqrt{n \times (n)} = n$ ，放大为 $\sqrt{(n+1) \times (n+1)} = n+1$ ，所以原式就有  $$\frac{1}{n^2} \cdot \frac{n(n+1)}{2} <= \frac{1}{n^2} \sum_{k=1}^{n} \sqrt{k(k+1)} <= \frac{1}{n^2} \cdot \frac{(n+1)(n+2)}{2}.$$  
$$\frac{1}{2} <= \frac{1}{n^2} \sum_{k=1}^{n} \sqrt{k(k+1)} <= \frac{1}{2}$$

极限为 $\frac{1}{2}$


**2. 设 $f(x) = \left( \frac{x-1}{x+1} \right)^x$，求 $\lim_{x \to +\infty} f(x+1)$。**

$1^ \infty $，用x+1替换x，再根据一高数的口诀：
>e的极限往里带，指数乘以底减一

可以得出 $\lim_{x \to +\infty} f(x+1)$ = $ \lim_{x \to +\infty}e^{(x+1)(\frac{x}{x+2} - 1)}$.只要求 $ \lim_{x \to +\infty} (x+1)(\frac{x}{x+2} - 1)$ 解得 $\lim_{x \to +\infty} f(x+1) = e^{-2}$

**3. 设 $f(x)$ 可导，$y = \frac{f(e^x)}{e^{f(x)}}$，求 $dy$。**

复合函数求导，高中生都会，小心别抄错字母就行 $$y' = \frac{f'(e^x) e^x e^{f(x)} - f(e^x) e^{f(x)} f'(x)}{e^{2f(x)}} = e^{-f(x)} \left[ e^x f'(e^x) - f(e^x) f'(x) \right]$$

**4. 设 $y = y(x)$ 由方程 $e^y + xy^2 = e^2$ 确定，求 $y''(0)$。**

隐函数求导（话说怎么这么多求导的题啊），用x=0把 y y' y'' 分别解出来就行。 
由 $e^y + xy^2 = e^2$，令 $x = 0$ 得 $y = 2$。两边对 $x$ 求导：
$$
e^y y' + y^2 + 2xy y' = 0 \implies y' = -\frac{y^2}{e^y + 2xy}
$$

在 $(0, 2)$ 处 $y' = -\frac{4}{e^2} = -4e^{-2}$。再对 $x$ 求导：$$e^y (y')^2 + e^y y'' + 2yy' + 2yy' + 2x(y')^2 + 2xyy'' = 0,$$

代入 $x = 0$、$y = 2$、$y' = -4e^{-2}$：$$e^2 \cdot 16e^{-4} + e^2 y'' - 16e^{-2} - 16e^{-2} = 0 \implies y'' = 16e^{-4}.$$

**5. 求曲线 $$\begin{cases}x = t + \tan t, \\y = 2(\sin t + 1)\end{cases}$$ 在 $t = 0$ 对应点处的切线方程与法线方程。**

参数方程求导$t = 0$ 对应点 $(0, 2)$。$\frac{dx}{dt} = 1 + \sec^2 t$，$\frac{dy}{dt} = 2\cos t$，在 $t = 0$ 处分别为 $2$ 与 $2$，故

$$
\frac{dy}{dx} =\frac{\frac{dy}{dt}}{\frac{dx}{dt}}= \frac{2}{2} = 1.
$$

切线：$y - 2 = x$，即 $y = x + 2$；法线斜率为 $-1$：$y - 2 = -x$，即 $y = -x + 2$。

>又来一个求导，感觉把所有求导类型考了个遍，这题出得一点水平都没有，纯粹为了考查而考查，当然对学生来说是好事，只要把该掌握的都掌握了，这些题没有一丁点难度，直接上手做，一点都不用思考。

**6. 求 $f(x) = \frac{\ln |x|}{x^2 - 3x + 2}$ 的全部间断点，并指出其类型。**

考查间断点的判断和类型，分母 $(x - 1)(x - 2)$，加上 $\ln|x|$ 的定义域，间断点为 $x = 0, 1, 2$。


   - $x = 0$：$\ln|x| \to -\infty$，分母 $\to 2$，故 $f(x) \to -\infty$，是无穷间断点；
   - $x = 2$：$\ln 2 \neq 0$，分母 $\to 0$，$f(x) \to \infty$，是无穷间断点；
   - $x = 1$：$\ln x \sim x - 1$，而 $x^2 - 3x + 2 \sim -(x - 1)$，故 $\lim_{x \to 1} f(x) = -1$ 为有限值，是可去间断点。
   
## 四、证明题
 
**1. 设 $0 < x_1 < 4$，$x_{n+1} = \sqrt{x_n(4 - x_n)}$ $(n = 1, 2, \dots)$。证明数列 $\{x_n\}$ 极限存在，并求 $\lim_{n \to \infty} x_n$。**

证明有界：若 $x_n \in (0,4)$，则 $x_n(4-x_n) > 0$，且 $x_n(4-x_n) = 4 - (x_n - 2)^2 \le 4$，故 $x_{n+1} \in (0,2]$。
于是 $n \ge 2$ 时恒有 $0 < x_n \le 2$。

证明单调：对 $n \ge 2$（此时 $x_n \le 2$），$$x_{n+1}^2 - x_n^2 = x_n(4 - x_n) - x_n^2 = 2x_n(2 - x_n) \ge 0,$$

故 $x_{n+1} \ge x_n$，即 $\{x_n\}_{n \ge 2}$ 单调递增且有上界 $2$。

求极限： 由单调有界准则，$\lim_{n \to \infty} x_n = a$ 存在，$a \in (0,2]$。对递推式取极限：$$a^2 = a(4 - a) \implies 2a^2 = 4a \implies a = 2 \text{（舍去 } a = 0\text{）}.$$

>这道题我失掉了5分，究其原因，是因为几乎没有证明极限存在，直接就求极限了，具体过程我也不太记得了，总之就是单调有界性准则记忆不牢，其证明方法遗忘，不会证有界性和单调性导致失分

**2. 设 $f(x)$ 在 $[0, 2]$ 上连续，且 $f(0) = f(2)$。证明：存在 $x_1, x_2 \in [0, 2]$，使得 $$|x_1 - x_2| = 1, \quad f(x_1) = f(x_2).$$**

典型例题，不管你在哪里学高数的函数零点存在性定理（甚至可能是在高中）和介值定理，肯定都会做过原题，甚至是它的拓展题。

令
$$
g(x) = f(x+1) - f(x), \quad x \in [0, 1].
$$

$g$ 在 $[0, 1]$ 上连续，且$$g(0) = f(1) - f(0), \quad g(1) = f(2) - f(1) = f(0) - f(1) = -g(0).$$

$g(1) = -g(0)$，  
当 $g(1) = g(0) = 0 $  取 $x_1 = 0$、$x_2 = 1$，则 $|x_1 - x_2| = 1$ 且 $f(0) = f(1)$，结论成立；  
当 $g(1) = g(0)\ne 0 $ ，即两者异号，根据零点存在性定理，必有一点 $x_0$ 使得 $g(x_0) = 0$ ,取 $x_1 = x_0 ，x_2 = x_0 + 1$则 $|x_1 - x_2| = 1$ , $f(x_1) = f(x_2)$，结论成立。

## 结语

总算把所有题目写完了，线性代数的题目前并未找到，编者已经向老师申请，等下周拿到原题后再来做分享。最后，祝所有人都能取得满意的成绩！


<script loading="lazy"
        src="https://giscus.app/client.js"
        data-repo="mobellling/mobellling.github.io"
        data-repo-id="R_kgDOVU1Z4g"
        data-category="Announcements"
        data-category-id="DIC_kwDOVU1Z4s4DJfbN"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="top"
        data-theme="cobalt"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>
