##  HTML

### 快速入门

语法：
1. html文档后缀名 .html 或者 .htm
2. 标签分为
	①围堵标签：有开始标签和结束标签。如 <html> </html>
	②自闭和标签：开始标签和结束标签在一起。如 <br/>

	③标签可以嵌套：
		需要正确嵌套，不能你中有我，我中有你
		错误：<a><b></a></b>
		正确：<a><b></b></a>
	
	④在开始标签中可以定义属性。属性是由键值对构成，值需要用引号(单双都可)引起来
	⑤ html的标签不区分大小写，但是建议使用小写。





### 标签学习

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
	*<br>：换行标签
	*<hr>：展示一条水平线
	

	*属性：
		*color：颜色
		*width：宽度
		*size：高度
		*align：对其方式
				*center：居中
				*left：左对齐
				*right：右对齐
	
	*<b>：字体加粗
	*<i>：字体斜体
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

	<!--展示一张图片 img-->
	<img src="image/jingxuan_2.jpg" align="right" alt="古镇" width="500" height="500"/>
	//alt表示入如果图片位置错误将会显示的内容


​	
​	<!--
​	    相对路径
​	        * 以.开头的路径
​	            * ./：代表当前目录  ./image/1.jpg（./可以省略)
​	                * ../:代表上一级目录
​	-->
​	
​	<img src="./image/jiangwai_1.jpg">
​	
​	<img src="../image/jiangwai_1.jpg">
#### 4. 列表标签
⑴有序列表：
	*ol:
	 *li:
⑵无序列表：
	*ul:
	*li:

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
<a href="./1_HelloWorld.html">列表标签</a>
<br>
<a href="mailto:473373584@qq.com">联系我们</a>
<br>
<a href="http://www.baidu.com"target="_self"><img src="111.png"></a>
```



#### 6. div和span
* div:每一个div占满一整行。块级标签
* span：文本信息在一行展示，行内标签 内联标签

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
		  	*align：对齐方式
⑶td：定义单元格
		  	*colspan：合并列
		 	 *rowspan：合并行
⑷th：定义表头单元格
⑸<caption>：表格标题
⑹<thead>：表示表格的头部分
⑺<tbody>：表示表格的体部分
⑻<tfoot>：表示表格的脚部分

```java
<table border="1" width="50%" cellpadding="0" cellspacing="0" bgcolor="#d3d3d3" align="center">
<caption>学生成绩表</caption>
    <tr bgcolor="#faebd7">
        <th rowspan="2">编号</th>
        <th>姓名</th>
        <th>成绩</th>
    </tr>
    <tr align="center">
        <td>李四</td>
        <td>100</td>
    </tr>
    <tr>
		<td>张三</td>
       	<td colspan="2">90</td>
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

​					⑧label：指定输入项的文字描述信息
​							注意：label的for属性一般会和 input 的 id属性值 对应。如果对应了，则点击label区域，会让input输入框获取焦点。

⑵select: 下拉列表
				*子元素：option，指定列表项

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







## CSS

页面美化和布局控制

#### 1. CSS的使用
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

#### 2. css语法
*格式：
	选择器 {
		属性名1:属性值1;
		属性名2:属性值2;
		...
	}
*选择器:筛选具有相似特征的元素
*注意：
	*每一对属性需要使用；隔开，最后一对属性可以不加；


#### 3. 选择器
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
		        *注意：类选择器选择器优先级高于元素选择器

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
​			③ 子选择器：筛选选择器1元素下的选择器2元素
​			    *语法：  选择器1 选择器2{}
​			④ 父选择器：筛选选择器2的父元素选择器1
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
​                    a:link{color:pink};
​                    a:hover{color:green;};
​       

#### 4. 属性
⑴. 字体、文本
		① font-size：字体大小
		② color：文本颜色
		③ text-align：对齐方式
		④ line-height：行高 
⑵. 背景
	   background：
	  background：url("img/logo.jpg") no-repeat;//不重复
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







## JavaScript

JavaScript = ECMAScript + JavaScript自己特有的东西(BOM+DOM)

### ECMAScript

##### 1. 基本语法：
###### ⑴. 与html结合方式
①. 内部JS：
	*定义<script>，标签体内容就是js代码
②. 外部JS：
	*定义<script>，通过src属性引入外部的js文件
	*注意：
		①. <script>可以定义在html页面的任何地方。但是定义的位置会影响执行顺序。
		②. <script>可以定义多个。
	```html
	<!--内部js-->
	<script>
	    alert("Hello World");
	</script>
<!--外部js-->
	<script src="js/a.js"></script>
	```
###### ⑵. 注释
①. 单行注释：//注释内容
②. 多行注释：/*注释内容*/
	
###### ⑶. 数据类型
①原始数据类型(基本数据类型)：
		❶number：数字。 整数/小数/NaN(not a number 一个不是数字的数字类型)
		❷string：字符串。 字符串  "abc" "a" 'abc'
		❸ boolean: true和false
		❹null：一个对象为空的占位符
		❺undefined：未定义。如果一个变量没有给初始化值，则会被默认赋值为undefined
②引用数据类型：对象
	
###### ⑷. 变量
*Java语言是强类型语言，而JavaScript是弱类型语言。
		*强类型：在开辟变量存储空间时，定义了空间将来存储的数据的数据类型。只能存储固定类型的数据
		*弱类型：在开辟变量存储空间时，不定义空间将来的存储数据类型，可以存放任意类型的数据。
语法：
	var 变量名 = 初始化值;
typeof运算符：获取变量的类型。
	document.write(typeof(a));
	*注：null运算后得到的是object
	
###### ⑸. 运算符

① 一元运算符：只有一个运算数的运算符
	++，-- ， +(正号)  
	*++ --: 自增(自减)
		*++(--) 在前，先自增(自减)，再运算
		* ++(--) 在后，先运算，再自增(自减)
	*+(-)：正负号
	*注意：在JS中，如果运算数不是运算符所要求的类型，那么js引擎会自动的将运算数进行类型转换
        *其他类型转number：
            *string转number：按照字面值转换。如果字面值不是数字，则转为NaN（不是数字的数字）
            *boolean转number：true转为1，false转为0
② 算数运算符
	+ - * / % ...
③赋值运算符
	= += -+....
④比较运算符
	>      <    >=     <=   ==     = == (全等于)
	*比较方式
    ❶. 类型相同：直接比较
       	*字符串：按照字典顺序比较。按位逐一比较，直到得出大小为止。
    ❷. 类型不同：先进行类型转换，再比较
      	 *===：全等于。在比较之前，先判断类型，如果类型不一样，则直接返回false
⑤逻辑运算符
			&& || !
			*其他类型转boolean：
      		 	❶. number：0或NaN为假，其他为真
      		 	❷. string：除了空字符串("")，其他都是true
    			❸. null&undefined:都是false
    			❹. 对象：所有对象都为true(对象为null的时候)
⑥ 三元运算符
		? : 表达式
		var a = 3;
		var b = 4;

​	var c = a > b ? 1:0;
​	*语法：
​	*表达式? 值1:值2;
​	*判断表达式的值，如果是true则取值1，如果是false则取值2；

###### ⑹. 流程控制语句
跟java一样
①. if...else...
②. switch:
		*在java中，switch语句可以接受的数据类型： byte int shor char,枚举(1.5) ,String(1.7)
		*switch(变量):
			case 值:
		*在JS中,switch语句可以接受任意的原始数据类型
③. while
④. do...while
⑤. for

###### ⑺. JS特殊语法
①. 语句以;结尾，如果一行只有一条语句则 ;可以省略 (不建议)
②. 变量的定义使用var关键字，也可以不使用
        *用： 定义的变量是局部变量
        *不用：定义的变量是全局变量(不建议)

###### 练习：九九乘法表

```java
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        td{
            border:1px solid;
        }

    </style>
    <script>
        document.write("<table align='center' >");
        for (var i = 1; i < 10; i++) {
            document.write("<tr >")
            for (var j=1;j<=i;j++){
                document.write("<td >")
                document.write(i+"x"+j+"="+i*j);
                document.write("</td>")
            }
            document.write("</tr>")
        }
        document.write("</table>")
    </script>

</head>
<body>

</body>
</html>
```









##### 2. 基本对象

###### Function：函数(方法)对象

⑴ 创建：
	① function 方法名称(形式参数列表){
                        方法体
      }
    ②var 方法名 = function(形式参数列表){
                        方法体
    }

```html
<script>
        function f(a,b) {
            alert(a+b);
        }
        var f2=function(a,b){
            alert(a+b);
        }
        alert(f.length);
        f(1,2);
</script>
```



⑵方法：
⑶属性：
    length:代表形参的个数
⑷特点：
	①方法定义是，形参的类型不用写,返回值类型也不写。
	②方法是一个对象，如果定义名称相同的方法，会覆盖
	③在JS中，方法的调用只与方法的名称有关，和参数列表无关
	④在方法声明中有一个隐藏的内置对象（数组），arguments,封装所有的实际参数
⑸调用：
   方法名称(实际参数列表);





######  Array:数组对象

⑴. 创建：
       ①. var arr = new Array(元素列表);
       ②. var arr = new Array(默认长度);
       ③. var arr = [元素列表];
⑵. 方法
        join(参数):将数组中的元素按照指定的分隔符拼接为字符串
        push()	向数组的末尾添加一个或更多元素，并返回新的长度。
⑶. 属性
       length:数组的长度
⑷. 特点：
        ①. JS中，同一个数组可以放多种数据类型。
        ②. JS中，数组长度可变的。



###### Date：日期对象

⑴. 创建：
      var date = new Date();
⑵. 方法：
      toLocaleString()：返回当前date对象对应的时间本地字符串格式
      getTime():获取毫秒值。返回当前如期对象描述的时间到1970年1月1日零点的毫秒值差

###### Math：数学对象
⑴. 创建：
      *特点：Math对象不用创建，直接使用。  Math.方法名();
⑵. 方法：
      random():返回 0 ~ 1 之间的随机数。 含0不含1
      ceil(x)：对数进行上舍入。
      floor(x)：对数进行下舍入。
      round(x)：把数四舍五入为最接近的整数。
⑶. 属性：
       PI

###### 

###### 

###### RegExp：正则表达式对象
⑴. 正则表达式：定义字符串的组成规则。
		①. 单个字符:[]
			如： [a] [ab] [a-zA-Z0-9_]
			*特殊符号代表特殊含义的单个字符:
				\d:单个数字字符 [0-9]
				\w:单个单词字符[a-zA-Z0-9_]
		②. 量词符号：
			?：表示出现0次或1次
			*：表示出现0次或多次
			+：出现1次或多次
			{m,n}:表示 m<= 数量 <= n
				*m如果缺省： {,n}:最多n次
				*n如果缺省：{m,} 最少m次
		③. 开始结束符号
			*^:开始
			*$:结束
⑵. 正则对象：
		①. 创建
			❶. var reg = new RegExp("正则表达式");
			❷. var reg = /正则表达式/;
		②. 方法	

					1. test(参数):验证指定的字符串是否符合正则定义的规范	

```java
<script>
        <!--一个斜杠会变成转义字符-->
        var reg=new RegExp("^\\w{6,12}$");
        var reg1=/^\w{6,12}$/;
        var username="zhangsadaasdan";
        var flag = reg1.test(username);
        alert(flag);
</script>
```





###### Global

⑴. 特点：全局对象，这个Global中封装的方法不需要对象就可以直接调用。  方法名();
⑵. 方法：
		encodeURI():url编码
		decodeURI():url解码

​		encodeURIComponent():url编码,编码的字符更多
​		decodeURIComponent():url解码
​	
​		parseInt():将字符串转为数字
​			*逐一判断每一个字符是否是数字，直到不是数字为止，将前边数字部分转为number
​		isNaN():判断一个值是否是NaN
​			 *NaN六亲不认，连自己都不认。NaN参与的==比较全部问false
​	
​		eval():讲 JavaScript 字符串，并把它作为脚本代码来执行。
⑶. URL编码
​        传智播客 =  %E4%BC%A0%E6%99%BA%E6%92%AD%E5%AE%A2





### DOM

功能：控制html文档的内容
获取页面标签(元素)对象：Element
	document.getElementById("id值"):通过元素的id获取元素对象
	
操作Element对象：
	⑴. 修改属性值：
		①. 明确获取的对象是哪一个？
		②. 查看API文档，找其中有哪些属性可以设置
	⑵. 修改标签体内容：
		*属性：innerHTML
		①. 获取元素对象
		②. 使用innerHTML属性修改标签体内容

```java
<img src="img/login_bg.png" id="imag1">
<h1 id="title">AAA</h1>
<script>
		var imag1 = document.getElementById("imag1");
     	alert("我要换图片了。。。");
        imag1.src="img/login_logo.png";

        var title = document.getElementById("title");
        alert("我要换内容了。。。");
        title.innerText("BBB");
</script>
```



#### 事件简单学习

功能： 某些组件被执行了某些操作后，触发某些代码的执行。

 如何绑定事件
 1. 直接在html标签上，指定事件的属性(操作)，属性值就是js代码
    ⑴ 事件：onclick--- 单击事件
    	<img src="img/off.gif" id="light" onclick="alert('点击');">
 2. 通过js获取元素对象，指定事件属性，设置一个函数

```java
<body>
			<img id="light" src="img/off.gif"  onclick="fun();">
			<img id="light2" src="img/off.gif">
			
			<script>
			    function fun(){
			        alert('我被点了');
			        alert('我又被点了');
			    }
			
			    function fun2(){
			        alert('咋老点我？');
			    }
			
			    //1.获取light2对象
			    var light2 = document.getElementById("light2");
			    //2.绑定事件
			    light2.onclick = fun2;
				light2.onclick
			</script>
</body>
```





```java
* 案例1：电灯开关
<body>
    <img src="img/off.gif" id="light" onclick="alert('点击');">

    <script>
        var light=document.getElementById("light");
        var flag=false;
        light.onclick=function () {
            if(flag){
                light.src="img/off.gif";
                flag=false;
            }else{
                light.src="img/on.gif";
                flag=true;
            }
        }
    </script>
</body>
```







### BOM

--------------------------------------------------

概念：Browser Object Model 浏览器对象模型，将浏览器的各个组成部分封装成对象。

组成：
	*Window：窗口对象
	*Navigator：浏览器对象
	*Screen：显示器屏幕对象
	*History：历史记录对象
	*Location：地址栏对象

#### Window：窗口对象

1. 创建

2. 方法
      ⑴. 与弹出框有关的方法：
             ①alert()	显示带有一段消息和一个确认按钮的警告框。
             ②confirm()	显示带有一段消息以及确认按钮和取消按钮的对话框。
                   *如果用户点击确定按钮，则方法返回true
                   *如果用户点击取消按钮，则方法返回false
             ③prompt()	显示可提示用户输入的对话框。
                   *返回值：获取用户输入的值
      ⑵. 与打开关闭有关的方法：
             ①close()	关闭浏览器窗口。
                  *谁调用我 ，我关谁
             ②open()	打开一个新的浏览器窗口
                  *返回值是一个新的Window对象，可传参打开指定网址
      ⑶. 与定时器有关的方式
             ①setTimeout()	在指定的毫秒数后调用函数或计算表达式。
                  *参数：
                      ⅰ. js代码或者方法对象
                      ⅱ. 毫秒值
                  *返回值：唯一标识，用于取消定时器
             ② clearTimeout()	取消由 setTimeout() 方法设置的 timeout。
             ③ setInterval()	按照指定的周期（以毫秒计）来调用函数或计算表达式。
              ④ clearInterval()	取消由 setInterval() 设置的 timeout。
      
3. 属性：      
		⑴. 获取其他BOM对象：
            history
            location
            Navigator
            Screen:
     ⑵. 获取DOM对象
            document

4. 特点
		  *Window对象不需要创建可以直接使用 window使用。 window.方法名();
      *window引用可以省略。  方法名();

````java
轮播图
<body>
<img  id="tu" src="img/banner_1.jpg" width="100%">
<script>
    var falg=1;
    var img = document.getElementById("tu");
    function fun() {
        if (falg == 1){
            img.src="img/banner_2.jpg";
            falg++;
        }else if (falg == 2){
            img.src="img/banner_3.jpg";
            falg++;
        } else if (falg == 3) {
            img.src="img/banner_1.jpg";
            falg=1;
        }
    }
    setInterval(fun,2000);
</script>
</body>
````





#### Location：地址栏对象
1. 创建(获取)：
		    ①. window.location
		②. location

2. 方法：
		*reload()	重新加载当前文档。刷新
3. 属性
		*href	设置或返回完整的 URL。

```java
<body>
    <input type="button" id="btn" value="刷新">
    <input type="button" id="gobaidu" value="去百度">
    <script>
        var btn=document.getElementById("btn");
        btn.onclick=function () {
            location.reload();
        }
        //获取href
        var hrf=location.href;
        //alert(hrf);

        var gobaidu=document.getElementById("gobaidu");
        gobaidu.onclick=function () {
            location.href="http://www.baidu.com";
        }
    </script>
</body>
```

```java
自动跳转首页
<body>
    <p>
        <span id="time">5</span>秒后，自动跳转首页
    </p>
    <script>
        var time = document.getElementById("time");
        var flag=5;
        function fun(){
            flag--;
            time.innerText=flag;
            if (flag==0){
                location.href="http://www.baidu.com";
            }
        }
        var id = setInterval(fun,1000);
    </script>
</body>
```







#### History：历史记录对象

1. 创建(获取)：
        ①. window.history
        ②. history

2. 方法：
        *back()	加载 history 列表中的前一个 URL。
        *forward()	加载 history 列表中的下一个 URL。
        *go(参数)	加载 history 列表中的某个具体页面。
            * 参数：
                * 正数：前进几个历史记录
                * 负数：后退几个历史记录
3. 属性：
        *length	返回当前窗口历史列表中的 URL 数量。

```java
<body>
    <input type="button" id="btn" value="获取历史记录个数">
    <input type="button" id="forward" value="前进">
    <script>
        var btn = document.getElementById("btn");
        btn.onclick=function () {
            var length = history.length;
            alert(length);

        }
		var forward = document.getElementById("forward");
		forward.onclick = function(){
       //前进
       // history.forward();
        history.go(1);
   	 }
    </script>
</body>
```



### DOM

-------------------------

概念： Document Object Model 文档对象模型
	将标记语言文档的各个组成部分，封装为对象。可以使用这些对象，对标记语言文档进行CRUD的动态操作

W3C DOM 标准被分为 3 个不同的部分：
*核心 DOM - 针对任何结构化文档的标准模型
		*Document：文档对象
		*Element：元素对象
		*Attribute：属性对象
		*Text：文本对象
		*Comment:注释对象

​         *Node：节点对象，其他5个的父对象

*XML DOM - 针对 XML 文档的标准模型
*HTML DOM - 针对 HTML 文档的标准模型

#### 核心DOM模型

##### Document：文档对象
1. 创建(获取)：在html dom模型中可以使用window对象来获取
			        ①. window.document
			②. document
	
2. 方法：
			⑴. 获取Element对象：
				①. getElementById()	： 根据id属性值获取元素对象。id属性值一般唯一
				②. getElementsByTagName()：根据元素名称获取元素对象们。返回值是一个数组
				③. getElementsByClassName():根据Class属性值获取元素对象们。返回值是一个数组
				④. getElementsByName(): 根据name属性值获取元素对象们。返回值是一个数组
	
	```java
     <body>
         <div id="div1">div1</div>
         <div id="div2">div2</div>
         <div id="div3">div3</div>
     
         <div class="cls1">div4</div>
         <div class="cls1">div5</div>
     
         <input type="text" name="username">
     
     <script>
         var divs = document.getElementsByTagName("div");
         alert(divs.length);
     
         var div_cls = document.getElementsByClassName("cls1");
         alert(div_cls.length)
     
         var ele_username = document.getElementsByName("username");
         alert(ele_username.length)
     </script>
     </body>
     ```
     
     
     
      ⑵. 创建其他DOM对象：
     		   createAttribute(name)
            	createComment()
            	createElement()
            	createTextNode()
     
3. 属性


##### Element：元素对象

1. 获取/创建：通过document来获取和创建
2. 方法：
			            ⑴. removeAttribute()：删除属性
			⑵. setAttribute()：设置属性

```java
<body>
    <a>点我试一试</a>
    <input type="button" id="btn_set" value="设置属性">
    <input type="button" id="btn_remove" value="删除属性">
<script>
    var btn_set = document.getElementById("btn_set");
    btn_set.onclick=function () {
        var element_a = document.getElementsByTagName("a")[0];
        element_a.setAttribute("href","http://www.baidu.com");
    }

    var btn_remove = document.getElementById("btn_remove");
    btn_remove.onclick=function () {
        var element_a = document.getElementsByTagName("a")[0];
        element_a.removeAttribute("href");
    }

</script>
</body>
```



##### Node：节点对象，其他5个的父对象

1. 特点：所有dom对象都可以被认为是一个节点
2. 方法：
		*CRUD dom树：
			*appendChild()：向节点的子节点列表的结尾添加新的子节点。
			*removeChild()	：删除（并返回）当前节点的指定子节点。

3.属性：
			*parentNode 返回节点的父节点。

```java
<body>
    <div id="div1">
        <div id="div2">div2</div>
        div1
    </div>
    <a href="javascript:void(0);" id="del">删除子节点</a>
    <a href="javascript:void(0);" id="add">添加子节点</a>
    <!--<input type="button" id="del" value="删除子节点">-->
<script>
    var element_a = document.getElementById("del");
    element_a.onclick=function () {
        var div1 = document.getElementById("div1");
        var div2 = document.getElementById("div2");
        div1.removeChild(div2);
    }

    var element_add = document.getElementById("add");
    element_add.onclick=function () {
        var div1 = document.getElementById("div1");
        //给div1添加子节点
        var div3 = document.createElement("div");//创建div节点
        div3.setAttribute("id","div3");//设置属性
        div1.appendChild(div3);
    }

    var div2 = document.getElementById("div2");
    var div1 = div2.parentNode;
    alert(div1)

    /*
       超链接功能：
           1.可以被点击：样式
           2.点击后跳转到href指定的url

       需求：保留1功能，去掉2功能
       实现：href="javascript:void(0);"
    */
</script>
</body>
```

```java
动态表格
<style>
        #div1{
            text-align: center;
            margin: 50px;
        }
        table{
            border: 1px solid;
            margin: auto;
            width: 500px;
        }
        td,th{
            text-align: center;
            border: 1px solid;
        }
</style>
<body>
    <div id="div1">
        <input type="text" id="id" placeholder="请输入编号">
        <input type="text" id="name" placeholder="请输入姓名">
        <input type="text" id="gender" placeholder="请输入性别">
        <input type="button" value="添加" id="btn_add">
    </div>
    <table>
        <caption>学生信息表</caption>
        <tr>
            <th>编号</th>
            <th>姓名</th>
            <th>性别</th>
            <th>操作</th>
        </tr>
        <tr>
            <td>1</td>
            <td>令狐冲</td>
            <td>男</td>
            <td><a href="javascript:void(0);" onclick="delTr(this);">删除</a></td>
        </tr>
        <tr>
            <td>2</td>
            <td>任我行</td>
            <td>男</td>
            <td><a href="javascript:void(0);" onclick="delTr(this);">删除</a></td>
        </tr>
        <tr>
            <td>3</td>
            <td>岳不群</td>
            <td>？</td>
            <td><a href="javascript:void(0);" onclick="delTr(this);">删除</a></td>
        </tr>
    </table>
</body>
<script>
    // 添加
   document.getElementById("btn_add").onclick=function () {
       var id = document.getElementById("id").value;
       var name = document.getElementById("name").value;
       var gender = document.getElementById("gender").value;

       var td_id=document.createElement("td");
       var text_id=document.createTextNode(id);
       td_id.appendChild(text_id);
       var td_name=document.createElement("td");
       var text_name=document.createTextNode(name);
       td_name.appendChild(text_name);
       var td_gender=document.createElement("td");
       var text_gender=document.createTextNode(gender);
       td_gender.appendChild(text_gender);

       var td_a=document.createElement("td");
       var ele_a = document.createElement("a");
       ele_a.setAttribute("href","javascript:void(0);");
       ele_a.setAttribute("onclick","delTr(this);");
       var text_a = document.createTextNode("删除");
       ele_a.appendChild(text_a);
       td_a.appendChild(ele_a);

       var tr=document.createElement("tr");
       tr.appendChild(td_id);
       tr.appendChild(td_name);
       tr.appendChild(td_gender);
       tr.appendChild(td_a);
        var table = document.getElementsByTagName("table")[0];
        table.appendChild(tr);
   }

</script>

<script>
    <!--删除-->
    function delTr(obj) {
        var table=obj.parentNode.parentNode.parentNode;
        var tr=obj.parentNode.parentNode;
        table.removeChild(tr);
    }
</script>
```





##### HTML DOM

1. 标签体的设置和获取：innerHTML

    ```java
    <body>
        <div id="div1">
            div
        </div>
    <script>
        var div = document.getElementById("div1");
        var innerHTML=div.innerHTML;
        //alert(innerHTML);
        //div.innerHTML="<input type='text'>";
        div.innerHTML+="<input type='text'>";
    </script>
    </body>
    ```

    ```java
    动态表格 简化添加部分
    <script>
        // 添加
        document.getElementById("btn_add").onclick=function () {
             var id = document.getElementById("id").value;
             var name = document.getElementById("name").value;
             var gender = document.getElementById("gender").value;
    
            var table = document.getElementsByTagName("table")[0];
            table.innerHTML+="<tr>\n" +
                "        <td>"+id+"</td>\n" +
                "        <td>"+name+"</td>\n" +
                "        <td>"+gender+"</td>\n" +
                "        <td><a href=\"javascript:void(0);\" onclick=\"delTr(this);\">删除</a></td>\n" +
                "    </tr>"
        }
    </script>
    
    ```

    

2. 使用html元素对象的属性

3. 控制元素样式
		    ⑴. 使用元素的style属性来设置
		⑵. 提前定义好类选择器的样式，通过元素的className属性来设置其class属性值。

```java
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .d1{
            border: 1px solid red;
            width: 100px;
            height: 100px;
        }
        .d2{
            border: 1px solid blue;
            width: 200px;
            height: 200px;
        }
    </style>
</head>
<body>
    <div id="div1">
        div1
    </div>
    <div id="div2">
        div2
    </div>
<script>
    var div1 = document.getElementById("div1");
    div1.onclick=function () {
        //修改样式方式一
        div1.style.border="1px solid red";
        div1.style.width="200px";
        div1.style.fontSize="20px";
    }
    var div2 = document.getElementById("div2");
    div2.onclick=function () {
        //修改样式方式二
        div2.className="d1";
    }
</script>
</body>
</html>
```











## 事件监听机制

概念：某些组件被执行了某些操作后，触发某些代码的执行。

常见的事件：
	1. 点击事件：
		①. onclick：单击事件
		②. ondblclick：双击事件
	2. 焦点事件
		①. onblur：失去焦点
		  *一般用于表单验证
		②. onfocus:元素获得焦点。

3. 加载事件：
	①. onload：一张页面或一幅图像完成加载。

4. 鼠标事件：
	①. onmousedown	鼠标按钮被按下。
	       *定义方法时，定义一个形参，接受event对象。
          *event对象的button属性可以获取鼠标按钮键被点击了。
	②. onmouseup	鼠标按键被松开。
	③. onmousemove	鼠标被移动。
	④. onmouseover	鼠标移到某元素之上。
	⑤. onmouseout	鼠标从某元素移开。

5. 键盘事件：
	①. onkeydown	某个键盘按键被按下。	
	②. onkeyup		某个键盘按键被松开。
	③. onkeypress	某个键盘按键被按下并松开。

6. 选择和改变
	①. onchange	域的内容被改变。
	②. onselect	文本被选中。

7. 表单事件：
	①. onsubmit	确认按钮被点击。
	    *可以阻止表单的提交
                    *方法返回false则表单被阻止提交。
	②. onreset	重置按钮被点击。

```java
<body>
<form action="#" id="form">
    <input name="username" id="username">
    <select id="city">
        <option>--请选择--</option>
        <option>北京</option>
        <option>上海</option>
        <option>杭州</option>

    </select>
    <input type="submit" value="提交">
</form>
<script>

    //2.加载完成事件  onload
    window.onload=function () {
    //1.失去焦点事件
        document.getElementById("username").onblur=function () {
            alert("失去焦点");
        }
        //3.绑定鼠标之上事件
         document.getElementById("username").onmouseover=function(){
             alert("鼠标来了");
         }
        //3.绑定鼠标点击事件
        document.getElementById("username").onmousedown=function (event) {
            //alert("鼠标点击了");
            alert(event.button);//左键右键滚轮
        }
        document.getElementById("username").onkeydown=function (event) {
            alert(event.keyCode);//左键右键滚轮
        }
        document.getElementById("city").onchange=function () {
            alert("改变了");
        }
        document.getElementById("form").onsubmit=function () {
            return false;
        }

    }
</script>
</body>
```

```java
表格全选，全不选，反选
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>表格全选</title>
    <style>
        table{
            border: 1px solid;
            width: 500px;
            margin-left: 30%;
        }

        td,th{
            text-align: center;
            border: 1px solid;
        }
        div{
            margin-top: 10px;
            margin-left: 30%;
        }
        
    </style>
    <script>
        //在页面加载完后绑定事件
        window.onload=function () {
            //2.给全选按钮绑定单击事件
            document.getElementById("selectAll").onclick=function () {
                var cbs = document.getElementsByName("cb");
                for (var i = 0; i < cbs.length; i++) {
                    cbs[i].checked=true;
                }
            }

            document.getElementById("unSelectAll").onclick=function () {
                var cbs = document.getElementsByName("cb");
                for (var i = 0; i < cbs.length; i++) {
                    cbs[i].checked=false;
                }
            }
            document.getElementById("selectRev").onclick=function () {
                var cbs = document.getElementsByName("cb");
                for (var i = 0; i < cbs.length; i++) {
                    cbs[i].checked=!cbs[i].checked;
                }
            }

            document.getElementById("firstCb").onclick=function () {
                var cbs = document.getElementsByName("cb");
                for (var i = 1; i < cbs.length; i++) {
                    cbs[i].checked=cbs[0].checked;
                }
            }
            //给所有tr绑定鼠标移到元素之上和移出元素事件
            var trs = document.getElementsByTagName("tr");
            for (var i = 0; i < trs.length; i++) {
                trs[i].onmouseover=function () {
                    this.style.backgroundColor="pink";
                }
                trs[i].onmouseout=function () {
                    this.style.backgroundColor="white";
                }
            }
        }
    </script>
    

</head>
<body>

<table>
    <caption>学生信息表</caption>
    <tr>
        <th><input type="checkbox" name="cb" id="firstCb"></th>
        <th>编号</th>
        <th>姓名</th>
        <th>性别</th>
        <th>操作</th>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>1</td>
        <td>令狐冲</td>
        <td>男</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>2</td>
        <td>任我行</td>
        <td>男</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>3</td>
        <td>岳不群</td>
        <td>?</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

</table>
<div>
    <input type="button" id="selectAll" value="全选">
    <input type="button" id="unSelectAll" value="全不选">
    <input type="button" id="selectRev" value="反选">
</div>
</body>
</html>
```

```java
表单验证

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>注册页面</title>
    <style>
        * {
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        body {
            background: url("img/register_bg.png") no-repeat center;
            padding-top: 25px;
        }

        .rg_layout {
            width: 900px;
            height: 500px;
            border: 8px solid #EEEEEE;
            background-color: white;
            /*让div水平居中*/
            margin: auto;
        }

        .rg_left {
            /*border: 1px solid red;*/
            float: left;
            margin: 15px;
        }

        .rg_left > p:first-child {
            color: #FFD026;
            font-size: 20px;
        }

        .rg_left > p:last-child {
            color: #A6A6A6;
            font-size: 20px;

        }

        .rg_center {
            float: left;
            /* border: 1px solid red;*/

        }

        .rg_right {
            /*border: 1px solid red;*/
            float: right;
            margin: 15px;
        }

        .rg_right > p:first-child {
            font-size: 15px;

        }

        .rg_right p a {
            color: pink;
        }

        .td_left {
            width: 100px;
            text-align: right;
            height: 45px;
        }

        .td_right {
            padding-left: 50px;
        }

        #username, #password, #email, #name, #tel, #birthday, #checkcode {
            width: 251px;
            height: 32px;
            border: 1px solid #A6A6A6;
            /*设置边框圆角*/
            border-radius: 5px;
            padding-left: 10px;
        }

        #checkcode {
            width: 110px;
        }

        #img_check {
            height: 32px;
            vertical-align: middle;
        }

        #btn_sub {
            width: 150px;
            height: 40px;
            background-color: #FFD026;
            border: 1px solid #FFD026;
        }

        #td_sub{
            padding-left: 150px;
        }

        .error{
            color:red;
            vertical-align: middle;
        }
    </style>
<script>
    window.onload = function(){
        document.getElementById("form").onsubmit = function(){
           
            return checkUsername() && checkPassword();
        }

        document.getElementById("username").onblur = checkUsername;
        document.getElementById("password").onblur = checkPassword;
    }

    function checkUsername(){
        var username = document.getElementById("username").value;
        var reg_username = /^\w{6,12}$/;
        var flag = reg_username.test(username);
        var s_username = document.getElementById("s_username");
        if(flag){
            s_username.innerHTML = "<img height='25' width='35' src='img/gou.png'>"
        }else{
            s_username.innerHTML = "用户名格式有误";
        }
        return flag;
    }

    function checkPassword(){
        var password = document.getElementById("password").value;
        var reg_password = /^\w{6,12}$/;
        var flag = reg_password.test(password);
        var s_password = document.getElementById("s_password");
        if(flag){
            s_password.innerHTML = "<img height='25' width='35' src='img/gou.png'>"
        }else{
            s_password.innerHTML = "密码格式有误";
        }
        return flag;
    }

</script>
</head>
<body>

<div class="rg_layout">
    <div class="rg_left">
        <p>新用户注册</p>
        <p>USER REGISTER</p>

    </div>

    <div class="rg_center">
        <div class="rg_form">
            <!--定义表单 form-->
            <form action="#" id="form" method="get">
                <table>
                    <tr>
                        <td class="td_left"><label for="username">用户名</label></td>
                        <td class="td_right">
                            <input type="text" name="username" id="username" placeholder="请输入用户名">
                            <span id="s_username" class="error"></span>
                        </td>

                    </tr>

                    <tr>
                        <td class="td_left"><label for="password">密码</label></td>
                        <td class="td_right">
                            <input type="password" name="password" id="password" placeholder="请输入密码">
                            <span id="s_password" class="error"></span>
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="email">Email</label></td>
                        <td class="td_right"><input type="email" name="email" id="email" placeholder="请输入邮箱"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="name">姓名</label></td>
                        <td class="td_right"><input type="text" name="name" id="name" placeholder="请输入姓名"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="tel">手机号</label></td>
                        <td class="td_right"><input type="text" name="tel" id="tel" placeholder="请输入手机号"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label>性别</label></td>
                        <td class="td_right">
                            <input type="radio" name="gender" value="male"> 男
                            <input type="radio" name="gender" value="female"> 女
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="birthday">出生日期</label></td>
                        <td class="td_right"><input type="date" name="birthday" id="birthday" placeholder="请输入出生日期">
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="checkcode">验证码</label></td>
                        <td class="td_right"><input type="text" name="checkcode" id="checkcode" placeholder="请输入验证码">
                            <img id="img_check" src="img/verify_code.jpg">
                        </td>
                    </tr>


                    <tr>
                        <td colspan="2"  id="td_sub"><input type="submit" id="btn_sub" value="注册"></td>
                    </tr>
                </table>

            </form>


        </div>

    </div>

    <div class="rg_right">
        <p>已有账号?<a href="#">立即登录</a></p>
    </div>


</div>


</body>
</html>
```









## Bootstrap

概念： 一个前端开发的框架

 快速入门
1. 下载Bootstrap
2. 在项目中将这三个文件夹复制
3. 创建html页面，引入必要的资源文件

==引入基本模板==

```java
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap HelloWorld</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">


    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="js/jquery-3.2.1.min.js"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="js/bootstrap.min.js"></script>
</head>
<body>
<h1>你好，世界！</h1>

</body>
</html>
```







### 响应式布局

同一套页面可以兼容不同分辨率的设备。

**实现**：依赖于栅格系统：将一行平均分成12个格子，可以指定元素占几个格子
**步骤：**
	1. 定义容器。相当于之前的table、
		*容器分类：
			①. container：两边留白
			②. container-fluid：每一种设备都是100%宽度无留白
	2. 定义行。相当于之前的tr   样式：row
	3. 定义元素。指定该元素在不同的设备上，所占的格子数目。样式：col-设备代号-格子数目
		*设备代号：
			①. xs：超小屏幕 手机 (<768px)：col-xs-12
			②. sm：小屏幕 平板 (≥768px)
			③. md：中等屏幕 桌面显示器 (≥992px)
			④. lg：大屏幕 大桌面显示器 (≥1200px)

   ==*注意：==
	①. 一行中如果格子数目超过12，则超出部分自动换行。
	②. 栅格类属性可以向上兼容。栅格类适用于与屏幕宽度大于或等于分界点大小的设备。
	③. 如果真实设备宽度小于了设置栅格类属性的设备代码的最小值，会一个元素沾满一整行。



### CSS样式和JS插件

1. 全局CSS样式：
	⑴ 按钮：class="btn btn-default"
	⑵ 图片：
		*class="img-responsive"：图片在任意尺寸都占100%
		*图片形状
			*<img src="..." alt="..." class="img-rounded">：方形
			*<img src="..." alt="..." class="img-circle"> ： 圆形
			*<img src="..." alt="..." class="img-thumbnail"> ：相框
	⑶表格
		*table
		*table-bordered
		*table-hover
	⑷表单
		*给表单项添加：class="form-control" 
2. 组件：
	⑴导航条
	⑵分页条
3. 插件：
	⑴轮播图

```java
<body>
    <a class="btn btn-default" href="#">Link</a>
    <button class="btn btn-default" type="submit">Button</button>
    <input class="btn btn-default" type="button" value="Input">
    <input class="btn btn-default" type="submit" value="Submit">
    <br><br>
    <!-- Standard button -->
    <button type="button" class="btn btn-default">（默认样式）Default</button>
    <!-- Provides extra visual weight and identifies the primary action in a set of buttons -->
    <button type="button" class="btn btn-primary">（首选项）Primary</button>
    <!-- Indicates a successful or positive action -->
    <button type="button" class="btn btn-success">（成功）Success</button>
    <!-- Contextual button for informational alert messages -->
    <button type="button" class="btn btn-info">（一般信息）Info</button>
    <!-- Indicates caution should be taken with this action -->
    <button type="button" class="btn btn-warning">（警告）Warning</button>
    <!-- Indicates a dangerous or potentially negative action -->
    <button type="button" class="btn btn-danger">（危险）Danger</button>
    <!-- Deemphasize a button by making it look like a link while maintaining button behavior -->
    <button type="button" class="btn btn-link">（链接）Link</button>

    <hr>
    <img src="img/banner_1.jpg" width="100%" class="img-responsive">
    <!--<img src="img/banner_1.jpg" class="img-circle">-->
    <!--<img src="img/banner_1.jpg" class="img-thumbnail">-->
    <br>

    <table class="table table-bordered table-hover">
        <tr>
            <th>编号</th>
            <th>姓名</th>
            <th>年龄</th>
        </tr>
        <tr>
            <td>001</td>
            <td>张三</td>
            <td>23</td>
        </tr>
        <tr>
            <td>002</td>
            <td>张三</td>
            <td>23</td>
        </tr>
        <tr>
            <td>003</td>
            <td>张三</td>
            <td>23</td>
        </tr>
    </table>
    <hr><hr><hr>
    <form>
        <div class="form-group">
            <label for="exampleInputEmail1">Email address</label>
            <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">Password</label>
            <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        </div>
        <div class="form-group">
            <label for="exampleInputFile">File input</label>
            <input type="file" id="exampleInputFile">
            <p class="help-block">Example block-level help text here.</p>
        </div>
        <div class="checkbox">
            <label>
                <input type="checkbox"> Check me out
            </label>
        </div>
        <button type="submit" class="btn btn-default">Submit</button>
    </form>

    <br><br><br>
    <nav class="navbar navbar-default">
        <div class="container-fluid">
            <!-- Brand and toggle get grouped for better mobile display -->
            <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="#">Brand</a>
            </div>

            <!-- Collect the nav links, forms, and other content for toggling -->
            <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
                <ul class="nav navbar-nav">
                    <li class="active"><a href="#">Link <span class="sr-only">(current)</span></a></li>
                    <li><a href="#">Link</a></li>
                    <li class="dropdown">
                        <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>
                        <ul class="dropdown-menu">
                            <li><a href="#">Action</a></li>
                            <li><a href="#">Another action</a></li>
                            <li><a href="#">Something else here</a></li>
                            <li role="separator" class="divider"></li>
                            <li><a href="#">Separated link</a></li>
                            <li role="separator" class="divider"></li>
                            <li><a href="#">One more separated link</a></li>
                        </ul>
                    </li>
                </ul>
                <form class="navbar-form navbar-left">
                    <div class="form-group">
                        <input type="text" class="form-control" placeholder="Search">
                    </div>
                    <button type="submit" class="btn btn-default">Submit</button>
                </form>
                <ul class="nav navbar-nav navbar-right">
                    <li><a href="#">Link</a></li>
                    <li class="dropdown">
                        <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>
                        <ul class="dropdown-menu">
                            <li><a href="#">Action</a></li>
                            <li><a href="#">Another action</a></li>
                            <li><a href="#">Something else here</a></li>
                            <li role="separator" class="divider"></li>
                            <li><a href="#">Separated link</a></li>
                        </ul>
                    </li>
                </ul>
            </div><!-- /.navbar-collapse -->
        </div><!-- /.container-fluid -->
    </nav>

    <br><br>
    <div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
        <!-- Indicators -->
        <ol class="carousel-indicators">
            <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
            <li data-target="#carousel-example-generic" data-slide-to="1"></li>
            <li data-target="#carousel-example-generic" data-slide-to="2"></li>
        </ol>

        <!-- Wrapper for slides -->
        <div class="carousel-inner"  role="listbox">
            <div class="item active" >
                <img src="img/banner_1.jpg" width="100%" alt="...">
            </div>
            <div class="item">
                <img src="img/banner_2.jpg" width="100%" alt="...">
            </div>
            <div class="item">
                <img src="img/banner_3.jpg" width="100%" alt="...">

            </div>

        </div>

        <!-- Controls -->
        <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
            <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
            <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a>
    </div>
</body>
```





### 案例

```java
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap HelloWorld</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">


    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="js/jquery-3.2.1.min.js"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="js/bootstrap.min.js"></script>
    <style>

        .paddingtop{
            padding-top: 10px;
        }
        .search-input{
            float: left;
            border: 2px solid #ffc900;
            width: 400px;
            height: 35px;
            padding-left:5px ;
            margin-top: 15px;
        }
        .search-btn{
            float: left;
            border: 2px solid #ffc900;
            width: 90px;
            height: 35px;
            background-color: #ffc900;
            text-align: center;
            line-height: 35px;/*设置成跟高度一样则为竖直居中*/
            margin-top: 15px;
        }
        .jx{
            border-bottom: 2px solid #ffc900;
            padding:5px;
        }
        .company{
            background-color:#ffc900;
            height: 40px;
            text-align: center;
            line-height: 40px;
            font-size: 8px;
        }
    </style>
</head>
<body>
    <!--页眉部分-->
    <header class="container-fluid">
        <div class="row"><!--4行-->
            <img src="img/top_banner.jpg" class="img-responsive" width="100%">
        </div>
        <div class="row paddingtop">
            <div class="col-md-4">
                <img src="img/logo.jpg" class="text-center">
            </div>
            <div class="col-md-5">
                <input type="text" class="search-input" placeholder="请输入线路名称" >
                <a href="#" class="search-btn">搜索</a>
            </div>
            <div class="col-md-3">
                <img src="img/hotel_tel.png" class="img-responsive">
            </div>
        </div>
        <!--导航条-->
        <div class="row">
            <nav class="navbar navbar-default">
                <div class="container-fluid">
                    <!-- Brand and toggle get grouped for better mobile display -->
                    <div class="navbar-header">
                        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                            <span class="sr-only">Toggle navigation</span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                        </button>
                        <a class="navbar-brand" href="#">传智播客</a>
                    </div>
                    <!-- Collect the nav links, forms, and other content for toggling -->
                    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
                        <ul class="nav navbar-nav">
                            <li class="active"><a href="#">JavaEE <span class="sr-only">(current)</span></a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li>
                        </ul>
                    </div><!-- /.navbar-collapse -->
                </div><!-- /.container-fluid -->
            </nav>
        </div>
        <!--轮播图-->
        <div class="row">
            <div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
                <!-- Indicators -->
                <ol class="carousel-indicators">
                    <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
                    <li data-target="#carousel-example-generic" data-slide-to="1"></li>
                    <li data-target="#carousel-example-generic" data-slide-to="2"></li>
                </ol>

                <!-- Wrapper for slides -->
                <div class="carousel-inner"  role="listbox">
                    <div class="item active" >
                        <img src="img/banner_1.jpg" width="100%" alt="...">
                    </div>
                    <div class="item">
                        <img src="img/banner_2.jpg" width="100%" alt="...">
                    </div>
                    <div class="item">
                        <img src="img/banner_3.jpg" width="100%" alt="...">

                    </div>

                </div>

                <!-- Controls -->
                <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
                    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                    <span class="sr-only">Previous</span>
                </a>
                <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
                    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                    <span class="sr-only">Next</span>
                </a>
            </div>

        </div>
    </header>
    <!--主体部分-->
    <div class="container">
        <div class="row jx">
            <img src="img/icon_5.jpg">
            <span>黑马精选</span>
        </div>

        <div class="row paddingtop">
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="img/jiangxuan_1.jpg" alt="...">
                    <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                    <font color="red">&yen;888</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="img/jiangxuan_1.jpg" alt="...">
                    <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                    <font color="red">&yen;888</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="img/jiangxuan_1.jpg" alt="...">
                    <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                    <font color="red">&yen;888</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="img/jiangxuan_1.jpg" alt="...">
                    <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                    <font color="red">&yen;888</font>
                </div>
            </div>
        </div>
        <div class="row jx">
            <img src="img/icon_6.jpg">
            <span>国内游</span>
        </div>
        <div class="row paddingtop" >
            <div class="col-md-4">
                <img src="img/guonei_1.jpg">
            </div>
            <div class="col-md-8">
                <div class="row">
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="img/jiangxuan_1.jpg" alt="...">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">&yen;888</font>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!--页脚部分-->
    <div class="container-fluid">
        <div class="row">
            <img src="img/footer_service.png" class="img-responsive" width="100%">
        </div>
        <div class="row company">
            江苏传智播客教育科技股份有限公司 版权所有Copyright 2006-2018, All Rights Reserved 苏ICP备16007882
        </div>
    </div>
</body>
</html>
```





## XML

 **概念：**可扩展标记语言
			可扩展：标签都是自定义的。 <user>  <student>

**功能**
		*存储数据
			⑴. 配置文件
			⑵. 在网络中传输
		

**xml与html的区别**
		⑴. xml标签都是自定义的，html标签是预定义。
		⑵. xml的语法严格，html语法松散
		⑶. xml是存储数据的，html是展示数据

**语法：**
	 基本语法：
		1. xml文档的后缀名 .xml
		2. xml第一行必须定义为文档声明
		3. xml文档中有且仅有一个根标签
		4. 属性值必须使用引号(单双都可)引起来
		5. 标签必须正确关闭
		6. xml标签名称区分大小写

```java
<?xml version="1.0" ?>

<users><!--根标签-->
    <user id="1">
        <name>zhangsan</name>
        <age>23</age>
        <gender>male</gender>
    </user>
    <user id="2">
        <name>lisi</name>
        <age>24</age>
        <gender>female</gender>
    </user>
</users>
```

**组成部分：**

1. 文档声明
			    ⑴. 格式：<?xml 属性列表 ?>
		⑵. 属性列表：
				*version：版本号，必须的属性
				*encoding：编码方式。告知解析引擎当前文档使用的字符集，默认值：ISO-8859-1
				*standalone：是否独立
					*取值：
						*yes：不依赖其他文件
						*no：依赖其他文件
2. 指令(了解)：结合css的
			*<?xml-stylesheet type="text/css" href="a.css" ?>
3. 标签：标签名称自定义的
			*规则：
				*名称可以包含字母、数字以及其他的字符 
				*名称不能以数字或者标点符号开始 
				*名称不能以字母 xml（或者 XML、Xml 等等）开始 
				*名称不能包含空格 

4. 属性：
			id属性值唯一
5. 文本：
			*CDATA区：在该区域中的数据会被原样展示（解决转义字符）
				*格式：  <![CDATA[ 数据 ]]>

#### 约束

约束：规定xml文档的书写规则

作为框架的使用者(程序员)：
1. 能够在xml中引入约束文档
2. 能够简单的读懂约束文档

**分类：**
			⑴. DTD:一种简单的约束技术
			⑵. Schema:一种复杂的约束技术

#####　DTD
*引入dtd文档到xml文档中
			*内部dtd：将约束规则定义在xml文档中
			*外部dtd：将约束的规则定义在外部的dtd文件中
				   *本地：<!DOCTYPE 根标签名 SYSTEM "dtd文件的位置">
				   *网络：<!DOCTYPE 根标签名 PUBLIC "dtd文件名字" "dtd文件的位置URL">

##### Schema

引入：

   1.填写xml文档的根元素
   2.引入xsi前缀.  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    3.引入xsd文件命名空间.  xsi:schemaLocation="http://www.itcast.cn/xml  student.xsd"
    4.为每一个xsd约束声明一个前缀,作为标识  xmlns="http://www.itcast.cn/xml" 



**解析**：操作xml文档，将文档中的数据读取到内存中

操作xml文档
		⑴. 解析(读取)：将文档中的数据读取到内存中
		⑵. 写入：将内存中的数据保存到xml文档中。持久化的存储

解析xml的方式：
		⑴. DOM：将标记语言文档一次性加载进内存，在内存中形成一颗dom树
			*优点：操作方便，可以对文档进行CRUD的所有操作
			*缺点：占内存
		⑵. SAX：逐行读取，基于事件驱动的。
			*优点：不占内存。
			*缺点：只能读取，不能增删改

##### Jsoup

快速入门：
			步骤：
				①. 导入jar包
				②. 获取Document对象
				③. 获取对应的标签Element对象
				④. 获取数据

```java
public class demo {
    public static void main(String[] args) throws IOException {
        //获取document对象，根据xml文档获取
        //2.1获取student.xml的path
        String path=demo.class.getClassLoader().getResource("student.xml").getPath();
        //2.2解析xml文档，加载文档进内存，获取dom树---
        Document document = Jsoup.parse(new File(path), "utf-8");
        //3.获取元素对象 Element
        Elements elements = document.getElementsByTag("name");
        System.out.println(elements.size());
        //3.1获取第一个name的Element对象
        Element element = elements.get(0);
        //3.2获取数据
        String name = element.text();
        System.out.println(name);
    }
}
```



**对象的使用：**

1. Jsoup：工具类，可以解析html或xml文档，返回Document
			*parse：解析html或xml文档，返回Document
				*parse​(File in, String charsetName)：解析xml或html文件的。
				*parse​(String html)：解析xml或html字符串
				*parse​(URL url, int timeoutMillis)：通过网络路径获取指定的html或xml的文档对象
	
	
	
2. Document：文档对象。代表内存中的dom树
     *获取Element对象
     			*getElementById​(String id)：根据id属性值获取唯一的element对象
     			*getElementsByTag​(String tagName)：根据标签名称获取元素对象集合
     			*getElementsByAttribute​(String key)：根据属性名称获取元素对象集合
     			*getElementsByAttributeValue​(String key, String value)：根据对应的属性名和属性值获取元素对象集合

     ```java
     public class JsoupDemo3 {
         public static void main(String[] args) throws IOException {
             //1.获取student.xml的path
             String path = JsoupDemo3.class.getClassLoader().getResource("student.xml").getPath();
             //2.获取Document对象
             Document document = Jsoup.parse(new File(path), "utf-8");
     
             //3.获取元素对象了。
             //3.1获取所有student对象
             Elements elements = document.getElementsByTag("student");
             System.out.println(elements);
     
             System.out.println("-----------");
     
     
             //3.2 获取属性名为id的元素对象们
             Elements elements1 = document.getElementsByAttribute("id");
             System.out.println(elements1);
             System.out.println("-----------");
             //3.2获取 number属性值为heima_0001的元素对象
             Elements elements2 = document.getElementsByAttributeValue("number", "heima_0001");
             System.out.println(elements2);
     
             System.out.println("-----------");
             //3.3获取id属性值的元素对象
             Element itcast = document.getElementById("itcast");
             System.out.println(itcast);
         }
     
     }
     ```

     

3. Elements：元素Element对象的集合。可以当做 ArrayList<Element>来使用

4. Element：元素对象
     ⑴. 获取子元素对象
     			*getElementById​(String id)：根据id属性值获取唯一的element对象
     			*getElementsByTag​(String tagName)：根据标签名称获取元素对象集合
     			*getElementsByAttribute​(String key)：根据属性名称获取元素对象集合
     			*getElementsByAttributeValue​(String key, String value)：根据对应的属性名和属性值获取元素对象集合

     ⑵. 获取属性值
     		*String attr(String key)：根据属性名称获取属性值
     ⑶. 获取文本内容
     		*String text():获取文本内容
     		*String html():获取标签体的所有内容(包括字标签的字符串内容)

     ```java
     public class JsoupDemo4 {
         public static void main(String[] args) throws IOException {
             //1.获取student.xml的path
             String path = JsoupDemo4.class.getClassLoader().getResource("student.xml").getPath();
             //2.获取Document对象
             Document document = Jsoup.parse(new File(path), "utf-8");
             
             //通过Document对象获取name标签，获取所有的name标签，可以获取到两个
             Elements elements = document.getElementsByTag("name");
             System.out.println(elements.size());
             System.out.println("----------------");
             //通过Element对象获取子标签对象
             Element element_student = document.getElementsByTag("student").get(0);
             Elements ele_name = element_student.getElementsByTag("name");
             System.out.println(ele_name.size());
     
             //获取student对象的属性值
             String number = element_student.attr("NUMBER");
             System.out.println(number);
             System.out.println("------------");
             //获取文本内容
             String text = ele_name.text();
             String html = ele_name.html();
             System.out.println(text);
             System.out.println(html);
         }
     
     }
     
     ```

     

5. Node：节点对象	
     *是Document和Element的父类

#####  快捷查询方式

1. selector:选择器
				*使用的方法：Elements	select(String cssQuery)
				*语法：参考Selector类中定义的语法
	
	```java
	public class demo {
	    public static void main(String[] args) throws IOException {
	        String path=demo.class.getClassLoader().getResource("student.xml").getPath();
	        Document document = Jsoup.parse(new File(path), "utf-8");
	        Elements elements = document.select("name");
	        System.out.println(elements);
	        System.out.println("---------------------------");
	        //查询id值为itcast的元素
	        Elements elements1 = document.select("#itcast");
	        System.out.println(elements1);
	        //5.1.获取student标签并且number属性值为heima_0001
	        Elements elements2 = document.select("student[number='heima_0001']");
	        System.out.println(elements2);
	        //5.2获取student标签并且number属性值为heima_0001的age子标签
	        Elements elements3 = document.select("student[number='heima_0001']>age");
	        System.out.println(elements3);
	    }
	}
	```
	
	
	
2. XPath：XPath即为XML路径语言，它是一种用来确定XML（标准通用标记语言的子集）文档中某部分位置的语言
      *使用Jsoup的Xpath需要额外导入jar包。
      			*查询w3cshool参考手册，使用xpath的语法完成查询(w3cschool菜鸟教程.CHM)

```java
public class demo {
    public static void main(String[] args) throws IOException, XpathSyntaxErrorException {
        String path=demo.class.getClassLoader().getResource("student.xml").getPath();
        Document document = Jsoup.parse(new File(path), "utf-8");
        JXDocument jxDocument=new JXDocument(document);
        //查询所有student标签
        List<JXNode> jxNodes = jxDocument.selN("//student");
        for (JXNode jxNode : jxNodes) {
            System.out.println(jxNode);
        }
        System.out.println("==================================");
        //查询所有student标签下的name标签
        List<JXNode> jxNodes2 = jxDocument.selN("//student/name");
        for (JXNode jxNode : jxNodes2) {
            System.out.println(jxNode);
        }
        System.out.println("==================================");
        //查询student标签下带有id属性的name标签
        List<JXNode> jxNodes3 = jxDocument.selN("//student[@id]/name");
        for (JXNode jxNode : jxNodes3) {
            System.out.println(jxNode);
        }
        System.out.println("==================================");

        //查询student标签下带有id属性的name标签 并且id属性值为itcast
        List<JXNode> jxNodes4= jxDocument.selN("//student[@id='1']/name");
        for (JXNode jxNode : jxNodes4) {
            System.out.println(jxNode);
        }
    }
}
```





## web服务器软件

服务器：安装了服务器软件的计算机
服务器软件：接收用户的请求，处理请求，做出响应

### Tomcat

Tomcat：web服务器软件
	1. 下载：http://tomcat.apache.org/
	2. 安装：解压压缩包即可。
		*注意：安装目录建议不要有中文和空格
	3. 卸载：删除目录就行了
	4. 启动：
		*bin/startup.bat ,双击运行该文件即可
		*访问：浏览器输入：http://localhost:8080 回车访问自己
						  http://别人的ip:8080 访问别人
		*可能遇到的问题：
			⑴. 黑窗口一闪而过：
				*原因： 没有正确配置JAVA_HOME环境变量
				*解决方案：正确配置JAVA_HOME环境变量

​			⑵. 启动报错：
​				①. 暴力：找到占用的端口号，并且找到对应的进程，杀死该进程
​					*netstat -ano
​				②. 温柔：修改自身的端口号
​					*conf/server.xml
​					*<Connector port="8888" protocol="HTTP/1.1"
​	               connectionTimeout="20000"
​	               redirectPort="8445" />
​					*一般会将tomcat的默认端口号修改为80。80端口号是http协议的默认端口号。
​					*好处：在访问时，就不用输入端口号
5. 关闭：
	⑴. 正常关闭：
		*bin/shutdown.bat
		*ctrl+c
	⑵. 强制关闭：
		*点击启动窗口的×
	
6. 配置:
	*部署项目的方式：
		⑴. 直接将项目放到webapps目录下即可。
			*/hello：项目的访问路径-->虚拟目录
			*简化部署：将项目打成一个war包，再将war包放置到webapps目录下。
				*war包会自动解压缩

	​	⑵. 配置conf/server.xml文件
	​			在<Host>标签体中配置
	​			<Context docBase="D:\hello" path="/hehe" />
	​			*docBase:项目存放的路径
	​			*path：虚拟目录

	​	⑶. 在conf\Catalina\localhost创建任意名称的xml文件。在文件中编写
	​			<Context docBase="D:\hello" />
	​			*虚拟目录：xml文件的名称
	
	*静态项目和动态项目：
		*目录结构
			*java动态项目的目录结构：
				-- 项目的根目录
					-- WEB-INF目录：
						-- web.xml：web项目的核心配置文件
						-- classes目录：放置字节码文件的目录
						-- lib目录：放置依赖的jar包

 将Tomcat集成到IDEA中，并且创建JavaEE的项目，部署项目



### Servlet：  server applet

-------------------------------

 概念：运行在服务器端的小程序
		Servlet就是一个接口，定义了Java类被浏览器访问到(tomcat识别)的规则。
		将来我们自定义一个类，实现Servlet接口，复写方法。

#### 快速入门

1. 创建JavaEE项目
2. 定义一个类，实现Servlet接口
	*public class ServletDemo1 implements Servlet
3. 实现接口中的抽象方法
4. 配置Servlet

```java
 在web.xml中配置：
	    <!--配置Servlet -->
	    <servlet>
	        <servlet-name>demo1</servlet-name>
	        <servlet-class>cn.itcast.web.servlet.ServletDemo1</servlet-class>
	    </servlet>
	
	    <servlet-mapping>
	        <servlet-name>demo1</servlet-name>
	        <url-pattern>/demo1</url-pattern>
	    </servlet-mapping>
```

Servlet中的生命周期方法：

1. 被创建：执行init方法，只执行一次
		*Servlet什么时候被创建？
			*默认情况下，第一次被访问时，Servlet被创建
			*可以配置执行Servlet的创建时机。
				*在<servlet>标签下配置
					①. 第一次被访问时，创建
                		*<load-on-startup>的值为负数,默认值
		            ②. 在服务器启动时，创建
		                *<load-on-startup>的值为0或正整数
            *Servlet的init方法，只执行一次，说明一个Servlet在内存中只存在一个对象，Servlet是单例的
			*多个用户同时访问时，可能存在线程安全问题。
			*解决：尽量不要在Servlet中定义成员变量。即使定义了成员变量，也不要对修改值

2. 提供服务：执行service方法，执行多次
		*每次访问Servlet时，Service方法都会被调用一次。
3. 被销毁：执行destroy方法，只执行一次
		*Servlet被销毁时执行。服务器关闭时，Servlet被销毁
		*只有服务器正常关闭时，才会执行destroy方法。
		*destroy方法在Servlet被销毁之前执行，一般用于释放资源

```java
public class ServlerDemo implements Servlet {
    //初始方法
    //在Servlet被创建时。只会执行一次。
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
        System.out.println("init.......");
    }
    //获取ServletConfig对象
    //ServletConfig：servlet的配置对象
    @Override
    public ServletConfig getServletConfig() {
        return null;
    }
    //提供服务的方法
    //每一次Servlet被访问时执行。执行多次。
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("service。。。。。。");
    }
    //获取Servlet的一些信息，版本，作者等等
    @Override
    public String getServletInfo() {
        return null;
    }
    //销毁方法
    //在服务器正常关闭。执行一次。
    @Override
    public void destroy() {
        System.out.println("destroy........");
    }
}
```



#### Servlet3.0

*好处：
		*支持注解配置。可以不需要web.xml了。

*步骤：
  		1. 创建JavaEE项目，选择Servlet的版本3.0以上，可以不创建web.xml
                		2. 定义一个类，实现Servlet接口
            		3. 复写方法
                      		4. 在类上使用@WebServlet注解，进行配置
                   
                       @WebServlet("/demo")

**IDEA与tomcat的相关配置**

 1. IDEA会为每一个tomcat部署的项目单独建立一份配置文件
	* 查看控制台的log：Using CATALINA_BASE:   "C:\Users\fqy\.IntelliJIdea2018.1\system\tomcat\_itcast"

2. 工作空间项目    和     tomcat部署的web项目
	* tomcat真正访问的是“tomcat部署的web项目”，"tomcat部署的web项目"对应着"工作空间项目" 的web目录下的所有资源
	* WEB-INF目录下的资源不能被浏览器直接访问。
3. 断点调试：使用"小虫子"启动 dubug 启动





6. Servlet的体系结构	
	Servlet -- 接口
		|
	GenericServlet -- 抽象类
		|
	HttpServlet  -- 抽象类



#### HttpServlet

HttpServlet：对http协议的一种封装，简化操作

1. 定义类继承HttpServlet
2. 复写doGet/doPost方法

```java
@WebServlet("/demo3")
public class ServletDome3 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("doget........");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("dopost.......");
    }
}
```

#### Servlet相关配置

1. urlpartten:Servlet访问路径
			⑴. 一个Servlet可以定义多个访问路径 ： 	@WebServlet({"/d4","/dd4","/ddd4"})
		⑵. 路径定义规则：
			  ①  /xxx：路径匹配
			  ②  /xxx/xxx:多层路径，目录结构  @WebServlet("/user/demo4")
			  ③  * .do：扩展名匹配*    @WebServlet("/user/*")







## HTTP

请求消息数据格式
1. 请求行
		请求方式 请求url 请求协议/版本
		GET /login.html	HTTP/1.1

	​	*请求方式：
	​	*HTTP协议有7中请求方式，常用的有2种
	​		*GET：
	​			①. 请求参数在请求行中，在url后。
	​			②. 请求的url长度有限制的
	​			③. 不太安全
	​		*POST：
	​			①. 请求参数在请求体中
	​			②. 请求的url长度没有限制的
	​			③. 相对安全
	
2. 请求头：客户端浏览器告诉服务器一些信息
		请求头名称: 请求头值
		*常见的请求头：
			⑴. User-Agent：浏览器告诉服务器，我访问你使用的浏览器版本信息
				*可以在服务器端获取该头的信息，解决浏览器的兼容性问题
	
	​		⑵. Referer：http://localhost/login.html
	​			*告诉服务器，我(当前请求)从哪里来？
	​				*作用：
	​					①. 防盗链：
	​					②. 统计工作：
	
3. 请求空行
		空行，就是用于分割POST请求的请求头，和请求体的。
	
4. 请求体(正文)：
		*封装POST请求消息的请求参数的

* 字符串格式：
		    POST /login.html	HTTP/1.1
		Host: localhost
		User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:60.0) Gecko/20100101 Firefox/60.0
		Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
		Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
		Accept-Encoding: gzip, deflate
		Referer: http://localhost/login.html
		Connection: keep-alive
		Upgrade-Insecure-Requests: 1
		
	
	​	username=zhangsan	



## Request

1. request对象和response对象的原理

  ​	①request和response对象是由服务器创建的。我们来使用它们

  ​	②request对象是来获取请求消息，response对象是来设置响应消息

2. request对象继承体系结构：	
	   ServletRequest		--	接口
		    |	继承
	   HttpServletRequest	-- 接口
		    |	实现
	   org.apache.catalina.connector.RequestFacade 类(tomcat)

3. request功能：

  ⑴获取请求消息数据
       ①. 获取请求行数据
  	     *GET /day14/demo1?name=zhangsan HTTP/1.1
  	     *方法：
  		     ❶. 获取请求方式 ：GET
  			     *String getMethod()  
  		     ❷. ( * )获取虚拟目录：/day14
  		         *String getContextPath()
  		     ❸. 获取Servlet路径: /demo1
  			     *String getServletPath()
  		     ❹. 获取get方式请求参数：name=zhangsan
  			     *String getQueryString()
  		     ❺. ( * )获取请求URI：/day14/demo1
  			     *String getRequestURI():		/day14/demo1
  			     *StringBuffer getRequestURL()  :http://localhost/day14/demo1

  			     *URL:统一资源定位符 ： http://localhost/day14/demo1	中华人民共和国
  			     *URI：统一资源标识符 : /day14/demo1					共和国
  		
  		      ❻. 获取协议及版本：HTTP/1.1
  			     *String getProtocol()

  		      ❼. 获取客户机的IP地址：
  			     *String getRemoteAddr()

  ```java
@WebServlet("/RequestDemo1")
public class RequestDemo1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1. 获取请求方式 ：GET
        String method=request.getMethod();
        System.out.println(method);
        //2.(*)获取虚拟目录：/day14
        String contextPath = request.getContextPath();
        System.out.println(contextPath);
        //3. 获取Servlet路径: /demo1
        String servletPath = request.getServletPath();
        System.out.println(servletPath);
        //4. 获取get方式请求参数：name=zhangsan
        String queryString = request.getQueryString();
        System.out.println(queryString);
        //5.(*)获取请求URI：/day14/demo1
        String requestURI = request.getRequestURI();
        StringBuffer requestURL = request.getRequestURL();
        System.out.println(requestURI);
        System.out.println(requestURL);
        //6. 获取协议及版本：HTTP/1.1
        String protocol = request.getProtocol();
        System.out.println(protocol);
        //7. 获取客户机的IP地址：
        String remoteAddr = request.getRemoteAddr();
        System.out.println(remoteAddr);
    }
}

  ```





​       ②获取请求头数据
 ​ 	      *方法：
​   		     * ( * )String getHeader(String name):通过请求头的名称获取请求头的值
​   		     *Enumeration<String> getHeaderNames():获取所有的请求头名称

```java
@WebServlet("/RequestDemo2")
public class RequestDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
         //演示获取请求头数据
        //1.获取所有请求头名称
        Enumeration<String> headerNames = request.getHeaderNames();
        //2.遍历
        while (headerNames.hasMoreElements()){
            String name = headerNames.nextElement();
            //根据名称获取请求头的值
            String value = request.getHeader(name);
            System.out.println(name+"----"+value);
        }
    }
}

```



​       ③获取请求体数据:
  	      *请求体：只有POST请求方式，才有请求体，在请求体中封装了POST请求的请求参数
  	      *步骤：
  		     ❶. 获取流对象
​  			    *BufferedReader getReader()：获取字符输入流，只能操作字符数据

​    			    *ServletInputStream getInputStream()：获取字节输入流，可以操作所有类型数据
​    				*在文件上传知识点后讲解

  		     ❷. 再从流对象中拿数据

```java
@WebServlet("/RequestDemo3")
public class RequestDemo3 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        BufferedReader br = request.getReader();
        String line=null;
        while ((line=br.readLine())!=null){
            System.out.println(line);
            //br.readLine()
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }
}
```



⑵ 其他功能

​	①获取请求参数通用方式：不论get还是post请求方式都可以使用下列方法来获取请求参数
​		❶ String getParameter(String name):根据参数名称获取参数值    		​​		  username=zs&password=123
​		❷ String[] getParameterValues(String name):根据参数名称获取参数值的数组  hobby=xx&hobby=game 获取复选框被选择的值
​		❸ Enumeration<String> getParameterNames():获取所有请求的参数名称  
​		❹. Map<String,String[]> getParameterMap():获取所有参数的map集合
​	
​		*中文乱码问题：
​			*get方式：tomcat 8 已经将get方式乱码问题解决了
​			*post方式：会乱码
​				*解决：在获取参数前，设置request的编码					request.setCharacterEncoding("utf-8");

```java
@WebServlet("/requestDemo6")
public class RequestDemo6 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //post 获取请求参数

        //根据参数名称获取参数值
        String username = request.getParameter("username");
       /* System.out.println("post");
        System.out.println(username);*/

       //根据参数名称获取参数值的数组
        String[] hobbies = request.getParameterValues("hobby");
        /*for (String hobby : hobbies) {
            System.out.println(hobby);
        }*/

        //获取所有请求的参数名称

        Enumeration<String> parameterNames = request.getParameterNames();
        /*while(parameterNames.hasMoreElements()){
            String name = parameterNames.nextElement();
            System.out.println(name);
            String value = request.getParameter(name);
            System.out.println(value);
            System.out.println("----------------");
        }*/

        // 获取所有参数的map集合
        Map<String, String[]> parameterMap = request.getParameterMap();
        //遍历
        Set<String> keyset = parameterMap.keySet();
        for (String name : keyset) {
            
            //获取键获取值
            String[] values = parameterMap.get(name);
            System.out.println(name);
            for (String value : values) {
                System.out.println(value);
            }

            System.out.println("-----------------");
        }


    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //get 获取请求参数
/*
        //根据参数名称获取参数值
        String username = request.getParameter("username");
        System.out.println("get");
        System.out.println(username);*/

        this.doPost(request,response);
    }
}

```



​	②. 请求转发：一种在服务器内部的资源跳转方式 
​			❶. 步骤：
​				ⅰ. 通过request对象获取请求转发器对象：RequestDispatcher getRequestDispatcher(String path)
​				ⅱ. 使用RequestDispatcher对象来进行转发：forward(ServletRequest request, ServletResponse response) 
​	
​			❷. 特点：
​				ⅰ. 浏览器地址栏路径不发生变化
​				ⅱ. 只能转发到当前服务器内部资源中。
​				ⅲ. 转发是一次请求

```java
@WebServlet("/RequestDemo4")
public class RequestDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo4被访问了");
//        RequestDispatcher requestDispatcher = request.getRequestDispatcher("/RequestDemo5");
//        requestDispatcher.forward(request,response);
       request.getRequestDispatcher("/RequestDemo5").forward(request,response);
    }
}

@WebServlet("/RequestDemo5")
public class RequestDemo5 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo5被访问了");
    }
}
```



​	③. 共享数据：
​​			*域对象：一个有作用范围的对象，可以在范围内共享数据
​			*request域：代表一次请求的范围，一般用于请求转发的多个资源中共享数据
​			*方法：
​				❶. void setAttribute(String name,Object obj):存储数据
​				❷. Object getAttitude(String name):通过键获取值
​				❸. void removeAttribute(String name):通过键移除键值对

```java
@WebServlet("/RequestDemo4")
public class RequestDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo4被访问了");
//        RequestDispatcher requestDispatcher = request.getRequestDispatcher("/RequestDemo5");
//        requestDispatcher.forward(request,response);
        //存储数据到request域中
        request.setAttribute("msg","hello");
        request.getRequestDispatcher("/RequestDemo5").forward(request,response);
    }
}

@WebServlet("/RequestDemo5")
public class RequestDemo5 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //获取数据
        Object msg = request.getAttribute("msg");
        System.out.println(msg);
        System.out.println("demo5被访问了");
    }
}
```



​	④. 获取ServletContext：
​			*ServletContext getServletContext()
​					ServletContext servletContext = request.getServletContext();

### BeanUtil

```java
/* //2.获取请求参数
        String username = req.getParameter("username");
        String password = req.getParameter("password");

        //3.封装user对象
        User loginuser=new User();
        loginuser.setUsername(username);
        loginuser.setPassword(password);*/
        Map<String, String[]> map = req.getParameterMap();
        User loginuser=new User();
        //使用BeanUtil封装
        try {
            BeanUtils.populate(loginuser,map);
        } catch (IllegalAccessException e) {
            e.printStackTrace();
        } catch (InvocationTargetException e) {
            e.printStackTrace();
        }
```

 JavaBean：标准的Java类
				⑴. 要求：
					①. 类必须被public修饰
					②. 必须提供空参的构造器
					③. 成员变量必须使用private修饰
					④. 提供公共setter和getter方法
				⑵. 功能：封装数据

⑶. 概念：
			成员变量：
			属性：setter和getter方法截取后的产物
				例如：getUsername() --> Username--> username

⑷. 方法：
			①. setProperty()设置属性值
			②. getProperty()
			③. populate(Object obj , Map map):将map集合的键值对信息，封装到对应的JavaBean对象中









## Response

### http

响应消息：服务器端发送给客户端的数据
```java
* 响应字符串格式
		HTTP/1.1 200 OK
		Content-Type: text/html;charset=UTF-8
		Content-Length: 101
		Date: Wed, 06 Jun 2018 07:08:42 GMT

		<html>
		  <head>
		    <title>$Title$</title>
		  </head>
		  <body>
		  hello , response
		  </body>
		</html>
```

### Response对象

 功能：设置响应消息
	1. 设置响应行
		⑴. 格式：HTTP/1.1 200 ok
		⑵. 设置状态码：setStatus(int sc) 

 	2.  设置响应头：setHeader(String name, String value) 

3. 设置响应体：
   ​	*使用步骤：
   ​			⑴. 获取输出流
   ​				*字符输出流：PrintWriter getWriter()
   ​				*字节输出流：ServletOutputStream getOutputStream()
   ​	
   ​			⑵. 使用输出流，将数据输出到客户端浏览器

### 案例
#### 完成重定向

*重定向：资源跳转的方式

```java
@WebServlet( "/responseDemo1")
public class ResponseDemo1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo111.......");
        //访问/responseDemo1，会自动跳转到/responseDemo2资源
        /*//1. 设置状态码为302
        response.setStatus(302);
        //2.设置响应头location
        response.setHeader("location","/responseDemo2");*/
        //简单重定向方法
        response.sendRedirect("/responseDemo2");

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}

@WebServlet("/responseDemo2")
public class ResponseDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo2.......");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

##### 重定向和转发的区别

*重定向的特点:redirect
			1. 地址栏发生变化
			2. 重定向可以访问其他站点(服务器)的资源
			3. 重定向是两次请求。不能使用request对象来共享数据

*转发的特点：forward
			1. 转发地址栏路径不变
			2. 转发只能访问当前服务器下的资源
			3. 转发是一次请求，可以使用request对象来共享数据

##### 路径写法

1. 相对路径：通过相对路径不可以确定唯一资源
			*如：./index.html
			*不以/开头，以.开头路径

​			*规则：找到当前资源和目标资源之间的相对位置关系(访问)
​				*./：当前目录
​				*../:后退一级目录

2. 绝对路径：通过绝对路径可以确定唯一资源
			*如：http://localhost/day15/responseDemo2		/day15/responseDemo2
			*以/开头的路径

	​		*规则：判断定义的路径是给谁用的？判断请求将来从哪儿发出
	​			*给客户端浏览器使用：需要加虚拟目录(项目的访问路径)
	​					*建议虚拟目录动态获取：request.getContextPath()
	​					*<a> , <form> 重定向...
	​			*给服务器使用：不需要加虚拟目录（转发）
	​				*转发路径




#### 服务器输出字符数据到浏览器

步骤：
      			1. 获取字符输出流
      			2.  输出数据

```java
@WebServlet("/responseDemo3")
public class ResponseDemo3 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //解决乱码问题
        response.setContentType("text/html;charset=utf-8");
        //1. 获取字符输出流
        PrintWriter pw = response.getWriter();
        //2. 输出数据
        pw.write("<h1> 你好 hello </h1>");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

#### 服务器输出字节数据到浏览器
*步骤：
     		1. 获取字节输出流
     		2.  输出数据

```java
@WebServlet("/responseDemo4")
public class ResponseDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //解决编码问题
        response.setContentType("text/html;charset=utf-8");
        //1. 获取字节输出流
        ServletOutputStream sos = response.getOutputStream();
        //2. 输出数据
        sos.write("hello".getBytes());
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}

```





#### 验证码

  		1. 本质：图片
                		2. 目的：防止恶意表单注册

```java

@WebServlet( "/checkCodeServlet")
public class CheckCodeServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        int width=100;
        int height=50;
        //1.创建一对象，在内存中图片(验证码图片对象)
        BufferedImage image=new BufferedImage(width,height,BufferedImage.TYPE_INT_RGB);
        //2.美化图片
        //2.1 填充背景色
        Graphics g = image.getGraphics();//画笔对象
        g.setColor(Color.pink);
        g.fillRect(0,0,width,height);
        //2.2画边框
        g.setColor(Color.BLUE);
        g.drawRect(0,0,width-1,height-1);
        //生成随机角标
        String string = "QWERTYUIOPASDFGHJKLZXCVBNMqwertyuiopasdfghjklzxcvbnm0123456789";
        Random ran = new Random();
        for(int i=1;i<=4;i++){
            int index=ran.nextInt(string.length());
            char ch=string.charAt(index);
            g.drawString(ch+"",width/5*i,height/2);
        }
        //2.4画干扰线
        g.setColor(Color.GREEN);
        for(int i=0;i<10;i++){
            int x1=ran.nextInt(width);
            int x2=ran.nextInt(width);
            int y1=ran.nextInt(height);
            int y2=ran.nextInt(height);
            g.drawLine(x1,y1,x2,y2);
        }

        //随机生成坐标点
        //3.将图片输出到页面展示
        ImageIO.write(image,"jpg",response.getOutputStream());
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

```java
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
        window.onload = function () {
            var img = document.getElementById("checkCode");
            img.onclick=function () {
                //时间戳不重复
                var date=new Date().getTime();
                img.src="/checkCodeServlet?"+date;
            }
            var change = document.getElementById("change");
            change.onclick=function () {
                var date=new Date().getTime();
                img.src="/checkCodeServlet?"+date;
            }
        }
    </script>
</head>
<body>
    <img id="checkCode" src="/checkCodeServlet">
    <a id="change" href="">看不清，换一张</a>
</body>
</html>
```







## ServletContext对象

1. 概念：代表整个web应用，可以和程序的容器(服务器)来通信

2. 获取：
	⑴. 通过request对象获取
		    request.getServletContext();
​⑵. 通过HttpServlet获取
​		this.getServletContext();
	
	```java
	@WebServlet("/servletContextDemo1")
	public class ServletContextDemo1 extends HttpServlet {
	    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        //1. 通过request对象获取
	        ServletContext context1 = request.getServletContext();
	        //2. 通过HttpServlet获取
	        ServletContext context2 = this.getServletContext();
	
	        System.out.println(context1);
	        System.out.println(context2);
	
	        System.out.println(context1 == context2);//true
	
	    }
	
	    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        this.doPost(request,response);
	    }
	}
	```
	
	
	
3. 功能：
    ⑴. 获取MIME类型：

​		   *MIME类型:在互联网通信过程中定义的一种文件数据类型
 ​ 		  *格式： 大类型/小类型   text/html		image/jpeg

​		     *获取：String getMimeType(String file)  

```java

@WebServlet("/servletContextDemo2")
public class ServletContextDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {        
        //2. 通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //3. 定义文件名称
        String filename = "a.jpg";//image/jpeg


        //4.获取MIME类型
        String mimeType = context.getMimeType(filename);
        System.out.println(mimeType);


    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```



​	   ⑵. 域对象：共享数据
​		     ①. setAttribute(String name,Object value)
​		     ②. getAttribute(String name)
​		     ③. removeAttribute(String name)

​		     *ServletContext对象范围：所有用户所有请求的数据

```java
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {   
        //2. 通过HttpServlet获取
        ServletContext context = this.getServletContext();
        //设置数据
        context.setAttribute("msg","haha");

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}

@WebServlet("/servletContextDemo4")
public class ServletContextDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {     
        //2. 通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //获取数据
        Object msg = context.getAttribute("msg");
        System.out.println(msg);

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```



​	  ⑶. 获取文件的真实(服务器)路径
​		①. 方法：String getRealPath(String path)  

```java
String b = context.getRealPath("/b.txt");//web目录下资源访问
System.out.println(b);


String c = context.getRealPath("/WEB-INF/c.txt");//WEB-INF目录下的资源访问
System.out.println(c);
	    
String a = context.getRealPath("/WEB-INF/classes/a.txt");//src目录下的资源访问
System.out.println(a);
```



### 案例：附件下载

```java
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <a href="/downloadServlet?filename=1.jpg">图片一</a>
    <!--<a href="/downloadServlet?filename=1.avi">视频</a>-->
</body>
</html>
```



```java
@WebServlet("/downloadServlet")
public class DownloadServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.获取请求参数，文件名称
        String filename = request.getParameter("filename");
        //2.使用字节输入流加载文件进内存
        //2.1找到文件服务器路径
        ServletContext servletContext = this.getServletContext();
        String realPath = servletContext.getRealPath("/img/" + filename);
        //2.2用字节流关联
        FileInputStream fis = new FileInputStream(realPath);

        //3.设置response的响应头
        //3.1设置响应头类型：content-type
        String mimeType = servletContext.getMimeType(filename);//获取文件的mime类型
        response.setHeader("content-type",mimeType);
        //3.2设置响应头打开方式:content-disposition

        //解决中文文件名问题
        //1.获取user-agent请求头、
        String agent = request.getHeader("user-agent");
        //2.使用工具类方法编码文件名即可
        filename = DownLoadUtils.getFileName(agent, filename);
        

        response.setHeader("content-disposition","attachment;filename="+filename);
        //4.将输入流的数据写出到输出流中
        ServletOutputStream sos = response.getOutputStream();
        byte[] buff = new byte[1024 * 8];
        int len = 0;
        while((len = fis.read(buff)) != -1){
            sos.write(buff,0,len);
        }

        fis.close();
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }
}
```







## 会话

1. 会话：一次会话中包含多次请求和响应。
	*一次会话：浏览器第一次给服务器资源发送请求，会话建立，直到有一方断开为止
2. 功能：在一次会话的范围内的多次请求间，共享数据
3. 方式：
	⑴. 客户端会话技术：Cookie
	⑵. 服务器端会话技术：Session

### Cookie

-------------------------------------------

1. 概念：客户端会话技术，将数据保存到客户端

2. 快速入门：
	*使用步骤：
		⑴. 创建Cookie对象，绑定数据
			*new Cookie(String name, String value) 
		⑵. 发送Cookie对象
			*response.addCookie(Cookie cookie) 
		⑶. 获取Cookie，拿到数据
			*Cookie[]  request.getCookies()  

	```java
	@WebServlet("/cookieDemo1")
	public class CookieDemo1 extends HttpServlet {
	    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        //1.创建Cookie对象
	        Cookie c=new Cookie("msg","hello");
	        response.addCookie(c);
	
	
	    }
	
	    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        this.doPost(request,response);
	    }
	}
	@WebServlet("/cookieDemo2")
	public class CookieDemo2 extends HttpServlet {
	    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        //3.获取Cookie
	        Cookie[] cs=request.getCookies();
	        //获取数据，遍历Cookie
	        if(cs!=null){
	            for (Cookie c : cs) {
	                String name=c.getName();
	                String value = c.getValue();
	                System.out.println(name+":"+value);
	            }
	        }
	    }
	
	    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        this.doPost(request, response);
	    }
	}
	```
	
	
	
3. 实现原理
    *基于响应头set-cookie和请求头cookie实现

4. cookie的细节
    ⑴. 一次可不可以发送多个cookie?
    	*可以
    	*可以创建多个Cookie对象，使用response调用多次addCookie方法发送cookie即可。
    ⑵. cookie在浏览器中保存多长时间？
    	①. 默认情况下，当浏览器关闭后，Cookie数据被销毁
    	②. 持久化存储：
    		*setMaxAge(int seconds)
    			❶. 正数：将Cookie数据写到硬盘的文件中。持久化存储。并指定cookie存活时间，时间到后，cookie文件自动失效
    			❷. 负数：默认值
    			❸. 零：删除cookie信息

```java
 		//1.创建Cookie对象
        Cookie c1 = new Cookie("msg","setMaxAge");
        //2.设置cookie的存活时间
        //c1.setMaxAge(30);//将cookie持久化到硬盘，30秒后会自动删除cookie文件
        //c1.setMaxAge(-1);
        //c1.setMaxAge(300);
        c1.setMaxAge(0);//删除Cookie
        //3.发送Cookie
        response.addCookie(c1);
```

  ⑶. cookie能不能存中文？
  	*在tomcat 8 之前 cookie中不能直接存储中文数据。
  		*需要将中文数据转码---一般采用URL编码(%E3)
  	*在tomcat 8 之后，cookie支持中文数据。特殊字符还是不支持，建议使用URL编码存储，URL解码解析
  ⑷. cookie共享问题？
  	①. 假设在一个tomcat服务器中，部署了多个web项目，那么在这些web项目中cookie能不能共享？
  		*默认情况下cookie不能共享

​			*setPath(String path):设置cookie的获取范围。默认情况下，设置当前的虚拟目录
​				*如果要共享，则可以将path设置为"/"
​		②. 不同的tomcat服务器间cookie共享问题？
​			*setDomain(String path):如果设置一级域名相同，那么多个服务器之间cookie可以共享
​				*setDomain(".baidu.com"),那么tieba.baidu.com和news.baidu.com中cookie可以共享
​	

5. Cookie的特点和作用
	⑴. cookie存储数据在客户端浏览器
	⑵. 浏览器对于单个cookie 的大小有限制(4kb) 以及 对同一个域名下的总cookie数量也有限制(20个)

	*作用：
		①. cookie一般用于存出少量的不太敏感的数据
		②. 在不登录的情况下，完成服务器对客户端的身份识别

6. 案例：记住上一次访问时间
	⑴. 需求：
		①. 访问一个Servlet，如果是第一次访问，则提示：您好，欢迎您首次访问。
		②. 如果不是第一次访问，则提示：欢迎回来，您上次访问时间为:显示时间字符串

	⑵. 分析：
		①. 可以采用Cookie来完成
		②. 在服务器中的Servlet判断是否有一个名为lastTime的cookie
			❶. 有：不是第一次访问
				ⅰ. 响应数据：欢迎回来，您上次访问时间为:2018年6月10日11:50:20
				ⅱ. 写回Cookie：lastTime=2018年6月10日11:50:01
			❷. 没有：是第一次访问
				ⅰ. 响应数据：您好，欢迎您首次访问
				ⅱ. 写回Cookie：lastTime=2018年6月10日11:50:01

```java
 //设置响应的消息体的数据格式以及编码
        response.setContentType("text/html;charset=utf-8");

        //1.获取所有Cookie
        Cookie[] cookies = request.getCookies();
        boolean flag = false;//没有cookie为lastTime
        //2.遍历cookie数组
        if(cookies != null && cookies.length > 0){
            for (Cookie cookie : cookies) {
                //3.获取cookie的名称
                String name = cookie.getName();
                //4.判断名称是否是：lastTime
                if("lastTime".equals(name)){
                    //有该Cookie，不是第一次访问

                    flag = true;//有lastTime的cookie

                    
                    //响应数据
                    //获取Cookie的value，时间
                    String value = cookie.getValue();
                    System.out.println("解码前："+value);
                    //URL解码：
                    value = URLDecoder.decode(value,"utf-8");
                    System.out.println("解码后："+value);
                    response.getWriter().write("<h1>欢迎回来，您上次访问时间为:"+value+"</h1>");
                    
                    
                    
                    //设置Cookie的value
                    //获取当前时间的字符串，重新设置Cookie的值，重新发送cookie
                    Date date  = new Date();
                    SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
                    String str_date = sdf.format(date);
                    System.out.println("编码前："+str_date);
                    //URL编码
                    str_date = URLEncoder.encode(str_date,"utf-8");
                    System.out.println("编码后："+str_date);
                    cookie.setValue(str_date);
                    //设置cookie的存活时间
                    cookie.setMaxAge(60 * 60 * 24 * 30);//一个月
                    response.addCookie(cookie);


                    break;

                }
            }
        }


        if(cookies == null || cookies.length == 0 || flag == false){
            //没有，第一次访问

            //设置Cookie的value
            //获取当前时间的字符串，重新设置Cookie的值，重新发送cookie
            Date date  = new Date();
            SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
            String str_date = sdf.format(date);
            System.out.println("编码前："+str_date);
            //URL编码
            str_date = URLEncoder.encode(str_date,"utf-8");
            System.out.println("编码后："+str_date);

            Cookie cookie = new Cookie("lastTime",str_date);
            //设置cookie的存活时间
            cookie.setMaxAge(60 * 60 * 24 * 30);//一个月
            response.addCookie(cookie);

            response.getWriter().write("<h1>您好，欢迎您首次访问</h1>");
        }

```

### JSP

-----------------------------

1. 概念：
	*Java Server Pages： java服务器端页面
		*可以理解为：一个特殊的页面，其中既可以指定定义html标签，又可以定义java代码
		*用于简化书写！！！
	
2. 原理
	*JSP本质上就是一个Servlet

3. JSP的脚本：JSP定义Java代码的方式
	⑴. <%  代码 %>：定义的java代码，在service方法中。service方法中可以定义什么，该脚本中就可以定义什么。
	⑵. <%! 代码 %>：定义的java代码，在jsp转换后的java类的成员位置。(定义成员变量成员方法静态代码块)
	⑶. <%= 代码 %>：定义的java代码，会输出到页面上。输出语句中可以定义什么，该脚本中就可以定义什么。

4. JSP的内置对象：
	*在jsp页面中不需要获取和创建，可以直接使用的对象
	*jsp一共有9个内置对象。
	*今天学习3个：
		*request
		*response
		*out：字符输出流对象。可以将数据输出到页面上。和response.getWriter()类似
			*response.getWriter()和out.write()的区别：
				*在tomcat服务器真正给客户端做出响应之前，会先找response缓冲区数据，再找out缓冲区数据。
				*response.getWriter()数据输出永远在out.write()之前
	
	```java
	<%
	    response.getWriter().write("response");
	  %>
	  <%
	    System.out.println("hello jsp");
	    int i=5;
	    String contextPath = request.getContextPath(
	    out.print("2222"););
	  %>
	```
	
	


5. 案例:改造Cookie案例

```java
<%@ page import="java.net.URLDecoder" %>
<%@ page import="java.util.Date" %>
<%@ page import="java.net.URLEncoder" %>
<%@ page import="java.text.SimpleDateFormat" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>itcast</title>
</head>
<body>
<%

    //1.获取所有Cookie
    Cookie[] cookies = request.getCookies();
    boolean flag = false;//没有cookie为lastTime
    //2.遍历cookie数组
    if(cookies != null && cookies.length > 0){
        for (Cookie cookie : cookies) {
            //3.获取cookie的名称
            String name = cookie.getName();
            //4.判断名称是否是：lastTime
            if("lastTime".equals(name)){
                //有该Cookie，不是第一次访问

                flag = true;//有lastTime的cookie

                //响应数据
                //获取Cookie的value，时间
                String value = cookie.getValue();
                System.out.println("解码前："+value);
                //URL解码：
                value = URLDecoder.decode(value,"utf-8");
                System.out.println("解码后："+value);
                out.write("<h1>欢迎回来，您上次访问时间为:"+value+"</h1>");

                //设置Cookie的value
                //获取当前时间的字符串，重新设置Cookie的值，重新发送cookie
                Date date  = new Date();
                SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
                String str_date = sdf.format(date);
                System.out.println("编码前："+str_date);
                //URL编码
                str_date = URLEncoder.encode(str_date,"utf-8");
                System.out.println("编码后："+str_date);
                cookie.setValue(str_date);
                //设置cookie的存活时间
                cookie.setMaxAge(60 * 60 * 24 * 30);//一个月
                response.addCookie(cookie);


                break;

            }
        }
    }


    if(cookies == null || cookies.length == 0 || flag == false){
        //没有，第一次访问

        //设置Cookie的value
        //获取当前时间的字符串，重新设置Cookie的值，重新发送cookie
        Date date  = new Date();
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
        String str_date = sdf.format(date);
        System.out.println("编码前："+str_date);
        //URL编码
        str_date = URLEncoder.encode(str_date,"utf-8");
        System.out.println("编码后："+str_date);

        Cookie cookie = new Cookie("lastTime",str_date);
        //设置cookie的存活时间
        cookie.setMaxAge(60 * 60 * 24 * 30);//一个月
        response.addCookie(cookie);

        out.write("<h1>您好，欢迎您首次访问</h1>");
    }

%>

    </body>
</html>

```



### Session

1. 概念：服务器端会话技术，在一次会话的多次请求间共享数据，将数据保存在服务器端的对象中。HttpSession

2. 快速入门：
	⑴. 获取HttpSession对象：
		HttpSession session = request.getSession();
	⑵. 使用HttpSession对象：
		Object getAttribute(String name)  
		void setAttribute(String name, Object value)
		void removeAttribute(String name)  

	```java
	  //1.获取session
	        HttpSession session = request.getSession();
	        //2.存储数据
	        session.setAttribute("msg", "hello session");
	        //3.获取数据
	        Object msg = session.getAttribute("msg");
	        System.out.println(msg);
	```
	
	
	
3. 原理
    *Session的实现是依赖于Cookie的。

4. 细节：
    ⑴. 当客户端关闭后，服务器不关闭，两次获取session是否为同一个？
    		*默认情况下。不是。
    		*如果需要相同，则可以创建Cookie,键为JSESSIONID，设置最大存活时间，让cookie持久化保存。
    			 Cookie c = new Cookie("JSESSIONID",session.getId());
    	         c.setMaxAge(60*60);
    	         response.addCookie(c);
    ​⑵客户端不关闭，服务器关闭后，两次获取的session是同一个吗？
    ​			*不是同一个，但是要确保数据不丢失。tomcat自动完成以下工作
    ​				*session的钝化：
    ​					*在服务器正常关闭之前，将session对象系列化到硬盘上
    ​				*session的活化：
    ​					*在服务器启动后，将session文件转化为内存中的session对象即可。
    		

​		⑶. session什么时候被销毁？
​			 ①. 服务器关闭
​			 ②. session对象调用invalidate() 。
​			 ③. session默认失效时间 30分钟
​				选择性配置修改	
​				<session-config>
​					<session-timeout>30</session-timeout>
​		    	</session-config>

5. session的特点
	  ⑴. session用于存储一次会话的多次请求的数据，存在服务器端
	 ⑵. session可以存储任意类型，任意大小的数据

	​	*session与Cookie的区别：
	​			⑴. session存储数据在服务器端，Cookie在客户端
	​			⑵. session没有数据大小限制，Cookie有
	​			⑶. session数据安全，Cookie相对于不安全



###  案例：验证码

1. 案例需求：
	1. 访问带有验证码的登录页面login.jsp
	2. 用户输入用户名，密码以及验证码。
		* 如果用户名和密码输入有误，跳转登录页面，提示:用户名或密码错误
		* 如果验证码输入有误，跳转登录页面，提示：验证码错误
		* 如果全部输入正确，则跳转到主页success.jsp，显示：用户名,欢迎您





## JSP

1. 指令
	*作用：用于配置JSP页面，导入资源文件
	*格式：
		<%@ 指令名称 属性名1=属性值1 属性名2=属性值2 ... %>
	*分类：

​		⑴. page		： 配置JSP页面的
​			*contentType：等同于response.setContentType()
​				  ①. 设置响应体的mime类型以及字符集
​				  ②. 设置当前jsp页面的编码（只能是高级的IDE才能生效，如果使用低级工具，则需要设置pageEncoding属性设置当前页面的字符集）
​			*import：导包
​			*errorPage：当前页面发生异常后，会自动跳转到指定的错误页面
​			*isErrorPage：标识当前也是是否是错误页面。
​				  *true：是，可以使用内置对象exception
​				  *false：否。默认值。不可以使用内置对象exception
​		
​		⑵. include	： 页面包含的。导入页面的资源文件
​			*<%@include file="top.jsp"%>

​		⑶. taglib	： 导入资源
​			*<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
​				*prefix：前缀，自定义的
2. 注释:
	⑴. html注释：
		<!-- -->:只能注释html代码片段
	⑵. jsp注释：推荐使用
		<%-- --%>：可以注释所有
	
3. 内置对象
	*在jsp页面中不需要创建，直接使用的对象
	*一共有9个：
			变量名					真实类型						作用
		*pageContext				PageContext					当前页面共享数据，还可以获取其他八个内置对象
		*request					HttpServletRequest			一次请求访问的多个资源(转发)
		*session					HttpSession					一次会话的多个请求间
		*application				ServletContext				所有用户间共享数据
		*response					HttpServletResponse			响应对象
		*page						Object						当前页面(Servlet)的对象  this
		*out						JspWriter					输出对象，数据输出到页面上
		*config					ServletConfig				Servlet的配置对象
		*exception					Throwable					异常对象