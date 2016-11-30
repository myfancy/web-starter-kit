There are many commands available to help you build and test sites. Here are a few highlights to get started with.

这里有很多可用的命令，来帮助你建设和测试你的网站。下面是一些特别需要注意的地方。

## Watch For Changes & Automatically Refresh Across Devices
监听变化并自动跨设备刷新

```sh
$ gulp serve
```

This outputs an IP address you can use to locally test and another that can be used on devices
connected to your network.
`serve` does not use [service worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/)
caching, so your site will stop being available when the web server stops running.

这会输出一个IP地址，你可以用它进行本地测试，也可以用到连接到你的网络上的设备上（局域网内）。
`serve` 不适用[service worker] 缓存，所以当你的服务器停止运行时，你的站点会不可用。

备注：上面说的service worker介绍链接在墙内不可用。

参考：https://developer.mozilla.org/zh-CN/docs/Web/API/Service_Worker_API

简介：Service workers本质上作为一个代理服务器坐落于web应用和浏览器与网络（可用时）之间。他们旨在（包括其他事情）建立高效的离线体验，
拦截网络请求，并且会根据当前的网络是否可用、服务器的内容是否有所更新来采取合适的策略。他们还允许通知推送和后台同步API.

概念和用法：
service worker是一个被注册在一个源和路径下的事件驱动的worker。它允许JavaScript文件控制与其相关的页面或者网站，拦截或者修改导航和资源
请求，并且运用十分细化的方式来缓存资源。这让你可以完全控制自己的网页APP无论是在什么情况下。（最明显的情况就是当网络不可用的时）。
Service worker运行在一个worker的环境中：因此，他不会用dom的访问权，并且是在主线程之外的另一个线程中运行来加速你的APP，所以它不会造成
阻塞。它的设计是完全异步的，因此，同步的XHR请求和localStorage都不能应用在service worker中。
为了安全起见，Service workers 只通过HTTPS运行。在被篡改的网络连接中被第三者攻击可就不好了。
【具体可打开上述参考链接】

## Build & Optimize
创建和优化（完善）

```sh
$ gulp
```

Build and optimize the current project, ready for deployment.
This includes linting as well as image, script, stylesheet and HTML optimization and minification.
Also, a [service worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/)
script will be automatically generated, which will take care of precaching your sites' resources.
On browsers that [support](https://jakearchibald.github.io/isserviceworkerready/) service
workers, the site will be loaded directly from the service worker cache, bypassing the server.
This means that this version of the site will work when the server isn't running or when there is
no network connectivity.

创建和优化当前的工程，阅读下面内容以便部署
这包括 语法规范检测（linting？？）还有 image，script，和HTML的优化和缩小。
另外，一个【service worker】脚本也自动的产生，用来预加载你的网站资源。
在支持【service worker】的浏览器上，网站会被直接从【service worker cache】加载，跳过服务器。
这意味着这个版本的网站可以在服务器不运行或者没有网络连接的情况下工作。

## Serve the Fully Built & Optimized Site

服务器的完整搭建和网站的优化

```sh
$ gulp serve:dist
```

This outputs an IP address you can use to locally test and another that can be used on devices
connected to your network.
`serve:dist` includes will serve a local copy of the built and optimized site generated as part
of the `default` task.
Because the optimized site includes a service worker which serves your site directly from the
cache, you will need to reload the page after regenerating the site to pick up the latest changes.
`serve:dist` uses a different HTTP port than `serve`, which means that the service workers are
kept isolated in different [scopes](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers#Registering_your_worker).

这会输出一个IP地址，你可以用它进行本地测试，也可以用到连接到你的网络上的设备上（局域网内）

`serve:dist`包括 提供一个本地副本 和 优化生成的网站 作为`default`任务的一部分
因为优化的站点包括一个service worker ，直接从缓存加载你的网站。当你生成网站后，你需要重新加载页面，来接载最后一个的变化。

`serve:dist`使用一个相对于`serve`不同的http端口,这意味着service workers会被隔离在不同的[scope]（作用域）


## Difference Between `serve` & `serve:dist`

 `serve` 和 `serve:dist`的不同

It is important to note a difference between the `serve` and `serve:dist` tasks.

记录`serve` & `serve:dist` 的不同很重要


* `serve` uses a no-op `service-worker.js` and cannot run offline.
* `serve:dist` uses the `sw-precache`-generated output and can run offline.

一个不可以离线运行，一个可以

The `serve` task runs on port 3000 and `serve:dist` runs on port 3001.
The main purpose is to ensure that different service workers will not impact each other's environment. 
Using the `sw-precache`-generated output makes it very difficult to quickly test local changes which is not ideal for a development server environment.

serve 运行在端口3000上 serve:dist 运行在端口3001上。
主要的意图是确保两个不同的service workers不会影响彼此的环境。
使用`sw-precache`-generated output ，使快速测试本地变化变得很难，不是理想的服务器环境开发（方式）。

## Performance Insights

表现 见解？？

```sh
$ gulp pagespeed
```

Runs the deployed (public) version of your site against the [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) API to help you stay on top of where you can improve.

根据 [PageSpeed Insights] 运行 你的网站部署的（公开的）的版本。
