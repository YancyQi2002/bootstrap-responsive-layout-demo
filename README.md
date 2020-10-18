# Bootstrap项目案例学习：阿里百秀首页

### 第一章 概述

##### 技术选型：

方案：采取响应式页面开发方案

技术：Bootstrap 框架

设计图：1280px设计尺寸

##### 需求分析：

###### 1.页面布局分析

![](./页面布局.png)

###### 2.屏幕划分分析

① 屏幕缩放发现 中屏幕 和 大屏幕 布局是一致的。因此将列定义为 col-md- 就可以了。(md : ≥970)

② 屏幕缩放发现 小屏幕 布局发生变化。因此需要为 小屏幕 根据需求改变布局。

③ 屏幕缩放发现 超小屏幕 布局又发生变化。因此需要为 超小屏幕 根据需求改变布局。

④ 策略：先布局 md 以上的PC端布局，最后根据实际需求修改 小屏幕 和 超小屏幕 的特殊布局样式。

### 第二章 页面制作

#### Bootstrap 使用四部曲：

（1）创建文件夹结构 （2）创建 html 骨架结构 （3）引入相关样式文件 （4）书写内容

##### **$\textcolor{red}{（1）创建文件夹结构} $**

```
.alibaixiu/
	│▁▁.bootstrap
	│▁▁.css
	│▁▁.images
	│▁▁.upload
	│▁▁index.html
```

##### **$\textcolor{red}{（2）创建 html 骨架结构} $**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge,chrome=1">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

```html
<!-- [if lt IE 9]>
<script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
<script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
<![engif] -->
```

##### **$\textcolor{red}{（3）引入相关样式文件} $**

```html
<!-- 引入bootstrap样式文件 -->
<link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
<!-- 引入自己的首页样式文件 -->
<link rel="stylesheet" href="css/index.css">
```

##### **$\textcolor{red}{（4）书写内容} $**

```html
<body>
    123  <!-- 测试 -->
</body>
```

```html
<body>
    <div class="container">123</div>
</body>
```

#### container 宽度修改

因为效果图采取1280的宽度，而Bootstrap里面container宽度最大为1170px，因此需要手动改下container宽度

```css
/* 修改container的最大宽度为 1280 */
@media screen and (min-width: 1280px) {
    .container {
        width: 1280px;
    }
}
```

#### 页面布局

###### 总体（一行分三列）：

```html
<div class="container">
	<div class="row">
        <header class="col-md-2">左侧</header>
        <article class="col-md-7">中间</article>
    	<aside class="col-md-3">右侧</aside>
	</div>
</div>
```

###### 左侧布局：

```html
<header class="col-md-2">
	<div class="logo">
    	<a href="#">
        	<img src="images/logo.png" alt="">
        </a>
    </div>
    
    <div class="nav">
    	<ul>
        	<li>
            	<a href="#">
                	<svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-camera-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                    	<path d="M10.5 8.5a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0z"/>
                        <path fill-rule="evenodd" d="M2 4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2h-1.172a2 2 0 0 1-1.414-.586l-.828-.828A2 2 0 0 0 9.172 2H6.828a2 2 0 0 0-1.414.586l-.828.828A2 2 0 0 1 3.172 4H2zm.5 2a.5.5 0 1 0 0-1 .5.5 0 0 0 0 1zm9 2.5a3.5 3.5 0 1 1-7 0 3.5 3.5 0 0 1 7 0z"/>
                    </svg>
                    生活馆
                 </a>
              </li>
              <li>
                 <a href="#">
                 	<svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-card-image" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                    	<path fill-rule="evenodd" d="M14.5 3h-13a.5.5 0 0 0-.5.5v9c0 .013 0 .027.002.04V12l2.646-2.354a.5.5 0 0 1 .63-.062l2.66 1.773 3.71-3.71a.5.5 0 0 1 .577-.094L15 9.499V3.5a.5.5 0 0 0-.5-.5zm-13-1A1.5 1.5 0 0 0 0 3.5v9A1.5 1.5 0 0 0 1.5 14h13a1.5 1.5 0 0 0 1.5-1.5v-9A1.5 1.5 0 0 0 14.5 2h-13zm4.502 3.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0z"/>
                    </svg>
                    自然汇
                  </a>
               </li>
               <li>
                  <a href="#">
                  	<svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-phone" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                    	<path fill-rule="evenodd" d="M11 1H5a1 1 0 0 0-1 1v12a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1zM5 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H5z"/>
                        <path fill-rule="evenodd" d="M8 14a1 1 0 1 0 0-2 1 1 0 0 0 0 2z"/>
                    </svg>
                    科技潮
                  </a>
               </li>
               <li>
                   <a href="#">
                         <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-wallet-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                            <path d="M1.5 2A1.5 1.5 0 0 0 0 3.5v2h6a.5.5 0 0 1 .5.5c0 .253.08.644.306.958.207.288.557.542 1.194.542.637 0 .987-.254 1.194-.542.226-.314.306-.705.306-.958a.5.5 0 0 1 .5-.5h6v-2A1.5 1.5 0 0 0 14.5 2h-13z"/>
                        	<path d="M16 6.5h-5.551a2.678 2.678 0 0 1-.443 1.042C9.613 8.088 8.963 8.5 8 8.5c-.963 0-1.613-.412-2.006-.958A2.679 2.679 0 0 1 5.551 6.5H0v6A1.5 1.5 0 0 0 1.5 14h13a1.5 1.5 0 0 0 1.5-1.5v-6z"/>
                    	</svg>
                 	奇趣事
                 </a>
             </li>
             <li>
                 <a href="#">
                     <svg width="1em" height="1.0625em" viewBox="0 0 16 17" class="bi bi-cup-straw" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                     	<path fill-rule="evenodd" d="M13.964 1.18a.5.5 0 0 1-.278.65l-2.255.902-.462 2.08c.375.096.714.216.971.368.228.135.56.396.56.82 0 .046-.004.09-.011.132l-.955 9.068a1.28 1.28 0 0 1-.524.93c-.488.34-1.494.87-3.01.87-1.516 0-2.522-.53-3.01-.87a1.28 1.28 0 0 1-.524-.93L3.51 6.132A.78.78 0 0 1 3.5 6c0-.424.332-.685.56-.82.262-.154.607-.276.99-.372C5.824 4.614 6.867 4.5 8 4.5c.712 0 1.389.045 1.985.127l.527-2.37a.5.5 0 0 1 .302-.355l2.5-1a.5.5 0 0 1 .65.279zM9.768 5.608A13.991 13.991 0 0 0 8 5.5c-1.076 0-2.033.11-2.707.278A3.284 3.284 0 0 0 4.645 6c.146.073.362.15.648.222C5.967 6.39 6.924 6.5 8 6.5c.571 0 1.109-.03 1.588-.085l.18-.808zm.292 1.756a5.513 5.513 0 0 0 1.325-.297l-.845 8.03c-.013.12-.06.185-.102.214-.357.249-1.167.69-2.438.69-1.27 0-2.08-.441-2.438-.69-.041-.029-.09-.094-.102-.214l-.845-8.03c.137.046.283.088.435.126.774.194 1.817.308 2.95.308.742 0 1.445-.049 2.06-.137zm-5.593-1.48s.003.002.005.006l-.005-.006zm7.066 0l-.005.006a.026.026 0 0 1 .005-.006zM11.354 6a3.282 3.282 0 0 1-.703.235l.1-.446c.264.069.464.142.603.211z"/>
                    </svg>
                	美食街
            	</a>
        	</li>
    	</ul>
	</div>
</header>
```

```css
ul {
    padding: 0;
    margin: 0;
    list-style-type: none;
}

a {
    text-decoration: none;
    color: #666;
}

a:hover {
    text-decoration: none;
}

/* 修改container的最大宽度为 1280 */
@media screen and (min-width: 1280px) {
    .container {
        width: 1280px;
    }
}

/* header */
header {
    padding-left: 0!important;
}

.logo {
    position: relative;
    background-color: #429ad9;
}

.logo img {
    width: 100%;
}

.nav {
    background-color: #eee;
    border-bottom: 1px solid #ccc;
}

.nav a {
    display: block;
    padding: 1px 53px;
    width: 100%;
    height: 60px;
    line-height: 60px;
    font-size: 16px;
}

.nav a:hover {
    color: #333;
    background-color: #fff;
}
```

![](./左侧布局.png)

###### 中间布局：

中间新闻布局：

![](./中间新闻布局.png)

中间发表布局：

![](./中间发表布局.png)

CSS样式代码：

```css
/* article */
.news li {
    float: left;
    padding-right: 10px;
    margin-bottom: 10px;
    width: 25%;
    height: 128px;
}

.news li a {
    display: block;
    position: relative;
    width: 100%;
    height: 100%;
}

.news li:nth-child(1) {
    width: 50%;
    height: 266px;
}

.news li:nth-child(1) p {
    padding: 0 10px;
    line-height: 41px;
    font-size: 20px;
}

.news li a img {
    width: 100%;
    height: 100%;
}

.news li a p {
    position: absolute;
    padding: 5px 10px;
    margin-bottom: 0;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 41px;
    font-size: 12px;
    color: #fff;
    background-color: rgba(0, 0, 0, .5);
}

.publish {
    border-top: 1px solid #ccc;
}

.publish .row {
    padding: 10px 0;
    border-bottom: 1px solid #ccc;
}

.pic {
    margin-top: 10px;
    margin-bottom: 10px;
}

.pic img {
    width: 100%;
    height: 100%;
}
```

###### 右侧布局：

![](./右侧布局.png)

```html
<aside class="col-md-3">
	<a href="#" class="banner">
		<img src="upload/zgboke.jpg" >
	</a>
	<a href="#" class="hot">
		<span class="btn btn-primary">热搜</span>
		<h4 class="text-primary">欢迎加入中国博客联盟</h4>
		<p class="text-muted">这里收录了国内各个领域的优秀博客，是一个全人工编辑的的开放式博客联盟交流和展示平台......</p>
	</a>
</aside>
```

```css
/* aside */
.banner img {
    width: 100%;
}

.hot {
    display: block;
    padding: 0 20px 20px;
    margin-top: 20px;
    border: 1px solid #ccc;
}

.hot span {
    margin-bottom: 20px;
    border-radius: 0;
}

.hot p {
    font-size: 12px;
}
```

###### 超小屏布局：

```html
<div class="logo">
	<a href="#">
		<img src="images/logo.png" class="d-none d-sm-block">
        <span class="d-sm-none">阿里百秀</span>
	</a>
</div>
```

```css
.logo img {
    display: block;
    margin: 0 auto;
    /* width: 100%; */
    /* logo图片不需要缩放 */
    max-width: 100%;
}

/* 进入超小屏幕下，logo图片隐藏 */

/* span元素平时隐藏，仅在超小屏幕下显示 */
.logo span {
    display: block;
    height: 50px;
    line-height: 50px;
    text-align: center;
    font-size: 18px;
    color: #fff;
}
```

![](./超小屏logo布局.png)

```css
/* 进入 小屏幕 和 超小屏幕 时， nav 里的 li 浮动起来， 并且宽度为 20% */
@media screen and (max-width: 991px) {
    .nav li {
        float: left;
        width: 20%;
    }

    .nav a {
        padding: 0 15px;
    }

    article {
        margin-top: 10px;
    }
}

/* 进入 超小屏幕 时， nav 文字变为 14px */
@media screen and (max-width: 767px) {
    .nav li a {
        font-size: 14px;
    }
}
```

```css
body {
    background-color: #f5f5f5;
}

.container {
    background-color: #fff;
}
```

![](./微调-1.png)

```css
/* 进入 超小屏幕 时， nav 文字变为 14px */
/* 处于超小屏幕时，news 第一个 li 宽度为 100% 剩下的 li 各占 50% */
@media screen and (max-width: 767px) {
    .nav li a {
        font-size: 14px;
    }

    .news li:nth-child(1) {
        width: 100%!important;
    }

    .news li {
        width: 50%!important;
    }
}
```

![](C:\Users\Administrator\Desktop\alibaixiu\微调-2.png)

```css
/* 进入 超小屏幕 时， nav 文字变为 14px */
/* 处于超小屏幕时，news 第一个 li 宽度为 100% 剩下的 li 各占 50% */
@media screen and (max-width: 767px) {
    .nav li a {
        padding-left: 14px;
        font-size: 14px;
    }

    .news li:nth-child(1) {
        width: 100%!important;
    }

    .news li {
        width: 50%!important;
    }
}
```

```html
<div class="row">
	<div class="col-sm-9">
		<h3>科技潮 华为：持续创新，引领5G</h3>
		<p class="text-muted d-none d-sm-block">砍柴网 发布时间：10-16  16:11 砍柴网官方百家号</p>
		<p class="d-none d-sm-block">2020年10月15日，在IMT-2020（5G）大会 5G创新发展高峰论坛上，华为无线产品线副总裁甘斌发表了《持续创新，引领5G》的主题演讲。会上，甘斌表示，“从19年商用至今，中国在5G网络体验、用户发展、终端生态、行业应用等领域一直引领整个5G产业。未来产业各方仍需协同创新，助力中国5G持续领先。”</p>
		<p class="text-muted">阅读(520) 评论(2) 赞(200) <span class="d-none d-sm-block">标签：华为 / 科技 / 创新 / 5G</span></p>
	</div>
	<div class="col-sm-3 pic d-none d-sm-block">
		<img src="upload/5.jpg">
	</div>
</div>
```

```css
/* 进入 超小屏幕 时， nav 文字变为 14px */
/* 处于超小屏幕时，news 第一个 li 宽度为 100% 剩下的 li 各占 50% */
@media screen and (max-width: 767px) {
    .nav li a {
        padding-left: 14px;
        font-size: 14px;
    }

    .news li:nth-child(1) {
        width: 100%!important;
    }

    .news li {
        width: 50%!important;
    }

    .publish h3 {
        font-size: 24px;
    }
}
```

![](C:\Users\Administrator\Desktop\alibaixiu\超小屏布局.png)

###

参照 黑马pink老师移动WEB开发-Bootstrap案例 

演示图片来源：网络

项目演示地址：https://yancyqi2002.github.io/bootstrap-responsive-layout-demo

项目仓库：https://github.com/YancyQi2002/bootstrap-responsive-layout-demo