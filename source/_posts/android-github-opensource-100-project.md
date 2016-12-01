---
title: GitHub 排名前 100 的安卓、iOS项目简介
tags:
  - android
  - ios
  - github
categories:
  - Android
description: >-
  本文转载 原文地址： [GitHub 排名前 100
  的安卓、iOS项目简介](http://www.open-open.com/lib/view/open1463059022864.html)
date: 2016-11-30 15:14:16
---


![GitHub logo](\images\android\android_githublogo.jpeg)

### Android 项目 ###
排名完全是根据 GitHub 搜索 Java 语言选择 (Best Match) 得到的结果, 然后过滤了跟 Android 不相关的项目, 所以排名并不具备任何官方效力, 仅供参考学习, 方便初学者快速了解当前一些流行的 Android 开源库。
<!-- more -->

| 项目名称        | 项目简介           |
| ---------------- | ------------- | 
| 1. [react-native](https://github.com/facebook/react-native) | 这个是 Facebook 在 React.js Conf 2015 大会上推出的基于 JavaScript 的开源框架 React Native, 该框架结合了 Web 应用和 Native 应用的优势, 可以使用 JavaScript 来开发 iOS 和 Android 原生应用 |
| 2.[Android-Universal-Image-Loader](https://github.com/nostra13/Android-Universal-Image-Loader) | ImageLoader 是最早开源的 Android 图片缓存库, 强大的缓存机制, 早期被广泛 Android 应用使用, 至今仍然有很多 Android 开发者在使用 |
| 3. [RxJava](https://github.com/ReactiveX/RxJava) | RxJava 是一个在 Java VM 上使用可观测的序列来组成异步的, 基于事件的程序的库, 简单来说它就是一个实现异步操作的库, RxJava 的优点在于一个词 "简洁", 使用它就算你程序逻辑有多么复杂, 它依然能够保持简洁易懂 |
| 4. [retrofit](https://github.com/square/retrofit) | Retrofit 是 Square 公司出品的 HTTP 请求库, 同时是 Square 是最早开源项目之一, Retrofit 是目前 Android 最流行的 Http Client 库之一, 目前版本是 Retrofit2.0 Beta4, 越来越多 Android 开发者开始使用这个请求库了 |
| 5. [okhttp](https://github.com/square/okhttp) | OkHttp 是 Square 公司出品的 HTTP 另一个请求库, Google 不推荐人们使用 HttpClient, 可是 HttpURLConnection 实在是太难用了, 因此很多人使用了 OkHttp 来解决这问题, 据说 Android4.4 的源码中可以看到 HttpURLConnection 已经替换成 OkHttp 实现呢 |
| 6. [SlidingMenu(不建议使用)](https://github.com/jfeinstein10/SlidingMenu) | 一个侧滑菜单开源库, 在 Google 自己原生态的侧滑菜单 NavigationDrawer 没有出现之前, 这个库就已经被广泛使用, 可是到现在这个库已经被放弃了 |
| 7. [picasso](https://github.com/square/picasso) | Picasso 是 Square 公司出品的一款图片缓存库, 主导者是 JakeWharton 大神 |
| 8. [android-best-practices](https://github.com/futurice/android-best-practices) | Android 开发最佳实践, 里面所介绍的经验都是来自于 Futurice 公司 Android 开发者, 介绍内容有 Android 开发规范, 架构, 布局技巧, 以及使用一些有助于快速开发相关工具等等, 非常适合新手去学习 |
| 9. [EventBus](https://github.com/greenrobot/EventBus) | EventBus 是 Android 事件管理总线, 使用它可以替带 Android BroadCast, BroadCastReceiver, Handler 在 Activity, Fragment, Service, 线程之间传递消息, 大大简化了事件传递逻辑 |
| 10. [android-async-http](https://github.com/loopj/android-async-http) | Android-Async-Http 是 Android 一款老牌异步请求库, 专门对 Android 在 Apache 的 HttpClient 基础上构建的异步 http 连接, 该库有很多特征, 例如: 库的 size 小, 支持文件上传不需使用第三方库支持, 内部使用线程池来处理并发, 等等 |
| 11. [fresco](https://github.com/facebook/fresco) | Fresco 是 FaceBook 公司出品的一款图片缓存库, Fresco 是一个强大的图片加载组件, 支持加载 Gif 图和 WebP 格式, 支持 Android2.3(API level 9) 及其以上系统, Fresco 中设计了 Image pipeline 和 Drawees 两个模块各施其职, 使得图片完美加载出来, 想知道更多 image pipeline 和 Drawees 有关于它的特性, 可以到它[官方平台](http://fresco-cn.org/)看介绍 |
| 12. [zxing](https://github.com/zxing/zxing) | ZXing 是二维码领域中名气最大的开源项目, 它提供了多个平台的二维码/条形码扫描解决方案, 拥有扫描快, 识别率高, 使用简单等特点 |
| 13. [leakcanary](https://github.com/square/leakcanary) | LeakCanary 是 Square 公司出的一款检测内存泄露工具, 该工具能帮助你在开发阶段方便的检测出内存泄露的问题, 使用起来非常简单方便 |
| 14. [butterknife](https://github.com/JakeWharton/butterknife) | 由 JakeWharton 大神开发出来的, ButterKnife 是 View 注入框架, 使用它为了简写很多 findViewById 代码, 同时还支持 View 的一些事件处理函数 |
| 15. [MPAndroidChart](https://github.com/PhilJay/MPAndroidChart) | MPAndroidChart 是一款强大的 Android 图表库, 支持各种各样图表显示, 能想到的图表样式这里几乎都有, 图表还支持选择, 拖放和缩放动画效果 |
| 16. [ActionBarSherlock (不建议使用)](https://github.com/JakeWharton/ActionBarSherlock) | ActionBarSherlock 这个库是 JakeWharton 大神开发出来支持 Android3.0 以下版本的, 后来慢慢的 Google 也提供了 AppCompat 库来支持 Android3.0 以下版本使用 ActionBar, 因此作者不建议我们再使用这个库了 |
| 17. [androidannotations](https://github.com/excilys/androidannotations) | AndroidAnnotations 是一个能够让你快速进行 Android 开发的开源框架, 它能让你专注于真正重要的地方, 使代码更加精简, 使项目更加容易维护, 它的目标就是 "Fast Android Development.Easy maintainance" |
| 18. [ViewPagerIndicator](https://github.com/JakeWharton/ViewPagerIndicator) | 由 JakeWharton 大神开发出来的一个 ViewPager 指示器, 使用起来简单方便, 可高度定制, 开发出各种各样动画效果 |
| 19. [glide](https://github.com/bumptech/glide) | Glide 是 Google 员工的开源项目, 广泛应用于 Google 一些 App 上, 在2014年 Google I/O 大会上被推荐使用, Glide 和 Picasso 被人拿来比较研究过, Glide 与 Picasso 有 90% 的相似度, 但在一些细节上还是有点区别的, 各有各优缺点看君选择 |
| 20. [HomeMirror](https://github.com/HannahMitt/HomeMirror) | 开发者是由一名程序媛 Hannah Mittelstaedt , HomeMirror 是一款 Android 镜子应用, 目前它能实现日期, 时间, 天气, 生日信息, 事件提醒器, 骑车天气的推荐, 股票信息, XKCD 漫画网站的新帖等等 |
| 21. [Android-PullToRefresh(不建议使用)](https://github.com/chrisbanes/Android-PullToRefresh) | 一个强大的拉动刷新开源项目, 支持各种控件下拉刷新, ListView, ViewPager, WebView, ExpandableListView, GridView, ScrollView, Horizontal ScrollView, Fragment 上下左右拉动刷新, 不过现在这个项目已经停止维护更新了, 推荐使用[Android-Ultra-Pull-To-Refresh](https://github.com/liaohuqiu/android-Ultra-Pull-To-Refresh) |
| 22. [MaterialDesignLibrary](https://github.com/navasmdc/MaterialDesignLibrary) | 这个库控件都是遵循了 Google Material Design 设计规范开发出来, 例如有: Flat Button, Rectangle Button, CheckBox, Switch, Progress bar circular indeterminate 等等 |
| 23. [PhotoView](https://github.com/chrisbanes/PhotoView) | PhotoView 是 ImageView 的子类, 支持所有 ImageView 的源生行为, 例如: 支持 Pinch 手势自由缩放, 支持双击放大/还原, 支持平滑滚动等等, 并且非常方便的与 ImageLoader/Picasso 之类的网络图片读取库集成使用, 还方便的与 ViewPager 等同样支持滑动手势的控件集成 |
| 24. [RxAndroid](https://github.com/ReactiveX/RxAndroid) | 由 JakeWharton 大神主导开发的项目, RxAndroid 是 RxJava 的一个针对 Android 平台的扩展, 主要用于 Android 开发 |
| 25. [material-dialogs](https://github.com/afollestad/material-dialogs) | Material Dialogs 是一个可高度定制易用, 符合 Material Design 风格的 Dialogs, 兼容 Android API8 以上版本, 个人使用感觉它完全可替代 Android 原生那个, 比原生那个更加简单易用 |
| 26.[Android-ObservableScrollView](https://github.com/ksoichiro/Android-ObservableScrollView) | ObservableScrollView 是一款用于在滚动视图中观测滚动事件的 Android 库, 它能够轻而易举地与 Android 5.0 Lollipop 引进的工具栏 (Toolbar) 进行交互, 还可以帮助开发者实现拥有 Material Design 应用视觉体验的界面外观, 支持ListView, ScrollView, WebView, RecyclerView, GridView组件 |
| 27. [Android-Bootstrap](https://github.com/Bearded-Hen/Android-Bootstrap) | Android 版的 Bootstrap, 利用这个库能够实现很多 Bootstrap 样式风格, 之前有学过 Html 的人就知道 Bootstrap 是什么玩意啦 |
| 28. [AndroidSwipeLayout](https://github.com/daimajia/AndroidSwipeLayout) | 开发者是代码家, AndroidSwipeLayout 是一个支持ListView, GridView, ViewGroup等等左右上下滑动出操作菜单, 类似 qq 消息列表向左滑动显示出多某条信息的操作菜单 |
| 29. [dagger](https://github.com/square/dagger) | Dagger 是 Square 公司出品的一个针对 Android 和 Java 的快速依赖注入器, 能够有效减少你敲代码量 |
| 30. [ListViewAnimations](https://github.com/nhaarman/ListViewAnimations) | 一个轻轻松松给 Android ListView 添加动画效果的库, 支持的动画有: Alpha, SwingRightIn, SwingLeftIn, SwingBottomIn, SwingRightIn and ScaleIn等等, 使用它能很容易就实现帅爆的效果 |
| 31.[PagerSlidingTabStrip(不建议使用)](https://github.com/astuetz/PagerSlidingTabStrip) | PagerSlidingTabStrip 是一个给 Android ViewPager添加上 ViewPager 滑动指示器, 从 GitHub 上面看, 这个库似乎没有人在维护了, 因此不建议使用, 可使用[SmartTabLayout](https://github.com/ogaclejapan/SmartTabLayout) 来代替 |
| 32. [AndroidViewAnimations](https://github.com/daimajia/AndroidViewAnimations) | 开发者是代码家, 这个库实现很多很酷炫的 Android 动画, 动画效果是借鉴 Animate.css 来实现的, 非常酷, 而且这个使用起来也是非常简单 |
| 33. [AndroidSlidingUpPanel](https://github.com/umano/AndroidSlidingUpPanel) | AndroidSlidingUpPanel 是一个上拉面板, 就是向上滑动的时候往上飞出一个显示面板控件, 该库效果在 Google Music, Google Maps and Rdio等 App 应用到 |
| 34. [MaterialDrawer](https://github.com/mikepenz/MaterialDrawer) | MaterialDrawer 是一个类似 Google 官方 NavigationView 侧滑显示控件, 个人认为 NavigationView 并没有 MaterialDrawer 实用, 因为 NavigationView 自由度不是很好, 很多都写死了不可以自由定义布局, 而 MaterialDrawer 能够实现跟 NavigationView 一样的效果, 同时还支持自定义效果, 自由度非常高 |
| 35. [Material-Animations](https://github.com/lgvalle/Material-Animations) | Material-Animations 是一个很好过渡动画库, 可以应用于 Activity 与 Activity 之间的跳转, Fragment 与 Fragment 之间的跳转, 以及各个 View 变化前后的过渡动画 |
| 36. [MaterialViewPager](https://github.com/florent37/MaterialViewPager) | 一个简单易用 Material Design 风格的 ViewPager 库 |
| 37. [ion](https://github.com/koush/ion) | ion 是一个让 Android 的网络操作变得极其简单, 支持异步获取和处理JSON, 支持 Android 文件下载 (同时支持下载进度条绑定), 支持安全链接和代理 |
| 38. [stetho](https://github.com/facebook/stetho) | Stetho是 Facebook 出品的一个强大的 Android 调试工具,使用该工具你可以在 Chrome Developer Tools查看App的布局, 网络请求(仅限使用Volley, okhttp的网络请求库), sqlite, preference, 一切都是可视化的操作,无须自己在去使用adb, 也不需要root你的设备 |
| 39. [fastjson](https://github.com/alibaba/fastjson) | Fastjson 是一个 Java 语言编写的高性能功能完善的 JSON 库. 它采用一种“假定有序快速匹配”的算法, 把 JSON Parse的性能提升到极致, 是目前Java语言中最快的JSON库. Fastjson接口简单易用, 已经被广泛使用在缓存序列化, 协议交互, Web输出, Android客户端等多种应用场景 |
| 40. [cardslib (不建议使用)](https://github.com/gabrielemariotti/cardslib) | Cardslib 是早期由 Gabriele Mariotti 开发的一个为开发者方便实现各种 Card UI 的 Android 开源代码库, 后来 Google 官方提供自己封装了 CardView 在 v7 包下, 使用 Google 官方的可以完全替代了这个库, 因此这个也被弃用了 |
| 41. [Android-Ultra-Pull-To-Refresh](https://github.com/liaohuqiu/android-Ultra-Pull-To-Refresh) | 开发者是廖祜秋, 这个是一个非常强大的下拉刷新库, 继承 ViewGroup 可以包含任何 View, 功能甚至比 SwipeRefreshLayout 强大, 使用起来也非常容易, 还可以自由定制自己的 UI 样式 |
| 42. [greenDAO](https://github.com/greenrobot/greenDAO) | greenDAO 是一个可以帮助 Android 开发者快速将 Java 对象映射到 SQLite 数据库的表单中的 ORM解决方案, 通过使用一个简单的面向对象 API, 开发者可以对 Java 对象进行存储, 更新, 删除和查询, greenDAO 相对 OrmLite, AndrORM 这两个 ORM 开源库, 性能是最高的 |
| 43. [AndroidStaggeredGrid](https://github.com/etsy/AndroidStaggeredGrid) | AndroidStaggeredGrid 是一个支持多列并且每一行的 item 大小不一, 交错排列的 GridView, 就是实现瀑布流样式效果, 目前该库已经被弃用了, 开发者建议我们使用 Google 官方控件 RecyleView 中的 StaggeredGridLayoutManager 布局来实现瀑布流效果 |
| 44. [otto](https://github.com/square/otto) | Otto 是 Square 公司出的一个事件库 (pub/sub 模式), 用来简化应用程序组件之间的通讯, otto 修改自 Google 的 Guava 库, 专门为 Android 平台进行了优化, 与上面介绍的 EventBus 相比, 两个库各有各的优点, 完全取决于我们自己项目的需求来选择它们哪一个 |
| 45. [xUtils](https://github.com/wyouflf/xUtils) | xUtils 是一个快速开发框架, 里面包含 DbUtils, ViewUtils, HttpUtils, BitmapUtils 四大模块, 可用于快速开发, 支持大文件上传, 拥有更加灵活的 ORM, 最低兼容 Android 2.2 |
| 46. [realm-java](https://github.com/realm/realm-java) | Realm 一个轻量的 Android 版本的数据存储库, 比 Android 原生系统的 SQLite 更加简洁快速对数据进行操作 |
| 47.[Android-CleanArchitecture](https://github.com/android10/Android-CleanArchitecture) | CleanArchitecture 是一个非常典型使用 MVP 架构的项目, 大家如果还没有理解 MVP 架构的可以看看这个项目 |
| 48. [StickyListHeaders](https://github.com/emilsjolander/StickyListHeaders) | StickyListHeaders 是一个实现能够固定在屏幕顶部的ListView Section Header库, 就是当前 section 的 header 固定在屏幕顶部, 当滑动到其他 section 时, 其他 section 的 header 会代替之前的 section 的 header, 固定到屏幕顶部, 类似于 Android4.0 的手机通讯录的效果 |
| 49. [AppIntro](https://github.com/PaoloRotolo/AppIntro) | AppIntro 是一个让人轻松快速搭建漂亮酷炫的引导页库 |
| 50. [ActiveAndroid](https://github.com/pardom/ActiveAndroid) | ActiveAndroid 是采用Rails中的 [Active Record](http://en.wikipedia.org/wiki/Object-relational_mapping)架构模式设计的适用于 Android 平台的轻量级 ORM 架构, 几乎可以不用写任何 SQL 代码实现快速开发 |
| 51. [android-volley](https://github.com/mcxiaoke/android-volley) | Volley 是谷歌官方开发团队在 2013 年 Google I/O 大会推出的一个新的网络通信框架, 这个框架把 AsyncHttpClient 和 Universal-Image-Loader 的优点集于了一身,既可以像AsyncHttpClient 一样非常简单地进行 HTTP 通信,也可以像 Universal-Image-Loader 一样轻松加载网络上的图片, 这个库并不是官方的, 只是托管同步在 Maven, 官方只提供的 Jar 包 |
| 52. [twoway-view](https://github.com/lucasr/twoway-view) | TwoWayView 是简化 RecyclerView 开发的一个库, 可以在其 Base LayoutManager 基础上构建各种各样的布局, 该库内置了几个常用布局 List, Grid, Staggered Grid,Spannable Grid |
| 53. [ShowcaseView](https://github.com/amlcurran/ShowcaseView) | ShowcaseView 是一个非常适合用于对用户进行第一次使用进行指导的库,使用起来非常简单还可以自定义样式 |
| 54. [Calligraphy](https://github.com/chrisjenx/Calligraphy) | Calligraphy 是一个用来简化 Android 应用使用自定义字体的类库, 该类库会自动查找应用中的 TextView 并设置其使用的字体 |
| 55. [NineOldAndroids](https://github.com/JakeWharton/NineOldAndroids) | NineOldAndroids 由 JakeWharton 大神开发的一个向下兼容的动画库, 主要是使低于API 11的系统也能够使用 View 的属性动画, 不过现在 JakeWharton 大神已经不推荐使用该库, 而是推荐我们使用官方封装在 Support 库里面的动画 |
| 56. [android-floating-action-button](https://github.com/futuresimple/android-floating-action-button) | FloatingActionButton 是一个悬浮操作按钮, 官方在 Support Design 包下也有封装一个类似这个库效果的 FloatingActionButton, 值得说明的是这个库是早在官方封装之前就存在的, 个人感觉这个库比官方那个更加好用 |
| 57. [CircleImageView](https://github.com/hdodenhof/CircleImageView) | CircleImageView 是一个轻松帮你实现圆形效果 ImageView 图片库, CircleImageView 是基于 ImageView 扩展出来, 因此它拥有 ImageView 控件所有属性, 简单易用值得你使用的库 |
| 58. [material](https://github.com/rey5137/material) | Material 是将 Material Design 风格控件封装在该库当中, 目前封装有Progress, Button, Switch, Slider, Spinner, Text Field, TabPageIndicator, SnackBar, Dialog, BottomSheetDialog, Dynamic theme |
| 59. [ActionBar-PullToRefresh](https://github.com/chrisbanes/ActionBar-PullToRefresh) | ActionBar-PullToRefresh 是一个下拉刷新, 下拉刷新时在 ActionBar 出现加载中提示的库 |
| 60. [FloatingActionButton](https://github.com/makovkastar/FloatingActionButton) | 又一个悬浮操作按钮库, 该库添加支持监听滑滚动事件, 当向下滑时按钮隐藏, 向上滑时按钮显示, 还有动画效果, 支持监听 ListView, ScrollView, RecylerView |
| 61. [AndroidAsync](https://github.com/koush/AndroidAsync) | AndroidAsync 是一款基于 NIO 的低端 Android 异步 socket, http (client+server), websocket 和 socket.io 网络通信协议类库 |
| 62. [rebound](https://github.com/facebook/rebound) | Rebound 是 Facebook 推出的一个弹性动画库, 可以让动画看起来真实自然, 像真实世界的物理运动, 带有力的效果, 使用的参数则是 Facebook 的 origami 中使用的 |
| 63. [android-common](https://github.com/Trinea/android-common) | android-common-lib 是 Trinea 大神收集的一些开发通用的缓存, 公共 View 以及一些常用工具类 |
| 64. [RippleEffect](https://github.com/traex/RippleEffect) | RippleEffect 是一个实现在 Android 任何组件点击出现 Material Design 的波纹效果, 向下兼容到 Android API9 |
| 65. [SmoothProgressBar](https://github.com/castorflex/SmoothProgressBar) | SmoothProgressBar 是一个帮你的 App 方便实现可定制, 平滑动画的水平滚动进度条库 |
| 66. [recyclerview-animators](https://github.com/wasabeef/recyclerview-animators) | RecyclerView Animators 是一个对 Recycler 控件的 Item 添加以及删除增加动画效果, 动画效果有Scale, Fade, Flip, Slide 里面各种各样效果 |
| 67. [circular-progress-button](https://github.com/dmytrodanylyk/circular-progress-button) | 一个带进度显示的 Button, 效果和动画做的都非常赞 |
| 68. [DroidPlugin](https://github.com/Qihoo360/DroidPlugin) | DroidPlugin 是 360 手机助手在 Android 系统上实现了一种新的插件机制: 它可以在无需安装, 修改的情况下运行APK文件, 此机制对改进大型APP的架构, 实现多团队协作开发具有一定的好处 |
| 69. [dynamic-load-apk](https://github.com/singwhatiwanna/dynamic-load-apk) | 开发者是 singwhatiwanna(任玉刚), 是《Android 开发艺术探索》书籍的作者, 这个是作者联合另两位开发者啸(时之沙)和宋思宇花了几个月时间研究出来的 Apk 动态加载框架, 想了解更多关于这框架可到作者博客看 [这篇文章](http://www.open-open.com/lib/view/open1463059225204.html) 有详细介绍 |
| 70. [ExoPlayer](https://github.com/google/ExoPlayer) | ExoPlayer 是Google 开发团队开源出来的一个媒体播放库, 比 Android 框架原生的 MediaPlayer 拥有更多优点支持动态的自适应流 HTTP(DASH) 和 平滑流, 支持高级的HLS特性, 支持自定义和扩治你的使用场景等等 |
| 71. [Crouton (不建议使用)](https://github.com/keyboardsurfer/Crouton) | Crouton 是一个显示提示信息的显示工具类, 可以用来代替 Toast, 默认显示在窗口的顶部, 可以按队列一个接着一个显示, 不过该库已经被弃用, 不推荐使用 |
| 72. [robospice](https://github.com/stephanenicolas/robospice) | RoboSpice 是一个使你建立异步的长时间的运行任务异常轻松的一个网络库，在网络请求，缓存支持，和提供开箱即用的 rest 请求方面尤为强大 |
| 73. [hugo](https://github.com/JakeWharton/hugo) | Hugo 是 JakeWharton 大神推出的一个用于打印 Log, hugo 是基于注解被调用的, 引入相关依赖后, 在方法上加上 @DebugLog 即可输出 Log, 使用非常简单 |
| 74. [async-http-client](https://github.com/AsyncHttpClient/async-http-client) | AsyncHttpClient 是又一款 Android 异步请求库, 该库支持 WebSocket 协议, 使用起来也比较简单易用 |
| 75. [UltimateRecyclerView](https://github.com/cymcsg/UltimateRecyclerView) | UltimateRecyclerView 是一个功能强大的 RecyclerView(advanced and flexible version of ListView), 包括了下拉刷新, 加载更多, 多种动画, 空数据提示, 拖动排序, 视差处理, 工具栏渐变, 滑动删除, 自定义floating button, 多种刷新效果, scrollbar, sticky header, 多 layout 支持等等元素, 而且使用起来跟 RecyclerView 一样的方便 |
| 76. [MaterialEditText](https://github.com/rengwuxian/MaterialEditText) | MaterialEditText 是就职于 Flipboard 的员工 [扔物线](https://www.zhihu.com/people/rengwuxian) 开发的, 在 AppCompat v21 中也提供了 Material Design 的控件 EditText, 可是由于比较难用, 没有提供设置颜色的 Api, 于是就产生这个第三方库 |
| 77. [Side-Menu.Android](https://github.com/Yalantis/Side-Menu.Android) | Side Menu 是 [Yalantis](https://yalantis.com/) 组织开源出来, 该组织因开源出一些动画很棒的开源库为大家所熟知该库是其中一个, 该库是提供翻页动画效果的侧边菜单, 动画体验超赞的 |
| 78. [drag-sort-listview](https://github.com/bauerca/drag-sort-listview) | DragSortListView 是一个可以实现拖动排序, 滑动删除的 listview 控件, 注意的是作者对该库已经放弃维护更新了, 不过感兴趣的人可以去研究一下 |
| 79. [android-times-square](https://github.com/square/android-times-square) | TimesSquare 是 Square 公司出品的一款显示日历选择日期的控件, 可以让用户选择多个日期 |
| 80. [GreenDroid(不建议使用)](https://github.com/cyrilmottier/GreenDroid) | GreenDroid 是一个封装好的 Android UI 界面库, 不过该库已经被弃用了, 不建议使用 |
| 81. [logger](https://github.com/orhanobut/logger) | Logger 是一个简单, 漂亮, 强大 Android 打印日志库 |
| 82. [acra](https://github.com/ACRA/acra) | Acra 是一个能够让 Android 应用自动将崩溃报告以谷歌文档电子表的形式进行发送的库, 旨在当应用发生崩溃或出现错误行为时, 开发者可以获取到相关数据 |
| 83. [FadingActionBar](https://github.com/ManuelPeinado/FadingActionBar) | FadingActionBar 是一个支持 ListView, ScrollView, WebView 向下滚动时逐渐显示 ActionBar 库 |
| 84. [AndroidImageSlider](https://github.com/daimajia/AndroidImageSlider) | AndroidImageSlider 库开发者是代码家, 该库是为 Banner 图片滑动提供多种动画效果, 还可以轻易为 Banner 加载网络图片 |
| 85. [SystemBarTint](https://github.com/jgilfelt/SystemBarTint) | SystemBarTint 是一个实现沉浸式状态栏库, 适用于 Android 系统 4.4 其以上的版本 |
| 86. [android-menudrawer](https://github.com/SimonVT/android-menudrawer) | MenuDrawer 是一款滑出式菜单库, 通过拖动屏幕边缘滑出菜单, 支持屏幕上下左右划出, 支持当前 View 处于上下层, 支持 Windows 边缘, ListView 边缘, ViewPager 变化划出菜单等 |
| 87. [RoundedImageView](https://github.com/vinc3m1/RoundedImageView) | RoundedImageView 一个快速支持图片圆角显示效果的库, 该库特点是能快速加载, 为了提高加载速度, 该库不用创建原始位图的副本, 不使用 clipPath, 不使用 setXfermode 裁剪的位图等方式来实现 ImageView 圆角, 使用也非常简单 |
| 88. [afinal](https://github.com/yangfuhai/afinal) | Afinal 是一个 android 的 sqlite orm 和 ioc 框架, 同时封装了 android 中的 http 框架, 使其更加简单易用, 使用 finalBitmap, 无需考虑 bitmap 在 android 中加载的时候 oom 的问题和快速滑动的时候图片加载位置错位等问题, Afinal 的宗旨是简洁, 快速, 约定大于配置的方式, 尽量一行代码完成所有事情 |
| 89. [android-pulltorefresh(不建议使用)](https://github.com/johannilsson/android-pulltorefresh) | 另一个下拉刷新库, 但是该库已经停止维护, 因此不建议使用, 推荐使用 [Android-Ultra-Pull-To-Refresh](https://github.com/liaohuqiu/android-Ultra-Pull-To-Refresh) |
| 90. [Bolts-Android](https://github.com/BoltsFramework/Bolts-Android) | Bolts 是一款底层类库集合, 在后台实现异步操作, 并提供接口反馈当前异步执行的程度 (可以通过接口实现UI进度更新), 最后反馈执行的结果给UI主线程, 与AsyncTask比较: (1)使用的是无大小限制的线程池; (2)任务可组合可级联,防止了代码耦合 |
| 91. [NumberProgressBar](https://github.com/daimajia/NumberProgressBar) | NumberProgressBar 开发者是代码家, 这是一个带简约性感数字显示的进度条库, 使用非常简单方便 |
| 92. [SwipeBackLayout](https://github.com/ikew0ng/SwipeBackLayout) | SwipeBackLayout 是一个支持屏幕上下左右滑动返回上层 Activity, 关闭当前 Activity, 类似简书 App |
| 93. [android-gif-drawable](https://github.com/koral--/android-gif-drawable) | 一个支持 gif 显示的 view, 用 jni 实现的, 编译生成 so 库后直接 xml 定义 view 即可, 简单易用 |
| 94. [VitamioBundle](https://github.com/yixia/VitamioBundle) | Vitamio 是一款 Android 与 iOS 平台上的全能多媒体开发框架, 特点：(1) 全面支持硬件解码与 GPU 渲染, (2) 能够流畅播放 720P 甚至 1080P 高清 MKV, FLV, MP4, MOV, TS, RMVB 等常见格式的视频, (3) 在 Android 与 iOS 上跨平台支持 MMS, RTSP, RTMP, HLS(m3u8)等常见的多种视频流媒体协议, 包括点播与直播 |
| 95. [SmartTabLayout](https://github.com/ogaclejapan/SmartTabLayout) | SmartTabLayout 是一个自定义的 Tab title strip, 基于 Google Samples 中的 android-SlidingTabBasic 项目, 滑动时 Indicator 可平滑过渡 |
| 96. [uCrop](https://github.com/Yalantis/uCrop) | uCrop 是[Yalantis](https://yalantis.com/) 组织开源的图片裁剪库, 支持缩放, 旋转图片, 支持各种比例的裁剪框, 非常强大的一个图片裁剪库 |
| 97. [android-crop](https://github.com/jdamcd/android-crop) | 又一个图片裁剪库, 向下兼容到 Api 10, 个人感觉这个库并没有比上面介绍的 uCrop 强大 |
| 98. [HoloEveryWhere](https://github.com/Prototik/HoloEverywhere) | HoloEveryWhere 是一套 Android 开发库, 提供了全套 Holo Style 控件, 它的外观与功能和标准 Holo Style 控件基本相同, 唯一不同的是它可以运行在低于 4.0 版本的 Android 系统上 |
| 99. [AVLoadingIndicatorView](https://github.com/81813780/AVLoadingIndicatorView) | AVLoadingIndicatorView 库含有各种各样漂亮的加载动画效果, 使用起来也非常简单, 和平时使用 ProgressBar 一样 |
| 100. [sweet-alert-dialog](https://github.com/pedant/sweet-alert-dialog) | Android 版的 SweetAlert, 清新文艺, 快意灵动的甜心弹框, 灵感来源于 JS 版[SweetAlert](http://t4t5.github.io/sweetalert/) |

### 粗计 ###
{% textcolor success %}
 Square 公司占有 7 席
 {% endtextcolor %}

| 项目名称 | 排名 |
| --- |:-------------- |
| [Retrofit](https://github.com/square/retrofit) | 4 |
| [OkHttp](https://github.com/square/okhttp) | 5 |
| [Picasso](https://github.com/square/picasso) | 7 |
| [LeakCanary](https://github.com/square/leakcanary) | 13 |
| [Dagger](https://github.com/square/dagger) | 29 |
| [Otto](https://github.com/square/otto) | 44 |
| [TimesSquare](https://github.com/square/android-times-square) | 79 |

{% textcolor success %}
 FaceBook 公司占有 4 席
 {% endtextcolor %}
 
| 项目名称 | 排名 |
| --- | --- |
| [React Native](https://github.com/facebook/react-native) | 1 |
| [Fresco](https://github.com/facebook/fresco) | 11 |
| [Stetho](https://github.com/facebook/stetho) | 38 |
| [Rebound](https://github.com/facebook/rebound) | 62 |

{% textcolor success %}
JakeWharton 大神占有 5 席
 {% endtextcolor %}

| 项目名称 | 排名 |
| --- | --- |
| [Butter Knife](https://github.com/JakeWharton/butterknife) | 14 |
| [ActionBarSherlock](https://github.com/JakeWharton/ActionBarSherlock) | 16 |
| [ViewPagerIndicator](https://github.com/JakeWharton/ViewPagerIndicator) | 18 |
| [NineOldAndroids](https://github.com/JakeWharton/NineOldAndroids) | 55 |
| [Hugo](https://github.com/JakeWharton/hugo) | 73 |

{% textcolor success %}
代码家大神占有 4 席
 {% endtextcolor %}

| 项目名称 | 排名 |
| --- | --- |
| [AndroidSwipeLayout](https://github.com/daimajia/AndroidSwipeLayout) | 28 |
| [AndroidViewAnimations](https://github.com/daimajia/AndroidViewAnimations) | 32 |
| [AndroidImageSlide](https://github.com/daimajia/AndroidImageSlider) | 84 |
| [NumberProgressBar](https://github.com/daimajia/NumberProgressBar) | 91 |

### IOS 项目 ###

主要对当前 GitHub 排名前 100 的项目做一个简单的简介, 方便初学者快速了解到当前 `Objective-C` 在 GitHub 的情况。

| 项目名称 | 项目信息 |
| --- | --- |
| 1. [AFNetworking](https://github.com/AFNetworking/AFNetworking) | 作者是 NSHipster 的博主, iOS 开发界的大神级人物, 毕业于卡内基·梅隆大学, 开源了许多牛逼的项目, 这个便是其中之一, AFNetworking 采用 NSURLConnection + NSOperation, 主要方便与服务端 API 进行数据交换, 操作简单, 功能强大, 现在许多人都用它取代 ASIHTTPRequest |
| 2. [GPUImage](https://github.com/BradLarson/GPUImage) | 一款强大的图片滤镜工具, 支持自定义滤镜, 可用来实时处理图片和视频流, 作者是 SonoPlot 公司的 CTO, 在很小的时候便开始接触编程, 他在 [SO](http://stackoverflow.com/users/19679/brad-larson)上面的回答也有很多值得阅读, GPUImage 这个项目从 2012 年开始, 使用 OpenGL 图形程序接口编写, 性能非常好, 现在很多 iOS 程序员都用它来实现 iOS 的模糊效果 |
| 3. [SDWebImage](https://github.com/rs/SDWebImage) | 作者 Olivier Poitrey 是 Dailymotion 的 CTO, 拥有多个不错的开源项目, 此项目常用于对从 Web 端接受到的图片进行缓存, 是 UIImageView 的扩展, 应用起来比较简单 |
| 4. [RestKit](https://github.com/RestKit/RestKit) | 主要用于 iOS 上网络通信, 允许与 RESTful Web 服务交互, 常用于处理 API, 解析 JSON, 映射响应对象等操作, 简单易用, 方便你把所有精力都放在对数据的操作上 |
| 5. [ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa) | 由 GitHub 工程师们开发的一个应用于 iOS 和 OS X 开发的函数响应式编程新框架, Matt 称其为 "An open source project that exemplifies this brave new era for Objective-C", 也有人说它是 Cocoa 的未来, 具体可看唐巧写的这篇[文章](http://www.devtang.com/blog/2014/02/11/reactivecocoa-introduction) |
| 6. [three20](https://github.com/facebookarchive/three20) | 由 Facebook iOS 客户端衍生出的一款 iPhone 框架, 内置许多丰富的功能, 有丰富的界面, 对底层的操作便捷, 为开发者省下了很多时间, 但现在已经停止了更新, 一个 [PR](https://github.com/facebookarchive/three20/pull/832?utm_source=iOS+Dev+Weekly&utm_campaign=46a7deb647-iOS_Dev_Weekly_Issue_100&utm_medium=email&utm_term=0_7bda94b7ca-46a7deb647-299428269) 把代码删得干干净净, 不要好奇去点开 Files changed, 我点开后该页面直接卡死, three20 当中的一位作者创建了 [Nimbus](https://github.com/jverkoey/nimbus), 算是 three20 的一个替代品 |
| 7. [MBProgressHUD](https://github.com/jdg/MBProgressHUD) | 作者 Matej Bukovinski 是一位全栈工程师, UI/UX 设计师, 此项目是一款提示框第三方库, 帮助开发者快速应用到项目中) |
| 8. [MagicalRecord](https://github.com/magicalpanda/MagicalRecord) | 作者是 Coursera 的 iOS 工程师, 该项目创作灵感来自于 Ruby on Rails 的 Active Record, 主要为方便操作 CoreData 而生, 帮助清除 CoreData 引用的代码, 协助方便 CoreData 的工作 |
| 9. [FMDB](https://github.com/ccgus/fmdb) | 一个对 SQLite 进行封装的库, 使用起来方便, 简单 |
| 10. [Mantle](https://github.com/Mantle/Mantle) | 作者是 GitHub 的员工, 文档写的很清楚: Mantle makes it easy to write a simple model layer for your Cocoa or Cocoa Touch application, 主要用来将 JSON 数据模型化为 Model 对象, 唱吧在前段时间也改用 Mantle 了. |
| 11. [FlatUIKit](https://github.com/Grouper/FlatUIKit) | 收集了很多扁平化 UI 的 iOS 组件, 方便使用 |
| 12. [ASIHTTPRequest](https://github.com/pokeb/asi-http-request) | 一个轻量级的 iOS 网络通信类库, 基于 CFNetwork 框架开发, 但现在已经停止更新, 多数开发者改用 AFNetworking 替代) |
| 13. [FastImageCache](https://github.com/path/FastImageCache) | Path 公司出品的 iOS 库, 作者 Mallory Paine 是苹果前员工, 此类库适用于在滚动时快速显示图像, 高速持久是其最大的特点 |
| 14. [Masonry](https://github.com/Masonry/Masonry) | 一个轻量级的布局框架, 同时支持 iOS 和 Mac OS X, 语法优雅, 帮助开发者快速适配不同分辨率的 iOS 设备 |
| 15. [Shimmer](https://github.com/facebook/Shimmer) | Facebook 推出的一款具有闪烁效果的第三方控件, 供它旗下一款名为 Paper 的应用使用, 安装使用整个过程都十分简单 |
| 16. [SVProgressHUD](https://github.com/TransitApp/SVProgressHUD) | 又一款轻量级的 iOS 第三方控件, 用于显示任务加载时的动画, 非常轻便, 容易使用 |
| 17. [Slate](https://github.com/jigish/slate) | 一款窗口管理应用程序, 但在两年前就已经停止更新了 |
| 18. [JSONKit](https://github.com/johnezang/JSONKit) | 主要用于解析 JSON, 适用于 iOS6 以下环境, 自从 iOS5 开始 Apple 官方给出了 NSJSONSerialization API, 自此大家都用官方的了 |
| 19. [Nimbus](https://github.com/jverkoey/nimbus) | 作者 Jeff 曾为 Facebook, Google 做过不少好东西, 也是 three20 的成员之一, three20 停更后, 他创造出这个框架来代替 three20, 文档齐全 |
| 20. [CocoaLumberjack](https://github.com/CocoaLumberjack/CocoaLumberjack) | 这是 Mac 和 iOS 的一款强大的日志框架, 配置简单, 多线程, 提供更高级的 log 功能, 可用于代替默认的 NSLog 语句 |
| 21. [Facebook SDK for iOS](https://github.com/facebook/facebook-ios-sdk) | Facebook 官方的 iOS SDK, 方便开发者集成 Facebook 的一些功能到自己的 iOS APP 里面 |
| 22. [AsyncDisplayKit](https://github.com/facebook/AsyncDisplayKit) | Facebook 开源的一款 iOS UI 框架, Paper 用的就是该框架, 另外框架还用到了 Facebook 早期开源 Pop 动画引擎 |
| 23. [Alcatraz](https://github.com/supermarin/Alcatraz) | Alcatraz 是一款管理 Xcode 插件、模版以及颜色配置的工具, 可以集成到 Xcode 的图形界面中, 安装删除都是几条命令的事, 很方便, 支持自己开发插件并上传 |
| 24. [ViewDeck](https://github.com/Inferis/ViewDeck) | 一款开源的 iOS 活动面板组件, 还原 Path 2.0 的侧滑效果, 作者因为时间关系在两年前停止对其更新 |
| 25. [JSQMessagesViewController](https://github.com/jessesquires/JSQMessagesViewController) | 优雅的 iOS 消息类库, 常用于聊天应用中, 可定制性高 |
| 26. [FLEX](https://github.com/Flipboard/FLEX) | 这是 Flipboard 官方发布的一组专门用于 iOS 开发的应用内调试工具, 开发者无需将其连接到 LLDB/Xcode 或其他远程调试服务器,支持直接在 App 中运行 |
| 27. [Xctool](https://github.com/facebook/xctool) | 是 Facebook 开源的一个命令行工具，用来替代苹果的 XcodeBuild 工具, 极大的方便了 iOS 的构建和测试, 输出错误信息也比较友好, 受到许多 iOS 开发者的称赞, 经常与其搭配使用的还有 OCUnit, [Travis CI](https://travis-ci.org/), [OCLint](http://oclint.org/) 等测试工具 |
| 28. [OpenEmu](https://github.com/OpenEmu/OpenEmu) | 超强的游戏模拟器, 做游戏开发必备, 官网做得也很不错 |
| 29. [iCarousel](https://github.com/nicklockwood/iCarousel) | 作者是英国 Charcoal Design 公司的创始人, 开源领域的贡献颇为卓著, 这个项目就是其中之一, 这是一款可以在 iOS 上实现旋转木马视图切换效果的第三方控件, 并提供多种切换效果 |
| 30. [RESideMenu](https://github.com/romaonthego/RESideMenu) | 作者 Roman Efimov 是雅虎的 iOS 工程师, 这个项目实现了 iOS 上的菜单侧滑效果, 创意来源于 Dribbble, 该项目支持 iOS8 |
| 321 [PNChart](https://github.com/kevinzhow/PNChart) | 作者周楷雯是 90 后, 秒视的创始人, 该项目是一个带动画效果的图表控件, 简约易用, 受到不少开发者喜爱 |
| 31.2[PonyDebugger](https://github.com/square/PonyDebugger) | 由 Square 公司推出的一款优秀的 iOS 应用网络调试工具, 用户可以实时看到应用程序的网络请求, 也可以对 iOS 应用程序的核心数据栈进行远程调试 |
| 33. [JVFloatLabeledTextField](https://github.com/jverdi/JVFloatLabeledTextField) | 作者是 Thumb Labs 的联合创始人, JVFloatLabeledTextField 是 UITextField 的子类, 主要实现输入框标签浮动效果, 创作灵感来自 Dribbble, 已出现多个移植版本 |
| 34. [SWTableViewCell](https://github.com/CEWendel/SWTableViewCell) | UITableViewCell 的子类, 实现了左右滑动显示信息视图并调出按钮 |
| 35. [AwesomeMenu](https://github.com/levey/AwesomeMenu) | 作者是一位中国人, 该项目主要是使用 CoreAnimation 还原了 Path menu 的动画效果 |
| 36. [Reachability](https://github.com/tonymillion/Reachability) | Reachablity 是用于检测 iOS 设备网络环境的库 |
| 37. [VVDocumenter-Xcode](https://github.com/onevcat/VVDocumenter-Xcode) | 作者是王巍国内著名的 iOS 开发者, 人称喵神, 目前在日本 LINE 公司工作, 该项目帮助开发者轻松的生成注释文档, 节省了不少工作量, 赞 |
| 38. [The Physical Web](https://github.com/google/physical-web) | 由 Chrome 团队主导的一个项目, 意在用 URL 连接世界, 方便用户接受数据, 目前尚处在实验阶段 |
| 39. [NewsBlur](https://github.com/samuelclay/NewsBlur) | 作者独自一个人 Samuel Clay 做出来的一款名为 NewsBlur 的新闻阅读器, 很多人都称其为 Google Reader 的替代品, 这是它的源码 |
| 40. [Cocos2D-SpriteBuilder](https://github.com/cocos2d/cocos2d-spritebuilder) | 一个可用于在 iOS, Mac 和 Android 上制作 2D 游戏或其它图形/交互应用的框架, 之前的项目名称为 Cocos Swift, 目前该项目在 GitHub 上更新较为频繁 |
| 41. [TTTAttributedLabel](https://github.com/TTTAttributedLabel/TTTAttributedLabel) | UILabel 的替代品, 使 iOS 上的 Label 功能更加丰富, 可支持链接植入等功能 |
| 42. [CocoaAsyncSocket](https://github.com/robbiehanson/CocoaAsyncSocket) | 一个功能强大、简单易用的异步 socket 通讯类库, 支持 TCP 和 UDP 协议, 可用于 Mac 和 iOS 设备上, 作者 Robbie Hanson 是 Deusty 的首席软件工程师 |
| 43. [TapkuLibrary](https://github.com/devinross/tapkulibrary) | 作者是 Devin Ross, 这是在 iOS 上一款功能强大的 UI 效果类库, 可以实现多种酷炫的效果, 目前仍在更新中 |
| 44. [Canvas](https://github.com/CanvasPod/Canvas) | 无需编码实现牛逼的动画效果的库, 连设计师都可以快速上手 |
| 45. [SocketRocket](https://github.com/square/SocketRocket) | Square 公司开源的一个 WebSocket 客户端, 稳定并且易用, 做实时应用常会用到, 受广大开发者喜爱 |
| 46. [ECSlidingViewController](https://github.com/ECSlidingViewController/ECSlidingViewController) | 一个视图控制器容器, 将子视图处理成两层, 通过滑动来处理层的切换, 创作灵感来自 Facebook 和 Path的 App, 作者是 Cleveland 的员工 |
| 47. [Json Framework](https://github.com/stig/json-framework) | 用于解析 JSON 数据的一个框架, 但是在 iOS5 以上版本大多数人都选择使用 NSJSONSerialization 来解析 JSON, 该项目现在在 GitHub 上也几乎没怎么更新了 |
| 48. [Tweaks](https://github.com/facebook/Tweaks) | Facebook 开源的一款工具, 旨在帮助 iOS 开发者更快的迭代应用, 方便用户动态的调整参数, 是的, Paper 这个项目也用到了 |
| 49. [realm-cocoa](https://github.com/realm/realm-cocoa) | Realm-Cocoa 是 Realm 公司推出一款移动端数据库, 可以运行在手机、平板和可穿戴设备之上, 其目标是取代 CoreData 和 SQLite 数据库 |
| 50. [BlocksKit](https://github.com/zwaldowski/BlocksKit) | 一个开源的与 Cocoa 紧密集合的基础性框架 |
| 51. [Appirater](https://github.com/arashpayan/appirater) | 一款用于提醒用户给你的 App 打分的工具 |
| 52. [KIF](https://github.com/kif-framework/KIF) | Square 出品的一个开源的用户界面测试框架, 极大的简化了 iOS 开发者的 UI 测试流程 |
| 53. [SlackTextViewController](https://github.com/slackhq/SlackTextViewController) | Slack 推出的一款具有文字输入框高度自适应, 自动输入, 复制单元格内容等功能的解决方案 |
| 54. [JazzHands](https://github.com/IFTTT/JazzHands) | IFTTT 开源的一个简单易用的关键帧基础动画框架, 可通过手势、scroll views, KVO, ReactiveCocoa 等方式来控制动画 |
| 55. [Bolts-iOS](https://github.com/BoltsFramework/Bolts-iOS) | Bolts 是一个 Parse 和 Facebook 在内部使用的底层库, 方便移动开发 |
| 56. [Spectacle](https://github.com/eczarny/spectacle) | 一款易用的 OS X 窗口分屏操作快捷键工具, 这是其源代码 |
| 57. [nui](https://github.com/tombenner/nui) | 方便样式化 iOS 应用中的 UI 元素, 可在短时间内样式化整个应用, 类 CSS 原理 |
| 58. [Induction](https://github.com/Induction/Induction) | Induction 是一款用于理解数据关系的管理工具, 这是其程序代码 |
| 59. [JSONModel](https://github.com/icanzilb/JSONModel) | 一个能迅速解析服务器返回的 Json 数据的库, 方便数据的类型转换 |
| 60. [DTCoreText](https://github.com/Cocoanetics/DTCoreText) | 一个开源的 iOS 富文本组件, 它可以解析 HTML 与 CSS 并最终用 CoreText 绘制出来, 通常用于在一些需要显示富文本的场景下代替低性能的 UIWebView |
| 61. [Popping](https://github.com/schneiderandre/popping) | 基于 Facebook Pop 引擎的 iOS 动画库, 集合了很多动画效果 |
| 62. [TSMessages](https://github.com/KrauseFx/TSMessages) | 一个用来弹出显示警告和通知的轻量级库, 样式丰富, 简单易用 |
| 63. [KVOController](https://github.com/facebook/KVOController) | 一个简单安全的 KVO(Key-value Observing, 键-值 观察)工具, 提供简单方便、线程安全的API, Facebook 的开源项目之一 |s
| 64. [MWPhotoBrowser](https://github.com/mwaterfall/MWPhotoBrowser) | 一款简单的 iOS 照片浏览控件 |
| 65. [MMDrawerController](https://github.com/mutualmobile/MMDrawerController) | 一个轻量级, 易于使用的侧边抽屉导航 iOS 控件 |
| 66. [QuickDialog](https://github.com/escoz/QuickDialog) | 用于快速创建复杂的 iOS 表单, 自定义了 UITableViewCell, TableView 的样式 |
| 67. [SVPullToRefresh](https://github.com/samvermette/SVPullToRefresh) | 一款只需一行代码便可集成上拉刷新和下拉加载的组件 |
| 68. [cheddar-ios](https://github.com/nothingmagical/cheddar-ios) | Cheddar 是一款简单易用的日程管理软件, 这是其早期版本的开源代码, 该项目已停止维护 |
| 69. [XVim](https://github.com/XVimProject/XVim) | 一款在 Xcode 上实现了 Vim 功能的插件 |
| 70. [EGOTableViewPullRefresh](https://github.com/enormego/EGOTableViewPullRefresh) | 一款提供下拉刷新的控件, 最后更新时间是一年前 |
| 71. [iOS-boilerplate](https://github.com/gimenete/iOS-boilerplate) | iOS 应用程序的基础模板, 使用该模板可以省掉许多项目初始编码的工作, 内置非常多丰富的功能, 现已经停止维护 |
| 72. [JASidePanels](https://github.com/gotosleep/JASidePanels) | 一个 UIViewController 容器, 灵感来自 Facebook 和 Path 2.0 应用的菜单, 实现了左右侧滑的操作 |
| 73. [FormatterKit](https://github.com/mattt/FormatterKit) | 收集了很多构思优秀的 NSFormatter 子类 |
| 74.[MSDynamicsDrawerViewController](https://github.com/erichoracek/MSDynamicsDrawerViewController) | 实现了具有动态弹性效果的抽屉式侧边导航栏, 效果丰富, 可定制性强 |
| 75. [idev-recipes](https://github.com/boctor/idev-recipes) | iDevRecipes 博客的代码, 演示如何实现一些有趣的控件, 该项目在两年前(2013)停止了更新 |
| 76. [XMPPFramework](https://github.com/robbiehanson/XMPPFramework) | 一个基于 RFC-3920 实现, 支持多线程和线程保护, 同时通用于所有的 iOS 和 Mac OS 开发设备的通信框架. |
| 77. [MacGap1](https://github.com/MacGapProject/MacGap1) | 一款可以将 HTML/CSS/JS 网络应用打包成原生 Mac App 的工具 |
| 78. [FXBlurView](https://github.com/nicklockwood/FXBlurView) | iOS 模糊背景类库, 可以方便的根据底层显示的状态生成模糊效果 |
| 79. [iOS7-Sampler](https://github.com/shu223/iOS7-Sampler) | 整合演示了多个具有 iOS7 新特性的的项目, 提供了非常多的例子参考 |
| 80. [PromiseKit](https://github.com/mxcl/PromiseKit) | 提供强大的 iOS 开发异步功能, 是 Promises 的实现, 受到广大开发者的追捧 |
| 81. [Origami](https://github.com/facebook/origami) | 此为 Facebook 推出的 Quartz Composer 的一个开源插件, 由其设计团队花费了 9 个月打造而成, 目的是为方便设计师快速构建原型, 以零代码完成复杂动画的合成和测试, 堪称神器 |
| 82. [NSLogger](https://github.com/fpillet/NSLogger) | 一款强大的日志分析工具, 具有大窗口查看 Log, 自定义日志等级等功能 |
| 83. [KSImageNamed-Xcode](https://github.com/ksuther/KSImageNamed-Xcode) | 一款对 UIImage 的 imageNamed 提供自动补全功能的插件, 非常方便 |
| 84. [PureLayout](https://github.com/smileyborg/PureLayout) | 一个简单却强大的 AutoLayout API 库, 兼容了 Objective-C 和 Swift, 扩展了 UIView/NSView, NSArray, 和 NSLayoutConstraint |
| 85. [AppleDoc](https://github.com/tomaz/appledoc) | 一款 Objective-C 文档生成工具, 生成的文档风格保持与 Apple 官方的一致, 极大的方便了 Xcode 识别自己写的 API 文档, 安装也是十分的简单 |
| 86. [iTerm2](https://github.com/gnachman/iTerm2) | iTerm2 被不少程序员称赞为 Mac 下最好用的终端, 这是其源代码, 配合 oh-my-zsh 使用效果更佳 |
| 87. [Kiwi](https://github.com/kiwi-bdd/Kiwi) | 一个行为驱动开发测试框架, 适用于 iOS 平台, 旨在为开发者提供一个简单配置便可使用的 BDD 库 |
| 88. [terminal-notifier](https://github.com/alloy/terminal-notifier) | 一款命令行工具, 用来给 Mac OS X 用户发送通知 |
| 89. [MacDown](https://github.com/uranusjr/macdown) | Mac OS X 下的一款开源的 Markdown 编辑器, 创意来自与 Mou, 使用 brew cask 即可完成安装 |
| 90. [TwUI](https://github.com/twitter/twui) | Twitter 开源的一个支持硬件加速的 Mac 的 UI 框架, 最后一次的更新时间是在 3 年前(2012) |
| 91. [PaperFold for iOS](https://github.com/honcheng/PaperFold-for-iOS) | 实现了类似折纸效果的视图切换, 可从不同方向进行切换, 该项目已经许久未更新 |
| 92. [Reader](https://github.com/vfr/Reader) | 一款开源的 iOS PDF 阅读器, 附带书签, 列纲要等功能 |
| 93. [WebViewJavascriptBridge](https://github.com/marcuswestin/WebViewJavascriptBridge) | 一个方便使用 Objective-C 与 JavaScript 进行通信的第三方库, 支持消息发送, 接收, 消息处理器的注册与调用以及设置消息处理的回调 |
| 94. [iOS8-Sampler](https://github.com/shu223/iOS8-Sampler) | iOSX-Sampler 系列之一, 整合演示了多个具有 iOS8 新特性的的项目, 提供了非常多的例子参考 |
| 95. [CocoaHTTPServer](https://github.com/robbiehanson/CocoaHTTPServer) | 一个用于 Mac OS X 或 iOS 应用的轻量级、可嵌入的HTTP 服务器框架, 方便开发者在应用中嵌入一个 HTTP 服务器 |
| 96. [Kod](https://github.com/rsms/kod) | Mac OS X 上一款专为程序员打造的编辑器, 这是其开源代码, 可惜的是作者在 2011 年停止了维护 |
| 97. [TPKeyboardAvoiding](https://github.com/michaeltyson/TPKeyboardAvoiding) | 下拉键盘在 iOS 移动文本字段的通用解决方案, 能够自动处理键盘弹出后出现遮挡到文本输入框的问题 |
| 98. [MKNetworkKit](https://github.com/MugunthKumar/MKNetworkKit) | 一个轻量级网络请求框架, 完全基于 ARC, 仅有两个类, 具有自主操作多个网络请求, 更加准确的显示网络活动指标等优点 |
| 99. [PKRevealController](https://github.com/pkluz/PKRevealController) | 一个 iOS 平台上的视图控制器集合, 通过展现多个视图控制器来进行控制器之间的切换. 设置简单, 高度灵活 |
| 100. [AQGridView](https://github.com/AlanQuatermain/AQGridView) | 一个命令行工具, 通过项目里的 `.xcdatamodel` 文件, 可以为每个 entity 生成两个类, 方便 CoreData 的使用 |