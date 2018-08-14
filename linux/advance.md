# Linux 进阶

## [jq](https://stedolan.github.io/jq/)

a lightweight and flexible command-line **JSON processor**

jq类似于JSON数据的sed——可以使用它对json进行切片、过滤、映射和转换结构化数据，就像[sed](/linux/command.md)、[awk](/linux/command.md)、[grep](/linux/command.md)轻松处理文本一样。

除了处理json的jq以外，还有其他的处理器。

* 处理xml的[XMLStarlet](http://xmlstar.sourceforge.net)
* 处理html的[pup](https://github.com/ericchiang/pup)。
* 处理yaml的[yq](https://github.com/mikefarah/yq)

### jq如何使用？

[命令行 JSON 处理工具 jq 的使用介绍](https://www.ibm.com/developerworks/cn/linux/1612_chengg_jq/index.html)

[jqplay](https://jqplay.org/)

安装

* mac`brew install jq`

* linux `apt-get install jq`

使用

stdin -&gt; jq &lt;filter&gt; -&gt; stdout

jq &lt;filter&gt; file -&gt; stdout

逐行输入

* read from stdin
* write to stdout

curl -s  ... \| jq ...

echo ... \| jq ...

cat ... \| jq ...

文件输入

* read from file

* write to stdout

jq .. file.json

`Usage: jq [options] <jq filter> [file...]`

[具体使用手册](https://stedolan.github.io/jq/manual/)

<iframe src="//www.slideshare.net/slideshow/embed_code/key/LMugvo5j5jl9EJ" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe>
<div style="margin-bottom:5px">
<strong><a href="//www.slideshare.net/btiernay/jq-json-like-a-boss" title="jq: JSON - Like a Boss" target="_blank">jq: JSON - Like a Boss
</a></strong>from<strong><a href="https://www.slideshare.net/btiernay" target="_blank">Bob Tiernay</a></strong> </div>

