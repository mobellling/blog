---
publishDate: 2026-10-31T12:00:00Z
author: Mobell
title: 移动的“桌面”——如何在安卓设备中实现Linux
excerpt: 随着移动办公和学习的需求日渐显露，在便携设备中使用桌面操作系统的需求也不可忽视。安卓系统的内核基于Linux，天然适用于Linux系统的搭建，而Linux作为强力的桌面级系统，若能运行在移动设备上，能大大提高我们的生产效率。本篇文章，就是在安卓设备没有root的情况下，搭建Linux系统的教程。
image: https://mobellling.github.io/-image-/Linux.webp
imageAlt: Animi girl
category: Host
tags:
  - linux
  - 安卓
  - Android
  - 教程
  - termux
  - VNC
---
## 准备工具

- 安卓设备（平板或手机，越新越好最好是 Android 7 以上）
- Termux（终端，输入命令的地方）
- VNC（显示图形化桌面的地方）

## 开始
可以参考

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=922458285&bvid=BV16u4y1M7yG&cid=1373006711&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

请做好不断失败的准备（我也是失败了5次才真正部署成功），享受折腾的过程不也非常美好吗？

常见问题：  
- 为什么我的操作和教程一样，却总是报错，卡在某一步？ 除去网络因素的话，应该是termux版本不对，建议在Github安装最新版本。
- 为什么下载这么慢？ 没办法，Linux发行版的官方源都在国外，网络延时肯定很大。可以试着切换国内的镜像源，比如清华、中科大、阿里云等等。请自行搜索或ai。
- 我的版本下载错了，怎么删除？ 脚本自带移除容器的功能，请自行查找。
- 为什么我的Linux无法运行软件？ 使用非沙盒模式打开软件,命令行输入
```
软件名 --no-sandbox
```
  
- 因为我们是在proot容器中运行的系统，部分软件不支持（比如微信）或不适配（比如WPS）。


### 下载软件

1. 下载termux，国内应用商店应该搜不到，GooglePlay的版本又太低，建议直接在[Github的官方仓库](https://github.com/termux/termux-app)中下载安装包。

2. 下载VNC，这是远程桌面软件，由于termux只能显示命令行界面，所以我们需要将桌面投放到VNC来显示。VNC可以在GooglePlay中找到。

### termux中的操作

1. 打开termux，你会看到命令窗口，这里就是我们执行命令的地方。输入  
```pkg update```  
来更新软件库。

如果有询问我们是否继续，输入y，回车即可。之后遇到所有询问的地方输入y回车即可。

由于手动部署容器和系统是非常麻烦的，好在有前人为我们铺平了道路，感谢[2MOE](https://github.com/2moe/tmoe)大佬为我们提供了一键安装脚本,让我们只需要一行命令就可以全自动安装。

完成更新后，输入以下代码,注意大小写：
```
bash -c "$(curl -L l.tmoe.me)"
```
回车等待，提示我们是否继续，输入y回车。弹出文件访问权限的提示框，授予权限即可。

跑完代码后，出现选择语言界面，保持默认中文即可。

2. 安装容器。在新弹出的窗口中选择第一项proot容器，开始安装容器。选项全部输入y即可。跑完代码后又返回到选择页面，仍然选择proot，回车，选择终端配色，字体，termux.properties，保持默认回车就行。

到安装共享sd目录的页面，这是你的Linux和Android的共享目录，可以参考上面的提示，也可以手动指定。
>ps：在文件管理器长按文件夹，点击详情，可以显示文件夹路径

共性home目录默认即可。

接着，询问容器架构，选第一个arm64发行版列表，选择你要安装的发行版，推荐新手选择Ubuntu（当然你想挑战自己的话可以选择Arch）。

以Ubuntu为例，选择后会提示选择系统版本，我个人建议选择长期支持的版本.

下一步选择启动容器。接着就是少女祈祷中……，开始安装系统。

3. 安装系统。在过程中会弹出新建sudo用户（管理员用户）的提示，选择<是>，输入用户名和密码，记住你的密码，接下来所有选项保持默认，继续跑代码。

几秒钟后，开始选择图形界面，由于没有root，选择rootless。根据自己的爱好和上面的提示，选择一个桌面就行。

接着问你是否安装软件包合集，这个怎么说呢，好处是可以把一些必要的软件给你安装完毕，就不用你再进系统装软件了（毕竟新手的话很难知道Linux的软件安装方法），但是坏处呢就是它会极大拖慢你的系统安装速度，如果你的网络情况不好，接下来的时间可能会有亿点长，看个人酌情选择吧。

其他保持默认。

到设置VNC访问密码的步骤，设置一个记得住的密码，之后要用。端口保持默认。分辨率根据自己设备的情况选择。

最后弹出VNC Commands，选择<确定>，然后返回到安装桌面的界面，选择取消，返回到第一页，退出即可。

等代码跑完，我们的系统就成功安装好了。

4. 此时终端应该会自动进入系统，如果没有，就输入指令```debian```来进入；如果界面卡死，删后台重进即可。

进入系统后，输入```startvnc```开启vnc服务，这时，程序会给我们一个类似于```198.168.0.1:5902```地址，进入VNC，点击右下角加号，输入这个地址和名称，点击connect，将warn me every time的开关取消掉，输入访问vnc的密码，然后就能看见你的系统桌面了。

### 在Linux系统中的操作

可以在系统内的终端中输入```tmoe```来打开脚本菜单，里面配置了很多常用的软件，可以一键下载，这里推荐先下载一个浏览器，方便我们以后下载其它软件。

Linux的终端可以实现对系统的所有操作，其使用可以自行搜索，在这里不过多赘述。

现在，你就拥有了一个便携版的桌面系统。

## 我的曲折经历
![error](https://mobellling.github.io/-image-/linux/1.webp)
![error](https://mobellling.github.io/-image-/linux/2.webp)
![error](https://mobellling.github.io/-image-/linux/3.webp)
![error](https://mobellling.github.io/-image-/linux/4.webp)
![error](https://mobellling.github.io/-image-/linux/5.webp)
![error](https://mobellling.github.io/-image-/linux/6.webp)
![error](https://mobellling.github.io/-image-/linux/7.webp)
![error](https://mobellling.github.io/-image-/linux/8.webp)
![error](https://mobellling.github.io/-image-/linux/9.webp)

在折腾 Linux 的整个过程中，几乎每一步都在与“意料之外”的错误撞怀。漫无目的地翻找各种技术教程，一遍又一遍地把报错信息复制给 AI 询问求助，甚至在面对一行行冰冷冗长的红色报错提示（No command found、gyp ERR!、各种架构与依赖冲突）时，陷入过深深的自我怀疑。你会忍不住想：为什么别人几步就能装好的环境，到我这里却处处踩坑？为什么我的设备总显得这么“不听话”？

但庆幸的是，虽然我也想过放弃，但我没有半途而废，一直死磕到了最后。下载的系统不一样？删了重新来！文件打不开？删了再下载！命令找不到？重新安装！

当所有的依赖补齐、变量配好、服务成功跑起来的那一瞬间，那种激动是无与伦比的。相比于一帆风顺的按部就班，这种历经多次折败、反复拆解问题后迎来的成功，带来的是一种更深沉、也更纯粹的快乐。

**探身迈入自己完全不熟悉的领域，在前辈留下的文档视频或 AI 技术的指引下，凭借自己的双手一步步去摸索、去试错。遇到阻碍时，不再纠结于“为什么我和别人不一样”的内耗，而是把注意力转为积极寻找解决办法——去思考“我该怎么做才能让它成功”。**

这次尝试，是对自我解决问题能力的一次极佳印证。只要愿意多想、敢于死磕，就没有跨不过去的坎。


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