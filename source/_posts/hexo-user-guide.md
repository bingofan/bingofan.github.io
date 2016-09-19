---
title: Hexo使用笔记
tags: Hexo
categories: Hexo
toc: true
description: >-
  记录平时常用的一些Hexo命令. 部分转载[Hexo Docs](http://www.ituring.com.cn/article/198930)
  [官方文档](https://hexo.io/docs/)
date: 2016-09-06 18:03:35
---


### 新建文章

```shell
hexo new [layout] <title>
```
**[layout]**
`post`  source/_posts
`page`  source
`draft` source/_draft

### 前置申明

```shell
title: Hexo使用笔记
tags: Hexo
categories: Hexo
toc: true
description: >-
	记录平时常用的一些Hexo命令.
```

*   `:title` 文章标题
*   `:tags` 文章标签
*   `:categories` 文章分类
*   `:toc` 是否生成目录
*   `description` 文章摘要
*   `layout` 布局
*   `date` 创建时间
*   `updated` 修改时间
*   `comments` 是否开启评论，默认为true 
*   `permalink` 文章永久链接

<!-- more -->

多级标签及分类
```shell
categories: 
- Sports
- Baseball
tags:
- Injury
- Fight
- Shocking

```

### 草稿发布

```shell
hexo publish [layout] <title>
```

### 模 板

`scaffolds`文件夹下
```
hexo new [templet] <title>
```

### 标签插件
_（1）Block Quote-块引用_

插入带有作者信息的应用，体现在Html上就是在`blockquote`标签下加入了`footer`标签。但是会给文章带来不一样的显示效果，书写格式非常简单。

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}

```


_（2）Freemind样式_

1.文本
```
{% textcolor muted %}
Fusce dapibus, tellus ac cursus commodo, tortor mauris nibh.
{% endtextcolor %}

{% textcolor primary %}
Nullam id dolor id nibh ultricies vehicula ut id elit.
{% endtextcolor %}

{% textcolor success %}
Duis mollis, est non commodo luctus, nisi erat porttitor ligula.
{% endtextcolor %}

{% textcolor info %}
Maecenas sed diam eget risus varius blandit sit amet non magna.
{% endtextcolor %}

{% textcolor warning %}
Etiam porta sem malesuada magna mollis euismod.
{% endtextcolor %}

{% textcolor danger %}
Donec ullamcorper nulla non metus auctor fringilla.
{% endtextcolor %}
```
{% textcolor muted %}Fusce dapibus, tellus ac cursus commodo, tortor mauris nibh.{% endtextcolor %}

{% textcolor primary %}Nullam id dolor id nibh ultricies vehicula ut id elit.{% endtextcolor %}

{% textcolor success %}Duis mollis, est non commodo luctus, nisi erat porttitor ligula.{% endtextcolor %}

{% textcolor info %}Maecenas sed diam eget risus varius blandit sit amet non magna.{% endtextcolor %}

{% textcolor warning %}Etiam porta sem malesuada magna mollis euismod.{% endtextcolor %}

{% textcolor danger %}Donec ullamcorper nulla non metus auctor fringilla.{% endtextcolor %}
.

2.按钮
```
{% btn http://hahack.com hahack %}

{% btn http://hahack.com hahack primary %}

{% btn http://hahack.com hahack success %}

{% btn http://hahack.com hahack warning %}

{% btn http://hahack.com hahack danger %}

{% btn http://hahack.com hahack info %}
```

{% btn http://hahack.com hahack %}

{% btn http://hahack.com hahack primary %}

{% btn http://hahack.com hahack success %}

{% btn http://hahack.com hahack warning %}

{% btn http://hahack.com hahack danger %}

{% btn http://hahack.com hahack info %}
.

3.标签
```
{% label default %}

{% label warinng warning %}

{% label success success %}

{% label danger danger %}

{% label primary primary %}

{% label info info %}
```
{% label default %}

{% label warinng warning %}

{% label success success %}

{% label danger danger %}

{% label primary primary %}

{% label info info %}
.

4.徽章（Badges)
```
{% badge 42 %}
```
{% badge 42 %}
.

5.警报（Alerts)
```
{% alert warning %}
Best check yo self, you're not looking too good.
{% endalert %}

{% alert danger %}
Change a few things up and try submitting again.
{% endalert %}

{% alert success %}
You successfully read this important alert message.
{% endalert %}

{% alert info %}
This alert needs your attention, but it's not super important.
{% endalert %}
```
{% alert warning %}
Best check yo self, you're not looking too good.
{% endalert %}

{% alert danger %}
Change a few things up and try submitting again.
{% endalert %}

{% alert success %}
You successfully read this important alert message.
{% endalert %}

{% alert info %}
This alert needs your attention, but it's not super important.
{% endalert %}


_（3）Pull Quote_

这个插件可以帮助您在文章中插入重要引述。

```
{% pullquote [class] %}
content
{% endpullquote %}

```

_（4）jsFiddle_

在文章中嵌入jsFiddle片段。

```
{% jsfiddle shorttag [tabs] [skin] [width] [height] %}

```

_（5）Gist_

嵌入Gist片段

```
{% gist gist_id [filename] %}

```

_（6）iFrame_

插入网页框架

```
{% iframe url [width] [height] %}

```

_（7）Image_

插入图片，可以自定义大小

```
img [class names] /path/to/image [width] [height] [title text [alt text]]

```

_（8）Link_

插入带有target="_blank"属性值的链接。

```
link text url [external] [title]

```

_（9）Include Code_

从资源目录中插入代码片段。

```
{% include_code [title] [lang:language] path/to/file %}

```

_（10）Youtube_

在文章中插入Youtube视频。天朝的孩子就不用试了

```
{% youtube video_id %}

```

_（11）Vimeo_

在文章中插入Vimeo视频。

```
{% vimeo video_id %}

```

_（12）Include Posts_

包含其他文章的链接。

```
{% post_path slug %}
{% post_link slug [title] %}

```

_（13）Include Assets_

包含文章资源。_(具体怎么使用，还不太明白，后续再补充)_

```
{% asset_path slug %}
{% asset_img slug [title] %}
{% asset_link slug [title] %}

```

_（14）Raw_

一些内容不想被主题渲染，可以使用该插件呈现原始状态。

```
{% raw %}
content
{% endraw %}

```


### 生成器 服务器

```shell
hexo clean
hexo generate
hexo server
hexo deploy
```

可以通过`http://localhost:4000`或者`http://0.0.0.0:4000`访问
.

**指定IP**
`hexo server -i 192.168.1.1`
.

**指定端口**
`hexo server -p 5000`
.

**生成后马上部署**
`hexo g -d` or `hexo d -g`
.

**部署配置**
```shell
deploy:
    type: git
    repo: https://github.com/pengloo53/pengloo53.github.io.git
    branch: master
```


