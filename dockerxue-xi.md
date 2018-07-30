# Docker解决的问题

* 环境配置
  > 环境配置如此麻烦，换一台机器，就要重来一次，旷日费时。很多人想到，能不能从根本上解决问题，软件可以带环境安装？也就是说，安装的时候，把原始环境一模一样地复制过来。

可以用虚拟机解决，但使用虚拟机还原软件的原始环境有以下缺点

1. 资源占用多
2. 冗余步骤多
3. 启动慢

# Docker原理

Linux容器 Linux Containers,LXC

> 容器有点像轻量级的虚拟机，能够提供虚拟化的环境，但是成本开销小得多

Docker属于Linux容器的一种封装，提供简单易用的容器使用接口。目前最流行的Linux容器解决方案。

Docker 的接口相当简单，用户可以方便地创建和使用容器，把自己的应用放入容器。容器还可以进行版本管理、复制、分享、修改，就像管理普通的代码一样。

参考视频：[https://www.youtube.com/watch?v=YFl2mCHdv24](https://www.youtube.com/watch?v=YFl2mCHdv24)

参考文章:http://www.ruanyifeng.com/blog/2018/02/docker-tutorial.html









