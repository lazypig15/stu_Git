﻿### css 面试重点

- BFC 概念 规范是什么 生成 有缺点
		级格式化上下文
    在什么情况下生成BFC？BFC 可以

- 弹性布局，盒子  子项目属性作用
	   在父元素设置弹性布局：display:flex;
      justify-content ：水平对齐方式，写在父级
		flex-decriction :方向，写在父级
		flex-wrap ：换行，写在父级
		align-items 垂直对齐方式，写在父级
		align-content ：垂直对齐方式，用于修改flex-wrap属性的行为（如果不换行则无效），写在父级
		align-self 垂直对齐方式，写在子级
		order 排序，子级
		flex 子元素分配空间
		flex-basis 定义弹性盒子元素的默认基准，写在子级
		flex-grow 定义弹性盒子元素的拓展比率，写在子级
		flex-shrink 定义弹性盒子的默认基准，写在子级

- css 性能优化方案
    尽量使用缩写
    减少重复代码
    删除未使用的样式
    使用精灵图  ​	

- 布局属性总结
    1、文档流布局：普通布局按照文档的顺序显示，块级元素独占一行，行元素不独占一行，
    2、浮动布局：使用float 属性，使元素脱离文档流，浮动起来；
    3、弹性布局：在父元素设置display flex；
    4、定位：通过position 设置相对定位 绝对定位 固定定位 属性来进行定位；
	
- css3 新特性；css4新特性

  ​	css3新特性 ：
  ​		1.过度动画transition: 过度的属性 2s(过度时间) linear(过度曲线) 1s(延时);
  ​		2、动画 animation  属性值：动画名称 ，一个周期花费的时间 ，运动曲线，延迟，播放次数
  ​		3、图形变换 transform 属性 ：translate 移动,rotate 旋转 , scale 缩放 
     4、3d图形变换 在2d 基础上加了z轴 且轴并不是固定的会跟着旋转
   css4新特性：

- 响应式布局

  ​	媒体查询：使用媒体查询针对打印机 屏幕等  以及不同屏幕宽度的设备进行布局和样式的设置，用来适配不同设备

- 重排和重绘：概念？什么时候触发？优化方案

     当DOM元素影响了元素的几何属性（例如宽和高），浏览器需要重新计算元素的几何属性，同样其它元素的几何属性也会和位置也会因此受到影响。浏览器会使渲染树中受到影响的部分失效，并重新构造渲染树。这个过程称为“重排”。 
     完成重排后，浏览器会重新绘制受影响的部分到屏幕上中，该过程称为“重绘”。

     ​		重排发生的情况：

     添加或删除可见的DOM元素。 
     元素位置改变。 
     元素的尺寸改变（包括：内外边距、边框厚度、宽度、高度等属性的改变）。 
     内容改变。 
     页面渲染器初始化。 
     浏览器窗口尺寸改变。

     ​		重绘发生的情况：

     重绘发生在元素的可见的外观被改变，但并没有影响到布局的时候。比如，仅修改DOM元素的字体颜色（只有Repaint，因为不需要调整布局）

     

- 什么浏览器渲染队列？浏览器的渲染机制是什么？

     浏览器将获取的页面文档解析成DOM文档树结构，

- 以下为其他小点问题

~~~
1: 伪元素 伪类选择器区别
	伪类选择器的作用：选中html添加样式
    伪元素：是在元素前面或者后面添加一个元素，可以具备所有元素的特点。
2：什么是盒模型
	 盒子的构成由magin border padding content决定，分为边框盒子和内容盒子
    谷歌默认内容盒子   ie默认边框盒子。
    边框盒子：宽度和高度决定盒子自身大小，内容需要计算
    内容盒子：标准盒子；宽度高度决定了内容的大小 盒子自身大小需要计算
    用边框盒子， 因为布局是子元素相对于父元素的布局 边框盒子可以直接控制子元素的大小 更容易布局。也为了解决一些兼容性问题
3：问题css 某一个属性的作用是什么
	
4  css属性优先级计算
	1. 首先看选择器优先级； *元素选择器<class<id<！important
    2. 相同权重的选择器：看顺序  用代码在下面的样式
    3. 利用权重及代码的执行顺序解决样式覆盖问题
5  css3新增伪类有什么
	 css3新增的：伪类选择器，(:hover  :checked :focus ...)
	:nth-child(n);父元素下，第n个该标签的子元素
	:first-child;父元素下，第一个该标签的子元素
	:last-child;父元素下，最后一个该标签的子元素
	:nth-of-type(n)父元素下，有该属性的同一类标签
6. em、ex、rem与px的计算规则
	单位分为  相对单位 和 绝对单位
         相对单位可实现响应式
            %  相对父元素，最大为视图窗口的大小
            em 相对是祖籍元素中的 font-size值
            rem 相对根元素的font-size值
            vw vh 浏览器视图窗口
            ex 相对字母 'x' 大小 ，默认浏览器默认字符 'x' 大小
         绝对单位
            px
7 ：如何使用自定义字体？
	使用@font-face引入
8 如何实现文字多行省略
设置不换行、超出隐藏、超出省略号
	white-space:nowrap;
	overflow:hidden;
	text-overflow:ellipsis;
	
	/* overflow: hidden;
       text-overflow: ellipsis;   
       display: -webkit-box;
       -webkit-line-clamp: 2; */
9：css哪些属性可以继承
	文本类属性：font-size color font-family font-weight
         布局属性不可继承
  其中a标签中的元素不能继承父元素的字体和颜色
10 如何去掉inline-block元素间隙？
 1.设置浮动
 1.压缩代码 不让inline-block之间有缝隙
 2.利用注释链接两个元素
 3.设置父容器的font-size为0
	
11 常见的布局有哪些？
  文档流布局 浮动布局 弹性布局 

12 CSS中visibility属性的collapse属性值，在不同浏览器下以后什么区别？
	谷歌保留位置，ie没有位置
13 请问display:none与visibility:hidden有什么区别？
	display:none; 元素隐藏，不保留位置；
	visibility:hidden; 元素隐藏，依旧保留自身的位置；
14 rgba和opacity的透明有何不同？
    rgba 渐变  属性不能继承 用来写遮罩层
    opacity属性可以继承 
15 如何居中一个浮动元素？如何让绝对定位的div居中？
绝对定位 top和left分别设为父元素的高和宽的一半减去自身宽和高的一半。
16 请解释一下CSS3的flexbox（弹性盒布局模型）,以及适用场景？
 适合于在固定大小的盒子里均匀分布子元素
17 请实现中间自适应宽度，左右两栏固定宽度布局。
<style>
  *{
    margin: 0;
  }
  
  .content{
    width: 100%;
    height: 500px; 
    margin: 0 auto;
    display: flex;
  }
  .left{
    background: blue;
    width: 100px;
    height: 100%;	
  }
  .right{
    background: green;
    width: 100px;
    height: 100%;
  }
  .center{
    background: pink;
    height: 100%;
    flex: 1;
  }
			
</style>
<body>
  <div class="content">
    <div class="left"></div>
      <div class="center">
        <h1>测试测试测试测试测试</h1>
					<p>测试测试</p>
					<p>测试测试</p>
					<p>测试测试</p>
					<p>测试测试</p>
					<p>测试测试</p>
					<p>测试测试</p>
      </div>   
      <div class="right"></div>
  </div>
18 浏览器是怎样解析CSS选择器的？
	CSS选择器的解析是从右向左解析的。若从左向右的匹配，发现不符合规则，需要进行回溯，会损失很多性能。若从右向左匹配，先找到所有的最右节点，对于每一个节点，向上寻找其父节点直到找到根元素或满足条件的匹配规则，则结束这个分支的遍历。两种匹配规则的性能差别很大，是因为从右向左的匹配在第一步就筛选掉了大量的不符合条件的最右节点（叶子节点），而从左向右的匹配规则的性能都浪费在了失败的查找上面。
而在 CSS 解析完毕后，需要将解析的结果与 DOM Tree 的内容一起进行分析建立一棵 Render Tree，最终用来进行绘图。在建立 Render Tree 时（WebKit 中的「Attachment」过程），浏览器就要为每个 DOM Tree 中的元素根据 CSS 的解析结果（Style Rules）来确定生成怎样的 Render Tree。--
19 png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？
		1.所有变更图片大小的属性全部都是会消耗浏览器性能
            ====>为了提高性能，直接使用原图
        2.png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过 webp？
        png-8,png-24,是无损
        jpg有损
        dif 动图无损 
        webp 谷歌开发的支持有损和无损压缩
19 link和@import有什么区别？
        @import:在css文件中导入css文件
        link：在HTML中导入css样式

## js 面试题

- 作用域
- 作用域链（scope）
- 闭包（执行期上下文）
- 预编译(变量提升)
- 原型对象（概念 继承 特点）
- 原型链

~~~~
1 js 的数据类型有哪些？
	Undefined、Null、Boolean、Number、String
2 原始类型有哪几种？null 是对象嘛？
	
2.1 ：什么是null？ ：什么是undefined？ null和undefined的异同？
null为空值，undefined未定义。
2.2 如何比较两个数组是否相等？
2.3 如何判断一个数据类型是否为naN   isNaN()
3 对象类型和原始类型的不同之处？函数参数是对象会发生什么问题？
4 typeof 是否能正确判断类型？instanceof 能正确判断对象的原理是什么？
5 类型转换有几种方式；分别是什么
字符型转化为数字型 数字型转化为u字符型 字符型转化为布尔型 数字型转化为布尔型（只有0为false）
6 如何正确判断 this？箭头函数的 this 是什么？
7 == 和 === 有什么区别？
==是数值相等 ===是所有属性相等数据类型
8 什么是闭包？
9 什么是作用域？作用域分类？分别是在什么时候产生的
10 什么是作用域链？
11 什么时候会残生内存泄露问题，如何解决呢？
12 什么是浅拷贝？如何实现浅拷贝？什么是深拷贝？如何实现深拷贝？
13 如何理解原型？如何理解原型链？
14 并发与并行的区别？
15 什么是回调函数？回调函数有什么缺点？如何解决回调地狱问题？
16 你理解的 Generator 是什么？
17 Promise 的特点是什么，分别有什么优缺点？什么是 Promise 链？Promise 构造函数执行和 then 函数执行有什么区别？
18：如果有一个任务，需要等待多个异步任务都执行成功后才能执行？怎么做呢？
19 async 及 await 的特点，它们的优点和缺点分别是什么？await 原理是什么？
20 async 及 await 的特点，它们的优点和缺点分别是什么？await 原理是什么？
21 什么是异步消息队列？ 
22 进程与线程区别？JS 单线程带来的好处？
   进程相对于运行程序。线程相对于单个程序的运行时间，性能而言
   js 是单线程程序 例如 渲染线程 js引擎线程
   优点：可以安全渲染ui 节省内存 节约上下文切换时间，没有锁可以解决问题
   缺点；脚本先运行会有阻塞
23 什么是执行栈？（递归）
   理解为 可以存放函数的栈 为执行栈。
   函数在执行时候先执行main 函数；然后安装 先进后出原则执行。执行完毕后 弹出栈
   执行栈中存放函数是有限的，递归中如果没有出口，就会导致暴栈

   递归：最先执行的程序，最后输出结果。
24 异步代码执行顺序？解释一下什么是 Event Loop
   1：执行js代码其实就是王执行栈中方式函数。
   2：异步：有的代码执行，有的没执行、
     执行的代码；就在执行栈中执行
     没有的代码；1：挂起，并放入到需要执行的【异步消息队列 /任务队列】
     在任务队列中的码；都等待满足条件后执行的代码。。
     当执行栈中为空的时候。evevt Loap 就会从了任务队列中 拿出一个任务并放在任务栈中执行
24.1 异步任务源？
    微任务先执行，宏任务后执行
    微任务：promise process.nextTick
    宏任务 setTimeOut setInterval
24.3 event Loap 的执行顺序是什么？
    1 执行同步代码，这属于宏任务 
当执行完所有同步代码后，执行栈为空，查询是否有异步代码需要执行
执行所有微任务
当执行完所有微任务后，如有必要会渲染页面
然后开始下一轮 Event Loop，执行宏任务中的异步代码，也就是setTimeout中的回调函数
    
25 ode 中的 Event Loop 和浏览器中的有什么区别？process.nexttick 执行顺序？
26 new 的原理是什么？通过 new 的方式创建对象和通过字面量创建有什么区别？
27 instanceof 的原理是什么？
28 为什么 0.1 + 0.2 != 0.3？如何解决这个问题？
~~~~

**js 在浏览器中是怎么运行的？运行原理是什么？**

~~~
js 是单线程程序。js程序的执行就是在执行栈中放入函数；当函数执行完毕后，从执行栈中释放。按照先进后出的原则执行。如果递归程序没有出口会导致暴栈。js中程序的执行，是通过event loap 从任务队列中获取任务等执行栈为空时候，放入到执行栈中。

js 程序执行的流程是 
  1执行所有同步代码==>2:执行异步代码中微任务 ===>3:执行宏任务

首先执行同步代码，这属于宏任务
当执行完所有同步代码后，执行栈为空，查询是否有异步代码需要执行
执行所有微任务
当执行完所有微任务后，如有必要会渲染页面
然后开始下一轮 Event Loop，执行宏任务中的异步代码，也就是setTimeout中的回调函数
~~~

**js 中异步的原理的是什么/ 什么是异步**（从任务队列） 

~~~
js 将所有的异步程序放在 任务队列中，当执行栈中程序执行完毕后，执行栈为空，event Loap 会从任务队列中获取任务，放入到执行栈中执行，这就是js 的异步程序。
任务源：为微任务和宏任务。同样的异步程序，先执行微任务，在执行宏任务  
~~~


~~~