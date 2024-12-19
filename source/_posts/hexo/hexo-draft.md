---
title: hexo draft
date: 2024-12-18 00:40:31
tags: hexo
---

## 传统建立文章方式

一般我们都会使用 `hexo new <title>` 来建立文章，这种建立方法会将新文章建立在 `source/_posts` 目录下，当使用 `hexo generate` 编译 markdown 文件时，会将其 HTML 结果编译在 `public` 目录下，之后 `hexo deploy` 将会把 `public` 目录下所有文章部署到 GitHub，这是我们熟悉的 Hexo 流程。

这种建立文章方式的缺点是：若我们同时编辑多篇文章，只要其中一篇文章尚未编辑完成，也会随着 `hexo deploy` 一起部署到 GitHub，也就是 GitHub 可能会看到我们尚未完成的文章。

## 建立文章草稿

```
$ hexo new draft <title>
```

Hexo 另外提供 `draft` 机制，它的原理是新文章将建立在 `source/_drafts` 目录下，因此 `hexo generate` 并不会将其编译到 `public` 目录下，所以 `hexo deploy` 也不会将其部署到 GitHub。

## 本机预览草稿

```
$ hexo S --draft
```

虽然 `hexo generate` 不会编译 `source/_drafts` 目录下的文章，但 Hexo 的 `Hexo server` 另外提供 `--draft` 参数，这让我们只要搭配 `hexo-browsersync` plugins，就可以达到一边编辑 `markdown` 文章，一边使用浏览器预览的目的。

## 将草稿发布为正式文章

```
$ hexo P <filename>
```

其中 `<filename>` 为不包含 `md` 后缀的文章名称。它的原理只是将文章从 `source/_drafts` 移动到 `source/_posts` 而已。

之后的 `hexo generate` 与 `hexo deploy` 的用法就完全一样了。

若日后想将正式文章转为为草稿，只需手动将文章从 `source/_posts` 目录移动到 `source/_drafts` 目录即可。



## Reference

[Hexo 文章保存为草稿 | novnan's notes](https://novnan.github.io/Hexo/hexo-draft/)
