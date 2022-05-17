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



---

## 1. 介绍

官网文档：[docsify](https://docsify.js.org/#/zh-cn/)

> 一个神奇的文档网站生成器。

参考网站：

[字节飞扬](https://bytesfly.github.io/blog/#/README)

#### 说明

把`js`和`css`的链接全部改成本地的，从 `unpkg`下载。否则的话，链接挂了，网站就没了，参考 `jsdeliver`

下载工具 [python的unpkg下载小工具](https://www.jianshu.com/p/6b58bdc9fc6f)



## 2. 基础设置

#### 1. 初始化

新建 `docs/`文件夹

```bash
cd docs
docker pull sujaykumarh/docsify
# 初始化项目
docker run --rm -v $(pwd):/docs sujaykumarh/docsify init
# 运行项目
docker run --rm -v $(pwd):/docs -p 3000:3000 -it sujaykumarh/docsify serve
```

在使用 docker 过程中，有**权限**问题 可以 在`docker run `中使用

```bash
-u root
```

**注意**: docker 初始化项目生成的文件所有人 可能是root

```bash
# 递归修改所有人，所有组
chown -R user:group folder
```



#### 2. 主题

使用默认的 vue 主题



#### 3. 配置项

```js
window.$docsify = {
    // 项目名称
    name: '记着积极记笔记',
    // 仓库地址，点击右上角的Github章鱼猫头像会跳转到此地址
    repo: 'https://github.com/sqdjn/sqdjn.github.io',
    basePath: '/posts/',
    // 侧边栏支持，默认加载的是项目根目录下的_sidebar.md文件
    loadSidebar: true,
    // 导航栏支持，默认加载的是项目根目录下的_navbar.md文件
    loadNavbar: true,
    // 封面支持，默认加载的是项目根目录下的_coverpage.md文件
    coverpage: true,
    onlycover: true,
    // 最大支持渲染的标题层级
    maxLevel: 5,
    // 自定义侧边栏后默认不会再生成目录，设置生成目录的最大层级（建议配置为2-4）
    subMaxLevel: 2,
    // 小屏设备下合并导航栏到侧边栏
    mergeNavbar: true,
    // 切换页面，自动跳转到顶部
    auto2top: true,
    search: {
        maxAge: 86400000,// 过期时间，单位毫秒，默认一天
        paths: 'auto',
        placeholder: '搜索',
        noData: '找不到结果！',
        depth: 2,
        hideOtherSidebarContent: false,
        namespace: 'website-1',
    }
}
```



## 3. 插件

- 搜索
- emoji
- 图片缩放
- 复制到粘贴板
- docsify-tabs

```markdown
开始
<!-- tabs:start -->
结束
<!-- tabs:end -->
标签
<!-- tab:title1 -->
```

- 代码高亮
