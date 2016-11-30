# Install

安装

**tl;dr**: [Download WSK](https://github.com/google/web-starter-kit/releases/latest) and run `$ npm install --global gulp && npm install` in that directory to get started.

下载最新版(https://github.com/google/web-starter-kit/releases/latest) 然后 在目录中运行
`$ npm install --global gulp && npm install` 来开始。

-

To take advantage of Web Starter Kit you need to:

利用Web Starter Kit你需要：


1. Get a copy of the code.
2. Install the dependencies if you don't already have them.
3. Modify the application to your liking.
4. Deploy your production code.
-
1. 备份代码
2. 安装依赖，如果你没有安装的话
3. 如你所愿的修改应用
4. 部署你的产品代码

## Getting the code

得到代码

[Download](https://github.com/google/web-starter-kit/releases/latest) and extract WSK to where you want to work.

[下载](https://github.com/google/web-starter-kit/releases/latest) 然后提取WSK到你需要工作的地方

## Prerequisites

先决条件

### [Node.js](https://nodejs.org)

Bring up a terminal and type `node --version`.
Node should respond with a version at or above 0.10.x.
If you require Node, go to [nodejs.org](https://nodejs.org) and click on the big green Install button.

打开终端，输入`node --version`。
Node会输出一个0.10.x以上的版本号
如果你没有安装Node，去官网https://nodejs.org下载一个。


### [Gulp](http://gulpjs.com)

Bring up a terminal and type `gulp --version`.
If Gulp is installed it should return a version number at or above 3.9.x.
If you need to install/upgrade Gulp, open up a terminal and type in the following:

打开终端，输入 `gulp --version`.
如果已经安装gulp，将会返回一个3.9.x上的版本号。
如果你需要安装/升级gulp，打开终端然后输入一下命令：

```sh
$ npm install --global gulp
```

*This will install Gulp globally. Depending on your user account, you may need to [configure your system](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md) to install packages globally without administrative privileges.*

这会全局安装gulp，根据你的用户账户，你可能需要配置你的系统，来安装全局包，在没有管理权限的时候。

### Local dependencies

本地依赖

Next, install the local dependencies Web Starter Kit requires:

下一个，安装本地依赖，Web Starter Kit需要：

```sh
$ npm install
```

That's it! You should now have everything needed to use the Web Starter Kit.

搞定了！你现在应该已经拥有Web Starter Kit需要的所有东西了。

-

You may also want to get used to some of the [commands](commands.md) available.

你可以也需要使用一些命令：打开command.md看看吧！
