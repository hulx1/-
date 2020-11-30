## 快捷键

!+tab 快速html页面骨架结构

Ctrl+加号键、Ctrl+减号键 放大缩小视图

利用插件在浏览器中预览页面：单击鼠标右键，在弹出窗口中点击“Open In Default Browser”

<!--注释语句--> 快捷键：ctrl+/

## 骨架标签

### 文档类型声明标签

*<!DOCTYPE>*文档类型声明，作用就是告诉浏览器使用哪种HTML版本来显示网页

### lang语言种类

 用来定义当前文档显示的语言

en:英语
zh-CN:中文

### 字符集

在<head>标签内，可以通过<meta>标签的charset属性来规HTML 文档应该使用哪种字符编码

<meta charset="UTF-8" />

### 标签

#### 1. 文件标签

  文件标签：构成html最基本的标签
	*html : html文档的根标签
	*head：头标签。用于指定html文档的一些属性。引入外部的资源
	*title：标题标签。
	*body：体标签
	*<!DOCTYPE html>：html5中定义该文档是html文档
	

#### 2. 文本标签

  文本标签：和文本有关的标签
	*注释：<!-- 注释内容 -->
	*<h1> to <h6>：标题标签
	*h1~h6:字体大小逐渐递减
	*<p>：段落标签
	*<br />：换行标签(单标签)
	*<hr>：展示一条水平线
	

	*属性：
		*color：颜色
		*width：宽度
		*size：高度
		*align：对其方式
				*center：居中
				*left：左对齐
				*right：右对齐
	
	*<strong></strong>：字体加粗
	*<em></em>：字体斜体
	*<del></del>:删除线
	*<ins></ins>:下划线
	*<font>:字体标签
	
	*<center>:文本居中
		*属性：
			*color：颜色
			*size：大小
			*face：字体
			
	*属性定义：
		*color：
			① 英文单词：red,green,blue
			② rgb(值1，值2，值3)：值的范围：0~255  如  rgb(0,0,255)
			③ #值1值2值3：值的范围：00~FF之间。如： #FF00FF
		*width：
			① 数值：width='20' ,数值的单位，默认是 px(像素)
			② 数值%：占比相对于父元素的比例

```java
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <!-- 注释 -->
    <!-- br -->
    百日<br/>
    sskfods
    <!--标题标签-->
    黑马旅游网
    <h1>黑马旅游网</h1>
    <h2>黑马旅游网</h2>
    <h3>黑马旅游网</h3>
    <h4>黑马旅游网</h4>
    <h5>黑马旅游网</h5>
    <!--段落标签-->
    <p>
    黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网
    </p>
    <p>黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网黑马旅游网</p>
    <!--hr 展示一条水平线-->
    <hr color="red" width="10" align="left"/>
    <hr>
    <!--加粗 b-->
    黑马旅游网<br>
    <b>黑马旅游网</b>
    <hr>
    <!--斜体 i-->
    黑马旅游网<br>
    <i>黑马旅游网</i>
    <!--字体标签 font-->
    <font color="#cd5c5c" size="5" face="楷体">黑马旅游网</font>
    <hr>
    <center> <font color="#cd5c5c" size="5" face="楷体">黑马旅游网</font></center>
</body>
</html>
```



#### 3. 图片标签

*img：展示图片
	   *属性：
		        *src：指定图片的位置
		        *alt：替换文本，图像显示不出来的时候用文字替换
		        *title：提示文本。鼠标放到图像上，显示的文字
		        *width
		        *height
		        *border：设置图像的边框粗细

	<!--展示一张图片 img-->
	<img src="image/jingxuan_2.jpg" align="right" alt="古镇" width="500" height="500"/>
	//alt表示入如果图片位置错误将会显示的内容

​	<!--
​	    相对路径
​	        * 以.开头的路径
​	            * ./：代表当前目录  ./image/1.jpg（./可以省略)
​	                * ../:代表上一级目录
​	-->
​	

​	<img src="C:/Users/Administrator/Desktop/笔记/java/image/jiangwai_1.jpg">
​	
​	<img src="C:/Users/Administrator/Desktop/笔记/image/jiangwai_1.jpg">

#### 4. 列表标签

用于布局

##### 有序列表：
​	*ol:
​	 *li:

##### 无序列表：
​	*ul:
​	*li:

```java
<!--有序列表 ol-->
    <ol type="A" start="4">
        <li>黑马教程</li>
        <li>黑马教程</li>
        <li>黑马教程</li>
        <li>黑马教程</li>
    </ol>

    <!--无序列表 ul-->

    <ul type="square">
        <li>黑马教程</li>
        <li>黑马教程</li>
        <li>黑马教程</li>
        <li>黑马教程</li>
    </ul>
```

##### 自定义列表

竖着的表格

```html
<dl>
        <dt>关注我们</dt>
        <dd>新浪微博</dd>
        <dd>官方微信</dd>
        <dd>联系我们</dd>
</dl>
```



#### 5. 链接标签

a:定义一个超链接
	 *属性：
		  *href：指定访问资源的URL(统一资源定位符)
		  *target：指定打开资源的方式
		  		*_ self:默认值，在当前页面打开
		  		*_ blank：在空白页面打开

```java
 <!--超链接 a-->
<a href="http://www.baidu.com">点我</a>
<br>
<a href="http://www.baidu.com" target="_blank">打开新窗口</a>
<br>
<a href="http://www.baidu.com"target="_self">点我</a>
<br>
<a href="#">空链接</a>
<br>
<a href="img.zip">下载链接</a>
<br>
<a href="./1_HelloWorld.html">列表标签</a>
<br>
<a href="mailto:473373584@qq.com">联系我们</a>
<br>
给图片添加超链接
<a href="http://www.baidu.com"target="_self"><img src="111.png"></a>
```

阻止链接跳转href="javascript:void(0);"或者 href="javascript:;"



##### 锚点链接

点击链接，可以快速定位到页面中的某个位置

```html
<h3 id="two">第二集介绍</h3>
<a href="#two">第二集</a>
```





#### 6. div和span

* div:用来布局，但是现在一行只能放一个<div>。大盒子
* span：用来布局，一行可以多个<span>。小盒子

#### 7. 语义化标签

语义化标签：html5中为了提高程序的可读性，提供了一些标签。
	⑴ <header>：页眉
	⑵ <footer>：页脚

####　8. 表格标签

⑴table：定义表格
		 	 *width：宽度
		 	 *border：边框
		 	 *cellpadding：定义内容和单元格的距离
		 	 *cellspacing：定义单元格之间的距离。如果指定为0，则单元格的线会合为一条、
		 	 *bgcolor：背景色
		 	 *align：对齐方式
⑵tr：定义行
		  	*bgcolor：背景色
		  	*align：对齐方式（left、center、right)
⑶td：定义单元格
		  	*colspan：合并列
		 	 *rowspan：合并行
⑷th：定义表头单元格
⑸<caption>：表格标题
⑹<thead>：表示表格的头部分
⑺<tbody>：表示表格的体部分
⑻<tfoot>：表示表格的脚部分

```html
<table border="1" width="50%" cellpadding="0" cellspacing="0" bgcolor="#d3d3d3" align="center">
<caption>学生成绩表</caption>
<thead>
    <tr bgcolor="#faebd7">
        <th rowspan="2">编号</th>
        <th>姓名</th>
        <th>成绩</th>
    </tr>
</thead>
<tbody>
    <tr align="center">
        <td>李四</td>
        <td>100</td>
    </tr>
    <tr>
		<td>张三</td>
       	<td colspan="2">90</td>
    </tr>
</tbody>
</table>
```

##### 表格结构标签

使用场景:因为表格可能很长,为了更好的表示表格的语义，可以将表格分割成 表格头部和表格主体两大部分.

在表格标签中，分别用：<thead>标签 表格的头部区域、<tbody>标签 表格的主体区域. 这样可以更好的分清表格结构。

##### 合并单元格

**合并单元格方式：**
跨行合并：rowspan="合并单元格的个数"   最上侧单元格为目标单元格, 写合并代码
跨列合并：colspan="合并单元格的个数"     最左侧单元格为目标单元格, 写合并代码

```html
<table width="500" height="249" border="1" cellspacing="0">
        <tr>
            <td></td>
            <td colspan="2"></td>
            
        </tr>
        <tr>
            <td rowspan="2"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
        </tr>
</table>
```



#### 9.表单标签

概念：用于采集用户输入的数据的。用于和服务器进行交互。
form：用于定义表单的。可以定义一个范围，范围代表采集用户数据的范围
*属性：
            *action：指定提交数据的URL
            *method:指定提交方式
                *分类：一共7种，2种比较常用
                   *get：
                        ①. 请求参数会在地址栏中显示。会封装到请求行中(HTTP协议后讲解)。
                        ②. 请求参数大小是有限制的。
                        ③. 不太安全。
                   *post：
                        ①. 请求参数不会再地址栏中显示。会封装在请求体中(HTTP协议后讲解)
                        ②. 请求参数的大小没有限制。
                        ③. 较为安全。

​        *表单项中的数据要想被提交：必须指定其name属性

```java
<form action="#" method="get">
    用户名：<input name="username"><br>
    密  码：<input name="password"><br>
    <input type="submit" value="登录">
</form>
```



##### 表单项标签

⑴input：可以通过type属性值，改变元素展示的样式
			*type属性：
					①text：文本输入框，默认值
						*placeholder：指定输入框的提示信息，当输入框的内容发生变化，会自动清空提示信息	

​					②password：密码输入框

​					③radio:单选框
​				   	注意：
​							❶ 要想让多个单选框实现单选的效果，则多个单选框的name属性值必须一样。
​							❷ 一般会给每一个单选框提供value属性，指定其被选中后提交的值
​							❸ checked属性，可以指定默认值
​					④ checkbox：复选框
​						*注意：
​							❶ 一般会给每一个单选框提供value属性，指定其被选中后提交的值
​							❷ checked属性，可以指定默认值

​					⑤ file：文件选择框

​					⑥ hidden：隐藏域，用于提交一些信息。

​					⑦ 按钮：
​							❶ submit：提交按钮。可以提交表单
​							❷ button：普通按钮
​							❸ image：图片提交按钮
​									*src属性指定图片的路径
​							❹ reset：重置按钮

​					⑧label：指定输入项的文字描述信息
​							注意：label的for属性一般会和 input 的 id属性值 对应。如果对应了，则点击label区域，会让input输入框获取焦点。

⑵select: 下拉列表
				*子元素：option，指定列表项
				默认选中 selected="selected"

⑶textarea：文本域
				cols：指定列数，每一行有多少个字符
				rows：默认多少行。

```java
<form action="#" method="get">
    <label for="username">用户名：</label><input name="username" placeholder="请输入用户名" id="username"><br>
    密  码：<input name="password" type="password" placeholder="请输入密码"><br>
    性  别：<input name="gender" type="radio" value="female" checked="checked">女
           <input name="gender" type="radio" value="male">男
    <br>
    爱  好：<input name="hobby" type="checkbox" value="shopping" checked="checked">逛街
           <input name="hobby" type="checkbox" value="java">游戏
           <input name="hobby" type="checkbox" value="game">阅读 <br/>

    图  片：<input type="file" name="file"><br/>

    生日：<input type="date" name="birthday"><br>
    生日：<input type="datetime-local" name="birthday"><br><br>
    年龄：<input type="number" name="age"><br>
    邮箱：<input type="email" name="email"><br>
    取色器：<input type="color" name="color" ><br>

    隐藏域：<input type="hidden" name="id" value="aaa"><br/>
    <input type="image" src="img/regbtn.jpg" value="图片按钮">
    <input type="submit" value="登录">

    <br><br>
    <select name="province">
        <option value="">--请选择--</option>
        <option value="1">--北京--</option>
        <option value="2" selected>--上海--</option>
    </select>
    <br><br><br>

    自我描述：<textarea name="des" cols="50" rows="20"></textarea>
</form>
```





### 文档

W3C : http://www.w3school.com.cn/ 

MDN: https://developer.mozilla.org/zh-CN/





