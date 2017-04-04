---
title: revealjs框架
date: 2016-11-02 22:49:42
tags: notes
---


reveal.js框架是一个基于javascript的演讲框架，官网在[reveal.js]( http://lab.hakim.se/reveal-js/ )，可以通过css样式创建各种炫丽的动画和字体，用html语言编辑使得作者可以更专注于内容本身，而默认的样式与此同时可以使表达效果不失观赏性  

<!--more-->

# reveal.js presentation framework

## 下载和测试revealjs
从revealjs的[Github]( https://github.com/hakimel/reveal.js/ )上下载zip压缩文件，使用git的同志可以git clone，解压缩完成以后打开目录中的demo.html或者index.html，如果看到revealjs的标题或者"slide 1"就说明框架可以使用了，而且浏览器兼容性正常(revealjs的html使用的是html5标准，旧版浏览器尤其IE9一下的可能会有兼容性问题)  

## 语法

### session语法
类比于powerpoint 在index.html中每一个单独的（无嵌套）<session></session>块代表了一页，嵌套最多两层，两层的嵌套代表在一页之中有几个分别呈现的内容，页的切换动画，各种字体颜色大小将在后文介绍。其中session中的换行、特殊符号、标题、表格遵循html5的标准  

示例：

```

<session>
  <h1>hello world</h1>
  <p>I am using revealjs presentation framework to make my speech</p>
</session>

```

### fragment语法
fragment可以使一页中的一些内容强调或突出   
有以下几种语法，是在标签的class中定义：  

- class="fragment grow" 表示变大
- class="fragment"表示按多一个键才显示出来
- class="fragment current-visible"显示以后马上又回消失
- class="fragment shrink"变小
- class="fragment fade-up"从下往上出现（也可以fade-down left和right）
- class="fragment fade-out"表示消失
- class="fragment highlight-red"表示红色高亮（也可以蓝和绿）  

可以在段落直接使用，也可以在段落中间使用（<span>标签），凡是有标签的都可以使用

示例：

```

<section>
  <h2>Fragment Styles</h2>
  <p>There's different types of fragments, like:</p>
  <p class="fragment grow">grow</p>
  <p class="fragment shrink">shrink</p>
  <p class="fragment fade-out">fade-out</p>
  <p class="fragment fade-up">fade-up (also down, left and right!)</p>
  <p class="fragment current-visible">current-visible</p>
  <p>Highlight <span class="fragment highlight-red">red</span> <span class="fragment highlight-blue">blue</span> <span class="fragment highlight-green">green</span></p>
					</section>

```

### data-transition与data-background-transition语法
这个是用来控制session与session之间切换的动画的，用css写的，如果属于程序员，可以自行添加，revealjs自带一下几种动画：

- slide
- zoom
- fade
- convex
- concave
- none

介绍在官网上有，只不过是英文的。  
使用方法是data-transition="slide"或data-background-transition="zoom"之类的  

示例：

```
<section data-transition="slide" data-background="#4d7e65" data-background-transition="zoom">
  <h2>Background Transitions</h2>
  <p>Different background transitions are available via the backgroundTransition option. This one's called "zoom".</p>
  <pre><code class="hljs">Reveal.configure({ backgroundTransition: 'zoom' })</code></pre>
</section>


```

### Markdown 支持




