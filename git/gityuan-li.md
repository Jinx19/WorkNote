# Git起步

> 直接记录快照，而非差异比较

Git是把数据看作是对小型文件系统的一组快照。每次你提交更新，或在 Git 中保存项目状态时，它主要对当时的全部文件制作一个快照并保存这个快照的索引。

## Git配置

每台计算机上只需要配置一次，程序升级时会保留配置信息。 你可以在任何时候再次通过运行命令来修改它们。

Git 自带一个`git config`的工具来帮助设置控制 Git 外观和行为的配置变量。 这些变量存储在三个不同的位置：

1. `/etc/gitconfig`文件: 包含系统上每一个用户及他们仓库的通用配置。 如果使用带有`--system`选项的`git config`时，它会从此文件读写配置变量。

2. `~/.gitconfig`或`~/.config/git/config`文件：只针对当前用户。 可以传递`--global`选项让 Git 读写此文件。

3. 当前使用仓库的 Git 目录中的`config`文件（就是`.git/config`）：针对该仓库。

每一个级别覆盖上一级别的配置，所以`.git/config`的配置变量会覆盖`/etc/gitconfig`中的配置变量。

> 如果使用了`--global`选项，那么该命令只需要运行一次，因为之后无论你在该系统上做任何事情， Git 都会使用那些信息。 当你想针对特定项目使用不同的用户名称与邮件地址时，可以在那个项目目录下运行没有`--global`选项的命令来配置。

## 三种状态

* 已提交commited 已提交表示数据已经安全的保存在本地数据库中
* 已修改modified 已修改表示修改了文件，但还没保存到数据库中
* 已暂存staged 已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中

Git的三个工作区域：Git仓库,工作目录，暂存区域

### ![](/assets/1*zw0bLFWkaAP2QPfhxkoDEA.png)

## 获得帮助

```
git help <verb>
git help <verb> --help

example:
git help diff
```

### 参考:

[https://hackernoon.com/understanding-git-index-4821a0765cf](https://hackernoon.com/understanding-git-index-4821a0765cf "Understanding Git — Index")

