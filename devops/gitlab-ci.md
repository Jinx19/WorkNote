# GitLab介绍

GitLab 是一个Git服务器，一个数据库支持的 web 应用.可以通过虚拟机或docker来安装gitlab服务器。

从 [https://bitnami.com/stack/gitlab](https://bitnami.com/stack/gitlab) 获取一键安装包,[bitnami使用指南](https://docs.bitnami.com/virtual-machine/apps/gitlab/)。![](/assets/屏幕快照 2018-08-08 下午9.50.35.png)![](/assets/屏幕快照 2018-08-08 下午9.51.01.png)

也可以使用docker,参照：[https://hub.docker.com/r/gitlab/gitlab-ce/](https://hub.docker.com/r/gitlab/gitlab-ce/)

#### 钩子 {#_钩子}

GitLab 在项目和系统级别上都支持钩子程序。 对任意级别，当有相关事件发生时，GitLab 的服务器会执行一个包含描述性 JSON 数据的 HTTP 请求。 这是自动化连接你的 git 版本库和 GitLab 实例到其他的开发工具，比如 CI 服务器，聊天室，或者部署工具的一个极好方法。

[如何跟别人解释Gitlab？](https://about.gitlab.com/2016/11/30/how-to-explain-gitlab-to-anyone/)

