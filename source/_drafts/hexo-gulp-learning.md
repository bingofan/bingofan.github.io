---
title: Gulp学习记录
toc: true
description: 'Gulp学习记录整理'
tags: hexo
categories: 
	hexo
	gulp
---

### gulp简介

听说可以优化网站性能,我就试试.
logo很好看
![gulp logo](\images\hexo\gulp-2x.png =150)
### gulp安装

**gulp常用网址**
gulp官方网址：http://gulpjs.com
gulp插件地址：http://gulpjs.com/plugins
gulp 官方API：https://github.com/gulpjs/gulp/blob/master/docs/API.md
gulp 中文API：http://www.ydcss.com/archives/424

**安装步骤**
{% badge 1 %}安装nodejs -> {% badge 2 %}全局安装gulp -> {% badge 3 %}项目安装gulp以及gulp插件 -> {% badge 4 %}配置gulpfile.js -> {% badge 5 %}运行任务

<!-- more -->
**npm介绍**
1.说明：
`npm（node package manager）` `nodejs`的包管理器，用于node插件管理（包括安装、卸载、管理依赖等）；

2.使用npm安装插件：
命令提示符执行
```shell
npm install <name> [-g] [--save-dev]；
```
* **<name>**：
	node插件名称。例：npm install gulp-less --save-dev
* **-g**：
	全局安装。将会安装在C:\Users\Administrator\AppData\Roaming\npm，并且写入系统环境变量；  
	非全局安装：将会安装在当前定位目录；  
	全局安装可以通过命令行在任何地方调用它，本地安装将安装在定位目录的 `node_modules` 文件夹下，通过 `require()` 调用；
* **--save**：
	将保存配置信息至`package.json`（`package.json`是`nodejs`项目配置文件）；
* **-dev**：
	保存至`package.json`的`devDependencies`节点，不指定`-dev`将保存至`dependencies`节点；
	一般保存在`dependencies`的像这些 `express/ejs/body-parser` 等等。
{% alert warning %}
为什么要保存至`package.json`？
因为node插件包相对来说非常庞大，所以不加入版本管理，将配置信息写入`package.json`并将其加入版本管理，其他开发者对应下载即可（命令提示符执行`npm install`，则会根据`package.json`下载所有需要的包，`npm install --production`只下载`dependencies`节点的包）。
{% endalert %}

3.使用npm卸载插件：
```shell
npm uninstall <name> [-g] [--save-dev]
```
PS：不要直接删除本地插件包

4.删除全部插件：
```shell
npm uninstall gulp-less gulp-uglify gulp-concat
```
 ……???太麻烦
借助`rimraf`：
```npm install rimraf -g```
用法：
```shell
rimraf node_modules
```

5.使用npm更新插件：
```shell
npm update <name> [-g] [--save-dev]
#更新全部插件
npm update [--save-dev]
```

6.查看npm帮助：
```shell
npm help
```

7.当前目录已安装插件：
```shell
npm list
```

npm安装插件过程：从http://registry.npmjs.org下载对应的插件包（该网站服务器位于国外，所以经常下载缓慢或出现异常）
解决办法往下看↓↓↓↓↓↓。

**选装cnpm**
因为npm安装插件是从国外服务器下载，受网络影响大，可能出现异常，如果npm的服务器在中国就好了，所以我们乐于分享的淘宝团队干了这事。
来自官网：“这是一个完整 `npmjs.org` 镜像，你可以用此代替官方版本(只读)，同步频率目前为 10分钟 一次以保证尽量与官方服务同步。”；
* 官方网址：http://npm.taobao.org；
* 安装：
	命令提示符执行`npm install cnpm -g --registry=https://registry.npm.taobao.org`  
	注意：安装完后最好查看其版本号`cnpm -v`或关闭命令提示符重新打开，安装完直接使用有可能会出现错误；
注：cnpm跟npm用法完全一致，只是在执行命令时将npm改为cnpm（以下操作将以cnpm代替npm）。

**全局安装gulp**
```shell
cnpm install gulp -g
```
`package.json`文件
```shell
    "gulp": "^3.9.1",
    "gulp-htmlclean": "^2.7.6",
    "gulp-htmlmin": "^1.3.0",
    "gulp-imagemin": "^2.4.0",
    "gulp-minify-css": "^1.2.4",
    "gulp-uglify": "^1.5.3",
```

###配置gulpfile.js文件
`gulpfile.js`是`gulp`项目的配置文件，是位于项目根目录的普通js文件（其实将`gulpfile.js`放入其他文件夹下亦可）。
gulpfile.js
```javascript
	var gulp = require('gulp');
    var minifycss = require('gulp-minify-css');
    var uglify = require('gulp-uglify');
    var htmlmin = require('gulp-htmlmin');
    var htmlclean = require('gulp-htmlclean');

    // 获取 gulp-imagemin 模块
    var imagemin = require('gulp-imagemin')

    // 压缩 public 目录 css
    gulp.task('minify-css', function() {
        return gulp.src('./public/**/*.css')
            .pipe(minifycss())
            .pipe(gulp.dest('./public'));
    });
    // 压缩 public 目录 html
    gulp.task('minify-html', function() {
      return gulp.src('./public/**/*.html')
        .pipe(htmlclean())
        .pipe(htmlmin({
             removeComments: true,
             minifyJS: true,
             minifyCSS: true,
             minifyURLs: true,
        }))
        .pipe(gulp.dest('./public'))
    });
    // 压缩 public/js 目录 js
    gulp.task('minify-js', function() {
        return gulp.src('./public/**/*.js')
            .pipe(uglify())
            .pipe(gulp.dest('./public'));
    });


    // 压缩图片任务
    // 在命令行输入 gulp images 启动此任务
    gulp.task('images', function () {
        // 1. 找到图片
        gulp.src('./photos/*.*')
        // 2. 压缩图片
            .pipe(imagemin({
                progressive: true
            }))
        // 3. 另存图片
            .pipe(gulp.dest('dist/images'))
    });

    // 执行 gulp 命令时执行的任务
    gulp.task('default', [
        'minify-html','minify-css','minify-js','images'
    ]);
```

### 参考

[gulp详细入门教程](http://www.ydcss.com/archives/18)
[Hexo折腾记——性能优化篇](https://yq.aliyun.com/articles/8608)


