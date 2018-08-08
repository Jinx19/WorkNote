# Docker 入门

# Docker解决的问题

* 环境配置
  > 环境配置如此麻烦，换一台机器，就要重来一次，旷日费时。很多人想到，能不能从根本上解决问题，软件可以带环境安装？也就是说，安装的时候，把原始环境一模一样地复制过来。

可以用虚拟机解决，但使用虚拟机还原软件的原始环境有以下缺点

1. 资源占用多
2. 冗余步骤多
3. 启动慢

# Docker原理

容器是一种轻量级虚拟化。

> 容器有点像轻量级的虚拟机，能够提供虚拟化的环境，但是成本开销小得多

Docker属于Linux容器 Linux Containers,LXC的一种封装，提供简单易用的容器使用接口。目前最流行的Linux容器解决方案。

> Docker,Build,Ship and Run Any App,Anywhere 一次封装，到处运行。

Docker为应用的开发、运行和部署提供一站式的解决方案。

## 容器技术

![](/assets/virtual-private-cloud-with-container-technologies-for-devops-9-638.jpg)

## Docker 与虚拟机的比较

|  | Docker | 虚拟机 |
| :--- | :--- | :--- |
| 速度 | 启动和停止秒级实现 | 需要数分钟 |
| 资源 | 资源需求很少,一台主机可以同时运行数千个Docker容器 |  |
| 版本控制 | Docker通过类似Git设计理念，方便用户获取、分发和更新应用镜像，存储复用。 |  |
| 创建 | 可以通过Dockerfile灵活自动化创建和部署，提高工作效率。 |  |
| 消耗 | Docker除了运行其中应用外,基本不消耗额外的系统资源，保证应用性能的同时，尽量减少系统开销。 | 运行N个不同的应用 |

Docker 的接口相当简单，用户可以方便地创建和使用容器，把自己的应用放入容器。容器还可以进行版本管理、复制、分享、修改，就像管理普通的代码一样。

参考视频：[https://www.youtube.com/watch?v=YFl2mCHdv24](https://www.youtube.com/watch?v=YFl2mCHdv24)

参考文章:[http://www.ruanyifeng.com/blog/2018/02/docker-tutorial.html](http://www.ruanyifeng.com/blog/2018/02/docker-tutorial.html)

参考文章:[https://yeasy.gitbooks.io/docker\_practice/image/build.html](https://yeasy.gitbooks.io/docker_practice/image/build.html)

# Docker相关文件

## Image 文件

Docker 把应用程序及其依赖，打包在 image 文件里面。Docker 根据 image 文件生成容器的实例。同一个 image 文件，可以生成多个同时运行的容器实例。

实际开发中，一个 image 文件往往通过继承另一个 image 文件。

为了方便共享，image 文件制作完成后，可以上传到网上的仓库。Docker 的官方仓库[Docker Hub](https://hub.docker.com/)是最重要、最常用的 image 仓库。

## Container文件

image 文件生成的容器实例，本身也是一个文件，称为容器文件。也就是说，一旦容器生成，就会同时存在两个文件： image 文件和容器文件。

## Dockerfile文件

学会使用 image 文件以后，接下来的问题就是，如何可以生成 image 文件？如果你要推广自己的软件，势必要自己制作 image 文件。这就需要用到 Dockerfile 文件。它是一个文本文件，用来配置 image。Docker 根据 该文件生成二进制的 image 文件。Dockerfile 逐行执行命令。Docker会重用cache,尤其在docker build时。

### Dockerfile格式及相关命令

```
#Comment
INSTRUCTION arguments
```

#### FROM

> 指定基础镜像 base image
>
> Dockerfile必需以FROM 指令开始。

```
FROM <image> [AS <name>]

Or

FROM <image>[:<tag>] [AS <name>]

Or

FROM <image>[@<digest>] [AS <name>]
```

FROM前面可以加ARG,但ARG不能被FROM后面任何命令使用

#### RUN

```
RUN <command> (shell form)
```

可以使用\来连接shell命令

#### CMD

Dockerfile文件只能有一个CMD指令。为容器指定一些默认指令。

* `CMD ["executable","param1","param2"]`\(\_exec\_form, this is the preferred form\)
* `CMD ["param1","param2"]`\(as _default parameters to ENTRYPOINT_\)
* `CMD command param1 param2`\(\_shell \_form\)

#### LABEL

添加元数据。key-value对。

```
LABEL "com.example.vendor"="ACME Incorporated"
LABEL com.example.label-with-value="foo"
LABEL version="1.0"
```

#### EXPOSE

```
EXPOSE <port> [<port>/<protocol>...]
```

指定容器监听设置的网络端口。

#### ENV

```
环境变量
ENV <key> <value>
ENV <key>=<value>...
```

#### ADD

```
ADD [--chown=<user>:<group>] <src>...<dest>
ADD [--chown=<user>:<group>] ["<src>,...<dest>"]
```

ADD指令将&lt;src&gt;的文件，目录或远端文件url复制到镜像中的&lt;dest&gt;目录下

```
ADD hom* /mydir/        # adds all files starting with "hom"
```

#### COPY

和add类似，但不能复制url文件

