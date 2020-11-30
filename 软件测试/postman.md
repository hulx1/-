## 接口的组成

URL   接口地址

method   接口类型   get   post

code    状态码  
200 （接口运行正常）   400（接口发送的具有语法错误）   404（接口地址输入不正确）   405（接口类型不正确）    500（接口代码有问题内部服务器错误）

Headers    请求头（客户端的一些信息记录在这里面）

response    返回数据

data 接口发送的数据

![post-json](图\post-json.png)

x-www-form-urlencoded对应于Content-Type头域为x-www-form-urlencoded的类型，是以键值对形式发送的表单参数，同时参数会携带在url中

form-data对应与Content-Type的multipart/form-data类型，既可以发送键值对也可以进行文件参数传递

raw可以使用请求体原始格式编辑各Content-Type类型对应的参数格式，直接按请求体的格式来进行内容发送

binary选项用于发送文件内容请求



**登陆后进行操作的页面**

登录页面获取token

![token](图\token.png)

填token

![token2](图\token2.png)





## 参数化

用一个变量代替经常重复使用的值

token=cbe58bfc8e5b7681edcb80cuhuhnivnive28563e54aa11fa01

host=http://192.144.148.91:2333

### 局部变量

定义

![参数化](图\参数化.png)

使用

![参数化1](图\参数化1.png)

局部变量必须在下框中选择了才能生效，全局变量不用选择

![局部变量](图\局部变量.png)

### 自定义脚本

![自动脚本](图\自动脚本.png)

获取环境变量

var id=pm.environment.get("inspirerid");
console.log(id)//控制台输出

设置环境变量

pm.environment.set("variable_key", "variable_value");



将登录页面获取的token值保存到局部变量

![保存token](图\保存token.png)

### 断言

自动判断测试是否成功

![断言1](图\断言1.png)

![断言2](图\断言2.png)

