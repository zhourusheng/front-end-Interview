


### 1 介绍一下标准的CSS的盒子模型？与低版本IE的盒子模型有什么不同的？

* 标准盒子模型：宽度=内容的宽度（content）+ border + padding + margin,

* 低版本IE盒子模型：宽度=内容宽度（content+border+padding）+ margin,

* 主要区别就是内容宽度是否包含margin 和 padding


### 2 box-sizing属性？

* 用来控制元素的盒子模型的解析模式，默认为content-box

* context-box：W3C的标准盒子模型，设置元素的 height/width 属性指的是content部分的高/宽

* border-box：IE传统盒子模型。设置元素的height/width属性指的是border + padding + content部分的高/宽

* 若box-sizing设置为border-box,则height/width会包含margin和padding


### 3 CSS选择器有哪些？哪些属性可以继承？

#### CSS选择符：

* id选择器(#myid)

* 类选择器(.myclassname)

* 标签选择器(div, h1, p)

* 相邻选择器(h1 + p)

* 子选择器（ul > li）

* 后代选择器（li a）

* 通配符选择器（*）

* 属性选择器（a[rel="external"]）

* 伪类选择器（a:hover, li:nth-child）

#### 可继承的属性：

* font-size

* font-family

* color

#### 不可继承的样式

* border

* padding

* margin

* width

* height

#### 优先级（就近原则）：
` !important > [ id > class > tag ] `
* !important 比内联优先级高


### 4 CSS优先级算法如何计算？

* 元素选择符：1

* class选择符：10

* id选择符：100

* 元素标签：1000

例如：
 div.test1 .span var  优先级 1+10 +10 +1 
 span#xxx .songs li   优先级 1+100 + 10 +1 
 #xxx li              优先级 100 +1

1. !important声明的样式优先级最高，如果冲突再进行计算。

2. 如果优先级相同，则选择最后出现的样式。

3. 继承得到的样式的优先级最低。


### 5 CSS3新增伪类有那些?

* p:first-of-type 选择属于其父元素的首个元素

* p:last-of-type 选择属于其父元素的最后元素

* p:only-of-type 选择属于其父元素唯一的元素

* p:only-child 选择属于其父元素的唯一子元素

* p:nth-child(2) 选择属于其父元素的第二个子元素

* :enabled :disabled 表单控件的禁用状态。

* :checked 单选框或复选框被选中。



### 7 display有哪些值？说明他们的作用?

* inline（默认）--内联

* none--隐藏

* block--块显示

* table--表格显示

* list-item--项目列表

* inline-block



### 8 position的值？

* static（默认）：按照正常文档流进行排列；

* relative（相对定位）：不脱离文档流，参考自身静态位置通过 top, bottom, left, right 定位；

* absolute(绝对定位)：参考距其最近一个不为static的父级元素通过top, bottom, left, right 定位；

* fixed(固定定位)：所固定的参照对像是可视窗口。



### 9 CSS3有哪些新特性？

* RGBA和透明度

* background-image，background-origin(content-box/padding-box/border-box)，background-size，background-repeat

* word-wrap（对长的不可分割单词换行），word-wrap：break-word

* 文字阴影： text-shadow：`5px 5px 5px #FF0000`;（水平阴影，垂直阴影，模糊半径，阴影颜色）

* font-face属性：定义自己的字体

* 圆角（边框半径）：border-radius 属性用于创建圆角

* 边框图片： `border-image:url(border.png) 3030round`

* 盒阴影： `box-shadow:10px 10px 5px #888888` 

* 媒体查询：定义两套css，当浏览器的尺寸变化时会采用不同的属性



### 10 请解释一下CSS3的flexbox（弹性盒布局模型）,以及适用场景？

* 该布局模型的目的是提供一种更加高效的方式来对容器中的条目进行布局、对齐和分配空间。在传统的布局方式中，block 布局是把块在垂直方向从上到下依次排列的；而 inline 布局则是在水平方向来排列。弹性盒布局并没有这样内在的方向限制，可以由开发人员自由操作。

* 使用场景：弹性布局适合于移动前端开发、微信小程序开发，在Android和ios上也完美支持。


### 11 用纯CSS创建一个三角形的原理是什么？

首先，需要把元素的宽度、高度设为0。然后设置边框样式。
```
width: 0;
height: 0;
border-top: 40px solid transparent;
border-left: 40px solid transparent;
border-right: 40px solid transparent;
border-bottom: 40px solid #ff0000;
```

### 17 display:none与visibility：hidden的区别？

* display：none 不显示对应的元素，在文档布局中不再分配空间（回流+重绘）

* visibility：hidden 隐藏对应元素，在文档布局中仍保留原来的空间（重绘）



### 42 png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？

* png是便携式网络图片（Portable Network Graphics）是一种无损数据压缩位图文件格式.优点是：压缩比高，色彩好。 大多数地方都可以用。

* jpg是一种针对相片使用的一种失真压缩方法，是一种破坏性的压缩，在色调及颜色平滑变化做的不错。在www上，被用来储存和传输照片的格式。

* gif是一种位图文件格式，以8位色重现真色彩的图像。可以实现动画效果.

* webp格式是谷歌在2010年推出的图片格式，压缩率只有jpg的2/3，大小比png小了45%。缺点是压缩的时间更久了，兼容性不好，目前谷歌和opera支持。


### 44 CSS属性overflow属性定义溢出元素内容区的内容会如何处理?

* 参数是scroll时候，必会出现滚动条。

* 参数是auto时候，子元素内容大于父元素时出现滚动条。

* 参数是visible时候，溢出的内容出现在父元素之外。
* 
* 参数是hidden时候，溢出内容会隐藏。



### 45 阐述一下CSS Sprites

将一个页面涉及到的所有图片都包含到一张大图中去，然后利用CSS的background-image，background- repeat，background-position 的组合进行背景定位。利用CSSSprites能很好地减少网页的http请求，从而大大的提高页面的性能；CSS Sprites能减少图片的字节。


### 46 有哪项方式可以对一个 DOM 设置它的 CSS 样式？  

* 外部样式表，引入一个外部 css 文件 

* 内部样式表，将 css 代码放在 <head> 标签内部 

* 内联样式，将 css 样式直接定义在 HTML 元素内部 
 

### 47 rgba()和 opacity 的透明效果有什么不同？ 

* rgba()和 opacity 都能实现透明效果

* 但最大的不同是 opacity 作用于元素，以及元素内的所有内容的透明度
 
* 而 rgba()只作用于元素的颜色或其背景色。（设置 rgba 透明的元素的子元素不会继承透明
效果！） 


### 48 px 和 em 的区别。 

* px 和 em 都是长度单位，区别是，px 的值是固定的，指定是多少就是多少，计算比较容易。
 
* em 得值不是固定的，并且 em 会继承父级元素的字体大小。 
 
* 浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em, 
10px=0.625em。 

