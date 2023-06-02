

# 前端工程化与webpack

## 前端工程化

> **前端工程化指的是**：在企业级的前端项目开发中，把前端开发所需的工具、技术、流程、经验等进行规范化、
> 标准化。
> 	企业中的 Vue 项目和 React 项目，都是基于工程化的方式进行开发的。
> 	**好处：前端开发自成体系，有一套标准的开发方案和流程。**

### 前端工程化的解决方案

目前主流的前端工程化解决方案：

- webpack（ https://www.webpackjs.com/ ）
-  parcel（ https://zh.parceljs.org/ ）

## webpack

### webpack基本使用

#### 1.什么是 webpack

概念：webpack 是前端项目工程化的具体解决方案。
主要功能：它提供了友好的前端模块化开发支持，以及代码压缩混淆、处理浏览器端JavaScript 的兼容性、性
能优化等强大的功能。
好处：让程序员把工作的重心放到具体功能的实现上，提高了前端开发效率和项目的可维护性。
注意：目前 Vue，React 等前端项目，基本上都是基于 webpack 进行工程化开发的。

#### 2. 创建列表隔行变色项目

① 新建项目空白目录，并运行 npm init –y 命令，初始化包管理配置文件 package.json
② 新建 src 源代码目录
③ 新建 src -> index.html 首页和 src -> index.js 脚本文件
④ 初始化首页基本的结构
⑤ 运行 npm install jquery –S 命令，安装 jQuery
⑥ 通过 ES6 模块化的方式导入 jQuery，实现列表隔行变色效果

#### 3. 在项目中安装 webpack

在终端运行如下的命令，安装webpack 相关的两个包：

`npm install webpack@5.42.1 webpack-cli@4.7.2 -D`

#### 4. 在项目中配置 webpack

##### ① 在项目根目录中，创建名为 webpack.config.js 的 webpack 配置文件，并初始化如下的基本配置：![](ph/Vue/初始化配置.png)

##### ② 在 package.json 的 scripts 节点下，新增 dev 脚本如下：![](ph/Vue/新增 dev 脚本.png)

##### 4.1 mode的可选值

mode 节点的可选值有两个，分别是：
① development

- 开发环境
-  不会对打包生成的文件进行代码压缩和性能优化

打包速度快，适合在开发阶段使用
② production

- 生产环境
-  会对打包生成的文件进行代码压缩和性能优化
-  打包速度很慢，仅适合在项目发布阶段使用 

##### 4.2 webpack.config.js 文件的作用

webpack.config.js 是 webpack 的配置文件。webpack 在真正开始打包构建之前，会先读取这个配置文件，
从而基于给定的配置，对项目进行打包。

> 注意：由于 webpack 是基于 node.js 开发出来的打包工具，因此在它的配置文件中，支持使用 node.js 相关
> 的语法和模块进行 webpack 的个性化配置。 

##### 4.3 webpack 中的默认约定

在 webpack 4.x 和 5.x 的版本中，有如下的默认约定：
① 默认的打包入口文件为src -> index.js
② 默认的输出文件路径为dist -> main.js

> 注意：可以在 webpack.config.js 中修改打包的默认约定 

##### 4.4 自定义打包的入口与出口

在 webpack.config.js 配置文件中，通过 **entry 节点**指定**打包的入口**。通过 **output 节点**指定打包的出口。
示例代码如下：![](ph/Vue/自定义打包的入口与出口.png)

### webpack插件

#### 1. webpack 插件的作用

通过安装和配置第三方的插件，可以拓展webpack 的能力，从而让 webpack 用起来更方便。最常用的
webpack 插件有如下两个：

##### ① webpack-dev-server

- 类似于 node.js 阶段用到的 nodemon 工具
- 每当修改了源代码，webpack 会自动进行项目的打包和构建

##### ② html-webpack-plugin

- webpack 中的 HTML 插件（类似于一个模板引擎插件）
-  可以通过此插件自定 制index.html 页面的内容 

#### 2. webpack-dev-server

>  webpack-dev-server 可以让 webpack 监听项目源代码的变化，从而进行自动打包构建。

##### 2.1 安装 webpack-dev-server

###### 运行如下的命令，即可在项目中安装此插件：

`npm install webpack-dev-server@3.11.2 -D`

##### 2.2 配置 webpack-dev-server

###### ① 修改 package.json -> scripts 中的 dev 命令如下：

###### ② 在 package.json 的 scripts 节点下，新增 dev 脚本如下：

###### ③ 在浏览器中访问 http://localhost:8080 地址，查看自动打包效果

> 注意：webpack-dev-server 会启动一个实时打包的 http 服务器

##### 2.3 打包生成的文件哪儿去了？

###### ① 不配置 webpack-dev-server 的情况下，webpack 打包生成的文件，会存放到实际的物理磁盘上

- 严格遵守开发者在 webpack.config.js 中指定配置

 根据 output 节点指定路径进行存放

###### 	② 配置了 webpack-dev-server 之后，打包生成的文件存放到了内存中

- 不再根据 output 节点指定 的路径，存放到实际的物理磁盘上
-  提高了实时打包输出的性能，因为内存比物理磁盘速度快很多

##### 2.4 生成到内存中的文件该如何访问？

> webpack-dev-server 生成到内存中的文件，默认**放到了项目的根目录中**，而且是**虚拟的、不可见的**。

- 可以直接用 **/** 表示**项目根目录**，**后面跟上要访问的文件名称**，即可访问内存中的文件
-  例如 **/bundle.js** 就表示要访问 webpack-dev-server 生成到内存中的 bundle.js 文件

#### 3. html-webpack-plugin

>html-webpack-plugin 是 **webpack 中的 HTML 插件**，可以通过此插件**自定制** index.html **页面的内容**。
>**需求：**通过 html-webpack-plugin 插件，将 src 目录下的 index.html 首页，**复制到项目根目录中一份！**

##### 3.1 安装 html-webpack-plugin

运行如下的命令，即可在项目中安装此插件：
`npm install html-webpack-plugin@5.3.2 -D`

##### 3.2 配置 html-webpack-plugin

![](ph/Vue/配置 html-webpack-plugin.png)

###### 3.3 解惑 html-webpack-plugin

① 通过 HTML 插件复制到项目根目录中的 index.html 页面，**也被放到了内存中**
		② HTML 插件在生成的 index.html **页面**，**自动注入**了打包的 bundle.js 文件

#### 4. devServer 节点

> 在 webpack.config.js 配置文件中，可以通过 **devServer** 节点对 webpack-dev-server 插件进行更多的配置，
> 示例代码如下：

![](ph/Vue/devServer对 webpack-dev-server 配置.png)

> 注意：凡是修改了 webpack.config.js 配置文件，或修改了 package.json 配置文件，**必须重启实时打包的服**
> **务器**，否则最新的配置文件无法生效！

### webpack中的loader

#### 1. loader概述

> 在实际开发过程中，webpack 默认只能打包处理以 .js 后缀名结尾的模块。其他**非 .js 后缀名结尾的模块**，
> webpack 默认处理不了，**需要调用 loader 加载器才可以正常打包**，否则会报错！

loader 加载器的作用：**协助 webpack 打包处理特定的文件模块**。比如：

-  css-loader 可以打包处理 .css 相关的文件
-  less-loader 可以打包处理 .less 相关的文件
-  babel-loader 可以打包处理 webpack 无法处理的高级 JS 语法

#### 2. loader 的调用过程

![](ph/Vue/loader 的调用过程.png)

#### 3. 打包处理 css 文件

① 运行 npm i **style-loader@3.0.0 css-loader@5.2.6** -D 命令，安装处理 css 文件的 loader
		② 在 webpack.config.js 的 **module** -> **rules** 数组中，添加 loader 规则如下：

![](ph/Vue/打包css文件.png)

其中，**test** 表示匹配的**文件类型**， use 表示对应**要调用的 loader**
注意：
⚫ use 数组中指定的 loader **顺序是固定的**
⚫ 多个 loader 的调用顺序是：**从后往前调用**
webpack 中的 loader

#### 4.打包处理 less 文件

① 运行 npm i **less-loader@10.0.1 less@4.1.1** -D 命令
		② 在 webpack.config.js 的 **module** -> **rules** 数组中，添加 loader 规则如下

![](ph/Vue/打包处理 less 文件.png)

#### 5. 打包处理样式表中与 **url 路径相关**的文件

① 运行 npm i **url-loader@4.1.1 file-loader@6.2.0** -D 命令
		② 在 webpack.config.js 的 **module** -> **rules** 数组中，添加 loader 规则如下：

![](ph/Vue/打包处理样式表中与 url 路径相关的文件.png)

其中 **?** 之后的是 **loader 的参数项：**

- limit 用来指定**图片的大小**，单位是字节（byte）
-  只有 **≤** limit 大小的图 片，才会被转为base64 格式的图片

#### 6. 打包处理 js 文件中的高级语法

webpack 只能打包处理**一部分**高级的JavaScript 语法。对于那些 webpack 无法处理的高级 js 语法，需要借
助于 **babel-loader** 进行打包处理。例如 webpack 无法处理下面的 JavaScript 代码：

![](ph/Vue/打包处理 js 文件中的高级语法.png)

##### 6.1 安装 babel-loader 相关的包

运行如下的命令安装对应的依赖包：
npm i **babel-loader@8.2.2 @babel/core@7.14.6 @babel/plugin-proposal-decorators@7.14.5** -D

在 webpack.config.js 的 **module** -> **rules** 数组中，添加 loader 规则如下：

![](ph/Vue/安装 babel-loader 相关的包.png)

##### 6.2 配置 babel-loader

> 在项目根目录下，创建名为 babel.config.js 的配置文件，定义 Babel 的配置项如下：

```js
module.exports = {
    //声明babel可用的插件
    plugins:[['@babel/plugin-proposal-decorators',{legacy:true}]]
}

```

详情请参考 Babel 的官网 https://babeljs.io/docs/en/babel-plugin-proposal-decorators

## 打包发布

### 1.为什么要打包发布

**项目开发完成之后**，需要使用webpack **对项目进行打包发布**，主要原因有以下两点：
① 开发环境下，打包生成的文件**存放于内存中**，无法获取到最终打包生成的文件
② 开发环境下，打包生成的文件**不会进行代码压缩和性能优化**
**为了让项目能够在生产环境中高性能的运行**，因此需要对项目进行打包发布。

### 2. 配置 webpack 的打包发布

在 package.json 文件的 scripts 节点下，新增 build 命令如下：

![](ph/Vue/配置 webpack 的打包发布.png)

**--model** 是一个参数项，用来指定 webpack 的**运行模式**。production 代表生产环境，会对打包生成的文件
进行**代码压缩**和**性能优化。**

> 注意：通过 --model 指定的参数项，会**覆盖** webpack.config.js 中的 model 选项。

### 3. 把 JavaScript 文件统一生成到 js 目录中

在 webpack.config.js 配置文件的 output 节点中，进行如下的配置：

![](ph/Vue/配置webpack.config.js的output节点.png)

### 4.把图片文件统一生成到 image 目录中

> 修改 webpack.config.js 中的 **url-loader** 配置项，新增 **outputPath** 选项即可指定图片文件的输出路径：

![](ph/Vue/指定图片文件的输出路径.png)

### 5. 自动清理 dist 目录下的旧文件

为了在每次打包发布时**自动清理掉 dist 目录中的旧文件**，可以安装并配置**clean-webpack-plugin** 插件：

![](ph/Vue/自动清理 dist 目录下的旧文件.png)

## Source Map

### 1. 什么是 Source Map

>**Source Map 就是一个信息文件，里面储存着位置信息**。也就是说，Source Map 文件中存储着压缩混淆后的
>代码，所对应的**转换前的位置**。
>有了它，出错的时候，除错工具将**直接显示原始代码，而不是转换后的代码**，能够极大的方便后期的调试。

### 2.解决默认 Source Map 的问题

>开发环境下，推荐在 webpack.config.js 中添加如下的配置，即可保证运行时报错的行数与源代码的行数
>保持一致：

![](ph/Vue/解决默认 Source Map 的问题.png)

### 3. 只定位行数不暴露源码

在生产环境下，如果**只想定位报错的具体行数**，且**不想暴露源码**。此时可以将**devtool** 的值设置为:**nosources-source-map**

### 4. 定位行数且暴露源码

在生产环境下，如果**想在定位报错行数的同时，展示具体报错的源码**。此时可以将 **devtool** 的值设置为**source-map**

### 5. Source Map 的最佳实践

① 开发环境下：

- 建议把 devtool 的值设置为  **eval-source-map**

- 好处：可以精准定位到具体的错误行

② 生产环境下：

- 建议**关闭 Source Map** 或将 devtool 的值设置为 **nosource s-source-map**
- 好处：防止源码泄露，提高网站的安全性 

# Vue2.0+Vue3.0