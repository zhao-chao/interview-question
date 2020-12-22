 

##  

## 第一部分：前端基础(HTML CSS JS基础)

### 1.   怎么让一个不定宽高的 DIV，垂直水平居中？

答：1.使用 CSS 方法：

​    父盒子设置：display：table-cell； text-align：center；vertical-align：middle； 

Div设置：  display：inline-block；vertical-align：middle； 

   2.使用 CSS3 transform： 

​     父盒子设置：display：relative 

​    Div 设置：  transform： translate(-50%，-50%)；position： absolute；top： 50%；left:50%

 

### 2.   px，em，rem 的区别？ 

答：1.px 像素（Pixel）。绝对单位。像素 px 是相对于显示器屏幕分辨率而言的，是一个虚拟长度单位，是计算机系统的数字化图像长度单位，如果 px 要换算成物理长度，需要指定精度 DPI。 

   2.em是相对长度单位，相对于当前对象内文本的字体尺寸。如当前对行内文本的字体尺寸未被人为设置，则相对于浏览器的默认字体尺寸。它会继承父级元素的字体大小，因此并不是一个固定的值。

   3.rem 是 CSS3 新增的一个相对单位（root em，根 em），使用 rem 为元素设定字体大小时，仍然是相对大小，但相对的只是 HTML根元素。 

   4.区别：IE 无法调整那些使用 px作为单位的字体大小，而 em和 rem可以缩放，rem相对的只是 HTML 根元素。这个单位可谓集相对大小和绝对大小的优点于一身，通过它既可以做到只修改根元素就成比例地调整所有字体大小，又可以避免字体大小逐层复合的连锁反应。目前，除了IE8 及更早版本外，所有浏览器均已支持 rem。

 

### 3.   CSS 引入的方式有哪些? link 和@import 的区别是? 

答：内联 内嵌 外链 导入 

区别 ：同时加载 前者无兼容性，后者 CSS2.1 以下浏览器不支持 Link 支持使用javascript 改变样式，后者不可

 

### 4.   div+css的布局较table布局有什么优点？

答: 1.改版的时候更方便 只要改css文件。

   2.页面加载速度更快、结构化清晰、页面显示简洁。

   3.表现与结构相分离。

   4.易于优化（seo）搜索引擎更友好，排名更容易靠前。

 

### 5.   描述 css reset 的作用和用途？ 

答：Reset 重置浏览器的 css 默认属性 ，览器的品种不同，样式不同，然后重置，让他们统一

 

### 6.   解释 css sprites，如何使用？ 

答：Css 精灵图，把一堆小的图片整合到一张大的图片（png）上，减轻服务器对图片的请求数量。

### 7.   简述一下src与href的区别。

答:src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。src是source的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素。

<script src =”js.js”></script>

当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部。

href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加

<link href=”common.css” rel=”stylesheet”/>

那么浏览器会识别该文档为css文件，就会并行下载资源并且不会停止对当前文档的处理。这也是为什么建议使用link方式来加载css，而不是使用@import方式。

 

### 8.   CSS都有哪些选择器？

答:

​    派生选择器（用HTML标签申明）

​    id选择器（用DOM的ID申明）

​    类选择器（用一个样式类名申明）

​    属性选择器（用DOM的属性申明，属于CSS2，IE6不支持，不常用，不知道就算了）

​    除了前3种基本选择器，还有一些扩展选择器，包括

​    后代选择器（利用空格间隔，比如div .a{ }）

​    群组选择器（利用逗号间隔，比如p,div,#a{ }）

 

### 9.   CSS选择器的优先级是怎么样定义的？

答:一般而言，选择器越特殊，它的优先级越高。也就是选择器指向的越准确，它的优先级就越高。

复杂的计算方法：

用1表示派生选择器的优先级

用10表示类选择器的优先级

用100标示ID选择器的优先级

div.test1 .span var 优先级 1+10 +10 +1

span#xxx .songs li 优先级1+100 + 10 + 1

\#xxx li 优先级 100 +1

 

### 10. 清除浮动的几种方式？ 

答：1，父级 div定义 height 原理：父级 div 手动定义 height，就解决了父级 div 无法自动获取到高度的问题。 简单、代码少、 容易掌握 ，但只适合高度固定的布局. 

​    2，结尾处加空div标签 clear：both 原理：在浮动元素的后面添加一个空 div兄弟元素，利用 css 提高的 clear：both 清除浮动，让父级 div能自动获取到高度 ，如果页面浮动布局多，就要增加很多空 div，让人感觉很不好 . 

​    3，父级 div定义 伪类：after 和 zoom /*清除浮动代码*/ .clearfix：after{ content：""； display：block； visibility：hidden； height：0； line-height：0； clear：both； } .clearfix{zoom：1} 原理：IE8 以上和非 IE 浏览器才支持：after，原理和方法 2 有点类似，zoom(IE 转有属性)可解决 ie6，ie7浮动问题 ，推荐使用，建议定义公共类，以减少 CSS 代码。 

​    4，父级 div定义 overflow：hidden 超出盒子部分会被隐藏，不推荐使用. 5. 双伪元素法： .clearfix：before，.clearfix：after {  content： ""；  display： block；  clear： both；  }  .clearfix {  zoom： 1；  }

 

### 11. CSS中可以通过哪些属性定义，使得一个DOM元素不显示在浏览器可视范围内？

答:

​    最基本的：设置display属性为none，或者设置visibility属性为hidden

​    技巧性：设置宽高为0，设置透明度为0，设置z-index位置在-1000em

 

### 12. 能否简述一下如何使一套设计方案，适应不同的分辨率，有哪些方法可以实现？ 

答：

​    流式布局:使用非固定像素来定义网页内容，也就是百分比布局，通过盒子的宽度设置成百分比来根据屏 幕的宽度来进行伸缩，不受固定像素的限制，内容向两侧填充。   这样的布局方式，就是移动 web 开发使用的常用布局方式。这样的布局可以适配移动端不同 的分辨率设备。   

​    响应式开发:那么 Ethan Marcotte 在 2010年5月份提出的一个概念，简而言之，就是一个网站能够兼容多 个终端。越来越多的设计师也采用了这种设计。CSS3 中的 Media Query（媒介查询），通过查询 screen 的宽度来指定某个宽度区间的网页布局。 

\1.  超小屏幕（移动设备）768px以下

\2.  小屏设备 768px-992px 

\3.  中等屏幕 992px-1200px

\4.  宽屏设备 1200px 以上 

 

### 13. 合理的页面布局中常听过结构与表现分离，那么结构是什么？表现是什么？ 

答：结构是 html，表现是 css

 

### 14. 简述对 Web 语义化的理解？ 

答：就是让浏览器更好的读懂你写的代码，在进行 HTML结构、表现、行为设计时，尽量使 用语义化的标签，使程序代码简介明了，易于进行 Web 操作和网站SEO，方便团队协作的一种标 准，以图实现一种“无障碍”的 Web开发

 

### 15. display： none；与 visibility： hidden 的区别是什么？ 

答：

   display：none； 使用该属性后，HTM元素（对象）的宽度、高度等各种属性值都将“丢失”；   

   visibility：hidden； 使用该属性后，HTML元素（对象）仅仅是在视觉上看不见（完全 透明），而它所占据的空间位置仍然存在，也即是说它仍具有高度、宽度等属性值

 

### 16. HTML 与 XHTML——二者有什么区别 

答: HTML是一种基本的 WEB 网页设计语言，XHTML 是一个基于XML 的置标语言 最主要的不同： XHTML 元素必须被正确地嵌套。 XHTML 元素必须被关闭。 标签名必须用小写字母。 XHTML 文档必须拥有根元素。

 

### 17. 行内元素和块级元素的具体区别是什么？行内元素的padding和margin可设置吗？

答:

​    块级元素(block)特性：总是独占一行，表现为另起一行开始，而且其后的元素也必须另起一行显示;宽度(width)、高度(height)、内边距(padding)和外边距(margin)都可控制;

​    内联元素(inline)特性：和相邻的内联元素在同一行;宽度(width)、高度(height)、内边距的top/bottom(padding-top/padding-bottom)和外边距的top/bottom(margin-top/margin-bottom)都不可改变（也就是padding和margin的left和right是可以设置的），就是里面文字或图片的大小。

### 18. 浏览器还有默认的天生inline-block元素（拥有内在尺寸，可设置高宽，但不会自动换行），有哪些？

答:<input> 、<img> 、<button> 、<texterea> 、<label>。

 

### 19. 什么是外边距重叠？重叠的结果是什么？

答: 外边距重叠就是margin-collapse。在CSS当中，相邻的两个盒子（可能是兄弟关系也可能是祖先关系）的外边距可以结合成一个单独的外边距。这种合并外边距的方式被称为折叠，并且因而所结合成的外边距称为折叠外边距。

折叠结果遵循下列计算规则：

两个相邻的外边距都是正数时，折叠结果是它们两者之间较大的值。

两个相邻的外边距都是负数时，折叠结果是两者绝对值的较大值。

两个外边距一正一负时，折叠结果是两者的相加的和。

 

### 20. rgba()和opacity的透明效果有什么不同？

答:rgba()和opacity都能实现透明效果，但最大的不同是opacity作用于元素，以及元素内的所有内容的透明度，而rgba()只作用于元素的颜色或其背景色。（设置rgba透明的元素的子元素不会继承透明效果！）

 

### 21. css中可以让文字在垂直和水平方向上重叠的两个属性是什么？

答:

​    垂直方向：line-height

​    水平方向：letter-spacing

### 22. 关于letter-spacing的实际用法有哪些？

答:可以用于消除inline-block元素间的换行符空格间隙问题。

 

### 23. display：inline-block 什么时候会显示间隙？

答:真正意义上的 inline-block 水平呈现的元素间，换行显示或空格分隔的情况下会有间距。 解决：父元素{font-size：0；-webkit-text-size-adjust：none；}

 

### 24. overflow 有哪些属性值？ 

答:

Visible：默认值。内容不会被修剪，会呈现在元素框之外。

Hidden：内容会被修剪，并且其余内容是不可见的。

Scroll：内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。

Auto：如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。

Inherit：规定应该从父元素继承 overflow 属性的值

 

### 25. CSS 样式初始化的目的 

答:是为了考虑到浏览器的兼容问题，其实不同浏览器对有些标签的默认值是不同的，如果没对 CSS 初 始化往往会出现浏览器之间的页面差异。当然，初始化样式会对 SEO 有一定的影响，但鱼和熊掌 不可兼得，但力求影响最小的情况下初始化

 

### 26. Sass、LESS是什么？大家为什么要使用他们？

他们是CSS预处理器。他是CSS上的一种抽象层。他们是一种特殊的语法/语言编译成CSS。

例如[Less](http://www.lesscss.org/)是一种动态样式语言. 将CSS赋予了动态语言的特性，如变量，继承，运算， 函数. LESS 既可以在客户端上运行 (支持IE 6+, Webkit, Firefox)，也可一在服务端运行 (借助 Node.js)。

 

为什么要使用它们？

结构清晰，便于扩展。可以方便地屏蔽浏览器私有语法差异。这个不用多说，封装对浏览器语法差异的重复处理，减少无意义的机械劳动。

可以轻松实现多重继承。完全兼容 CSS 代码，可以方便地应用到老项目中。LESS 只是在 CSS 语法上做了扩展，所以老的 CSS 代码也可以与 LESS 代码一同编译。

 

### 27. 用 div+css 网站布局的好处

答:

1：表现和内容相分离  将设计部分剥离出来放在一个独立样式文件中，HTML 文件中只存放文本信息。 

2：提高搜索引擎对网页的索引效率用只包含结构化内容的 HTML 代替嵌套的标签，搜索引擎将更有效地搜索到你的网页内容，并 可能给你一个较高的评价。 

3：提高页面浏览速度对于同一个页面视觉效果，采用 CSS+DIV 重构的页面容量要比 TABLE 编码的页面文件容量小得多，前者一般只有后者的1/2大小。 

4：易于维护和改版  你只要简单的修改几个 CSS 文件就可以重新设计整个网站的页面。从以上的描述来看，采用 CSS+DIV 对网站重构可以大大提升网站用户与搜索引擎的友好度,CSS+DIV 所以成为目前网页布局主流

 

### 28. CSS3 新特性有哪些？ 

答：

​    1.颜色：新增 RGBA，HSLA 模式 

​    \2. 文字阴影（text-shadow、）

​    3.边框： 圆角（border-radius）边框阴影： box-shadow 

​    \4. 盒子模型：box-sizing 

​    5.背景：background-size 设置背景图片的尺寸 background-origin 设置背景图片的原点 background-clip 设置背景图片的裁切区域，以”，”分隔可以设置多背景，用于自适应布局

​    6.渐变：linear-gradient、radial-gradient 

​    \7. 过渡：transition，可实现动画

​    \8. 自定义动画 animate  @keyfrom 

​    \9. 在 CSS3 中唯一引入的伪元素是 ：：selection. 

​    \10. 媒体查询，多栏布局 @media screen and (width:800px){ … } 

​    \11. border-image 

​    12.2D 转换：transform：translate(x，y) rotate(x，y) skew(x，y) scale(x，y) 

​    \13. 3D 转换 

​    14 字体图标  font-face 

​    15 弹性布局 flex

 

### 29. 移动端优先使用弹性布局（flex）来解决布局问题，请列出弹性布局的相关属性，并说明属性用途: 

答:

flex 的 3 个属性 flex-grow | flex-shrink| flex-basis flex-grow 一个数字，规定项目将相对于其他灵活的项目进行扩展的量。 flex-shrink 一个数字，规定项目将相对于其他灵活的项目进行收缩的量。 flex-basis 项目的长度。合法值："auto"、"inherit" 或一个后跟 "%"、"px"、"em" 或任何其他长 度单位的数字。 用 js 设置 flex object.style.flex="1"

 

### 30. CSS3 的兼容问题怎么处理？ 

答:一般加私有前缀否则不做特殊处理，再有就是遵循 2 大原则，渐进增强和优雅降级 

 

### 31. CSS3 新增伪类有那些？ 

答:p:first-child 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。 p:last-child 选择属于其父元素的最后 <p> 元素的每个 <p> 元素。 p:nth-child(2n) 选择属于其父元素的第二个子元素的每个 <p> 元素。 :enabled、:disabled 控制表单控件的禁用状态。 :checked，单选框或复选框被选中。

 

### 32. CSS3 动画和 JS 动画主要的不同点是什么？

答:

\1.  功能涵盖面，JS 比 CSS3 大  

​    ①定义动画过程的@keyframes 不支持递归定义，如果有多种类似的动画过程，需要调 节多个参数来生成的话，将会有很大的冗余（比如 jQuery Mobile 的动画方案），而 JS 则天然可以 以一套函数实现多个不同的动画过程  

​    ② 时间尺度上，@keyframes 的动画粒度粗，而 JS 的动画粒度控制可以很细  

​    ③ CSS3 动画里被支持的时间函数非常少，不够灵活  ④ 以现有的接口，CSS3 动画无法做到支持两个以上的状态转化 

   \2. 实现/重构难度不一，CSS3 比 JS 更简单，性能调优方向固定 

   \3. 对于帧速表现不好的低版本浏览器，CSS3 可以做到自然降级，而 JS 则需要撰写额外代码

   \4. CSS 动画有天然事件支持（TransitionEnd、AnimationEnd，但是它们都需要针对浏览器加前 缀），JS 则需要自己写事件  

   \5. CSS3 有兼容性问题，而 JS 大多时候没有兼容性问

 

### 33. 简介盒子模型：

CSS的盒子模型有两种：IE盒子模型、标准的W3C盒子模型模型

盒模型：内容、内边距、外边距（一般不计入盒子实际宽度）、边框

​                               

 

### 34. 前端页面有哪三层构成，分别是什么?作用是什么?

答：结构层 Html 表示层 CSS 行为层 js。

 

### 35. 列出display的值，说明他们的作用。position的值， relative和absolute定位原点是？

答: 

\1. block 象块类型元素一样显示。

   none 缺省值。向行内元素类型一样显示。

   inline-block 象行内元素一样显示，但其内容象块类型元素一样显示。

   list-item 象块类型元素一样显示，并添加样式列表标记。

 \2. position的值

   *absolute 

​    生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。 

   *fixed （老IE不支持）

​    生成绝对定位的元素，相对于浏览器窗口进行定位。 

   \* relative 

​    生成相对定位的元素，相对于其正常位置进行定位。 

   \* static 默认值。没有定位，元素出现在正常的流中

   *（忽略 top, bottom, left, right z-index 声明）。

   \* inherit 规定从父元素继承 position 属性的值。

 

### 36. css的基本语句构成是?

答:选择器{属性1:值1;属性2:值2;……}

 

### 37. 哪些css属性可以继承？

答:

   可继承： font-size font-family color, ul li dl dd dt;

   不可继承 ：border padding margin width height ;

 

### 38. b标签和strong标签,i标签和em标签的区别？

答:后者有语义，前者则无。

 

### 39. image 和 canvas 在处理图片的时候有什么区别？

答：image 是通过对象的形式描述图片的；canvas 通过专门的 API将图片绘制在画布上。

 

### 40. javascript的typeof返回哪些数据类型

  答:

​    alert(typeof [1, 2]); //object

​    alert(typeof 'leipeng'); //string

​    var i = true; 

   alert(typeof i); //boolean

   alert(typeof 1); //number

   var a; 

​    alert(typeof a); //undefined

   function a(){;};

​    alert(typeof a) //function

 

### 41. 例举3种强制类型转换和2种隐式类型转换?

答:

   强制（parseInt(),parseFloat(),Number()）

   隐式（== ,!!）

 

### 42. split() 、join() 的区别

   答:前者是切割成数组的形式，后者是将数组转换成字符串

 

### 43. 数组方法pop() push() unshift() shift()

答:

   Push()尾部添加 

   pop()尾部删除

   Unshift()头部添加

   shift()头部删除

 

### 44. 事件绑定和普通事件有什么区别

普通添加事件的方法：

var btn = document.getElementById("hello");

btn.onclick = function(){

   alert(1);

}

btn.onclick = function(){

   alert(2);

}

执行上面的代码只会alert 2 

 

事件绑定方式添加事件：

var btn = document.getElementById("hello");

btn.addEventListener("click",function(){

   alert(1);

},false);

btn.addEventListener("click",function(){

   alert(2);

},false);

执行上面的代码会先alert 1 再 alert 2

普通添加事件的方法不支持添加多个事件，最下面的事件会覆盖上面的，而事件绑定（addEventListener）方式添加事件可以添加多个。

addEventListener不兼容低版本IE

普通事件无法取消

addEventLisntener还支持事件冒泡+事件捕获

 

### 45. IE和DOM事件流的区别

答:

   1.执行顺序不一样、

   2.参数不一样

   3.事件加不加on

   4.this指向问题

 

### 46. call和apply的区别

**答:**

​    **call****方法:** 
​    语法：call(thisObj，Object1,Object2...)
​    定义：调用一个对象的一个方法，以另一个对象替换当前对象。
​    说明：call 方法可以用来代替另一个对象调用一个方法。call 方法可将一个函数的对象上下文从初始的上下文改变为由 thisObj 指定的新对象。 如果没有提供 thisObj 参数，那么 Global 对象被用作 thisObj。 
 
​    **apply****方法：** 
​    语法：apply(thisObj，[argArray])
​    定义：应用某一对象的一个方法，用另一个对象替换当前对象。 
​    说明： 如果 argArray 不是一个有效的数组或者不是 arguments 对象，那么将导致一个 TypeError。 如果没有提供 argArray 和 thisObj 任何一个参数，那么 Global 对象将被用作 thisObj， 并且无法被传递任何参数。

 

### 47. 如何阻止事件冒泡和默认事件

答:

​    canceBubble() //只支持IE,

​    return false,stopPropagation()

 

### 48. 添加 删除 替换 插入到某个接点的方法

答:

​    obj.appendChid()

​    obj.insertBefore()

​    obj.replaceChild()

​    obj.removeChild()

### 49. javascript的本地对象，内置对象和宿主对象

答:

​    本地对象为array obj regexp等可以new实例化

​    内置对象为gload Math 等不可以实例化的

​    宿主为浏览器自带的document,window 等

### 50. window.onload 和document ready的区别

答: window.onload 是在dom文档树加载完和所有文件加载完之后执行一个函数Document.ready原生种没有这个方法，jquery中有 $().ready(function),在dom文档树加载完之后执行一个函数（注意，这里面的文档树加载完不代表全部文件加载完）。$(document).ready要比window.onload先执行window.onload只能出来一次，$(document).ready可以出现多次

 

### 51. javascript的同源策略

答:一段脚本只能读取来自于同一来源的窗口和文档的属性，这里的同一来源指的是主机名、议和端口号的组合

### 52. JavaScript是一门什么样的语言，它有哪些特点？

答:javaScript一种[直译](http://baike.baidu.com/view/295412.htm)式[脚本语言](http://baike.baidu.com/view/76320.htm)，是一种动态类型、弱类型、基于原型的语言，内置支持类型。它的[解释器](http://baike.baidu.com/view/592974.htm)被称为JavaScript引擎，为[浏览器](http://baike.baidu.com/view/7718.htm)的一部分，广泛用于[客户端](http://baike.baidu.com/view/930.htm)的脚本语言，最早是在[HTML](http://baike.baidu.com/view/692.htm)网页上使用，用来给[HTML](http://baike.baidu.com/view/692.htm)网页增加动态功能。JavaScript[兼容](http://baike.baidu.com/subview/348591/5144387.htm)于ECMA标准，因此也称为[ECMAScript](http://baike.baidu.com/view/810176.htm)。

**基本特点**

1．是一种解释性脚本语言（代码不进行[预编译](http://baike.baidu.com/view/176610.htm)）。

2．主要用来向[HTML](http://baike.baidu.com/view/692.htm)（[标准通用标记语言](http://baike.baidu.com/view/5286041.htm)下的一个应用）页面添加交互行为。

3．可以直接嵌入HTML页面，但写成单独的[js](http://baike.baidu.com/subview/9866/6241710.htm)文件有利于结构和行为的[分离](http://baike.baidu.com/view/351036.htm)。

4．跨平台特性，在绝大多数浏览器的支持下，可以在多种平台下运行（如[Windows](http://baike.baidu.com/view/4821.htm)、[Linux](http://baike.baidu.com/view/1634.htm)、Mac、Android、iOS等）。

 

### 53. 当一个DOM节点被点击时候，我们希望能够执行一个函数，应该怎么做？

答:

​    直接在DOM里绑定事件：<div onclick=”test()”></div>

​    在JS里通过onclick绑定：xxx.onclick = test

​    通过事件添加进行绑定：addEventListener(xxx, ‘click’, test)

### 54. Javascript的事件流模型都有什么？

答:

​    “事件冒泡”：事件开始由最具体的元素接受，然后逐级向上传播

​    “事件捕捉”：事件由最不具体的节点先接收，然后逐级向下，一直到最具体的

​    “DOM事件流”：三个阶段：事件捕捉，目标阶段，事件冒泡

 

### 55. foo = foo||bar ，这行代码是什么意思？为什么要这样写？

答：if(!foo) foo = bar; //如果foo存在，值不变，否则把bar的值赋给foo。

短路表达式：作为”&&”和”||”操作符的操作数表达式，这些表达式在进行求值时，只要最终的结果已经可以确定是真或假，求值过程便告终止，这称之为短路求值。

 

### 56. 怎样添加、移除、移动、复制、创建和查找节点（原生JS，实在基础，没细写每一步）

答:

​    1）创建新节点

​       createDocumentFragment()  //创建一个DOM片段

​       createElement()  //创建一个具体的元素

​       createTextNode()  //创建一个文本节点

​    2）添加、移除、替换、插入

​       appendChild()   //添加

​       removeChild()   //移除

​       replaceChild()   //替换

​       insertBefore()   //插入

​    3）查找

​       getElementsByTagName()  //通过标签名称

​       getElementsByName()   //通过元素的Name属性的值

​       getElementById()    //通过元素Id，唯一性

 

### 57. 正则表达式构造函数var reg=new RegExp(“xxx”)与正则表达字面量var reg=//有什么不同？匹配邮箱的正则表达式？

答：当使用RegExp()构造函数的时候，不仅需要转义引号（即\”表示”），并且还需要双反斜杠（即\\表示一个\）。使用正则表达字面量的效率更高。 

邮箱的正则匹配：

|      | var regMail =  /^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+((.[a-zA-Z0-9_-]{2,3}){1,2})$/; |
| ---- | ------------------------------------------------------------ |
|      |                                                              |

 

### 58. Javascript中callee和caller的作用？

答:

​    caller是返回一个对函数的引用，该函数调用了当前函数；

​    callee是返回正在被执行的function函数，也就是所指定的function对象的正文。

 

### 59. 简述列举文档对象模型DOM里document的常用的查找访问节点的方法并做简单说明

答:

​    Document.getElementById 根据元素id查找元素

​    Document.getElementByName 根据元素name查找元素

​    Document.getElementTagName 根据指定的元素名查找元素

 

### 60. 简述创建函数的几种方式

答:

​    第一种（函数声明）： 

​       function sum1(num1,num2){
​           return num1+num2;
​        }

​    第二种（函数表达式）：

​       var sum2 = function(num1,num2){
​           return num1+num2;
​        }

​    第三种（函数对象方式）：

​       var sum3 = new Function("num1","num2","return num1+num2");

 

### 61. Javascript如何实现继承？

答: 

​    1.构造继承法
​    2.原型继承法
​    3.实例继承法

### 62. Javascript创建对象的几种方式？

答:

   1、var obj = {};（使用json创建对象）

   2、var obj = new Object();（使用Object创建对象）

   3、通过函数创建对象。

​      (1)、使用this关键字

​      (2)、使用prototype关键字

   4、通过Window创建对象。

   5、使用内置对象创建对象。

### 63. iframe的优缺点？

答:

   优点：

​      \1. 解决加载缓慢的第三方内容如图标和广告等的加载问题

​      \2. Security sandbox

​      \3. 并行加载脚本

   缺点：

​      \1. iframe会阻塞主页面的Onload事件

​      \2. 即时内容为空，加载也需要时间

​      \3. 没有语意

### 64. 请你谈谈Cookie的弊端？

答:

   1.Cookie数量和长度的限制。每个domain最多只能有20条cookie，每个cookie长度不能超过4KB，否则会被截掉。

   2.安全性问题。如果cookie被人拦截了，那人就可以取得所有的session信息。即使加密也与事无补，因为拦截者并不需要知道cookie的意义，他只要原样转发cookie就可以达到目的了。

   3.有些状态不可能保存在客户端。例如，为了防止重复提交表单，我们需要在服务器端保存一个计数器。如果我们把这个计数器保存在客户端，那么它起不到任何作用。

### 65. js延迟加载的方式有哪些？

答: 

   \1. defer和async

   \2. 动态创建DOM方式（创建script，插入到DOM中，加载完毕后callBack）

   \3. 按需异步载入js

### 66. documen.write和 innerHTML 的区别？

答:

   document.write 只能重绘整个页面

   innerHTML 可以重绘页面的一部分

### 67. 哪些操作会造成内存泄漏？

答:

   内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。

   \1. setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。

   \2. 闭包

   \3. 控制台日志

   \4. 循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）

 

### 68. 解释jsonp的原理，以及为什么不是真正的ajax

答:

​    动态创建script标签，回调函数

​    Ajax是页面无刷新请求数据操作

### 69. javascript的本地对象，内置对象和宿主对象

答:

​    本地对象为array obj regexp等可以new实例化

​    内置对象为gload Math 等不可以实例化的

​    宿主为浏览器自带的document,window 等

 

### 70. window.location.search() 返回的是什么？

答：

​    查询(参数)部分。除了给动态语言赋值以外，我们同样可以给静态页面,并使用javascript来获得相信应的参数值返回值：?ver=1.0&id=timlq 也就是问号后面的！

### 71. window.location.hash 返回的是什么？

  答：锚点 ， 返回值：#love ；

### 72. window.location.reload() 作用？

  答：刷新当前页面。

### 73. javascript 中的垃圾回收机制？

  答：在Javascript中，如果一个对象不再被引用，那么这个对象就会被GC回收。如果两个对象互相引用，而不再  被第3者所引用，那么这两个互相引用的对象也会被回收。因为函数a被b引用，b又被a外的c引用，这就是为什么  函数a执行后不会被回收的原因。 

 

### 74. 如何在HTML中添加事件，几种方法？

答:

​    1、标签之中直接添加 onclick="fun()";

​      2、JS添加 Eobj.onclick = method;

​     3、现代事件IE： obj.attachEvent('onclick', method)；

​             FF: obj.addEventListener('click', method, false);

### 75. BOM对象有哪些，列举window对象？

  答:

​       1、window对象 ，是JS的最顶层对象，其他的BOM对象都是window对象的属性；

​     2、document对象，文档对象；

​     3、location对象，浏览器当前URL信息；

​     4、navigator对象，浏览器本身信息；

​     5、screen对象，客户端屏幕信息；

​     6、history对象，浏览器访问历史信息；

 

### 76. bind(), live(), delegate()的区别

答:

​    bind： 绑定事件，对新添加的事件不起作用，方法用于将一个处理程序附加到每个匹配元素的事件上并返回jQuery对象。

​     live： 方法将一个事件处理程序附加到与当前选择器匹配的所有元素（包含现有的或将来添加的）的指定事件上并返回jQuery对象。

​     delegate： 方法基于一组特定的根元素将处理程序附加到匹配选择器的所有元素（现有的或将来的）的一个或多个事件上。  

 

### 77. 你如何优化自己的代码？

答:  

​    1.代码重用

​    2.避免全局变量（命名空间，封闭空间，模块化mvc..）

​    3.拆分函数避免函数过于臃肿

​    4.注释

 

### 78. 简述readyonly与disabled的区别

答:ReadOnly和Disabled的作用是使用户不能够更改表单域中的内容.但是二者还是有着一些区别的：
    1、Readonly只针对input(text/password)和textarea有效，而disabled对于所有的表单元素有效，包括select,radio,checkbox,button等。
    2、在表单元素使用了disabled后，我们将表单以POST或者GET的方式提交的话，这个元素的值不会被传递出去，而readonly会将该值传递出去

 

### 79. 请尽可能详尽的解释ajax的工作原理

​    答:Ajax的工作原理相当于在用户和服务器之间加了—个中间层，使用户操作与服务器响应异步化。这样把以前的一些服务器负担的工作转嫁到客户端，利于客户端闲置的处理能力来处理，减轻服务器和带宽的负担，从而达到节约ISP的空间及带宽租用成本的目的。简单来说通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。这其中最关键的一步就是从服务器获得请求数据。要清楚这个过程和原理，我们必须对 XMLHttpRequest有所了解。

### 80. 什么是三元表达式？“三元”表示什么意思？

​    三元运算符:

   三元如名字表示的三元运算符需要三个操作数。语法是 条件 ? 结果1 : 结果2;. 这里你把条件写在问号(?)的前面后面跟着用冒号(:)分隔的结果1和结果2。满足条件时结果1否则结果2。

### 81. 对于html的语义化标签的理解，结构化标签的理解，同时写出简洁的html结构，如何进行SEO优化？

**解答:**对于html的语义化标签，用正确的标签做正确的事情。html语义化，让页面的内容结构化，便于对浏览器和搜索引擎的解析，在没有css样式的情况下，以文档的形式同样易于阅读，符合文档语义的标签。标签本身所代表的语义，每一个标签所带有的语义，根据语义去使用标签，依赖标记确定权重，同时也可以提高SEO的优化。对于结构化标签，按照一定的结构去使用标签。

简单的html结构

 

### 82. 在form表单中，get方式和post方式提交数据的区别是什么？如何判断在实际开发中的应用？

解答:get方式和post方式提交数据的区别：

1） 大小不同，get方式传输的数据量较小，而post可以传输大量的数据。

2） 安全程度不同，get方式传输数据能够被别人轻易的看到数据内容，所以安全程度较低，而post则可以很好的隐藏。

3） 速度不同，post方式速度较慢，而get方式速度较快。

4） 在服务器上的作用不同，get是从服务器上获取数据，而post是向服务器上传送数据。

在实际开发中的应用：

1）在重要数据进行传输数据的时候，用post的方式进行提交数据。

2）在做数据查询的时候，用get的方式进行提交数据。

3）在做增加、删除和修改数据的时候，用post的方式进行提交数据。

 

### 83. 在input表单控件中，value和placeholder的区别是什么?

解答:placeholder: 表示在输入框中显示的提示信息，用户点击之后，提示信息就会消失。
 value: 叫做默认值，当用户想要在输入框中输入信息的时候，必须先手动的删除value的值 。

 

### 84. 在css当中，@import 和 link的区别是什么呢？

解答:

1）本质的差别：link是属于XHTML的标签，而@import是CSS提供的一种方式。

2）加载顺序的差别：当页面进行加载的时候，link引用的CSS时会被加载，而@import引用的CSS会等页面加载完成以后才被加载，所以在 @import加载CSS的时候，一开始会没有样式。

3）兼容性的差别：@import在老的浏览器上不兼容，只有在IE5以上的浏览器才可以被识别，但是link可以在任意浏览器的版本上进行加载执行。

4）使用DOM文档对象模型控制样式的差别：当使用JavaScript控制DOM区改变样式的时候，只能使用link标签，而@import是不可以的。

5）作用不同：link是属于XHTML，除了可以加载css,还可以定义RSS等其它事务，而@import是属于css范畴，只能加载css。

6）权重不同：link方式的权重高于@import的权重值。

7）标签不同：import在html使用的时候需要标签，而link在html使用的时候不需要标签。

 

### 85. 新的HTML5文档类型和字符集是？

解答:

HTML5文档类型 <!doctype html>
 HTML5使用UTF-8字符集



 

### 86. 对于web标准以及标准制定机构重要性的理解？

解答:

网页标准和标准制定机构都是为了能让web发展的更健康，开发者遵循统一的标准，降低开发难度，开发成本，SEO也会更好做，也不会因为滥用代码导致各种BUG、安全问题，最终提高网站易用性。

 

### 87. .html5的新特性有哪些？

解答:

用于绘画的 canvas 元素用于媒介回放的 video 和 audio 元素新的内容元素，比如 article、footer、header、nav、section、menu新的表单控件，比如 number、date、time、email、url、search、color、range、month、week、datetime、datetime_local。

 

\1. html5的存储类型有什么区别？

解答:

cookies:服务器和客户端都可以访问，大小只有4KB左右，有有效期，过期后将会删除；localStorage:将数据保存在本地的硬件设备，没有时间限制，关闭浏览器也不会丢失。永久保存sessionStorage:将数据保存在session对象中，关闭浏览器后数据也随之销毁。临时保存。

 

### 88. 对于常见的浏览器内核有哪些？

解答:

Trident( MSHTML )：IE MaxThon TT The World 360 搜狗浏览器

Geckos：Netscape6及以上版本 FireFox Mozilla Suite/SeaMonkey

Presto：Opera7及以上(Opera内核原为：Presto，现为：Blink)

Webkit：Safari Chrome

 

### 89. cookies，sessionStorage和localStorage的区别是什么？

解答:

它们之间的共同点：都是保存在浏览器端，且是同源的。

它们之间的区别：

1）cookies是为了标识用户身份而存储在用户本地终端上的数据，始终在同源http请求中携带，即cookies在浏览器和服务器间来回传递，而sessionstorage和localstorage不会自动把数据发给服务器，仅在本地保存。

2）存储大小的限制不同。cookie保存的数据很小，不能超过4k，而sessionstorage和localstorage保存的数据大，可达到5M。数据的有效期不同。cookie在设置的cookie过期时间之前一直有效，即使窗口或者浏览器关闭。sessionstorage仅在浏览器窗口关闭之前有效。localstorage始终有效，窗口和浏览器关闭也一直保存，用作长久数据保存。

3）作用域不同。cookie在所有的同源窗口都是共享；sessionstorage不在不同的浏览器共享，即使同一页面；localstorage在所有同源窗口都是共享。

 

### 90. iframe框架有那些优缺点有哪些呢？

解答:

frame框架的优点：

1）iframe能够原封不动的把嵌入的网页展现出来。

2）如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。

3）网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。

4）如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。

iframe框架的缺点：

1）搜索引擎的爬虫程序无法解读这种页面。

2）框架结构中出现各种滚动条。

3）使用框架结构时，保证设置正确的导航链接。

4）iframe页面会增加服务器的http请求。

5）iframe会阻塞主页面的Onload事件。

6）会产生很多的页面，不容易进行管理。

 

### 91. label的作用是什么? 是怎么用的?

解答:

label标签用来定义表单控件间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。label 中有两个属性是非常有用的, FOR和ACCESSKEY：

1）FOR属性功能：表示label标签要绑定的HTML元素，你点击这个标签的时候，所绑定的元素将获取焦点。

2）ACCESSKEY属性功能：表示访问label标签所绑定的元素的热键，当您按下热键，所绑定的元素将获取焦点。

 

### 92. .你知道多少种Doctype文档类型？

解答:

1）标签可声明三种 DTD 类型，分别表示严格版本、过渡版本以及基于框架的 HTML 文档。

2）HTML 4.01 规定了三种文档类型：Strict、Transitional 以及 Frameset。

3）XHTML 1.0 规定了三种 XML 文档类型：Strict、Transitional 以及 Frameset。

4）Standards （标准）模式（也就是严格呈现模式）用于呈现遵循最新标准的网页，Quirks（包容）模式（也就是松散呈现模式或者兼容模式）用于呈现为传统浏览器而设计的网页。

 

### 93. HTML和XHTML这两者之间有什么样的区别呢？

解答:

1）XHTML 元素必须被正确地嵌套。
 2） XHTML 元素必须被关闭。
 3） 标签名必须用小写字母。
 4） XHTML 文档必须拥有根元素。

 

### 94. .请你谈谈对于CSS的布局有什么样的理解？

解答：

常见的布局方式：固定布局、流式布局、弹性布局、浮动布局、定位布局、margin和padding。

 

### 95. CSS3有哪些新特性？

解答:

1）CSS3实现圆角（border-radius），阴影（box-shadow），对文字加特效（text-shadow），线性渐变（gradient），变形（transform）。

2）增加了更多的CSS选择器 多背景 rgba，在CSS3中唯一引入的伪元素是::selection，媒体查询，多栏布局。

 

 

### 96. 为什么要初始化CSS样式？

解答:

因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。

 

### 97. 经常遇到的浏览器兼容性有哪些？如何解决？

解答:

(1） 浏览器默认的margin和padding不同。

(2） IE6双边距bug。

(3）在ie6，ie7中元素高度超出自己设置高度。原因是IE8以前的浏览器中会给元素设置默认的行高的高度导致的。

(4）min-height在IE6下不起作用。

(5）透明性IE用filter:Alpha(Opacity=60)，而其他主流浏览器用 opacity:0.6。

(6）input边框问题，去掉input边框一般用border:none;就可以，但由于IE6在解析input样式时的BUG(优先级问题)，在IE6下无效。

 

 

### 98. 怪异盒模型box-sizing？弹性盒模型|盒布局?

解答:

在标准模式下的盒模型：盒子总宽度/高度=width/height+padding+border+margin
 在怪异模式下的盒模型下，盒子的总宽度和高度是包含内边距padding和边框border宽度在内的，盒子总宽度/高度=width/height + margin = 内容区宽度/高度 + padding + border + margin;
 box-sizing有两个值一个是content-box，另一个是border-box。
 当设置为box-sizing:content-box时，将采用标准模式解析计算；
 当设置为box-sizing:border-box时，将采用怪异模式解析计算。

### 99. 如何让一个div 上下左右居中?

解答:

```
方法1： .div1{ width:400px;  height:400px;  border:#CCC 1px solid;   background:#99f;  position:absolute;  left:50%;   top:50%;   transform: translate(-50%,-50%); }   <div class="div1"></div> 
```

```
方法2： .div2{ width:400px;  height:400px;  border:#CCC 1px solid;  background:#99f;  position: absolute;  left:0;  top: 0;  bottom: 0;  right: 0;  margin: auto; }  <div class="div2"></div> 
```

```
方法3： .div3{ width:400px;  height:400px;  border:#CCC 1px solid;  background:#9f9;  position: absolute;  left: 50%;  top:50%;  margin-left:-200px;  margin-top: -200px;  }   <div class="div3"></div>
```

### 100.   简述前端优化的方式 旧的雅虎34条|h5新添加的方式?

解答:

1、尽量减少HTTP请求次数
 2、减少DNS查找次数
 3、避免跳转
 4、可缓存的AJAX
 5、推迟加载内容
 6、预加载
 7、减少DOM元素数量
 8、根据域名划分页面内容
 9、使iframe的数量最小
 10、不要出现404错误
 11、使用内容分发网络
 12、为文件头指定Expires或Cache-Control 13、Gzip压缩文件内容
 14、配置ETag
 15、尽早刷新输出缓冲
 16、使用GET来完成AJAX请求
 17、把样式表置于顶部
 18、避免使用CSS表达式（Expression）
 19、使用外部JavaScript和CSS
 20、削减JavaScript和CSS
 21、用<link>代替@import
 22、避免使用滤镜
 23、把脚本置于页面底部
 24、剔除重复脚本

 

### 101.   css清除浮动的几种方式？

解答:

1、父级div定义 height
 2、结尾处加空div标签 clear:bothdd
 3、父级div定义 伪类:after 和 zoom
 4、父级div定义 overflow:hidden
 5、父级div定义 overflow:auto
 6、父级div 也一起浮动
 7、父级div定义 display:table

 

### 102.   介绍一下你对浏览器内核的理解？

解答:

 主要分成两部分：

渲染引擎(layout engineer或Rendering Engine)和JS引擎。

渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。

JS引擎则：解析和执行javascript来实现网页的动态效果。

 

 

 

最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。

 

 

### 103.   XHTML与HTML的有何异同？

解答:

HTML是一种基于WEB的网络设计语言，XHTML是基于XML的置标语言，XHTML可以认为是XML版的HTML，所以它的语法比较严谨：元素必须关闭，嵌套必须正确，大小写区分，属性值必须用双引号，id属性代替name属性.

 

### 104.   列举IE 与其他浏览器不一样的特性？

解答:

IE支持currentStyle，FIrefox使用getComputStyle

IE 使用innerText，Firefox使用textContent

滤镜方面：IE:filter:alpha(opacity= num)；Firefox：-moz-opacity:num

事件方面：IE：attachEvent：火狐是addEventListener

鼠标位置：IE是event.clientX；火狐是event.pageX

IE使用event.srcElement；Firefox使用event.target

IE中消除list的原点仅需margin:0即可达到最终效果；FIrefox需要设置margin:0;padding:0以及list-style:none

CSS圆角：ie7以下不支持圆角

 

### 105.   写出5 种以上ie6 bug 的解决方法，哪些你认为是解决起来最麻烦的？

解答:

float情况下有双边距的bug，使用display: inline解决

宽高为奇数时有bug，使用偶数

min-height设置不了，加!important

z-index问题，给父亲设置position：relative

设置高度小与10px左右的时候，实际高度高于设置高度，因为有默认行高，把行高也设置

 

### 106.   什么是Web workers？为什么我们需要他?

解答:

一个运行在后台的JavaScript，有助于异步执行JavaScript，提高页面性能

 

 

### 107.   对WEB标准以及W3C的理解与认识?

解答:

标签闭合、标签小写、不乱嵌套、提高搜索机器人搜索几率、使用外链css和 js 脚本、结构行为表现的分离，

 

 

 