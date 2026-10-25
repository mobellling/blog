---
publishDate: 2026-10-24T12:55:00Z
author: Mobell
title: 网站建成的第一天
excerpt: 花费了一点时间建成了这个网站，本意是记录一下我在虚拟代码世界的心路历程，但是建立网站也太难了，从头学习前端开发，太复杂了。前前后后两天的时间，也就弄成这个样了，凑活着用吧……
image: https://images.unsplash.com/photo-1502101872923-d48509bff386?ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80
imageAlt: Two toddlers standing at the bottom of a beige concrete staircase
category: Tutorials
tags:
  - astro
  - web
  - 网站
  - 第一天
---
## 前言
在这个信息爆炸、算法推荐将我们包裹在各类短视频和社交平台流里的时代，我常常感到一种莫名的精神消耗。所有的内容都在追求“快”和“爽”，却很少有属于自己的一方净土。

在大佬陈同学的启发下，我萌生了一个质朴的想法：我想要一个完全属于自己的、由我做主的网站。

## 开端
为什么想要一个属于自己的网站？
很大一部分原因，是由于看到陈同学在弄这玩意（不知道为什么），自己也想做一下，可无奈技术力不够，一边翻阅教程，一边求助ai，实在不行，就请教陈大佬。

于是，从零开始的“折腾”之旅开始了……

## 阻碍
作为一个非根正苗红的前端大神，刚决定动手时，内心其实是有些打鼓的。从选择用什么框架，到面对陌生的命令行，过程并不总是一帆风顺。

<div align="center">
  <img src="/images/warn.png" alt="报错" width="70%" />
</div>

工具：打开 VS Code，面对黑漆漆的终端，看着偶尔蹦出来的英文报错（比如让人头疼的网络连接超时、配置代理、Git 权限冲突）和全英文的工具网站，我抓耳挠腮，抱怨不止。但是最后还是选择一步一步坚持下来，自己不会的地方问ai，问大佬，对着成千上百行的代码“全局搜索”，一点一点排查warn原因。终于，网站正常运行了。

细节：然而，网站搭好之后，最让人上头的环节开始了——魔改（DIY）。虽然只是改改网站图标、调整导航栏的布局、把自己的 Logo 和名字放在左上角，为了让图标和文字乖乖排在同一行，反复调整 CSS 弹性盒和对齐属性，但却花费了我不少的时间，因为我对这些前端代码完全不敏感，不知道在什么地方调整想要的东西。在帮助文档和ai的帮助下，一个简单的小网页还是出来了。

远航：这只是一个开始，当把代码推送到 GitHub，通过 Netlify 一键部署，发现我辛辛苦苦修改的代码完全无法运行，我的心态是崩溃的。

<div align="center">
  <img src="/images/pagenotfound.png" alt="找不到页面" width="100%" />
</div>

由于网站是全英文的，没有任何中文翻译，我很难找到究竟应该修改哪里。在本地能正常运行，放在托管网站上却无法显示，这显然是网站配置没有调节好。

感谢大模型！感谢陈大佬！在我多次尝试未果后，我果断请求陈同学的帮助。很幸运，摸索过后，我们发现，astro的默认输出目录是dist，而Netlify并不知道这一点，需要手动输入。与英文界面斗智斗勇近半个小时后，我们终于解决了问题！

<div align="center">
  <img src="/images/dist.png" alt="dist" width="100%" />
</div>

## 结语
我明白自己掌握的知识只是冰山一角，这个网站还有许多我不知道的功能和页面，我只是实现了它最基础的功能。但拥有一个独立网站，最大的意义不是它有多么绚丽，而在于它由自己亲手编写。在这个瞬息万变的互联网上，我们拥有了一个永远不会关门、随时欢迎我回来驻足的虚拟空间。

未来，这里将记录我的技术心得、踩坑记录，以及那些稍纵即逝的灵感与生活碎碎念。

我的数字世界，正式开张！
<script src="https://giscus.app/client.js"
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