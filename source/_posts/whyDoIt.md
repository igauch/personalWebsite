---
title: 个人博客记
date: 2016-07-03 22:07:41
---
# WHY
 所有的IT从业者应该都希望有自己的一个博客网站，它很酷！从经济实用价值出发，它也无穷美妙！`《软技能-代码之外的生存指南》`就面试和如何成为专业人士的讨论中就有指出：
> 博客是推销自己的一种既廉价又简单的方式，对于让自己声名鹤起极具价值。    

But,You do? Do you succeed?     
当然，在这里我不是要炫耀我的优越感，我只是想记录下来，分享给你，让你做的更快、更好！

# WHAT
在众多个人网站/博客里令我影响深刻有两个：[阮一峰](http://www.ruanyifeng.com/blog/)和[张鑫旭](http://www.zhangxinxu.com/)，毫无疑问，他们都是大家，我等楷模。他们除了用自己的方式讲解IT的专业知识，更有他们的创作，他们不是码农，更像是享受生活的人。    
那么我要做什么？    
* 做享受生活的记录博客
* 只记录经过实践验证的、亲身经历的，不为堆高自己的技术而胡诌
* 做原创的（当然包括借鉴），用我不独特的方式展示我的技术经历和对技术的理解、对世界的理解
* 一本正经的胡说八道

# HOW
细心的同学可能已经在底部发现了我下面要开讲的主角——[hexo](https://hexo.io/zh-cn/)——快速、简介、高效的博客框架。    
对了，在开始讲主角之前，先说下关于部署的一些东西
## 准备工作  
### 存放网站的空间  
免费的空间毫无疑问是很吸引人的，你一定考虑过，但你也肯定知道还是自己购买服务器/空间靠谱，这样对吗？我觉得不对，毕竟这个世界不是非黑即白的，你不必在免费的诱惑和靠谱的付费下徘徊，你应该做的是选择合适的放到合适的位置上来。例如今天咱们讲的个人博客，它很简单，纯粹，就是一个静态的网站，那么你完全可以选择免费的空间来托管我们的网站代码，它已经足够。    
那么问题来了，选择哪个？    
首先你应该知道hexo支持哪些[快速的提交方式](https://hexo.io/zh-cn/docs/deployment.html),显而易见，我推荐git的方式，这是我们最熟悉的，也是免费空间最常提供的方式，可选择性更大。  
那直接使用github不就行了？还有pages服务，这好像看起来很不错，但有一个长期性和要命的问题：国内服务不稳定！那好吧，看来我们只能选择国内的一些[替代品](https://www.baidu.com/s?ie=UTF-8&wd=github%E5%9B%BD%E5%86%85%E6%9B%BF%E4%BB%A3%E5%93%81)了，至于怎么选择我不做推荐，我只说说我选择的开源中国的[码云](https://gitee.com/)    
* [码云pages服务说明](http://git.mydoc.io/?t=154714)
* 如果你想以`igauch.gitee.io`访问，请新建仓库名为igauch(这个也是我的用户名)，仓库名和用户名必须一致
* 码云暂不提供自定义域名服务，而且不支持域名解析，只能通过它指定的域名访问，否则就报403错误。目前我的妥协解决方案是通过nginx的重定向     
### 框架的选择   
除了存放网站的空间纠结，你一定也经历过自己手写博客的静态页面，这确实是非常痛苦的，毕竟：    
- 维护繁杂，加一篇日志链接往往需要改动很多HTML页面中的链接。
- 设计困难，非前端设计人员的通病，往往在界面设计以及效果实现上浪费很多时间。
- 不支持MD语法，写一篇博客相当于写一个HTML页面，相当累人。  
 
那么选择一个框架就势在必行，这个我接触的不多，除了hexo就是[Jekyll](http://jekyllcn.com/)，而最终选择hexo基于以下几点：
* Jekyll是基于ruby的，在Windows搭建Ruby环境并不是被推荐的，而Hexo基于NodeJs实现，这是很方便的
* Hexo看起来使用更方便

## 开始
所有的一切都应该从[hexo官方文档](https://hexo.io/zh-cn/docs/index.html)找到你所需要的指导，我比较讨厌只知道百度的，因为你要明白  
* 经验是建立在实践的基础上，所以经验是有保质期的，你可能只是找到了一个过保的东西
* 经验是可以复制的，大部分人更是热衷复制的，所以你在大部分时候找到的都是同一个东西，这太没意义
* 经验是二次加工的，直接看经验容易丧失很多东西，应尽量接触到一手的东西    

## 注意
在实践中，有几点需要注意    
* 发布，最佳实践是使用 `hexo d -g` 否则它可能不会以你期望的形式工作
* 新建栏目/菜单，和常规的不同，通过修改 `——config.yml` 并不能实现预期的效果(可能是我没搞好)，不过通过命令真的很方便 `hexo new page "about"` ，然后在主题文件夹的_config.yml里面的 `menu` 一项添加一行 `About: /about` ，这样就新增了一个 `about`菜单
* 汉化，首先，查看[官方国际化](https://hexo.io/zh-cn/docs/internationalization.html)，需要注意的一点是只有被标记为模板的才会被翻译，也就是你需要将你想翻译的单词格式化成模板形式 `__('about')` 或 `_p('about', 3)`  

## 国际惯例
个人网站长期地址：[igauch.cn](http://igauch.cn)  
托管到码云的个人博客：[igauch.gitee.io](http://igauch.gitee.io/)   
本个人博客源码托管：[github](https://github.com/igauch/personalWebsite)