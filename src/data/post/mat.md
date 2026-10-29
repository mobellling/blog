---
publishDate: 2026-10-28T20:20:00Z
author: Mobell
title: 2026级高等数学(上)期中考试试题讲解 Ⅰ
excerpt: 高数和线代是入学以来上课次数最多的两门课，也是大多数大学生投入精力最多的课程之一。即使满打满算我也就才学习了两个月的时间，但是这两门课的难度已经有所上升，令人十分无奈。这篇文章，我就高数的试题，进行一个讲解，同时巩固我对知识的理解程度。
image: https://mobellling.github.io/-image-/maths.webp
imageAlt: ss
category: Host
tags:
  - 数学
  - 高数
  - 线代
  - 考试
  - 大学
---
进入大学以来，这是第一次以大学知识为内容的考试。显然，没有大量的题目练习，我确实觉得有些力不从心。

高数和线代是入学以来上课次数最多的两门课，也是大多数大学生投入精力最多的课程之一。即使满打满算我也就才学习了两个月的时间，但是这两门课的难度已经有所上升，令人十分无奈。

这篇文章，我就高数的试题，进行一个讲解，同时巩固我对知识的理解程度。

 <div text-center>
  <img src="/images/maths/t1.png" alt="t1" width="100%" />
</div>

## 一、选择

**1. 函数 $f(x) = x^3 ln(x + \sqrt{1 + x^2})$ 在 $R$ 上是（ ）。**   
(A)偶函数 (B)奇函数 (C)周期函数(D)有界函数  

显然，这道题高中生都会做，奇函数×奇函数=偶函数。但是，由于这道题是第一题，我在做题的过程中，状态并没有调整好，顺手写了一个B上去，好在最后检查时先检查的这个题，成功避免痛失4分。

**2. 设 $$f(x) = \begin{cases} x \cos \frac{1}{x}, & x > 0, \\ x, & x \le 0, \end{cases}$$ 则$f(x)$在$x=0$处（）**  
(A)可导 (B)连续但不可导(C)不连续(D)无法判定

本题考查连续和可导的关系，以及函数极限的求解。$x \to 0^+$ 时 $x \cos \frac{1}{x} \to 0$，$x \to 0^-$ 时 $x \to 0$，且 $f(0) = 0$，故连续。直观来看，在$x \le 0$时，x趋近于0，在$x > 0$时，随着x趋近于0 ，函数图像振荡频率越来越快，但振荡幅度越来越小，函数极限不存在，不可导。

**3. 当 $x \to +\infty$ 时，$f(x) = x^2 \cos \frac{\pi x}{2}$ 是（  ）。**  
(A)有界(B)无界但非无穷大 (C)无穷大(D)无穷小

此题考查函数的有界性。因为$f(x) = x^2 \cos \frac{\pi x}{2}$的周期性，当$x = 4k$时，$x \to +\infty $，$f(x)\to +\infty $；当$x=2k+1$，$f(x) \equiv 0$,故无界但不是无穷大。

**4. 当 $x \to 0$ 时，$e^{\sin x} - e^{\tan x} $是$ x^n$的同阶无穷小，则 $n = (\quad)$。**  
(A) $1$ $\quad$ (B) $2$ $\quad$ (C) $3$ $\quad$ (D) $4$

看到 $e^{n} - e^{m} $ 的形式，先把后一个向外提，构建成 $e^{n-m} -1 $ 的形式，运用等价无穷小的替换，将其换为 $n-m$ 。本题中，提出 $e^{\tan x}$ , 变成 $e^{\tan x}(e^{\sin x - \tan x} - 1) $ ，而 $x \to 0$ 时 $e^{\tan x} = 1$ 直接带入， $e^{\sin x - \tan x} - 1$ 可以替换为 $\sin x - \tan x $ ,提出 $ \sin x$ ，转化为 $ \sin x (\frac{\cos x -1}{\cos x}) $ , 再用等价无穷小替换为 $ \frac{  \frac{1}{2} x^3 }1 $ 所以，原式与 $ x^3 $ 等价

>这道题我在考场上做错了，原因是我在向外提出$e^{\tan x}$ 的时候错把 $e^{\sin x - \tan x}$ 写成 $e^{\frac{\sin x }{\tan x} }$,导致后续无法求出正确结果。

**5. 设 $f(x)$ 可导，$D(x)$ 为狄利克雷函数 $x$ 为有理数时取 $1$，否则取 $0$），则关于 $D(f(x))$ 的结论是（ $\quad$ ）。**  
(A) 一定可导    (B) 一定不可导      (C) 一定连续    (D) 无法判定

若 $ f(x)$ 为常数，则 $D(F(x))$ 为常数(0或1)，可导且连续；若 $ f(x)$ 不为常数，如 $ f(x)=x$，则 $D(F(x))$ 处处不可导，处处不连续，无法判定。

>这道题我也做错了/(ㄒoㄒ)/~~，没有考虑到f(x)为常数的时候。

## 二、填空

**1. 设 $a, b \in \mathbb{R}$，$ab > 0$，且极限 $$ \lim_{x \to 0} \frac{\ln(1 + bx) \tan 2x}{(1 - \cos(ax)) \cos x} $$
存在且不为零， $b > 0$，该极限为 $\underline{\quad\quad}$。**
 
这道题的问法忘记了，好像和这个差不多，但我印象里不是这样问的，不过极限是一样的，通过等价无穷小的代换，可以很轻易得得到 $$ \lim_{x \to 0} \frac{\ln(1 + bx) \tan 2x}{(1 - \cos(ax)) \cos x} = \lim_{x \to 0} \frac{bx 2x}{\frac{1}{2} a^2 x^2 \cos x} $$ 化简得 $$ \lim_{x \to 0} \frac{\ln(1 + bx) \tan 2x}{(1 - \cos(ax)) \cos x}= \frac{4b}{a^2} $$

**2. 若 $\lim_{x \to +\infty} (\sqrt{x^2 + ax + b} - x) = 2$，则 $a = \underline{\quad\quad}$。**

如果没有提前做过这种类型的题，恐怕很难想到要用 $ \frac{1}{t} $ 来代替 $ x $,化为分式求解。代换完后是 $\lim_{t \to 0^+}  \frac{\sqrt{1 + at + bt^2} - 1}{t}  $ 分子用无穷小替换为 $\frac{1}{2}(at + bt^2)$ ,化简后得 $\lim_{t \to 0^+} ( \frac{a}{2} + \frac{bt}{2}) = 2$，$a = 4$

**3. 设曲线 $y = f(x)$ 与 $y = \sin x$ 在原点处相切，则 $\lim_{x \to +\infty} x f\left(\frac{1}{x}\right) = \underline{\quad\quad}$。**

因为 $y = f(x)$ 与 $y = \sin x$ 在原点处相切，所以 $f'(0) = (\sin 0)' = \cos 0 = 1$
且 $f(0) = \sin 0 = 0$，$\lim_{x \to \infty} x f\left(\frac{1}{x}\right) = \lim_{x \to \infty} \frac{f\left(\frac{1}{x}\right)}{\frac{1}{x}}$，由洛必达法则：

$$
\lim_{x \to \infty} \frac{f\left(\frac{1}{x}\right)}{\frac{1}{x}} = \lim_{t \to 0} \frac{f(t)}{t} = \lim_{t \to 0} \frac{f'(t)}{1} = 1
$$

**4. 设 $x = f^{-1}(y)$ 是 $y = f(x) = 2x + \ln x$ 的反函数，则 $\left.\frac{dx}{dy}\right|_{y=2} = \underline{\quad\quad}$。**

由 $\frac{dx}{dy} = \frac{1}{\frac{dy}{dx}}$，先求 $\frac{dy}{dx}$，$y' = f'(x) = 2 + \frac{1}{x}$
$$
\frac{dy}{dx} = 2 + \frac{1}{x}
$$


$$
\frac{dx}{dy} = \frac{1}{2 + \frac{1}{x}}
$$
当 $y = 2$ 时，由题易得 $x = 1$
$$
\left.\frac{dx}{dy}\right|_{y=2} = \frac{1}{2+1} = \frac{1}{3}
$$

**5. 设 $f(x) = (x - 3)^n \sin \frac{\pi x}{6}$，则 $f^{(n)}(3) = \underline{\quad\quad}$。**

由莱布尼茨公式 $(uv)^{(m)} = \sum_{k=0}^{m} C_m^k u^{(m-k)} v^{(k)}$

$$
f^{(n)}(x) = C_n^0 (x-3)^n \left(\sin\frac{\pi x}{6}\right)^{(n)} + C_n^1 n(x-3)^{n-1} \left(\sin\frac{\pi x}{6}\right)^{(n-1)} + \dots + C_n^n n! \sin\frac{\pi x}{6}
$$

$$
f^{(n)}(3) = 0 + 0 + \dots + n! \sin\frac{\pi}{2} = n!
$$

*未完待续……*

>数学符号可真难打啊，这里附一张图，让你们感受一下数学符号的恐怖，就这么短短几行，我得写了近三个小时，即使使用ai也不见得提高多少速度。其实高数的题目整体不算难，只要考前稍微做一点题，基本都能覆盖到。再加上稳定的心态，我个人感觉，有些人甚至可以拿满分，当然我是做不到了/(ㄒoㄒ)/~~



 <div text-center>
  <img src="\images\maths\mat.png" alt="t1" width="100%" />
</div>




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
