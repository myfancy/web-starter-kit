# [![Web Starter Kit](https://cloud.githubusercontent.com/assets/110953/11445049/f05512ba-9520-11e5-8fdb-8c8eb5f690d0.jpg)](https://github.com/google/web-starter-kit/releases/latest)

## Overview / 概览

[Web Starter Kit](https://developers.google.com/web/tools/starter-kit/) is an opinionated boilerplate for web development. Tools for building a great experience across many devices and [performance oriented](#web-performance). Helping you to stay productive following the best practices outlined in Google's [Web Fundamentals](https://developers.google.com/web/fundamentals/). A solid starting point for both professionals and newcomers to the industry.

[Web Starter Kit（web初学者工具包）](https://developers.google.com/web/tools/starter-kit/)是一个给web开发者自用的模板。它提供跨多个设备的很好的开发体验，有着不过的[速度表现](#web-performance)。跟着谷歌的[Web Fundamentals](https://developers.google.com/web/fundamentals/)中的最好的练习学习可以帮助你保持生产力。这是一个坚实的初学者指南，无论是对于高级开发人员还是初学者。

### Features / 特点

| Feature                                | Summary                                                                                                                                                                                                                                                     |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Responsive boilerplate | A responsive boilerplate optimized for the multi-screen web. Powered by [Material Design Lite](http://getmdl.io).  You're free to use either this or a completely clean-slate  via [basic.html](https://github.com/google/web-starter-kit/blob/master/app/basic.html).                          |
| Sass support                           | Compile [Sass](http://sass-lang.com/) into CSS with ease, bringing support for variables, mixins and more. (Run `gulp serve` or `gulp` for production)                                                                                                      |
| Performance optimization               | Minify and concatenate JavaScript, CSS, HTML and images to help keep your pages lean. (Run `gulp` to create an optimised version of your project to `/dist`)                                                                                                |
| Code Linting               | JavaScript code linting is done using [ESLint](http://eslint.org) - a pluggable linter tool for identifying and reporting on patterns in JavaScript. Web Starter Kit uses ESLint with [eslint-config-google](https://github.com/google/eslint-config-google), which tries to follow the Google JavaScript style guide.                                                                                                |
| ES2015 via Babel 6.0                   | Optional ES2015 support using [Babel](https://babeljs.io/). To enable ES2015 support remove the line `"only": "gulpfile.babel.js",` in the [.babelrc](.babelrc) file. ES2015 source code will be automatically transpiled to ES5 for wide browser support.  |
| Built-in HTTP Server                   | A built-in server for previewing your site locally while you develop and iterate                                                                                                                                                                            |
| Live Browser Reloading                 | Reload the browser in real-time anytime an edit is made without the need for an extension. (Run `gulp serve` and edit your files)                                                                                                                           |
| Cross-device Synchronization           | Synchronize clicks, scrolls, forms and live-reload across multiple devices as you edit your project. Powered by [BrowserSync](http://browsersync.io). (Run `gulp serve` and open up the IP provided on other devices on your network)                       |
| Offline support                     | Thanks to our baked in [Service Worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/) [pre-caching](https://github.com/google/web-starter-kit/blob/master/gulpfile.babel.js#L226), sites deploying `dist` to a HTTPS domain will enjoy offline support. This is made possible by [sw-precache](https://github.com/GoogleChrome/sw-precache/).                                                                                                                                              |
| PageSpeed Insights                     | Web performance metrics showing how well your site performs on mobile and desktop (Run `gulp pagespeed`)                                                                                                                                                    |

| 特征                                | 摘要                                                                                                                                                                                                                                                     |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 响应式模板 | 一个针对多屏幕网站优化的响应式模板。[Material Design Lite](http://getmdl.io)提供技术支持。 你有权使用这个，或者一个完全清除的版本，通过[basic.html](https://github.com/google/web-starter-kit/blob/master/app/basic.html).                      |
| Sass 支持                           | 轻松地把[Sass](http://sass-lang.com/)编译成css代码。提供变量，mixins以及更多的支持。（生产版本请运行`gulp serve` 和 `gulp` 命令。）                                                                                                      |
| 性能优化               | 缩小（混淆）和合并你的JavaScript，CSS，HTML和图片，来帮助你保持页面简洁精炼。（运行`gulp`命令给你的项目创建一个优化过的版本到`/dist`目录中）                                                                                                |
| 代码语法检测               |  使用[ESLint](http://eslint.org)完成了JavaScript代码的语法检测——一个可插入的语法检测小工具。Web Starter Kit 使用的是  [eslint-config-google](https://github.com/google/eslint-config-google)。它尝试跟随谷歌的样式指导。                                                                                             |
| ES2015 via Babel 6.0                   |  使用[Babel](https://babeljs.io/)提供可选择的ES2015支持。启用ES2015，可以移除[.babelrc](.babelrc)文件中的`"only": "gulpfile.babel.js",`这一行字。ES2015源代码会自动编译到ES5，以便支持更多的浏览器 |
| 内置 HTTP Server                   | 一个内置的HTTP Server，用以再本地预览你的网站。当你开发和反复修改时。                                                                                                                                                                         |
| 浏览器实时刷新                 | 无需chrome 扩展，实时刷新你的浏览器，当编辑结束后 (运行 `gulp serve` 命令然后编辑你的文件)                                                                                                                           |
| 跨设备同步           |当你编辑项目是，同步你的点击、滚动、填写表格和实时刷新操作在多个的设备上。[BrowserSync](http://browsersync.io)提供技术支持。 (运行 `gulp serve` 然后 在你的网络上的其他设备中打开对应的IP地址，如果有的话。)                       |
|离线支持                  | Thanks to our baked in [Service Worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/) [pre-caching](https://github.com/google/web-starter-kit/blob/master/gulpfile.babel.js#L226), sites deploying `dist` to a HTTPS domain will enjoy offline support. This is made possible by [sw-precache](https://github.com/GoogleChrome/sw-precache/).                                                                                                                                              |
| 页面速度见解                   | Web performance metrics 展示出你的网站在移动端和桌面端的表现怎么样 (运行 `gulp pagespeed`)                                                                                                                                                    |

## Quickstart / 快速入门

[Download](https://github.com/google/web-starter-kit/releases/latest) the kit or clone this repository and build on what is included in the `app` directory.

[下载](https://github.com/google/web-starter-kit/releases/latest)这个入门包或者git clone这个库，and 在`app`目录包含的内容的基础行进行开发。

There are two HTML starting points, from which you can choose:

你可以从下面两个`html`文件中选择一个开始。

- `index.html` - the default starting point, containing Material Design layout.
- `basic.html` - no layout, but still includes our minimal mobile best-practices

- `index.html` - 默认的入口，包含着 Material Design 布局.
- `basic.html` -没有布局t,但仍然包含着我们的 minimal mobile best-practices

Be sure to look over the [installation docs](docs/install.md) to verify your environment is prepared to run WSK.
Once you have verified that your system can run WSK, check out the [commands](docs/commands.md) available to get started.

务必仔细查看 [installation docs](docs/install.md)以确定你的环境支持运行WSK.
一旦你的确定你的系统可以运行 WSK, 看一下这个 [commands](docs/commands.md) 来开始项目。

## Web Performance / Web 表现

Web Starter Kit strives to give you a high performance starting point out of the box. Our median Web Page Test [scores](http://www.webpagetest.org/result/151201_VW_XYC/) for the default template have a [Speed Index](https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index) of ~1100 (1000 is ideal) and a repeat-visit Speed Index of ~550 thanks to Service Worker precaching.

Web Starter Kit 力求给你一个高性能的出发点. 我们的默认模板的平均网页测试成绩达到了1100个速度指数（1000是最理想的），重复访问速度指数达到了550的速度指数，得益于我们的Service Worker precaching(预先缓存).


## Browser Support / 浏览器支持

At present, we officially aim to support the last two versions of the following browsers:

目前，我们官方目标是支持下面的浏览器的最新的两个版本。

* Chrome
* Edge
* Firefox
* Safari
* Opera
* Internet Explorer 9+

This is not to say that Web Starter Kit cannot be used in browsers older than those reflected, but merely that our focus will be on ensuring our layouts work great in the above.
这不是说 Web Starter Kit 不支持这些浏览器的较老的版本。只是我们的重点是确保我们的布局在上面说的浏览器中正常。


## Troubleshooting / 解决困难

If you find yourself running into issues during installation or running the tools, please check our [Troubleshooting](https://github.com/google/web-starter-kit/wiki/Troubleshooting) guide and then open an [issue](https://github.com/google/web-starter-kit/issues). We would be happy to discuss how they can be solved.

如果你发现你要了问题，在安装和运行这个工具期间，请检查我们的[问题列表](https://github.com/google/web-starter-kit/wiki/Troubleshooting)指导，然后打开[issue](https://github.com/google/web-starter-kit/issues)（可以提问）。我们很乐意商量一下它们如何解决。

## A Boilerplate-only Option / 模板选项

If you would prefer not to use any of our tooling, delete the following files from the project: `package.json`, `gulpfile.babel.js` and `.travis.yml`. You can now safely use the boilerplate with an alternative build-system or no build-system at all if you choose.

如果你不愿意使用我们的加工（是指构建系统），从项目中删除下面的文件： `package.json`, `gulpfile.babel.js` and `.travis.yml`。你可以安全地使用模板，结合你的自己的替代构建系统或者完全不适用构建系统，如果你选择这样的话。

## Docs and Recipes / 文档和方法

* [File Appendix](https://github.com/google/web-starter-kit/blob/master/docs/file-appendix.md) - What do the different files here do?
* [Using Material Design Lite's Sass](https://github.com/google/web-starter-kit/blob/master/docs/mdl-sass.md) - how to get MDL's Sass working with WSK
* [Deployment guides](https://github.com/google/web-starter-kit/blob/master/docs/deploy.md) - available for Firebase, Google App Engine and other services.
* [Gulp recipes](https://github.com/gulpjs/gulp/tree/master/docs/recipes) - the official Gulp recipes directory includes a comprehensive list of guides for different workflows you can add to your project.

* [File Appendix](https://github.com/myfancy/web-starter-kit/blob/master/docs/file-appendix.md) - 这里不同的文件是干什么用的？
* [Using Material Design Lite's Sass](https://github.com/myfancy/web-starter-kit/blob/master/docs/mdl-sass.md) - 如何在WSK上使用MDL的Sass？
* [Deployment guides](https://github.com/myfancy/web-starter-kit/blob/master/docs/deploy.md) -  Firebase, Google App Engine 或者其他服务的可用指导.
* [Gulp recipes](https://github.com/gulpjs/gulp/tree/master/docs/recipes) - 官方的Gulp的使用方法目录中包括着一个综合的指导列表，针对不同的可以添加到项目中工作流程。

## Inspiration / 灵感

Web Starter Kit is inspired by [Mobile HTML5 Boilerplate](https://html5boilerplate.com/mobile/) and Yeoman's [generator-gulp-webapp](https://github.com/yeoman/generator-webapp), having taken input from contributors to both projects during development. Our [FAQs](https://github.com/google/web-starter-kit/wiki/FAQ) attempt to answer commonly asked questions about the project.

Web Starter Kit 灵感来自于[Mobile HTML5 Boilerplate](https://html5boilerplate.com/mobile/) 和 Yeoman 的 [generator-gulp-webapp](https://github.com/yeoman/generator-webapp)，开发期间给这两个项目都做过贡献。我们的[FAQs](https://github.com/google/web-starter-kit/wiki/FAQ) 尝试回答了关于这个项目的常见问题。


## Contributing / 贡献

Contributions, questions and comments are all welcome and encouraged. For code contributions to Web Starter Kit, please see our [Contribution guide](CONTRIBUTING.md) before submitting a pull request. [Website](https://developers.google.com/web/tools/starter-kit/) related issues should be filed on the [Web Fundamentals](https://github.com/google/WebFundamentals/issues/new) issue tracker.

我们欢迎和鼓励贡献、问题和评论。为了给Web Starter Kit做code贡献。请查看我们 贡献指导。在你的提交一个pull请求之前。网站相关问题应该被放到问题追踪中。

## License / 许可

Apache 2.0  
Copyright 2015 Google Inc
