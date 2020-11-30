

基本语法

#### javascript的使用

1.行内式js

```html
<input type="button" value="唐伯虎" onclick="alert('唐伯虎')">
```

2.内嵌式的js

```java
<script>
	alert('唐伯虎');
</script>
```

3.外部样式

```html
定义my.js文件中写 alert('唐伯虎');
引用：
<script src="my.js"></script>//中间不能写代码
```



#### 注释

```html
// 单行注释 ctrl+/
alert('hello'); // 单行注释
/*多行注释 默认：shift + alt + a
已经修改为 ctrl+shift+/
多行注释*/

```

#### 输入输出语句

alert(msg)    浏览器弹出警示框
console.log(mdg)    浏览器控制台打印输出信息
prompt(info)   浏览器弹出输入框，用户可以输入

#### 数据类型

JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：

```html
123; // 整数123
0.456; // 浮点数0.456
1.2345e3; // 科学计数法表示1.2345x1000，等同于1234.5
-99; // 负数
NaN; // NaN表示Not a Number，当无法计算结果时用NaN表示
Infinity; // Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity
```

#### 四则运算

Number可以直接做四则运算，规则和数学一致：

```html
1 + 2; // 3
(1 + 2) * 5 / 2; // 7.5(/号不是整除)
2 / 0; // Infinity
0 / 0; // NaN
10 % 3; // 1
10.5 % 3; // 1.5
```

#### 比较运算符

&&，||，！，>,>=,<,<=    和以前一致

第一种是`==`比较，它会自动转换数据类型再比较，很多时候，会得到非常诡异的结果；
第二种是`===`比较，它不会自动转换数据类型，如果数据类型不一致，返回`false`，如果一致，再比较。
由于JavaScript这个设计缺陷，*不要*使用`==`比较，始终坚持使用`===`比较。

另一个例外是`NaN`这个特殊的Number与所有其他值都不相等，包括它自己：

```
NaN === NaN; // false
```

唯一能判断`NaN`的方法是通过`isNaN()`函数：

```html
isNaN(NaN); // true
```

最后要注意浮点数的相等比较：

```
1 / 3 === (1 - 2 / 3); // false
```

这不是JavaScript的设计缺陷。浮点数在运算过程中会产生误差，因为计算机无法精确表示无限循环小数。要比较两个浮点数是否相等，只能计算它们之差的绝对值，看是否小于某个阈值：

```
Math.abs(1 / 3 - (1 - 2 / 3)) < 0.0000001; // true
```



#### null和undefined

`null`表示一个“空”的值，它和`0`以及空字符串`''`不同，`0`是一个数值，`''`表示长度为0的字符串，而`null`表示“空”。`undefined`和`null`类似，它表示“未定义”。区分两者的意义不大。大多数情况下，我们都应该用`null`。`undefined`仅仅在判断函数参数是否传递的情况下有用。

#### 变量

变量名是大小写英文、数字、`$`和`_`的组合，且不能用数字开头。通过var声明。

#### 条件判断

```html
var age = 3;
if (age >= 18) {
    alert('adult');
} else if (age >= 6) {
    alert('teenager');
} else {
    alert('kid');
}//建议永远都要写上{}
```

#### 循环

for循环

```
var x = 0;
var i;
for (i=1; i<=10000; i++) {
    x = x + i;
}
x; // 50005000
```

for ... in

```html
var o = {
    name: 'Jack',
    age: 20,
    city: 'Beijing'
};
for (var key in o) {
    if (o.hasOwnProperty(key)) {//过滤掉对象继承的属性，用hasOwnProperty()来实现
        console.log(key); // 'name', 'age', 'city'
    }
}
```

```html
//由于Array也是对象，而它的每个元素的索引被视为对象的属性，因此，for ... in循环可以直接循环出Array的索引
var a = ['A', 'B', 'C'];
for (var i in a) {
    console.log(i); // '0', '1', '2'
    console.log(a[i]); // 'A', 'B', 'C'
}
```



for ... in对Array的循环得到的是String而不是Number

while循环

```html
var x = 0;
var n = 99;
while (n > 0) {
    x = x + n;
    n = n - 2;
}
```









#### 数组

JavaScript的数组可以包括任意数据类型。可通过索引访问，索引起始值为0。

```html
var arr=[1, 2, 3.14, 'Hello', null, true];//创建新数组
var arr=new Array(1, 2, 3); // 创建了数组[1, 2, 3]//创建新数组

var len=arr.length;//获取数组长度

//Array可以通过索引把对应的元素修改为新的值
var arr = ['A', 'B', 'C'];
arr[1] = 99;
arr; // arr现在变为['A', 99, 'C']

//如果通过索引赋值时，索引超过了范围，同样会引起Array大小的变化
var arr = [1, 2, 3];
arr[5] = 'x';
arr; // arr变为[1, 2, 3, undefined, undefined, 'x']

```

##### 方法

**indexOf()**：来搜索一个指定的元素的位置，返回第一个满足条件的索引号,找不到元素返回-1

**lastIndexOf()**:返回最后一个满足条件法人索引号

```html
var arr = [10, 20, '30', 'xyz'，20];
arr.indexOf(10); // 元素10的索引为0
arr.indexOf(20); // 元素20的索引为1
arr.indexOf(30); // 元素30没有找到，返回-1
arr.lastIndexOf(20);//返回4
```

**slice()**：截取Array的部分元素，然后返回一个新的Array：

```
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
arr.slice(0, 3); // 从索引0开始，到索引3结束，但不包括索引3: ['A', 'B', 'C']
arr.slice(3); // 从索引3开始到结束: ['D', 'E', 'F', 'G']
```

注意到slice()的起止参数包括开始索引，不包括结束索引。

如果不给slice()传递任何参数，它就会从头到尾截取所有元素。利用这一点，我们可以很容易地复制一个Array：

```
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
var aCopy = arr.slice();
aCopy; // ['A', 'B', 'C', 'D', 'E', 'F', 'G']
aCopy === arr; // false
```

**push和pop**：push()向Array的末尾添加若干元素，pop()则把Array的最后一个元素删除掉：

```
var arr = [1, 2];
arr.push('A', 'B'); // 返回Array新的长度: 4
arr; // [1, 2, 'A', 'B']
arr.pop(); // pop()返回'B'
arr; // [1, 2, 'A']
arr.pop(); arr.pop(); arr.pop(); // 连续pop 3次
arr; // []
arr.pop(); // 空数组继续pop不会报错，而是返回undefined
arr; // []
```

**unshift和shift**：如果要往Array的头部添加若干元素，使用unshift()方法，shift()方法则把Array的第一个元素删掉：

```
var arr = [1, 2];
arr.unshift('A', 'B'); // 返回Array新的长度: 4
arr; // ['A', 'B', 1, 2]
arr.shift(); // 'A'
arr; // ['B', 1, 2]
arr.shift(); arr.shift(); arr.shift(); // 连续shift 3次
arr; // []
arr.shift(); // 空数组继续shift不会报错，而是返回undefined
arr; // []
```

**sort**：sort()可以对当前Array进行排序，它会直接修改当前Array的元素位置，直接调用时，按照默认顺序排序：

```
var arr = ['B', 'C', 'A'];
arr.sort();
arr; // ['A', 'B', 'C']
arr.sort(function(a,b){
	return a-b;//升序，默认
	return b-a;//降序
});
```

能否按照我们自己指定的顺序排序呢？完全可以，我们将在后面的函数中讲到。

**reverse**：reverse()把整个Array的元素给掉个个，也就是反转：

```
var arr = ['one', 'two', 'three'];
arr.reverse(); 
arr; // ['three', 'two', 'one']
```

**splice**：splice()方法是修改Array的“万能方法”，它可以从指定的索引开始删除若干元素，然后再从该位置添加若干元素：

```
var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
// 从索引2开始删除3个元素,然后再添加两个元素:
arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite']
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
// 只删除,不添加:
arr.splice(2, 2); // ['Google', 'Facebook']
arr; // ['Microsoft', 'Apple', 'Oracle']
// 只添加,不删除:
arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
```

**concat**：concat()方法把当前的Array和另一个Array连接起来，并返回一个新的Array：

```
var arr = ['A', 'B', 'C'];
var added = arr.concat([1, 2, 3]);
added; // ['A', 'B', 'C', 1, 2, 3]
arr; // ['A', 'B', 'C']
```

*请注意*，concat()方法并没有修改当前Array，而是返回了一个新的Array。

实际上，concat()方法可以接收任意个元素和Array，并且自动把Array拆开，然后全部添加到新的Array里：

```
var arr = ['A', 'B', 'C'];
arr.concat(1, 2, [3, 4]); // ['A', 'B', 'C', 1, 2, 3, 4]
```

**join**：join()方法是一个非常实用的方法，它把当前Array的每个元素都用指定的字符串连接起来，然后返回连接后的字符串：

```
var arr = ['A', 'B', 'C', 1, 2, 3];
arr.join('-'); // 'A-B-C-1-2-3'
```

如果`Array`的元素不是字符串，将自动转换为字符串后再连接。

**toString()**:转换为字符串

```html
var arr=[1,2,3];
arr.toString();//'1,2,3'
```



**instanceof**:检测是否为数组

```html
var arr=[];
arr instanceof Array;//是为true
Array.isArray(arr);
```





##### 多维数组

```html
var arr = [[1, 2, 3], [400, 500, 600], '-'];
```



#### Map

Map是一组键值对的结构，具有极快的查找速度。

```html
var m = new Map([['Michael', 95], ['Bob', 75], ['Tracy', 85]]);
var m = new Map(); // 空Map
m.set('Adam', 67); // 添加新的key-value
m.set('Bob', 59);
m.has('Adam'); // 是否存在key 'Adam': true
m.get('Adam'); // 67
m.delete('Adam'); // 删除key 'Adam'
m.get('Adam'); // undefined


//由于一个key只能对应一个value，所以，多次对一个key放入value，后面的值会把前面的值冲掉
var m = new Map();
m.set('Adam', 67);
m.set('Adam', 88);
m.get('Adam'); // 88


```

#### Set

Set和Map类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在Set中，没有重复的key。

```html
var s1 = new Set(); // 空Set
var s2 = new Set([1, 2, 3]); // 含1, 2, 3
s.add(4); // Set {1, 2, 3, 4}
s.add(4); // 仍然是 Set {1, 2, 3, 4}
var s = new Set([1, 2, 3]);Set {1, 2, 3}
s.delete(3);//Set {1, 2}

```

#### iterable

遍历Map和Set等没有下标的集合

```html
var a = ['A', 'B', 'C'];
var s = new Set(['A', 'B', 'C']);
var m = new Map([[1, 'x'], [2, 'y'], [3, 'z']]);
for (var x of a) { // 遍历Array
    console.log(x);
}
for (var x of s) { // 遍历Set
    console.log(x);
}
for (var x of m) { // 遍历Map
    console.log(x[0] + '=' + x[1]);
}
```





#### 字符串

JavaScript的字符串就是用`''`或`""`括起来的字符表示

##### 多行字符串

由于多行字符串用`\n`写起来比较费事，所以最新的ES6标准新增了一种多行字符串的表示方法，用反引号 示：

```
`这是一个
多行
字符串`;
```

##### 拼接

1.用+号

```
var name = '小明';
var age = 20;
var message = '你好, ' + name + ', 你今年' + age + '岁了!';
alert(message);
```

2.模板字符串

```
var name = '小明';
var age = 20;
var message = `你好, ${name}, 你今年${age}岁了!`;
alert(message);
```

##### 常用方法

JavaScript为字符串提供了一些常用方法，注意，调用这些方法本身不会改变原有字符串的内容，而是返回一个新字符串：

**toUpperCase()**：把一个字符串全部变为大写：

```
var s = 'Hello';
s.toUpperCase(); // 返回'HELLO'
```

**toLowerCase()**：把一个字符串全部变为小写：

```
var s = 'Hello';
var lower = s.toLowerCase(); // 返回'hello'并赋值给变量lower
lower; // 'hello'
```

**indexOf()**：会搜索指定字符串出现的位置：

```
var s = 'hello, world';
s.indexOf('world'); // 返回7
s.indexOf('World'); // 没有找到指定的子串，返回-1
s.indexOf('World',3);//从索引3开始往后查找
```



**concat（str1，str2，str3...）**:concat方法用于连接两个或多个字符串。拼接字符串，等效于+，+更常用。

**substr(start，length)**:从start位置开始（索引号），length取得个数

**slice（start，end）**:从start位置开始，截取到end位置，end取不到（他们俩都是索引号）

**substring(start，end)**：从start位置开始，截取到end位置，end取不到（他们俩都是索引号）。基本和slice相同，但不接受负值。

```
var s = 'hello, world'
s.concat('red');
s.substr(1,2);
s.substring(0, 5); // 从索引0开始到5（不包括5），返回'hello'
s.substring(7); // 从索引7开始到结束，返回'world'
```

**charAt(index)**:返回指定位置的字符（index字符串的索引号）

**cahrCodeAt(index)** :获取指定位置处字符的ASCLL码(index索引号)

**str[index]**:获取指定位置处字符，chatAt()等效。h5新增的。

```html
var str='andy';
str.chatAt(i);
str.charCodeAt(0);

//将字母转为ascii码的方法
var str1 = "A";
str1.charCodeAt();  // 65

//将ascii码转为对应字母的方法
var num = 97;
String.fromCharCode(num);  // 'a'
var num1 = 100;
String.fromCharCode(num1);  // 'd'

```

**replace('被替换的字符'，‘替换为的字符’)**

```html
var str='andy';
str.replace('a','b');
```

**split('分隔符')**:转换为数组

```html
var str2='red,pink,blue';
str2.split(',')
```





#### 对象

JavaScript的对象是一组由键-值组成的无序集合，例如：

```
var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null//
};
```

注意，最后一个键值对不需要在末尾加`,`，如果加了，有的浏览器（如低版本的IE）将报错。

JavaScript对象的键都是字符串类型，值可以是任意数据类型。上述`person`对象一共定义了6个键值对，其中每个键又称为对象的属性，例如，`person`的`name`属性为`'Bob'`，`zipcode`属性为`null`。

要获取一个对象的属性，我们用`对象变量.属性名`的方式：

```
person.name; // 'Bob'
person.zipcode; // null
```

```html
var xiaohong = {
    name: '小红',
    'middle-school': 'No.1 Middle School'
};
xiaohong的属性名middle-school不是一个有效的变量，就需要用''括起来。访问这个属性也无法使用.操作符，必须用['xxx']来访问：
xiaohong['middle-school']; // 'No.1 Middle School' 必须
xiaohong['name']; // '小红'
xiaohong.name; // '小红'
```

如果访问一个不存在的属性返回undefined

##### 增加或删除属性

```html
var xiaoming = {
    name: '小明'
};
xiaoming.age; // undefined
xiaoming.age = 18; // 新增一个age属性
xiaoming.age; // 18
delete xiaoming.age; // 删除age属性
xiaoming.age; // undefined
delete xiaoming['name']; // 删除name属性
xiaoming.name; // undefined
delete xiaoming.school; // 删除一个不存在的school属性也不会报错
```

##### 检测属性

如果我们要检测`xiaoming`是否拥有某一属性，可以用`in`操作符：

```
var xiaoming = {
    name: '小明',
    birth: 1990,
    school: 'No.1 Middle School',
    height: 1.70,
    weight: 65,
    score: null
};
'name' in xiaoming; // true
'grade' in xiaoming; // false
```

如果`in`判断一个属性存在，这个属性不一定是`xiaoming`的，它可能是`xiaoming`继承得到的：

要判断一个属性是否是`xiaoming`自身拥有的，而不是继承得到的，可以用`hasOwnProperty()`方法：

```
var xiaoming = {
    name: '小明'
};
xiaoming.hasOwnProperty('name'); // true
xiaoming.hasOwnProperty('toString'); // false
```

##### 方法

```html
var xiaoming = {
    name: '小明',
    birth: 1990,
    age: function () {
        var y = new Date().getFullYear();
        return y - this.birth;
    }
};
xiaoming.age(); 
```

##### 构造函数

类似Java中的类

```html
function 构造函数名(){
	this.属性=值;
	this.方法=function(){

	}
}
new 构造函数名();
//1.构造函数名首字母要大写

function Star(uname,age,sex){
	this.name=uname;
	this.age=age;
	this.sex=sex;
	this.sing=function(sang){
		console.log(sang);
	}
}
var t=new Star('张三','23','男')
t.sang('saf');
```

##### 遍历

```html
for(var k in obj){
	console.log(k);
	console.log(obj[k]);
}
```



#### 内置对象

文档：https://developer.mozilla.org/zh-CN/

##### Math

Math.PI  圆周率
Math.max(1,45,32,65)  最大值
Math.min()  最小值
Math.floor()  向下取整，往最小了取值
Math.ceil()   向上取整，往大了取
Math.round()   四舍五入   .5特殊，往大了取
Math.abs() 绝对值
Math.random() 返回范围为[0,1)之间的小数

##### Date

**创建**

```html
1.使用Date 如果没有参数 返回当前系统的当前时间
var date =new Date();
2.参数的常用写法 数字型 或者是 字符串型
var date =new Date(2019,10,1);//返回的是11月不是10月，月份从0开始
var date =new Date('2019-10-1 8:8:8');//返回的是10月
```

**方法**

```html
Date.getFullYear()//返回当前日期的年
Date.getMouth()//返回当前日期的月份（0-11）
Date.getDate()//返回当天日期
Date.getDay()//获取星期几（周日0-周六6）
Date.getHours()//获取当前小时
Date.getMinutes()//获取当前分钟
Date.getSeconds()//获取当前秒钟

Date.getTime()// 返回从 1970 年 1 月 1 日至今的毫秒数。
Date.valueOf()//返回从 1970 年 1 月 1 日至今的毫秒数
var date=+new Date();//+new Date()返回的就是总的毫秒数
Date.now()
```



##### Array

##### String





#### strict模式

正常并不强制要求用`var`申明变量。如果一个变量没有通过`var`申明就被使用，那么该变量就自动被申明为全局变量

在strict模式下运行的JavaScript代码，强制通过`var`申明变量，未使用`var`申明变量就使用的，将导致运行错误。
启用strict模式的方法是在JavaScript代码的第一行写上：

```
'use strict';
```



### 函数

#### 函数定义和调用

定义

```html
function abs(x) {
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}


var abs = function (x) {
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
};
//在这种方式下，function (x) { ... }是一个匿名函数，它没有函数名。但是，这个匿名函数赋值给了变量abs，所以，通过变量abs就可以调用该函数。
```

调用

```html
abs(10); // 返回10
abs(); // 返回NaN
abs(10, 'blablabla'); // 返回10,JavaScript允许传入任意个参数而不影响调用
```

#### return

```html
function foo() {
    return { name: 'foo' };
}
//多行写法。JavaScript引擎在行末自动添加分号的机制。
function foo() {
    return { // 这里不会自动加分号，因为{表示语句尚未结束
        name: 'foo'
    };
}
```





#### arguments

只在函数内部起作用，将传入的所有参数搞成一个数组。类似array但不是array。

```html
function foo(x) {
    console.log('x = ' + x); // 10
    for (var i=0; i<arguments.length; i++) {
        console.log('arg ' + i + ' = ' + arguments[i]); // 10, 20, 30
    }
}
foo(10, 20, 30);
```

#### rest

rest参数用于获取函数的多余参数

```html
function foo(a, b, ...rest) {
    console.log('a = ' + a);
    console.log('b = ' + b);
    console.log(rest);
}

foo(1, 2, 3, 4, 5);

function add (...values){
　　let sum = 0;
　　for (var val of values) {
　　	sum += val;
　　}
　　return sum;

}

add(2, 5, 3)  //输出 10
```

如果传入的参数连正常定义的参数都没填满，rest参数会接收一个空数组（注意不是undefined）。

#### 变量作用域

JavaScript的函数在查找变量时从自身函数定义开始，从“内”向“外”查找。如果内部函数定义了与外部函数重名的变量，则内部函数的变量将“屏蔽”外部函数的变量。



没有块级作用域，用let代替var声明一个块级作用域变量

```
function foo() {
    var sum = 0;
    for (let i=0; i<100; i++) {
        sum += i;
    }
    // SyntaxError:
    i += 1;
}
```

#### 常量

关键字const来定义常量，const与let都具有块级作用域，定义后不能修改值

```html
const PI = 3.14;
PI = 3; // 某些浏览器不报错，但是无效果！
PI; // 3.14
```

#### 解构赋值

```html
var [x, y, z] = ['hello', 'JavaScript', 'ES6'];
//x='hello',y='JavaScript',z='ES6'
let [x, [y, z]] = ['hello', ['JavaScript', 'ES6']];
let [, , z] = ['hello', 'JavaScript', 'ES6']; // 忽略前两个元素，只对z赋值第三个元素
z; // 'ES6'

//如果需要从一个对象中取出若干属性
var person = {
    name: '小明',
    age: 20,
    gender: 'male',
    passport: 'G-12345678',
    school: 'No.4 middle school',
    address: {
        city: 'Beijing',
        street: 'No.1 Road',
        zipcode: '100001'
    }
};
var {name, address: {city, zip}} = person;
name; // '小明'
city; // 'Beijing'
zip; // undefined, 因为属性名是zipcode而不是zip
// 注意: address不是变量，而是为了让city和zip获得嵌套的address对象的属性:
address; // Uncaught ReferenceError: address is not defined

```

使用解构赋值对对象属性进行赋值时，如果对应的属性不存在，变量将被赋值为undefined

```html
//如果要使用的变量名和属性名不一致，可以用下面的语法获取：
var person = {
    name: '小明',
    age: 20,
    gender: 'male',
    passport: 'G-12345678',
    school: 'No.4 middle school'
};

// 把passport属性赋值给变量id:
let {name, passport:id} = person;
name; // '小明'
id; // 'G-12345678'
// 注意: passport不是变量，而是为了让变量id获得passport属性:
passport; // Uncaught ReferenceError: passport is not defined
```

使用默认值

```html
var person = {
    name: '小明',
    age: 20,
    gender: 'male',
    passport: 'G-12345678'
};

// 如果person对象没有single属性，默认赋值为true:
var {name, single=true} = person;
name; // '小明'
single; // true
```

```html
// 声明变量:
var x, y;
// 解构赋值:
{x, y} = { name: '小明', x: 100, y: 200};
// 语法错误: Uncaught SyntaxError: Unexpected token =
//JavaScript引擎把{开头的语句当作了块处理，于是=不再合法。

解决办法
({x, y} = { name: '小明', x: 100, y: 200});
```

如果一个函数接收一个对象作为参数，那么，可以使用解构直接把对象的属性绑定到变量中。例如，下面的函数可以快速创建一个`Date`对象：

```
function buildDate({year, month, day, hour=0, minute=0, second=0}) {
    return new Date(year + '-' + month + '-' + day + ' ' + hour + ':' + minute + ':' + second);
}

buildDate({ year: 2017, month: 1, day: 1 });
// Sun Jan 01 2017 00:00:00 GMT+0800 (CST)
buildDate({ year: 2017, month: 1, day: 1, hour: 20, minute: 15 });
// Sun Jan 01 2017 20:15:00 GMT+0800 (CST)
```



### BOM浏览器对象

#### window对象的常见事件

##### 窗口加载事件

```html
window.onload = function () { }
window.addEventListener("load", function () { });
```

当文档内容完全加载会触发该事件(包括图像、脚本文件、CSS文件等)。使用该事件后JavaScript可以写在任意位置，不用考虑先后顺序。

注意：window.onload传统注册事件方式只能写一次，如果有多个，会以最后一个window.onload为准

```html
document.addEventListener("DOMContentLoaded", function () {});
```

DOMContentLoaded事件触发时，仅当DOM加载完成，不包括样式表、图片、flash等等。ie9以上支持。
如果页面的图片很多的话，从用户访问到onload触发可能需要较长的时间，交互效果就不能实现，必然影响用户的体验。

##### 调整窗口大小事件

```html
window.onresize=function(){}
window.addEventListener("resize",function(){});
```

window.onresize当窗口大小发生变化就会触发的事件

我们经常利用这个事件完成响应式布局。window.innerWidth当前屏幕的宽度

#### 定时器

##### 两种定时器

```html
setTimeout(调用函数,[延迟的毫秒数]);//设置定时器，只调用一次就结束了
clearTimeout(timeoutID);//停止定时器
setInterval(调用函数,[延迟的毫秒数]);//重复调用一个函数，每隔这个时间，就去调用一次回调函数
clearInterval(timeoutID);//停止定时器
```

setTimeout()这个调用函数我们也称为回调函数callback。

回调函数：上一件事情干完后，再回头调用这个函数


```html
<script>
    setTimeout(function () {
        console.log('调用');
    }, 2000)
    function callback() {
        console.log('调用');
    }
    var timer1 = setTimeout(callback, 3000);
    var timer2 = setTimeout('callback()', 3000);
    
    clearTimeout(timer1);
</script>
```



#### js执行机制

js是单线程任务。

##### 同步和异步

**同步**：前一个任务结束后再执行后一个任务
同步任务都在主线程上执行，形成一个执行栈

**异步**：同时做多个任务
js的异步是通过回调函数实现的
异步任务的三种类型：
1.普通事件，如click、resize等
2.资源加载，如load、error等
3.定时器，包括setInterval、setTimeout等
异步任务相关回调函数添加到任务队列中

1.先执行 执行栈中的同步任务 
2.在执行的过程中，若遇到异步任务，则提交给异步进程处理 
3.在异步进程中，若监听到某异步任务已经被触发了，即发送了点击，或者定时器时间已到，则将其放入任务队列中 
4.执行栈中的所有同步任务执行完后，主线程通过事件循环机制不断的查询任务队列中是否存在异步任务，若存在，则立即调入执行栈中执行 

#### location对象

用于获取或者设置URL

| location对象属性  | 返回值                         |
| ----------------- | ------------------------------ |
| location.href     | 获取或者设置整个url            |
| location.host     | 返回主机(域名) www.itheima.com |
| location.port     | 返回端口号 如未写返回空字符串  |
| location.pathname | 返回路径                       |
| location.search   | 返回参数                       |
| location.hash     | 返回片段                       |



| location对象方法   | 返回值                                                       |
| ------------------ | ------------------------------------------------------------ |
| location.assign()  | 跟href一样，可以跳转页面。记录浏览历史，所以可以实现后退功能。 |
| location.replace() | 替换当前页面，因为不记录历史，所以不能后退页面               |
| location.reload()  | 重新加载页面，相当于刷新按钮或者f5如果参数为true强制刷新ctrl+f5 |

```html
<script>
    var btn = document.querySelector('button');
    btn.addEventListener('click', function () {
        //location.assign('http://www.baidu.com');
        location.replace('http://www.baidu.com');
        location.reload();
    })
</script>
```



#### navigator对象

```html
<script>
        //navigator包含了用户浏览器的信息，通过navigator.userAgent可以获取请求路径中user-agent的值，即客户端的设备信息
        if ((navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i))) {
            window.location.href = "../H5/index.html"; //手机
        }
    </script>
```



#### history对象

| history对象方法   | 作用                                                      |
| ----------------- | --------------------------------------------------------- |
| history.back()    | 可以后退功能                                              |
| history.forward() | 前进功能                                                  |
| history.go(参数)  | 前进后退功能 参数如果是1 前进1个页面 如果是-1 后退1个页面 |

```html
<script>
    var btn = document.querySelector('button');
    btn.addEventListener('click', function () {
        history.back();
        history.back();
        history.go(1);
    })
</script>
```





### DOM

通过DOM接口可以改变网页的内容、结构和样式。

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
   
   ​			⑤. querySelector('选择器')：根据指定选择器返回第一个元素对象
   
   ​			⑥. querySelectorAll('选择器')：根据指定选择器返回所有元素对象

```html
<body>
    <div id="div1">div1</div>
    <div id="div2">div2</div>
    <div id="div3">div3</div>

    <div class="cls1">div4</div>
    <div class="cls1">div5</div>

    <input type="text" name="username">

<script>
    var divs = document.getElementsByTagName("div");
    for(var i=0;i<divs.length;i++){
        console.log(divs[i]);
    }

    var div_cls = document.getElementsByClassName("cls1");
    alert(div_cls.length)

    var ele_username = document.getElementsByName("username");
    alert(ele_username.length)
</script>
    <div class="box">盒子1</div>
    <div class="box">盒子2</div>
    <script>
        var fistBox=document.querySelector('.box');
        var allBox=document.querySelectorAll('.box');
    </script>
</body>
```

##### 获取body和html元素

```html
<body>
    <script>
        //1.获取body元素
        var bodyEle = document.body;
        console.log(bodyEle);
        //2.获取html元素
        var htmlEle = document.documentElement;
        console.log(htmlEle);
    </script>
</body>
```



##### 事件

###### 注册事件

```html
<button>按钮1</button>
<button>按钮2</button>
<button>按钮3</button>
<script>
    var btns = document.querySelectorAll('button');
    // 方式一：传统注册方式
    // 注意：以on开头,无兼容性问题
    // 同一元素，同一事件处理函数，只有最近的是有效的
    btns[0].onclick = function () {
        alert(11);
    }
    btns[0].onclick = function () {
        alert(22);
    }
    // 方式二：方法监听注册方式  
    // 注意：click不带on   【兼容性】IE9以上才支持
    // 同一元素，同一事件可以添加多个监听器（即事件处理函数）,按注册顺序依次执行
    btns[1].addEventListener('click', function () {
        alert(33);
    });
    btns[1].addEventListener('click', function () {
        alert(44)
    });

    // 方式三：IE9以前的方式，只有ie9之前的浏览器能识别这个函数
    btns[2].attachEvent('onclick', function () {
        alert(55);
    });
</script>
```

###### 删除事件

```html
<div>111</div>
<div>222</div>
<div>222</div>
<script>
    var divs = document.querySelectorAll('div');
    // 方式一：
    divs[0].onclick = function () {
        alert(111)
        this.onclick = null;//弹一次后不再弹出
    }

    // ♥ 方式二：
    divs[1].addEventListener('click', fn)

    function fn() {
        alert(22)
        divs[1].removeEventListener('click', fn)
    }

    // 方式三：
    divs[2].attachEvent('onclick', fn)

    function fn() {
        alert(33)
        divs[2].detachEvent('onclick', fn)
    }
</script>
```





###### target和this的区别

```html
<ul>
    <li>111</li>
    <li>222</li>
    <li>333</li>
</ul>
<script>
    var ul = document.querySelector('ul')
    ul.addEventListener('click', function (e) {
        // 1.  e.target指向的是触发事件的对象（元素）
        console.log(e.target); //<li>111</li>
        // 2.  this指向的是绑定事件的元素
        console.log(this); //<ul>...</ul>
        // 3.  e.currentTarget同this一样，但一般不这么使用
        console.log(e.currentTarget); //<ul>...</ul>
    })

    // 获取触发事件的对象e.target的兼容性处理：兼容IE6/7/8
    // ul.onclick = function(e) {
    //     e = e || window.event
    //     var target = e.target || e.srcElement
    //     console.log(target);
    // }

    ul.addEventListener('mouseover', function (e) {
        // 4.  e.type指向的是事件的类型
        console.log(e.type); //mouseover
    })
    ul.addEventListener('mouseout', function (e) {
        console.log(e.type); //mouseout
    })
</script>
```

###### 阻止默认行为

```html
<a href="https://www.baidu.com">百度</a>
<script>
    //阻止默认行为（事件） 让链接不跳转 或者让提交按钮不提交
    var a = document.querySelector('a');
    a.addEventListener("click", function (e) {
        e.preventDefault();
    });
    a.onclick = function (e) {
        e.preventDefault();//普通浏览器
        e.returnValue;//低版本浏览器ie678
        //利用return false也能阻止默认行为，没有兼容性问题
        return false;
    }
</script>
```

###### 阻止冒泡

```html

<div class="father">
    <div class="son">

    </div>
</div>
<script>
    var father = document.querySelector(".father")
    father.addEventListener('click', function () {
        alert('father');
    })

    var son = document.querySelector('.son')
    son.addEventListener('click', function (e) {
        alert('son');
        e.stopPropagation();//阻止冒泡
        e.cancelBubble=true;//ie678的方法
    })

    // 阻止事件冒泡，兼容性写法
    son.onclick = function (e) {
        if (e && e.stopPropagation) {
            e.stopPropagation();
        } else {
            window.event.cancelBubble = true;
        }
    }
</script>
```

###### 事件委托

事件委托也叫事件代理，事件委派

面试：事件委托的原理？
不在子节点单独设置事件监听器，而将事件监听器设置在父节点上，再利用冒泡原理使每一个子节点都能触发该事件

事件委托的作用：只操作一次Dom，提高了程序的性能。



```html
/*给ul注册点击事件，然后利用事件对象的target来找到当前点击的li，因为点击li，事件会冒泡到ul上，ul有注册事件，就会触发事件监听器*/
<ul>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
</ul>

<script>
    var ul = document.querySelector('ul');
    ul.addEventListener('click', function (e) {
        //alert('知否知否');
        e.target.style.backgroundColor = 'pink';
    })
</script>
```



###### 常见的鼠标事件

onclick 鼠标点击左键触发
onmouseover 鼠标经过触发
onmouseout 鼠标离开触发
onfocus 获得鼠标焦点触发
onblur 失去鼠标焦点触发
onmouseup 鼠标弹起触发
onmousemove 鼠标移动触发
onmousedown 鼠标按下触发
oncontextmenu 事件在元素中用户右击鼠标时触发并打开上下文菜单。
onselectstart 当目标对象刚开始被选择

```html
<body>
    文字文字
    <script>
        //1.contextmenu 可以禁用右键菜单
        document.addEventListener('contextmenu', function (e) {
            e.preventDefault();
        })
        //2.禁止选中文字
        document.addEventListener('selectstart', function (e) {
            e.preventDefault();
        })
    </script>
</body>
```

**鼠标事件对象**

e.clientX 返回鼠标相对于浏览器窗口可视区的x坐标
e.clientY 返回鼠标相对于浏览器窗口可视区的y坐标
e.pageX  返回鼠标相对于文档页面的x坐标 ie9+支持（滚动后点击区域和页面顶端的距离）
e.pageY   返回鼠标相对于文档页面的y坐标 ie9+支持（滚动后点击区域和页面顶端的距离）
e.screenX  返回鼠标相对于电脑屏幕的x坐标
e.screenY  返回鼠标相对于电脑屏幕的y坐标

```html
<script>
    document.addEventListener('click', function (e) {
        // 获取鼠标在可视区的坐标,可视区即展示在用户面前的页面区域
        console.log(e.clientX);
        console.log(e.clientY);
        console.log('------------');
        // 获取鼠标在整个html页面的坐标。一般实际应用使用pageX和pageY
        console.log(e.pageY);
        console.log('------------');
        // 获取鼠标在电脑屏幕的坐标，即整个电脑屏幕，15寸这个
        console.log(e.screenX);
        console.log(e.screenY);
    })
</script>
```



###### 常用键盘事件

onkeyup 某个键盘按键被松开时触发
onkeydown 某个键盘按键被按下时触发
onkeypress   某个键盘按键被按下时触发 但它不识别功能键 比如 ctrl shift 箭头等

三个事件的执行顺序：keydown——keypress——keyup

```html
<body>
    <script>
        document.addEventListener('keyup', function(e) {
            // keycode返回的是键的ASCII值，不需要记ASCII的值，可以通过触发键盘事件获取想要的keyCode的值
            console.log('keyup', e.keyCode);
        });
        // keyup事件和keydown事件是不区分大小写的
        // keypress事件可以区分大小写
        document.addEventListener('keypress', function(e) {
            console.log('keypress', e.keyCode);
        })
    </script>
```



##### 操作元素

1. 改变元素内容

element.innerText:从起始位置到终止位置的内容，但它去除html标签，同时空格和换行也会去掉。不识别html标签，会直接当文字显示出来。
element.innerHTML:起始位置到终止位置的全部内容，包括html标签，同时保留空格和换行。识别html标签，会显示相应的效果。W3C标准。

```html
<body>
    <button>显示当前系统时间</button>
    <div>某个时间</div>
    <script>
        //当我们点击了按钮，div里的文字发生变化
        //1.获取元素
        var btn = document.querySelector('button');
        var div = document.querySelector('div');
        btn.onclick = function () {
            div.innerText = '2020';
        }
        //这两个属性是可读写的 可以获取元素里面的内容
        console.log(div.innerText);
    </script>
</body>
```

2. src、href

3. id、alt、title

4. 表单中：type、value、checked、selected、disabled

5. 样式属性操作
   element.style 行内样式操作
   element.className  类名样式操作

   注意：
   ①.JS里面的样式采取驼峰命名法 比如fontSize、backgroundColor
   ②.JS修改style样式操作，产生的是行内样式，css权重比较高

```html
//element.style 行内样式操作
<body>
    <div></div>

    <script>
        var div = document.querySelector('div');
        div.onclick = function () {
            //div.style里面的属性采取驼峰命名法
            this.style.backgroundColor = 'purple';
            this.style.width = '250px';
        }
    </script>
</body>
```

```html
//element.className  类名样式操作
<style>
        .change {
            background-color: purple;
            color: #fff;
            font-size: 25px;
            margin-top: 100px;
        }
</style>
<script>
        var text = document.querySelector('div');
        text.onclick = function () {
            this.className = 'change';//修改class，覆盖之前的class
        }
</script>
```

##### 排他算法

点击按钮，变粉色，再次点击其他按钮，先把所有的按钮变灰色，被点击的按钮变粉色。

```html
<body>
    <button>按钮1</button>
    <button>按钮2</button>
    <button>按钮3</button>
    <button>按钮4</button>
    <button>按钮5</button>

    <script>
        //1.获取所有按钮元素
        var btns = document.getElementsByTagName('button');
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function () {
                //先把所有的按钮背景颜色去掉
                for (var j = 0; j < btns.length; j++) {
                    btns[j].style.backgroundColor = '';
                }
                this.style.backgroundColor = 'pink';
            }
        }
    </script>
</body>
```



##### 自定义属性的操作

h5规定自定义属性要以data-开头 如data-index

###### 获取元素的属性值

element.属性 ：获取内置属性值（元素本身自带的属性）

element.getAttribute('属性') ：主要获取自定义的属性值

```html
<div id="demo" index="1"></div>
<script>
    var div = document.querySelector('div');
    //1.获取元素的属性值
    //（1）element.属性
    console.log(div.id);
    //(2)element.getAttribute('属性')
    console.log(div.getAttribute('index'));
</script>
```

###### 设置元素属性值

element.属性 = '值' ：设置内置属性值

element.getAttribute('属性','值')：主要设置自定义的属性值

```html
<div id="demo" index="1" class="nav"></div>
<script>
    var div = document.querySelector('div');
    div.id = 'test';
    div.setAttribute('index', 2);
    div.className = 'navs';
    div.setAttribute('class', 'footer');
</script>
```



###### 移除属性

element.removeAttribute('属性');

```html
<div id="demo" index="1" class="nav"></div>
<script>
    var div = document.querySelector('div');
    div.removeAttribute('index');
</script>
```



##### node节点

###### 父子节点

parentNode.parentNode 返回离元素最近的父节点，找不到返回为null。
parentNode.children 返回所有的子元素节点
parentNode.firstElementChild返回第一个元素子节点，ie9以上
parentNode.lastElementChild返回最后一个元素子节点，ie9以上

```html
<div class="box">
    <span class="erweima"></span>
</div>
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
<script>
    var erweima = document.querySelector(".erweima");
    var ul = document.querySelector('ul');
    console.log(erweima.parentNode);
    console.log(ul.children);
    console.log(ul.firstElementChild);
    console.log(ul.children[0]);
</script>
```



###### 兄弟节点

node.nextElementSibling   返回当前元素的下一兄弟元素节点。ie9以上
node.previousElementSibling  返回当前元素的上一兄弟元素节点。ie9以上

```html
<div>我是div</div>
<span>我是span</span>

<script>
    var div = document.querySelector('div');
    var span = document.querySelector('span');
    console.log(div.nextElementSibling);
    console.log(span.previousElementSibling);
</script>
```

###### 创建添加节点

document.createElement('tagName')   创建元素节点

node.appendChild(child)    将一个节点添加到指定父节点的子节点列表的末尾。

node.insertBefore(child,指定元素) 将一个节点添加到父节点的指定子节点前面

```html
<ul></ul>
<script>
    //1.创建元素节点
    var li = document.createElement('li');
    //2.添加节点node.appendChild(child) node父级 child子级
    var ul = document.querySelector('ul');
    ul.appendChild(li);
    //3.node.insertBefore(child,指定元素);
    var lili = document.createElement('li');
    ul.insertBefore(lili, li);
</script>
```

###### 删除节点

node.removeChild(child) 从dom中删除一个子节点，返回删除的节点

```html
<button>删除</button>
<ul>
    <li>熊大</li>
    <li>熊二</li>
    <li>光头强</li>
</ul>
<script>
    var btn = document.querySelector('button');
    //1.获取元素
    var ul = document.querySelector('ul');
    btn.onclick = function () {
        //2.删除元素
        if (ul.children[0] == null) {
            this.disabled = true;
        } else {
            ul.removeChild(ul.children[0]);

        }
    }
</script>
```

###### 复制节点

node.cloneNode()

注意：
1.node.cloneNode()；如果括号参数为空或者为false，则是浅拷贝，只复制标签不复制里面的内容
2.node.cloneNode(true)；如果括号参数为true，则是深拷贝，复制标签复制里面的内容

```html
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
<script>
    var ul = document.querySelector("ul");
    //1.克隆节点
    var lili = ul.children[0].cloneNode(true);
    //2.添加节点
    ul.appendChild(lili);
</script>
```

###### 动态生成表格

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        table {
            width: 500px;
            margin: 100px auto;
            border-collapse: collapse;
            text-align: center;
        }

        td,
        th {
            border: 1px solid #333;
        }

        thead tr {
            height: 40px;
            background-color: #ccc;
        }
    </style>

</head>

<body>
    <table cellspacing="0">
        <thead>
            <tr>
                <th>姓名</th>
                <th>科目</th>
                <th>成绩</th>
                <th>操作</th>
            </tr>
        </thead>
        <tbody>

        </tbody>
    </table>
    <script>
        // 1.先去准备好学生的数据,对象型数组
        var datas = [{
            name: '魏璎珞',
            subject: 'JavaScript',
            score: 100
        }, {
            name: '弘历',
            subject: 'JavaScript',
            score: 98
        }, {
            name: '傅恒',
            subject: 'JavaScript',
            score: 99
        }, {
            name: '明玉',
            subject: 'JavaScript',
            score: 88
        }, {
            name: '大猪蹄子',
            subject: 'JavaScript',
            score: 0
        }];
        var tbody = document.querySelector('tbody');
        for (var i = 0; i < datas.length; i++) {
            var tr = document.createElement('tr');
            tbody.appendChild(tr);
            //var trs = document.querySelectorAll('tr')[i + 1];
            for (var k in datas[i]) {
                var th = document.createElement('th');
                th.innerHTML = datas[i][k]
                tr.appendChild(th);
            }
            var th = document.createElement('th');
            th.innerHTML = '<a href="javascript:;">删除</a>';
            tr.appendChild(th);
        }
        var as = document.querySelectorAll('a');
        for (var i = 0; i < as.length; i++) {
            as[i].onclick = function () {
                tbody.removeChild(this.parentNode.parentNode);
            }
        }

    </script>
</body>

</html>
```





### PC端网页特效

#### 元素偏移量offset系列

使用offset系列相关属性可以动态的得到该元素的位置、大小等



#### 元素可视区client系列

#### 元素滚动scoll系列

#### 动画函数封装

#### 常见的网页特效案例

