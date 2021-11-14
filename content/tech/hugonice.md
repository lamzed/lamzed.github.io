---
author: "lamzed"
date: 2019-08-07
title: 静态页面快速搭建神器HUGO
categories: ["技术随笔"]
tags: ["Hugo","Python"]
---

标题不搞个```UPPER_CASE```彷佛不能显示出雨果的官威。<!--more-->

***

## 狂

我赌你没见过哪个框架，敢在他们官网首页正中，写下这样一句话？

`The world’s fastest framework for building websites`

## 跑得比记者还快

<!--这么快的你我还是第一次见-->

> 假定你是python的环境，那么`pip install hugo`雨果你就安装好了。

`hugo new site name`没有前戏环境直接搭建完毕。name即目录名。

```
Congratulations! Your new Hugo site is created in D:\lamzed.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
   
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
   
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

到官网找个你心水的`theme`，扒拉下来，丢到对应目录，

敲下`hugo new blog01.md`，然后`vim`进去一顿输出，

接着`hugo server`啪的一下网站就推出去了。很快啊。

## 星剖

雨果提供了许多不错的主题，~~simple~~`星剖`就是让你不动脑筋。

`lamzed's page`使用的就是他们的一个叫`book`的极简风格`theme`。

但要是套个前端组件，或者稍微客制化下，你的站点可能会酷炫许多。

<!--当然，选择上雨果是不及诸如`bootstrap`这些框架提供的模板的，功能上也是逊色了一点。-->

<!--但这却正是雨果的优势体现。-->

<!--雨果之所以被我冠于`快速静态页面搭建神器`之名，因为除了快，最主要的还是它的使用简单。-->

<!--雨果主要是用来搭建轻博客或者展示页面的。它不需要过于复杂的功能，或者业务逻辑。-->

<!--搭建简单，使用简单，一行`new xxx.md` 命令就可以创建一篇`blog`。-->

<!--这可以让你把更多的精力集中在码字上。可以说简单是雨果相比其他框架最核心的竞争力。-->

## 抛瓦

简单却~~power~~`抛瓦`，或者`dio`。就说部署这点，*简直无敌*。

### 部署速度

它的`部署速度`贼™快，总能让我`high`到不行。

就是我的指头敲击回车的一刹那，甚至行程都还没走完——

还来不及听到那令人愉悦的段落声响，我眼前的终端就已经执行完了全部命令：

黑乎乎的窗口显示简单的数字和字母，

`13ms`，这四个字符组合起来，真让我着迷。

### 热部署

平平无奇的卖点，只是千不该万不该让上一秒还在用`tomcat`汤姆猫的我

下一秒和`hugo`雨果相遇。

`change detected, rebuilding site.`

也就`total in 3ms`而已。

### 响应式

：嗯，对于博客站点来说，这玩意确实挺香的。

### 课代表发言了

总的来说，雨果的抛瓦包含以下三点。

```
1. 部署快，它让开发编程的爽了
2. 热部署，它让写稿搬砖的爽了
3. 响应式，它让围观白嫖的爽了
```

## 课代表站起来了

快速，

简单，

强力，

他说，`hugo`极其适合静态页面快速搭建，嗯博客也可。

## 安利完结撒花

这是我[`lamzed的奇妙页面`](/)写的第一篇`blog`，也没技术含量，充其量是个随笔吐槽。

可能对于架构师以上级别的牛人来说，雨果充其量只是个类似小孩玩具的东西。可但是——

~~我是菜鸡~~。不是

既然我选择了雨果搭建自己的博客，那我肯定要稍微吹一下它啊。吹爆！

> 2021.2.13 改，删了废话。这个日期，新年哟~

## 彩蛋福利

或者，你也可以直接阅读[`Getting Started with Hugo`](/documents/hugoisforlovers/)和[`Creating a New Theme`](/documents/creating-a-new-theme/)这两份文档。

不带翻译的绝好`阅读材料`！wink~