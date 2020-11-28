#### 1、css盒子模型

​	css盒模型：本质上是一个盒子，用于封装周围的HTML元素，它包括边距margin，边框border，填充padding 和内容 content。

​	w3c 标准盒子模型：内容盒子

![](img/w3c%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B.png)

​	ie盒子模型：边框盒子

​									![](img/IE%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B.png)

​	什么是css3盒模型：分类

​	盒子的构成：由 margin border padding content 构成；

​	具体该分为边框盒子和内容盒子

谷歌默认为内容盒子，ie默认为边框盒子。

边框盒子：宽度和高度决定了盒子自身的大小，内容区域需要计算。

标准盒子：宽度和高度决定了内容的大小，盒子自身的大小需要计算获得。

习惯使用边框盒子，因为 布局是子元素相对父元素的布局，直接控制好子元素的大小，更容易布局；为了兼容ie浏览器，因为不支持内容盒子。

#### 2、选择器

​	1）选择器的作用：选中 html 中的样式，进行样式设置；

​	2）常用的选择器有哪些 ：id class * 元素选择器等等...

​	3）css3新增属性：

```
	1、box-shadow 阴影效果；
	2、border-color 边框颜色；
	3、border-image 图片边框；
	4、text-shadow 文本阴影；
	5、text-overflow 文本截断；
	6、word-wrap 自动换行；
	7、border-radius 圆角边框；
	8、opacity 不透明度；
	9、box-sizing 控制盒模型的组成；
		1）content-box：使用此值盒模型的组成是，元素宽度 = content + padding + border；
		2）border-box：使用此值，盒模型的组成是，元素的宽度 = content ；（即使设置了padding 和 border ，元素也不会变）；
	10、background-size 指定背景图片的尺寸；
	11、background-origin 指定背景图片从哪里开始显示；
		1）border 从border区域开始显示背景；
		2）padding 从padding 区域开始显示背景；
		3）content 从content区域开始显示背景。
	12、background-cilp 指定背景图片从什么位置开始裁切
		1）border-box 从border区域向外裁剪背景；
		2）padding-box 从padding区域向外裁剪背景；
		3）content-box 从content区域向外裁剪背景；
		4）no-clip 不裁剪背景。
		必须先指定background属性，然后才能指定该属性，如果该属性出现在background属性之前，会无效。
	13、background 为一个元素指定多个背景
	  使用：
		background：url(bg1.png) no-repeat ,url(bg2.png) no-repeat;	
	14、resize 元素缩放；
		必须将元素的overflow属性设置为auto或hidden，该属性才能起作用，设置为visible时无效；
		1）none 禁用缩放；
		2）both 可同时缩放宽度和高度；
		3）horizontal 仅能缩放宽度；
		4）vertical 仅能缩放高度；
		支持 ： safari 4 ，chrome 3
	15、outline 外边框
		outline：边框厚度，边框样式，边框颜色
		outline-offset 偏移值；
		outline-offset需要独立写，简写是无效的
	16、rgba 基于r，g，b 三个颜色通道来设置颜色值，通过a来设置透明度
		rgba:(r,g,b,opacity);
	17、背景渐变
	 线性渐变：
		background-image:linear-gradient(to 方向//45deg,color,color);
	 径向渐变：
	 	background-image:radial-gradient(20px at center , color , color);
	 
		
```

​	4）css3 新增的选择器：

​	1、关系选择器:

​	ul > li 子代选择器

​	ul li 后代选择器

​	.now+li 后一个兄弟为 li 的元素

​	.now~li 后面所有为 li 的兄弟元素

​	2、属性选择器 ：

​	li[属性 || 自定义属性 = '值'] li 里面属性或自定义属性 = 值的元素；

​	3、伪类选择器

​	li:first-child ；li 的元素下第一个为 li 的子元素

​	li:last-child ; li 的元素下最后一个为 li 的子元素

​	li:nth-child(下标) li的父元素下对应下标的子元素，

​	li:nth-of-type(n)

​	li:first-of-type

​	li:last-of-type

​	伪类选择器，:hover , :checked , :focus nth-type-of...

4、伪元素选择器

​	::after{}

​	::before{}

​	::first-letter

​	::first-line



#### 3、css样式权重

​	1）首先看选择器优先级：

​	* <  元素选择器 < class < id < !import

​	2）相同权重的选择器： 看顺序，用代码在下的样式。

​	3）利用权重以及代码的执行顺序，解决样式覆盖问题。

#### 4、css单位计算的规则

​	1）css的单位分类：相对单位 和 绝对单位

​	相对单位： 可以实现响应式

​		%  ：相对于父元素，最大视图为窗口的大小，不可以超过视图窗口的大小；

​		em ：相对于祖籍元素中的 font-size 的大小；

​		rem ：相对于根元素中的 font-size 的值；

​		vw vh ：浏览器视图窗口；

​		ex ：相对于字母 ‘x’ 的大小，浏览器默认字符 ‘x’的大		小；

​	绝对单位 ： px ；

#### 5、如何实现多行文本省略

```
text-overflow: ellipsis;//显示***
white-space: nowrap;//显示不换行
overflow: hidden;//溢出部分隐藏
```

#### 6、css 哪些属性可以继承 ？

​	文本类：font-size color font-family font-weight

​	布局属性不可以继承

#### 7、如何去除 inline-block 默认缝隙 ：

​	1、压缩代码，删除空格和换行，不让 inline-block 元素之间有缝隙；

​	2、利用 html 注释连接两个元素；

​	3、父容器的 font-size 属性设置为 0 ，//重点掌握

​	float : left;

​	布局属性：就是将 block 元素变成 inline-block 

​	浮动 绝对定位 固定定位 弹性布局子项目

​	盒子布局，保留元素本身的特点。

#### 8、如何实现垂直居中？

​	1、通过绝对定位，2d 平移实现垂直居中；

​	2、通过绝对定位 4 个值为0 ，margin ：auto 实现；

​	3、父容器弹性布局。

​	box-sizing 属性 ：

​	注意：联想到盒模型。

​	1、border-box；包含了 padding 和 border ，设置两者不会撑开盒子，盒子大小不会改变；

​	2、content-box；默认的盒子，设置 padding 和border 会撑开盒子，使盒子比原本的宽高更大；

​	3、inherit ：规定应从父元素继承 box-sizing 属性的值。

#### 9、隐藏元素的方法 ：

​	1、visibility : collapse; // ie浏览器中相当于 display :none;

​	2、display ：none；

​	3、visibility：hidden；

​	4、transform：scale(0,0);

​	5、transform : rotatex( 90 deg );

​	6、opacity : 0;

###### 	1）display ：none 与 visibility ：hidden 区别是什么？

​		1、设置 display：none；属性后，该元素下的元素都会隐藏，不占据空间，而visibility：hidden；属性隐藏仍旧占据空间；

​		2、visibility ：hidden ；属性具有继承性，其子元素会继承此属性。

​		3、visibility ：hidden；属性不会影响计数器的计算，虽然隐藏了，但是计数器仍然继续运行；

​		4、在transition属性中，支持visibility属性，但不支持display属性。

​		5、display：none；属性会引起回流（重排）和重绘；而visibility：hidden；属性会引起重绘。

###### 	2）visibili 属性的 collapse 属性值，在不同浏览器下有什么区别？

​	对于一般的元素，collapse 属性和 hidden 属性是一样的，如果是和 table 属性相关的元素，在各个浏览器中的处理方式都不一样；

​	1、在谷歌浏览器中，使用collapse值和使用hidden值没有区别；

​	2、在火狐浏览器、opera和	IE11里，使用 collapse 值的效果会消失，下面的一行会取代它的位置。

###### 	3）内外边距和边框

​	元素盒子最内的部分是 content 内容区域，直接包围内容区域的是内边距，内边距呈现了内容的背景。内边距的边缘是边框，边框以外是外边距，外边距默认是透明的，不会遮挡后面的任何元素。内外边距和边框的值都是可选的，默认值是 0 ；

​	外边距一般用于拉开相邻兄弟元素之间的距离；内边距一般用于拉开父子元素之间的距离。

#### 10、rgba 与 opacity 属性的区别

rgba 渐变属性不能继承，一般用于写遮罩层；

opacity 属性可以继承。

#### 11、布局

​	1）绝对定 位和相对定位的区别：

绝对定位：

​	绝对定位是相对祖籍元素中，具有 position ：relative ；属性进行定位，脱离文档流，位置移动幅度大，元素由 block 变为 inline-block；

​	优点：可以实现通用的布局，兼容低版本的IE；

​	缺点：触发重排，消耗浏览器性能，不容易实现复杂的布局，适合要求兼容低版本 ie 常见的布局。

相对定位：

​	相对定位是相对元素自身的位置进行移动。

​	优点 ：不会触发重排；

​	缺点：定位后占据位置；

​	使用：只适用于小范围微调。

固定定位：

​	固定定位是，相对浏览器视图窗口进行定位。

​	特点：定位后脱离文档流，位置被其他元素占据，块元素变为 inline-block；

​	缺点：触发重排；

​	适用于固定导航栏、广告等...

#### 12、css 优化、提高性能的方法有哪些？

​	1、避免过度约束；

​	2、避免后代选择符；

​	3、避免链式选择符；

​	4、使用紧凑的语法；

​	5、避免不必要的命名空间；

​	6、避免不必要的重复；

​	7、最好使用表示语义的名字；

​	8、避免！import ，可以选择其他选择器；

​	9、尽可能的精简规则，可以合并不同类型里的 重复规则。

​	10、图片是加载的资源，通过使用精灵图片减少加载图片次数；

​	11、能使用字体图标的不适用图片；

​	12、减少重排和重绘；重排一定会触发重绘，重绘不一定会触发重排

​	13、避免书写多余命名空间；

​	14、提取公共样式，提高样式的可重复性。

#### 13、圣杯布局、双飞翼布局：

​	圣杯布局：

​	为了让中间的 div 内容不被遮挡，将中间的 div 设置了左右两个 div 用相对布局 position ：relative；并分别配合 right 和 left 属性，以便左右两栏 div 移动后不遮挡中间的 div。

​	双飞翼布局：

​	为了让中间的 div 内容不被遮挡，直接在中间 div 内部创建子 div 用于放置内容，在该 div 里用 margin-left 和 marign-right 为左右两栏 div 留出位置。

#### 14、浏览器是怎样解析 css 选择器的？

​	css 选择器的解析是从右向左解析的。若从左向右的匹配，发现不符合规则，需要进行回溯，会损失很多性能。若从右向左匹配，先找到所有的最右节点，对于每一个节点，向上寻找其父节点直到找到根元素或满足条件的匹配规则，则技术，这个分支的遍历，两种匹配的规则性能差别很大，是因为从右向左的匹配在第一步就筛选掉了大量的不符合条件的最右节点，而从左向右的匹配规则的性能都浪费在了失败的查找上面。

​	而在 css 解析完毕后，需要将解析的结果与 dom tree 的内容一起进行分析建立一颗 render tree ，最终用来进行绘图，在建立 render tree 时 ，浏览器就要为每个 dom tree 中的元素根据 css 的解析结果来确定生成怎样的 render tree。

#### 15、png 、jpg 、gif 这些图片格式解释一下，分别什么时候使用，什么是webp？

png-8 是无损图片 具有更小的文件体积，同时支持透明度的调节

jpg 是有损图片，适合用来存储照片

gif 是无损的动图，适用于对色彩要求不高的同时需要文件体积较小的情况

webp 是谷歌的开发的，支持有损无损，压缩图，具有更小的文件体积，支持图片透明度，但兼容性不太好。 

#### 16、样式 4k 与 2k 显示器显示同一个页面，会有怎样的样式问题，如何解决？

显示的效果不一样，样式错位等，因为电脑的分辨率不同，像素密度不同，视觉250  上会有差异。

解决方案一：

​	可以设置固定宽度，整体居中两边留白来实现在不同分辨率的显示器上显示的效果是一样的。

二、设置宽度值为百分比（自适应布局），通过设置百分比宽度，对于不同分辨率的显示器上会自动适应大小。

三、根据不同的分辨率，加载不同的 css 样式文件，在<head> 标签中创建 js 文件，来判断电脑的分辨率，根据不同的结果调用不同的 css 。

四、通过响应式布局，媒体查询，根据不同的分辨率，引入不同的 css 样式表，或者在一个 css 样式表中，根据不同的分辨率，写不同的 css 样式。

17、link 与 @import 的区别

​	1、link 是 html 标签，无兼容性问题，@import 是 css 方式，低版本的浏览器不支持。

​	2、link 在引入 css 时，在页面载入时同时加载，@import 需要页面完全载入以后加载



​	