# file-appendix 文件附件

## .babelrc

[.babelrc](https://babeljs.io/docs/usage/babelrc/) is a configuration file for passing options to [Babel](https://babeljs.io) - the ES2015 transpiler recommended for writing next-generation JavaScript in Web Starter Kit. 

这个文件是babel插件的配置文件，用来指定转码规则和配置转码文件（跳过或仅编译某些文件），ES2015编译器 推荐 在 Web Starter Kit中 使用 下一代 JavaScript语法 。

## .editorconfig

[EditorConfig](http://editorconfig.org/) is a file format and collection of text editor plugins for maintaining consistent coding styles between different editors and IDEs.

EditorConfig帮助开发人员，在不同的编辑器和IDE中，定义和维护一致的编码风格。EditorConfig项目包含一个文件格式定义编码风格和文本编辑器插件的集合。
参考网址：http://editorconfig.org/

## gulpfile.babel.js

[Gulp](http://gulpjs.com) is a streaming build system that allows you to automate tedious development tasks. Compared with other build systems, such as Grunt, gulp uses Node.js streams as a means to automate tasks, thereby removing the need to create intermediate files when transforming source files. 

gulp是一个基于流的自动化构建工具，它允许你自动化冗长的开发任务。和其他的构建工具比，比如有Grunt，gulp使用Node.js的流作为一个自动化任务的方式，当源文件改变时由此移除需要创建的中间文件。

In gulp, you would install plugins, that do one thing and do it well, and construct a 'pipeline' by connecting them to each other. A `gulpfile` allows you to put together tasks that use plugins to accomplish a task like minification. 

使用gulp，你可以安装插件，去做一个事情并且做的很好。并且构成一个“管道”通过连接他们彼此。一个“gulpfile”允许你把任务放到一起，使用插件完成一个任务 如缩小。

`gulpfile.babel.js` is a gulpfile written in ES2015. The `babel` portion of the name refers to its use of the [Babel](https://babeljs.io) transpiler for enabling ES2015 code to run there.

`gulpfile.babel.js`是一个用ES2015标准写的“gulpfile”文件。名字上的“babel”代表它需要使用babel插件来转换ES2015代码以便支持运行。

## app/scripts/main.js

This is a file where your custom JavaScript can go. 

这是一个你的客户端的JavaScript代码入口。

## app/styles/main.css

This is a file where your custom CSS can go. You can place any Sass you wish to have compiled into the `styles` directory and renaming `main.css` to `main.scss` will cause Web Starter Kit to treat the file as Sass instead.

这是一个客户端的CSS入口。你可以把任何你想要的Sass编译后放入`style`目录，并且重命名`main.css`为`main.scss`会让Web Starter Kit把这个文件当做Sass处理。

## app/manifest.json
（就是用来配置快捷方式图标的）

`manifest.json` contains a [Web Application Manifest](https://w3c.github.io/manifest/) - a simple JSON file that gives you the ability to control how your app appears to the user in the areas that they would expect to see apps (for example the mobile home screen). In here you can control what the user can launch and more importantly how they can launch it. 

`manifest.json` 包含一个[Web Application Manifest](https://w3c.github.io/manifest/) - 一个简单的JSON文件，给予你能力去控制 你的APP如何表现给用户，在用户期待看到APP的区域（举例：移动手机桌面主页上）。在这里你可以控制用户登录什么和更重要的“他们怎么登录”。

For more information on the manifest, see [Web Fundamentals](https://developers.google.com/web/updates/2014/11/Support-for-installable-web-apps-with-webapp-manifest-in-chrome-38-for-Android).

关于manifest的更多信息，请看[Web Fundamentals](https://developers.google.com/web/updates/2014/11/Support-for-installable-web-apps-with-webapp-manifest-in-chrome-38-for-Android).

## app/manifest.webapp

`manifest.webapp` refers to the proprietary [Firefox OS manifest format](https://developer.mozilla.org/en-US/Apps/Build/Manifest), and not the W3C [manifest spec](https://w3c.github.io/manifest/), designed for cross-browser open web applications. 

这是火狐专有的配置，不是W3C的。W3C的才是为跨浏览器的Web应用程序而设计。

The Firefox OS app manifest provides information about an app (such as name, author, icon, and description) and a list of Web APIs that your app needs.

火狐的配置需要提供一个app的信息（比如：名字，图标，和描述）和一个你的app调用的Web APIs的列表。

This manifest included in Web Starter Kit until Firefox OS switches to using the manifest spec instead.

这个配置包含在Web Starter Kit中，直到 火狐os 切换至配置说明书 替代

## package.json

A [package.json](https://docs.npmjs.com/files/package.json) file is used to specify project tooling dependencies from [npm](http://npmjs.org) - the Node package manager. When you run `npm install`, `package.json` is read to discover what packages need to be installed. 

一个package.json文件被用作指定工程插件依赖，通过npm——node.js包管理器。当你运行 `npm install` ，package.json会被读取来发现你的需要安装的插件。

`package.json` can also contain other metadata such as a project description, version, license and configuration information.

`package.json` 也可以包含其他的信息，比如项目描述，版本，说明和配置信息。

## app/service-worker.js

A [service worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/) is a script that is run by your browser in the background, separate from a web page, opening the door to features such as offline support. In Web Starter Kit, the `app/service-worker.js` script is automatically generated for you by our build process via [sw-precache](https://github.com/GoogleChrome/sw-precache/).

一个service worker是一个在你的浏览器后台运行的脚本，独立于网站页面，打开特征的大门，如离线支持。在Web Starter Kit，app/service-worker.js 脚本是为你自动加载的，通过我们构建的工程通过[sw-precache](https://github.com/GoogleChrome/sw-precache/)。
