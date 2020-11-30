---

---

### CSS的使用

⑴ 内联样式
	 *在标签内使用style属性指定css代码
	 *如：<div style="color:red;">hello css</div>
⑵ 内部样式
	*在head标签内，定义style标签，style标签的标签体内容就是css代码
	*如：

```html
<style>
	div{
		color:blue;
	}
</style>
<div>hello css</div>
```


​	   

⑶ 外部样式
	① 定义css资源文件。
	② 在head标签内，定义link标签，引入外部的资源文件
	*如：
 		*a.css文件：
			div{
		    color:green;
			}
		<link rel="stylesheet" href="css/a.css">
		<div>hello css</div>
		<div>hello css</div>

*注意：
	 *1,2,3种方式 css作用范围越来越大
     *1方式不常用，后期常用2,3
	 *3种格式可以写为：
	    <style>
	        @import "css/a.css";
	</style>

###  CSS语法

*格式：
	选择器 {
		属性名1:属性值1;
		属性名2:属性值2;
		...
	}
*选择器:筛选具有相似特征的元素
*注意：
	*每一对属性需要使用；隔开，最后一对属性可以不加；

### 选择器

筛选具有相似特征的元素
	*分类：
		⑴ 基础选择器
			① id选择器：选择具体的id属性值的元素.建议在一个html页面中id值唯一
		        *语法：#id属性值{}
		    ② 元素选择器：选择具有相同标签名称的元素
		        *语法： 标签名称{}
		        *注意：id选择器优先级高于元素选择器
		    ③ 类选择器：选择具有相同的class属性值的元素。
		        *语法：.class属性值{}
		        *注意：类选择器选择器优先级高于元素选择器,一个标签可以拥有多个class属性值，但只能有一个id并且是唯一的。类选择器在修改样式中用得最多，id选择器一般用于页面唯一性的元素上，经常和JavaScript搭配使用

```java
<style>
        /*id选择器*/
        #div1{
            color:red;
        }
        /*元素选择器*/
        div{
            color: rebeccapurple;
        }
        /*类选择器*/
        .cls1{
            color: coral;
        }
</style>
<body>
    <div id="div1">111111111</div>
    <div >111111111</div>
    <p class="cls1">11111111111</p>
</body>
```



​		⑵ 扩展选择器：
​			① 选择所有元素：
​				*语法： *{}
​			② 并集选择器：
​				*选择器1,选择器2{}
​			③ 子选择器：筛选选择器1元素下的选择器2元素(选择器2可以是选择器1的儿子或者是孙子)
​			    *语法：  选择器1 选择器2{}
​			④ 父选择器：筛选选择器2的父元素选择器1（只能是最近一级的子元素）
​		   	  *语法：  选择器1 > 选择器2{}
​			⑤ 属性选择器：选择元素名称，属性名=属性值的元素
​				 *语法：  元素名称[属性名="属性值"]{}
​					input[type='text']{}
​			⑥ 伪类选择器：选择一些元素具有的状态
​					*语法： 元素:状态{}
​						*如： <a>
​								*状态：
​											*link：初始化的状态
​											*visited：被访问过的状态
​											*active：正在访问状态
​											*hover：鼠标悬浮状态
​                    a:link{color:pink};   选择所有未被访问过的连接
​                    a:hover{color:green;};   选择鼠标指针位于其上的链接
​                    a:visited   选择所有已被访问的链接
​                    a:active  选择活动链接（鼠标按下未弹起的链接）
​                    声明顺序：link visited  hover   active
​			⑦focus伪类选择器
​				选取获得光标的input表单
​				input:focus{}

```html
子选择器
ol li{
}


```



###  属性

⑴. 字体、文本
		① font-size：字体大小。标题标签比较特殊，需要单独指定大小。
		② font-family：字体系列，微软雅黑
		③ font-weight：字体粗细。400默认值，700加粗
		④ line-height：行间距，包括上间距、文本高度、下间距
		⑤ font-style：字体样式。**normal :** 正常的字体 **italic :** 斜体。
		⑥ 复合属性：font-style  font-weight  font-size/line-height  font-family(必须有font-size和font-family属性，否则font不起作用)
		⑦ color：文本颜色
		⑧ text-align：文本对齐方式center、right、left
		⑨ text-decoration:默认none、下划线underline、上划线overline、删除线line-through
		⑩ text-indent:文本缩进 单位1em表示当前元素一个文字的大小

⑵. 背景
	   ① background-color :transparent（透明度） | *color*  
	   ② background-image :none（无背景图） | url  (url)（使用绝对或者相对地址指定背景图像）
	   ③ background-repeat : repeat | no-repeat | repeat-x | repeat-y 
	          repeat : 　背景图像在纵向和横向上平铺（默认的）
	          no-repeat : 　背景图像不平铺
	          repeat-x : 　背景图像在横向上平铺
	          repeat-y : 　背景图像在纵向平铺 
	   ④ background-positon:
	          方位名词：top / center / bottom | left / center / right (顺序可颠倒，省略默认为center)background-positon:top center
	          精确单位：x y（顺序不能交换 x表示左边距，y表示上边距）background-positon:50px 20px
	          混合单位：x y（顺序不能变）background-positon:50px center
	   ⑤ background-attachment : 
	          scroll : 　背景图像是随对象内容滚动，默认
	          fixed : 　背景图像固定 
	   ⑥ background : 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置（没有特定的顺序一般习惯为）
	          background: black url(bg.jpg) no-repeat fixed center top;
	   ⑦ background : rgba(0,0,0,0.3)背景颜色半透明，第四个参数代表透明度，0是完全透明，1是不透明，可在0~1之间取值。前三个数值就是rgb取色。





⑶. 边框
		border：设置边框，符合属性
		border:1px solid red;
⑷. 尺寸
		①width：宽度
		②height：高度
⑸. 盒子模型：控制布局
		①margin：外边距
		②padding：内边距
			*默认情况下内边距会影响整个盒子的大小
			*box-sizing: border-box;  设置盒子的属性，让width和height就是最终盒子的大小

​        ③float：浮动
  	       *left
  	       *right

(6)去掉无序列表前面的项目小圆点
		list-style:none;

### CSS元素显示的方式

#### 块元素

常见的块元素有<h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>等，其中 <div> 标签是最典型的块元素。

块级元素的特点： 
① 比较霸道，自己独占一行。 
② 高度，宽度、外边距以及内边距都可以控制。
③ 宽度默认是容器（父级宽度）的100%。 
④ 是一个容器及盒子，里面可以放行内或者块级元素。

**注意：** 
①文字类的元素内不能使用块级元素
② &lt;p&gt;标签主要用于存放文字，因此  &lt;p&gt;里面不能放块级元素，特别是不能放 &lt;div&gt; 
③ 同理， &lt;h1&gt;~&lt;h6&gt;等都是文字类块级标签，里面也不能放其他块级元素

#### 行元素

常见的行内元素有 <a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>等，其中<span> 标签是最典型的行内元素。有的地方也将行内元素称为内联元素。

行内元素的特点： 
① 相邻行内元素在一行上，一行可以显示多个。
② 高、宽直接设置是无效的。
③ 默认宽度就是它本身内容的宽度。
④ 行内元素只能容纳文本或其他行内元素。

**注意：** 

①  链接里面不能再放链接
②  特殊情况链接 <a> 里面可以放块级元素，但是给 <a> 转换一下块级模式最安全

#### 行内块元素

在行内元素中有几个特殊的标签 —— <img />、<input />、<td>，它们同时具有块元素和行内元素的特点。有些资料称它们为行内块元素。 

行内块元素的特点： 
① 和相邻行内元素（行内块）在一行上，但是他们之间会有空白缝隙。一行可以显示多个（行内元素特点）。
② 默认宽度就是它本身内容的宽度（行内元素特点）。
③ 高度，行高、外边距以及内边距都可以控制（块级元素特点）。

#### 显示模式的转换

转换为块元素：display:block;

转换为行内元素：display:inline;

转换为行内块：display: inline-block;

### snipaste的使用

Snipaste 是一个简单但强大的截图工具，也可以让你将截图贴回到屏幕上. 

常用快捷方式:

1. F1 可以截图. 同时测量大小, 设置箭头 书写文字等

2. F3 在桌面置顶显示

3. 点击图片, alt 可以取色 (按下shift 可以切换取色模式)

4. 按下esc 取消图片显示

### CSS的三大特性

#### 层叠性

相同的选择器设置相同的样式，后来的会覆盖前面的样式。

```html
<style>
       div {
           color: red;
           font-size: 12px;
       }
       div {
           color: pink;
       }
</style>
div>长江后浪推前浪,前浪死在沙滩上</div>
粉色 12px
```

#### 继承性

字标签会继承父标签的某些样式，如文本颜色和色号（text-,font-,line-,color属性）

```html
<div>
    <p>
    </p>
</div>
给div设置属性，p标签会继承
```

当行高为n不带单位的时候，是当前font-size的n倍

```html
<style>
        body {
            color: pink;
            /* font: 12px/24px 'Microsoft YaHei'; */
            font: 12px/1.5 'Microsoft YaHei';
        }
        div {
            /* 子元素继承了父元素 body 的行高 1.5 */
            /* 这个1.5 就是当前元素文字大小 font-size 的1.5倍   所以当前div 的行高就是21像素 */
            font-size: 14px; 
        }
        p {
            /* 1.5 * 16 =  24 当前的行高 */
            font-size: 16px;
        }
        /* li 么有手动指定文字大小  则会继承父亲的 文字大小  body 12px 所以 li 的文字大小为 12px 
        
        当前li 的行高就是  12 * 1.5  =  18
        */
    </style>
<body>
    <div>粉红色的回忆</div>
    <p>粉红色的回忆</p>
    <ul>
        <li>我没有指定文字大小</li>
    </ul>
</body>
```

#### 优先级

当同一个元素指定多个选择器，根据优先级权重执行

!important (color: pink!important;) > 行内样式 style="" > id选择器 > 类选择器，伪类选择器 > 元素选择器 > 继承或者*

继承的权重为0，如果该元素没有直接选中，不管父元素的权重多高，子元素得到的权重都为0

复合选择器有权重叠加的问题

范围越小权重越大

### 盒子模型

border 边框
content 内容
padding 内边距
margin 外边距

#### 边框

① border : border-width || border-style || border-color （没有顺序）
② border-width：边框粗细，单位是px
③ border-style
		solid实线边框|dashed虚线边框|dotted点线边框
④ border-color：边框颜色 transparent透明的
⑤ border-top|border-bottom|border-left|border-right| none
⑥ border-collapse:collapse 合并相邻的表格边框
⑦ 圆角边框 border-radius：10px；数值越大圆角越大。
			参数值可以为数值或百分比的形式
			如果是正方形，想要设置为一个圆，把数值修改为高度或者宽度的一半即可，或者直接写为 50%
			该属性是一个简写属性，可以跟四个值，分别代表左上角、右上角、右下角、左下角 
			分开写：border-top-left-radius、border-top-right-radius、border-bottom-right-radius 和border-bottom-left-radius
			兼容性 ie9+ 浏览器支持, 但是不会影响页面布局,可以放心使用

边框会影响盒子的实际大小



#### 内边距

盒子边框与内容之间的距离

如果盒子已经有了宽度和高度，此时再指定内边框，会撑大盒子。如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小。

① padding-left|padding-right|padding-top|padding-bottom
② padding:5px;  1个值，表示上下左右都有5像素内边距
③ padding:5px 10px;   2个值，代表上下内边距是5像素，左右内边距是10像素
④ padding:5px 10px 20px;  3个值，代表上内边距5像素 左右内边距10像素 下内边距20像素
⑤ padding:5px 10px 20px 30px; 4个值，上是5像素，右是像素，下20像素，左30像素，顺时针

#### 外边距

控制盒子和盒子之间的距离

① margin-left|margin-right|margin-top|margin-bottom

几个参数和padding一样

外边距可以让块级盒子**水平居中**，但是必须满足两个条件：
① 盒子必须指定了宽度（width）。
② 盒子左右的外边距都设置为 auto 。 

```html
.header{ width:960px; margin:0 auto;}
margin-left: auto; margin-right: auto;
margin: auto;
margin: 0 auto;
```

**注意：**以上方法是让块级元素水平居中，行内元素或者行内块元素水平居中给其父元素添加 text-align:center 即可

**相邻块元素垂直外边距的合并**

当上下相邻的两个块元素（兄弟关系）相遇时，如果上面的元素有下外边距 margin-bottom，下面的元素有上外边距 margin-top ，则他们之间的垂直间距不是 margin-bottom 与 margin-top 之和。取两个值中的较大者这种现象被称为**相邻块元素垂直外边距的合并**。

![](img\相邻块元素垂直外边距的合并.png)

**解决方案：**
尽量只给一个盒子添加 margin 值。

**外边距合并**

对于两个嵌套关系（父子关系）的块元素，父元素有上外边距同时子元素也有上外边距，此时父元素会塌陷较大的外边距值。

![](img/嵌套块元素垂直外边距的塌陷.png)

**解决方案：**

① 可以为父元素定义上边框。 
② 可以为父元素定义上内边距。 
③ 可以为父元素添加 overflow:hidden。
还有其他方法，比如浮动、固定，绝对定位的盒子不会有塌陷问题，后面咱们再总结。

#### 清除内外边距

网页元素很多都带有默认的内外边距，而且不同的浏览器默认的也不一致。因此我们在布局前，首先要清除下网页元素的内外边距。

```html
*{
	padding: 0;
	margin: 0;
}
```

**注意：**行内元素为了照顾兼容性，尽量只设置左右内外边距，不要设置上下内外边距。但是转换为块级和行内块元素就可以了





#### 盒子阴影

box-shadow: **h-shadow v-shadow** blur spread color inset;
		h-shadow：必需，水平阴影的位置。允许负值。正值往右移，负值往左移动。
		v-shadow：必需，垂直阴影的位置。允许负值。正值往下移动，复制往上移动
		blur:可选，模糊距离。影子虚实的程度。
		spread:可选，阴影的尺寸
		color：可选，阴影的颜色。rgba(0,0,0,0.3)透明度
		inset：可选。将外部阴影改为内部阴影

注意：
1.默认的是外阴影(outset), 但是不可以写这个单词,否则造成阴影无效
2.盒子阴影不占用空间，不会影响其他盒子排列



#### 文字阴影

text-shadow: **h-shadow v-shadow** blur color;
		h-shadow：必需，水平阴影的位置。允许负值。
		v-shadow：必需，垂直阴影的位置。允许负值。
		blur:可选，模糊距离
		color：可选，阴影的颜色

### 显示与隐藏

#### **display 属性**

display 属性用于设置一个元素应如何显示。

1. display: none ；隐藏对象

2. display：block ；除了转换为块级元素之外，同时还有显示元素的意思

display 隐藏元素后，不再占有原来的位置

#### **visibility** 可见性

visibility 属性用于指定一个元素应可见还是隐藏。

1. visibility：visible ; 元素可视

2. visibility：hidden; 元素隐藏

visibility 隐藏元素后，继续占有原来的位置。

如果隐藏元素想要原来位置， 就用 visibility：hidden

如果隐藏元素不想要原来位置， 就用 display：none (用处更多 重点）

#### overflow 溢出

| 属性值  | 描述                                     |
| ------- | ---------------------------------------- |
| visible | 不剪切内容也不添加滚动条                 |
| hidden  | 不显示超过对象尺寸的内容，超出部分隐藏掉 |
| scroll  | 不管超出内容与否，总是显示滚动条         |
| auto    | 超出自动显示滚动条，不超出不显示滚动条   |

一般情况下，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。

但是如果有定位的盒子， 请慎用overflow:hidden 因为它会隐藏多余的部分。



### 浮动

浮动最典型的应用：可以让多个块元素一行内排序显示。
网页布局第一原则：多个块级元素纵向排序找标准流，多个块级元素横向排序找浮动

float 属性用于创建浮动框，将其移动到一边，直到左边缘或右边缘触及包含块或另一个浮动框的边缘。

float：none 元素不浮动|left 元素向左浮动|right 元素向右浮动



 #### 浮动特性（重难点）

1.浮动元素会脱离标准普通流的控制（浮） 移动到指定位置（动）, （俗称脱标）
2.如果多个盒子都设置了浮动，则它们会按照属性值一行内显示并且顶端对齐排列。
3.浮动的元素会具有行内块元素的特性

**注意：** 浮动的元素是互相贴靠在一起的（不会有缝隙），如果父级宽度装不下这些浮动的盒子， 多出的盒子会另起一行对齐

3任何元素都可以浮动。不管原先是什么模式的元素，添加浮动之后具有**行内块元素**相似的特性。
3如果块级盒子没有设置宽度，默认宽度和父级一样宽，但是添加浮动后，它的大小根据内容来决定
3浮动的盒子中间是没有缝隙的，是紧挨着一起的 



**浮动元素经常和标准流父级搭配使用**

为了约束浮动元素位置, 我们网页布局一般采取的策略是: 先用标准流的父元素排列上下位置, 之后内部子元素采取浮动排列左右位置. 符合网页布局第一准侧.

浮动的盒子只会影响后面的标准流不会影响前面的



#### 清除浮动

新闻什么的：让子盒子撑开父亲。当子元素都为浮动元素时，不占用高度，父元素高度就为0，对后续布局会产生影响

```html
选择器{
	clear:属性值;
}
```



| 属性值 | 描述                                           |
| ------ | ---------------------------------------------- |
| left   | 不允许左侧有浮动元素（清除左侧浮动元素的影响） |
| right  | 不允许右侧有浮动元素（清除右侧浮动元素的影响） |
| both   | 同时清除左右两侧浮动的影响                     |

实际工作中几乎只用clear:both;
清除浮动的策略是: 闭合浮动.

##### 清除浮动的方法

1. 额外标签法也称为隔墙法，是 W3C 推荐的做法。 (不推荐)

   ```html
   	<style>
           .box {
               width: 800px;
               border: 1px solid blue;
               margin: 0 auto;
           }
   
           .damao {
               float: left;
               width: 300px;
               height: 200px;
               background-color: purple;
           }
   
           .ermao {
               float: left;
               width: 200px;
               height: 200px;
               background-color: pink;
           }
   
           .footer {
               height: 200px;
               background-color: black;
           }
   
           .clear {
               clear: both;
           }
       </style>
   
   	<div class="box">
           <div class="damao">大毛</div>
           <div class="ermao">二毛</div>
           <div class="clear"></div>
       </div>
       <div class="footer"></div>
   ```

   

2. 父级添加 overflow 属性 
   可以给父级添加 overflow 属性，将其属性值设置为 hidden、 auto 或 scroll 。

   缺点：无法显示溢出的部分

   ```html
   	<style>
           .box {
               overflow: hidden;
               width: 800px;
               border: 1px solid blue;
               margin: 0 auto;
           }
   
           .damao {
               float: left;
               width: 300px;
               height: 200px;
               background-color: purple;
           }
   
           .ermao {
               float: left;
               width: 200px;
               height: 200px;
               background-color: pink;
           }
   
           .footer {
               height: 200px;
               background-color: black;
           }
       </style>
   
   	<div class="box">
           <div class="damao">大毛</div>
           <div class="ermao">二毛</div>
       </div>
       <div class="footer"></div>
   ```

   

3. 父级添加after伪元素 
   :after 方式是额外标签法的升级版。也是给父元素添加 

   ```html
   .clearfix:after { 
   	content: ""; 
   	display: block; 
   	height: 0; 
   	clear: both; 
   	visibility: hidden; 
   } 
   .clearfix { /* IE6、7 专有 */
   	*zoom: 1;
   }
   ```

   ```html
   <style>
           .clearfix:after {
               content: "";
               display: block;
               height: 0;
               clear: both;
               visibility: hidden;
           }
   
           .clearfix {
               /* IE6、7 专有 */
               *zoom: 1;
           }
   
           .box {
               width: 800px;
               border: 1px solid blue;
               margin: 0 auto;
           }
   
           .damao {
               float: left;
               width: 300px;
               height: 200px;
               background-color: purple;
           }
   
           .ermao {
               float: left;
               width: 200px;
               height: 200px;
               background-color: pink;
           }
   
           .footer {
               height: 200px;
               background-color: black;
           }
       </style>
   
   	<div class="box clearfix">
           <div class="damao">大毛</div>
           <div class="ermao">二毛</div>
       </div>
       <div class="footer"></div>
   ```

   

   

4. 父级添加双伪元素
   也是给给父元素添加

   ```html
   .clearfix:before,.clearfix:after {
   	content:"";
   	display:table;
   }
   .clearfix:after {
   	clear:both;
   }
   .clearfix {
   	*zoom:1;
   }
   ```

   ```html
   <style>
           .clearfix:before,
           .clearfix:after {
               content: "";
               display: table;
           }
   
           .clearfix:after {
               clear: both;
           }
   
           .clearfix {
               *zoom: 1;
           }
   
           .box {
               width: 800px;
               border: 1px solid blue;
               margin: 0 auto;
           }
   
           .damao {
               float: left;
               width: 300px;
               height: 200px;
               background-color: purple;
           }
   
           .ermao {
               float: left;
               width: 200px;
               height: 200px;
               background-color: pink;
           }
   
           .footer {
               height: 200px;
               background-color: black;
           }
       </style>
   
   <body>
       <div class="box clearfix">
           <div class="damao">大毛</div>
           <div class="ermao">二毛</div>
       </div>
       <div class="footer"></div>
   </body>
   ```

   

### 定位

**定位**：将盒子定在某一个位置，所以**定位也是在摆放盒子， 按照定位的方式移动盒子。**

定位 = 定位模式 + 边偏移 。

定位模式用于指定一个元素在文档中的定位方式。边偏移则决定了该元素的最终位置。

#### 定位模式

定位模式决定元素的定位方式 ，它通过 CSS 的 position 属性来设置，其值可以分为四个：

| 值       | 语义     |
| -------- | -------- |
| static   | 静态定位 |
| relative | 相对定位 |
| absolute | 绝对定位 |
| fixed    | 固定定位 |

##### 静态定位 static（了解）

默认定位方式，无定位的意思。

#####  相对定位 relative（重要）

相对定位是元素在移动位置的时候，是相对于它原来的位置来说的（自恋型）。

相对定位的特点：（务必记住）

1. 它是相对于自己原来的位置来移动的（移动位置的时候参照点是自己原来的位置）。

2. 原来在标准流的位置继续占有，后面的盒子仍然以标准流的方式对待它。

   因此，相对定位并没有脱标。它最典型的应用是给绝对定位当爹的

##### 绝对定位 absolute（重要）

绝对定位是元素在移动位置的时候，是相对于它祖先元素来说的（拼爹型）。

绝对定位的特点：（务必记住）

1. 如果没有祖先元素或者祖先元素没有定位，则以浏览器为准定位（Document 文档）。(父元素没加定位导致子元素乱跑可以给父元素家position：absolute)

2. 如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动位置。

3. 绝对定位不再占有原先的位置。（脱标）

所以绝对定位是脱离标准流的。

##### 固定定位 fixed （重要）

固定定位的特点：（务必记住）

**固定定位**是元素固定于浏览器可视区的位置。主要使用场景： 可以在浏览器页面滚动时元素的位置不会改变

1. 以浏览器的可视窗口为参照点移动元素。 

    跟父元素没有任何关系

    不随滚动条滚动。

2. 固定定位不在占有原先的位置。

固定定位也是脱标的，其实固定定位也可以看做是一种特殊的绝对定位

###### **固定定位小技巧： 固定在版心右侧位置。**

小算法：

1. 让固定定位的盒子 left: 50%. 走到浏览器可视区（也可以看做版心） 的一半位置。

2. 让固定定位的盒子 margin-left: 版心宽度的一半距离。 多走 版心宽度的一半位置

就可以让固定定位的盒子贴着版心右侧对齐了



##### **粘性定位 sticky（了解）**

粘性定位可以被认为是相对定位和固定定位的混合。 Sticky 粘性的

粘性定位的特点：

1. 以浏览器的可视窗口为参照点移动元素（固定定位特点）

2. 粘性定位占有原先的位置（相对定位特点）

3. 必须添加 top 、left、right、bottom 其中一个才有效

   跟页面滚动搭配使用。 兼容性较差，IE 不支持。

#### 边偏移

边偏移就是定位的盒子移动到最终位置。有 top、bottom、left 和 right 4 个属性

| 边偏移属性 | 示例        | 描述                                         |
| ---------- | ----------- | -------------------------------------------- |
| top        | top:80px    | 上侧偏移量，定义元素相对于其父亲上边线的距离 |
| bottom     | bottom:80px | 下侧偏移量，定义元素相对于其父亲下边线的距离 |
| left       | left:80px   | 左侧偏移量，定义元素相对于其父亲左边线的距离 |
| right      | right:80px  | 右侧偏移量，定义元素相对于其父亲右边线的距离 |



#### 子绝父相

子级是绝对定位的话，父级要用相对定位。 

① 子级绝对定位，不会占有位置，可以放到父盒子里面的任何一个地方，不会影响其他的兄弟盒子。 

② 父盒子需要加定位限制子盒子在父盒子内显示。

③ 父盒子布局时，需要占有位置，因此父亲只能是相对定位。 



#### **定位叠放次序 z-index**

```css
选择器 { z-index: 1; }
```

1. 数值可以是正整数、负整数或 0, 默认是 auto，数值越大，盒子越靠上

2. 如果属性值相同，则按照书写顺序，后来居上

3.  数字后面不能加单位

4. 只有定位的盒子才有 z-index 属性





#### 定位的拓展

##### 绝对定位的盒子居中

加了绝对定位的盒子不能通过 margin:0 auto 水平居中，但是可以通过以下计算方法实现水平和垂直居中。

水平居中

① left: 50%;：让盒子的左侧移动到父级元素的水平中心位置。 

② margin-left: -100px;：让盒子向左移动自身宽度的一半。

垂直居中

① top: 50%;：让盒子的左侧移动到父级元素的水平中心位置。 

② margin-top: -100px;：让盒子向左移动自身宽度的一半。

##### 定位特殊特性

绝对定位和固定定位也和浮动类似。

1. 行内元素添加绝对或者固定定位，可以直接设置高度和宽度。

2. 块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容的大小。
3. 脱标的盒子不会触发外边距塌陷
4. 浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字（图片）。但是绝对定位（固定定位） 会压住下面标准流所有的内容。



### **网页布局总结**

通过盒子模型，清楚知道大部分html标签是一个盒子。

通过CSS浮动、定位 可以让每个盒子排列成为网页。

一个完整的网页，是标准流、浮动、定位一起完成布局的，每个都有自己的专门用法。

1. 标准流

可以让盒子上下排列或者左右排列，**垂直的块级盒子显示就用标准流布局**。

2. 浮动

可以让多个块级元素一行显示或者左右对齐盒子，**多个块级盒子水平显示就用浮动布局**。

3. 定位

定位最大的特点是有层叠的概念，就是可以让多个盒子前后叠压来显示。**如果元素自由在某个盒子内移动就用定位布局**。





### PS

#### 基本操作

文件 --> 打开 ：可以打开我们要测量的图片

Ctrl+R：可以打开标尺，或者 视图 -> 标尺

右击标尺，把里面的单位改为像素 

Ctrl+ 加号(+)可以放大视图， Ctrl+ 减号(-)可以缩小视图

按住空格键，鼠标可以变成小手，拖动 PS 视图

用选区拖动 可以测量大小

Ctrl+ D 可以取消选区，或者在旁边空白处点击一下也可以取消选区





#### CSS属性书写顺序

建议遵循以下顺序：

1. 布局定位属性：display / position / float / clear / visibility / overflow（建议 display 第一个写，毕竟关系到模式）

2. 自身属性：width / height / margin / padding / border / background

3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word

4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …



#### 切图

##### 图层切图

最简单的切图方式：右击图层  导出 PNG 切片。

##### 切片切图

##### PS插件切图



