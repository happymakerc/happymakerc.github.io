## 1. 介绍

官网文档：[docsify](https://docsify.js.org/#/zh-cn/)

> 一个神奇的文档网站生成器。

参考网站：

[字节飞扬](https://bytesfly.github.io/blog/#/README)

#### 说明

* 把`js`和`css`的链接全部改成本地的，从 `unpkg`下载。否则的话，链接挂了，网站就没了，参考 `jsdeliver`

> 下载工具 [python的unpkg下载小工具](https://www.jianshu.com/p/6b58bdc9fc6f)

* Github Pages 运行在`/docs` 文件夹下

## 目录说明

```bash
├── favicon.svg	网站图标
├── index.html	网站主页
├── plugins		插件目录
├── posts		文章目录（通过basePath 配置项设置）
│   ├── _coverpage.md	封面
│   ├── _navbar.md		导航栏
│   ├── README.md		主页
│   └── _sidebar.md		侧边栏
├── prism		prism 各语言 js文件存放目录
├── themes		主题
└── .nojekyll 	用于阻止 GitHub Pages 忽略掉下划线开头的文件，是个空文件
```



## 新加文件

- 维护主目录 `/posts/README.md`
- 维护侧边栏 `_sidebar.md`(同目录下)
