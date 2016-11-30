## Using Material Design Lite's Sass in Web Starter Kit
在 Web Starter Kit 中使用 Material Design Lite's Sass

If you would like to swap out the CSS version of [Material Design Lite](http://getmdl.io) for the more customisable [Sass](http://sass-lang.com/) version, there are a few steps you can take to get this setup with Web Starter Kit.

如果你想换掉[Material Design Lite](http://getmdl.io)的CSS版本，以便使用更多可定制的版本的话，你可以尝试下面的步骤。

> This guide is intended to be used with Web Starter Kit 0.6.0 and above.

这个指导适用于 Web Starter Kit 0.6.0版本以上。

1. Download the [latest release](https://github.com/google/web-starter-kit/releases/latest) of Web Starter Kit. Extract it to a location on your drive.
2. Download the [latest release](https://github.com/google/material-design-lite/releases/latest) build of Material Design Lite (`material-design-lite-<version>.zip` where `version` is the latest version available). This file will include the Sass source files we need to get started.
3. Extract `material-design-lite-<version>.zip` to a local folder on your drive and open it. You should see a file/folder structure similar to the below:

1、下载最新版本的Web Starter Kit，解压到你的本地目录

2、下载最新版本的Material Design Lite。这个文件中包含着我们需要使用的Sass源文件

3、解压`material-design-lite-<version>.zip`到一个本地文件夹然后打开它，你会看到类似下面的文件和文件夹结构：

```
├── LICENSE
├── README.md
├── bower.json
├── gulpfile.js
├── material.css
├── material.js
├── material.min.css
├── material.min.css.map
├── material.min.js
├── material.min.js.map
├── package.json
├── src
└── utils
```

The `src` directory above contains MDL's Sass files and the JavaScript sources for all MDL components.

上面的`src`文件夹包含着所有MDL的组件的Sass文件和JavaScript源码

4. Copy the `src` directory from step 3. to Web Starter Kit's `app/styles` directory. Your folder structure for `app/styles` should now resemble:

复制第三部中得到的src文件夹到Web Starter Kit的`app/styles`目录中，你的`app/styles` 文件夹结构需要时下面这样的：

```
├── main.css
└── src
```

Next we have some changes to make to Web Starter Kit's `app/index.html`. By default it includes the CDN-hosted production builds of Material Design Lite. We will need to swap these out for references to our local files instead. 

接下来，我们需要对 Web Starter Kit's `app/index.html`做一些修改。默认情况下，它引用的都是cdn的链接，我们需要把它改成本地的版本。

5. First, we'll switch the CDN-hosted stylesheets to our local version.

首先我们需要切换CDN的样式表为我们本地的。

Replace the following line:
替换下面的一行：

```html
<link rel="stylesheet" href="https://code.getmdl.io/1.2.1/material.indigo-pink.min.css">
```

with:
替换成：

```html
<link rel="stylesheet" href="styles/main.css">
```

If you navigate to "app/styles/main.css" in your Text Editor (e.g Sublime Text), you will notice that it already contains some styles. These are for the default template that ships with Web Starter Kit. 

如果定位到"app/styles/main.css" 在你的编辑器中（如：Sublime Text）中，你会注意它已经包含了一些样式，他们是和Web Starter Kit.相关的默认的模板。

We're going to rename our `app/styles/main.css` file to `app/styles/main.scss` so that Web Starter Kit treats it as a Sass file. No further changes are required to our `app/index.html`.

我们准备重命名我们的`app/styles/main.css`为`app/styles/main.scss`，确保我们的Web Starter Kit把它当作一个Sass文件。

One final change for getting Sass working is adding the following line to the very top of `app/styles/main.scss`:

为了启用Sass，最后一个要改的是，在`app/styles/main.scss`的第一行需要加入下面一行：

```
@import "src/material-design-lite";
```

This imports in all of MDL's component styles. If you later decide to only use a smallet set of components, just edit `src/material-design-lite.scss`, commenting out what you don't want.

这回导入所有的 MDL 的组件的样式。如果你后来决定只使用一小部分的组件，你可以编辑`src/material-design-lite.scss`。注释掉你不想要的。

6. Next, we'll localise our JavaScript files for MDL. Once again, we'll edit `app/index.html`:

接下来，我们将要为MDL本地化我们的JavaScript文件的引用。我们再一次编辑`app/index.html`：

Remove:
移除：

```html
<script src="https://code.getmdl.io/1.2.1/material.min.js"></script>
```

and find the following block in `app/index.html`:
然后在 `app/index.html`中找到下面这块：

```html
    <!-- build:js(app/) ../../scripts/main.min.js -->
    <script src="scripts/main.js"></script>
    <!-- endbuild -->
```

Replace the above block with the following code:
用下面的代码，替换掉上面的部分：


```html
    <!-- build:js(app/) ../../scripts/main.min.js -->
    <script src="./styles/src/mdlComponentHandler.js"></script>
    <script src="./styles/src/button/button.js"></script>
    <script src="./styles/src/checkbox/checkbox.js"></script>
    <script src="./styles/src/icon-toggle/icon-toggle.js"></script>
    <script src="./styles/src/menu/menu.js"></script>
    <script src="./styles/src/progress/progress.js"></script>
    <script src="./styles/src/radio/radio.js"></script>
    <script src="./styles/src/slider/slider.js"></script>
    <script src="./styles/src/spinner/spinner.js"></script>
    <script src="./styles/src/switch/switch.js"></script>
    <script src="./styles/src/tabs/tabs.js"></script>
    <script src="./styles/src/textfield/textfield.js"></script>
    <script src="./styles/src/tooltip/tooltip.js"></script>
    <script src="./styles/src/layout/layout.js"></script>
    <script src="./styles/src/data-table/data-table.js"></script>
    <script src="./styles/src/ripple/ripple.js"></script>
    <script src="scripts/main.js"></script>
    <!-- endbuild -->
```

Then, in your `gulpfile.babel.js` (found in the root of Web Starter Kit), edit the `scripts` task. By default it will look something like this:
然后，在你的`gulpfile.babel.js`（在你的Web Starter Kit的根目录下找），编辑`scripts`任务。默认情况下它是这样的：

```js
gulp.task('scripts', () =>
    gulp.src([
      // Note: Since we are not using useref in the scripts build pipeline,
      //       you need to explicitly list your scripts here in the right order
      //       to be correctly concatenated
      './app/scripts/main.js'
    ])
```

We're just going to add in the MDL component scripts so that they're correctly copied over and minified into a build when running `gulp`:
我们只需要在MDL组件代码中添加代码（像下面这样），当运行`gulp`时，以确保他们正确的复制和最小化到一个build中：

```js
gulp.task('scripts', () =>
    gulp.src([
      // Component handler
      './app/styles/src/mdlComponentHandler.js',
      // Base components
      './app/styles/src/button/button.js',
      './app/styles/src/checkbox/checkbox.js',
      './app/styles/src/icon-toggle/icon-toggle.js',
      './app/styles/src/menu/menu.js',
      './app/styles/src/progress/progress.js',
      './app/styles/src/radio/radio.js',
      './app/styles/src/slider/slider.js',
      './app/styles/src/spinner/spinner.js',
      './app/styles/src/switch/switch.js',
      './app/styles/src/tabs/tabs.js',
      './app/styles/src/textfield/textfield.js',
      './app/styles/src/tooltip/tooltip.js',
      // Complex components (which reuse base components)
      './app/styles/src/layout/layout.js',
      './app/styles/src/data-table/data-table.js',
      // And finally, the ripples
      './app/styles/src/ripple/ripple.js',
      // Other scripts,
      './app/scripts/main.js'
    ])
```


> Note: We are aware that it can feel a little suboptimal to reference the same set of source files twice in the above pipeline. We wil be looking at simplifying this workflow in a future release. 
注意：我们注意到这可能有点不太理想，在上面的一串代码中参考源文件的相同的设置两次。我们将要简化一下这个工作流程在一个将来的发布中。

Similar to styles, you can comment out what you don't need here if you decide to only use a smaller set of components. 

和styles一样，你可以注视到你不需要的，如果你决定只使用一小部分组件的话。

7. Finally, we can run `gulp serve` to preview our site or `gulp` to build a production version. Yay!

最后，我们可以运行`gulp serve`来预览我们的的网站，或者`gulp`来建立一个生产版本。就酱！

## Bonus tips
额外提示

### Configuring colors
配置颜色

You will probably want to configure the color theme used in MDL. 
你使用MDL可能会想要配置颜色主题

MDL supports Material Design's [color palette](https://www.google.com/design/spec/style/color.html#color-color-palette) through Sass variables. 
MDL支持Material Design's [color palette]，通过Sass变量来设置。

If you find a color in the palette spec you would like to use e.g color name `Pink` with fill `500`, MDL exposes this as `$palette-pink-500`. Let's walk through customising the primary and accent colors for your theme.

如果你在调色板说明中发现一个你想要的颜色，比如颜色的名字叫`Pink`，颜色只是`500`，MDL把它叫为`$palette-pink-500`，让我们在你的主题中轻松的定制首选的和重要的颜色吧

This can be done using your setup as follows:
这需要你遵从下面的步骤：

1. Run `gulp serve` to preview your site. 
2. Open `app/styles/src/_variables.scss` in your Text Editor.
3. Find `$color-primary`. It should be in the same block as two other color variables we can use for theming - `$color-primary-dark` and `$color-accent`.

1、运行`gulp serve`预览网站
2、在文本编辑器中打开 `app/styles/src/_variables.scss`
3、找到`$color-primary`。它应该在和 我们可以用作主题的两个其他颜色的变量 相同的块中——`$color-primary-dark` and `$color-accent`.

```
$color-primary: $palette-indigo-500 !default;
$color-primary-dark: $palette-indigo-700 !default;
$color-accent: $palette-pink-A200 !default;
```

We can change out the default theme for a custom one by consulting `app/styles/src/_color-definitions.scss` for [Material Design color themes](https://www.google.com/design/spec/style/color.html) available. 
我们可以改变默认主题，换成可用的版本。

For this example, we're going to change out `palette-indigo-500` for `palette-purple-500` and `palette-indigo-700` for `palette-deep-purple-700`.
就比如我们把……

```
$color-primary: $palette-purple-500 !default;
$color-primary-dark: $palette-deep-purple-700 !default;
$color-accent: $palette-pink-A200 !default;
```

Make the above change and hit save. The page should refresh, now showing you your customised theme in action. 
改好了并保存，页面会刷新，然后展示出你定制的主题。

For complete Material Design theming, you need to set two other colours: `$color-primary-contrast` and `$color-accent-contrast` in the same `app/styles/src/_variables.scss` file. These are the colours for text that is rendered on top of a solid block of primary or accent, respectively. You should set them to `$color-dark-contrast` if you've chosen a dark primary/accent, and `$color-light-contrast` if you've chosen a light primary/accent.

为了完成aterial Design theming，你需要设置两个其他的颜色：`$color-primary-contrast` and `$color-accent-contrast`，在相同的 `app/styles/src/_variables.scss`文件中。这些文字的颜色会被渲染到首要的重要的固体块上。如果你选择了暗色的首要和重要部分，你应该设置他们到`$color-dark-contrast`，如果你选择了浅色的主题，你应该设置到`$color-light-contrast`。


