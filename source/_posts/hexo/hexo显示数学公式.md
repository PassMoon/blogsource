---
layout: blog
title: hexo显示数学公式
date: 2024-12-20 00:33:23
tags:
---

在做笔记的时候，发现公式显示不了，最后决定还是使用和 VsCode 一样的 KaTeX

首先去你的_config.butterfly.yml 配置文件中关闭 mathjax 并打开 KaTex

之后执行下面的命令卸载掉原来的渲染器

```bash
npm un hexo-renderer-marked --save
```

之后再安装新的渲染器

```bash
npm i hexo-renderer-markdown-it-katex
```

在_config.yml 中最后的部分配置以下字段

```yml
markdown:
  render:
    html: true
    xhtmlOut: false
    breaks: true
    linkify: true
    typographer: true
  plugins:
  anchors:
    level: 1
    collisionSuffix: ''
```

最后 hexo clean,hexo g ，之后就可以用了.

感谢 F10atingHeart，这个方式最方便且不用更改源文件

[butterfly 主题配置 KaTex | 回忆宫殿](https://mralridge.github.io/2024/07/30/butterfly主题配置KaTex/index.html)
