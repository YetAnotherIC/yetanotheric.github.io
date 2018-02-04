---
layout: post
title:  "微调博客主题"
date:   2018-01-24 00:00:00
categories: [杂谈, 技术]
---

对原来的博客主题有点不满，微调了一下。<!--more-->

也许有人注意到了，这个博客的主题是对有名的[solarized theme](http://ethanschoonover.com/solarized)的一个实现。我挺喜欢这个配色的，主题的效果也不错，不过，试了两天发现细节上还是有点小问题。



有问题那就改吧，当然，灵活性是自己追求的，要修改时自然也会麻烦点。

首先是整个网站的内容也太居中了，博文可怜巴巴的挤在中间的一个细条里，初看很简洁，仔细一想其实太浪费屏幕空间，所以我的第一想法就是调宽一点文章的区域，扫了一眼css的源代码，基本网站的排版就是用`absolute`和`xxx px`的写法实现的，看起来很令人困惑也不利于维护...2018年了！那就改成现代一点的写法吧。

图省事就用Bootstrap吧。搜了下Bootstrap的v4已经基本稳定了，之前也没用过v4这次刚好用下。

和v3直接提供[网页版的工具](https://getbootstrap.com/docs/3.3/customize/)不同，v4官方教程里的做法是[import并compile](https://getbootstrap.com/docs/4.0/getting-started/theming/)需要的scss，不过jekyll支持scss的自动compile所以也不是很麻烦，参考官方文档即可这里不再赘述。

总之暂时改成了现在的文章宽度，其实还是有点太窄，不过改起来也容易，先试用一段时间吧。

顺便也加了个read more，不然等文章多起来，点进主页刷啦一下加载一长串文字，用户体验就很差了。

其次是网站配色，文字的颜色过淡，看了下官网：
>Thus in the case of a dark background colorscheme, the normal relationship for background and body text is base03:base0 (please note that body text is not base00)

所以，我认为是作者错误的在light主题里使用了base0作为文字的颜色，那么直接换成base00就行。

其实也考虑过干脆就用黑色作为文字的颜色，试了下一股强烈的违和...作罢。

还有什么来着？哦，js，原来的主题里加入了一个完整的jQuery和一个jQuery的插件,就为了实现在手机上能自动把目录转换成一个下拉菜单，想来想去也觉得这么做没什么意义（还要往网站里塞那么多js影响加载速度），所以我干脆就全删掉了。

姑且还是保留了为了让网站兼容低版本IE的js。虽然这么说，完全没有为了兼容IE改动任何代码的打算，随缘吧。

然后既然对网站的排版做了这么大改动，顺便测下在各种设备上的表现好了，这么一测发现还真有些小毛病：


- 在Android O上被Chrome自作聪明的识别成了日语网页从而调用了日语字体(?)，导致某些汉字显示很奇怪。
- 手机版safari上会有一个诡异的水平滚动条。

第一个不知道怎么解决，第二个暂时加了个`overflow-x: hidden;`，其实应该是某个地方超宽了，<del>急着今晚打完レイライン呢懒得继续想而且又不是不能看</del>以后再说吧。

1月25追记: 第二个似乎是Bootstrap的问题，加了几个修改在`_bootstrap-customization.scss`里



