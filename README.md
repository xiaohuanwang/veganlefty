#                              Docsify快速搭建文档

- ## docsify

  > 一个神奇的文档网站生成器。

  ## docsify 概述

  docsify 可以快速帮你生成文档网站。不同于 GitBook、Hexo 的地方是它不会生成静态的 `.html` 文件，所有转换工作都是在运行时。如果你想要开始使用它，只需要创建一个 `index.html` 就可以开始编写文档并直接[部署在 GitHub Pages](zh-cn/deploy.md)。

  查看[快速开始](zh-cn/quickstart.md)了解详情。

  ## 特性

  - 无需构建，写完文档直接发布
  - 容易使用并且轻量 (压缩后 ~21kB)
  - 智能的全文搜索
  - 提供多套主题
  - 丰富的 API
  - 支持 Emoji
  - 兼容 IE11
  - 支持服务端渲染 SSR ([示例](https://github.com/docsifyjs/docsify-ssr-demo))

# 快速开始

推荐全局安装 `docsify-cli` 工具，可以方便地创建及在本地预览生成的文档。

```bash
npm i docsify-cli -g
```

## 初始化项目

如果想在项目的 `./docs` 目录里写文档，直接通过 `init` 初始化项目。

```bash
docsify init ./docs
```

## 开始写文档

初始化成功后，可以看到 `./docs` 目录下创建的几个文件

- `index.html` 入口文件
- `README.md` 会做为主页内容渲染
- `.nojekyll` 用于阻止 GitHub Pages 忽略掉下划线开头的文件

直接编辑 `docs/README.md` 就能更新文档内容，当然也可以[添加更多页面](zh-cn/more-pages.md)。

## 本地预览

通过运行 `docsify serve` 启动一个本地服务器，可以方便地实时预览效果。默认访问地址 http://localhost:3000 。

```bash
docsify serve docs
```

?> 更多命令行工具用法，参考 [docsify-cli 文档](https://github.com/docsifyjs/docsify-cli)。

## 手动初始化

如果不喜欢 npm 或者觉得安装工具太麻烦，我们可以直接手动创建一个 `index.html` 文件。

*index.html*

```html
<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <meta charset="UTF-8">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/vue.css">
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      //...
    }
  </script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
</body>
</html>
```

如果你的系统里安装了 Python 的话，也可以很容易地启动一个静态服务器去预览你的网站。

```python2
cd docs && python -m SimpleHTTPServer 3000
```

```python3
cd docs && python -m http.server 3000
```

## Loading 提示

初始化时会显示 `Loading...` 内容，你可以自定义提示信息。


```html
  <!-- index.html -->

  <div id="app">加载中</div>
```


