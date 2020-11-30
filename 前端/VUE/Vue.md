### Vue基础

#### Vue文档

https://cn.vuejs.org/

#### 第一个Vue程序

```vue
<div id="app">
	{{message}}
</div>
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
	var app = new Vue({
		el: '#app',
		data: {
			message: 'Hello Vue!'
		}
	})
</script>
```



### 本地应用

#### v-text

v-text指令的作用是：设置标签的内容

默认写法会替换全部内容，使用差值表达式{{}}可以替换指定内容

```html
<div id="app">
    <h2 v-text="message">深圳</h2><!-- 全部替换 -->
    <h2 v-text="message+'!'">深圳</h2><!-- 全部替换 -->
    <h2>深圳{{message+"!"}}</h2><!-- 部分替换 -->
</div>
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            message: "你好，小黑",
        }
    })
</script>
```

#### v-html

作用：设置元素的innerHTML

v-html指令内容中有html结构会被解析为标签，而v-text指令无论内容是什么，只会解析为文本。

```vue
<div id="app">
    <p v-html="content"></p>
    <p v-text="content"></p>
</div>
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            content: "<a href='http://www.itheima.com'>黑马程序员</a>"
        }
    })
</script>
```



#### v-on

作用：为元素绑定事件

```vue
<div id="app">
    <input type="button" value="事件绑定" v-on:click="dolt">
    <input type="button" value="事件绑定" v-on:monseenter="dolt">
    <input type="button" value="事件绑定" v-on:dblclick="dolt">
    <input type="button" value="事件绑定" @dblclick="dolt"><!-- v-on替换为@ -->
</div>
 

<script>
    var app = new Vue({
        el: "#app",
        methods: {
            dolt: function () {
                //逻辑
            }
        }
    })
</script>
```

传递自定义参数，事件修饰符

事件后面跟上.修饰符可以对事件进行限制

```html
<div id="app">
    <input type="button" value="点击" @click="doIt(666,'老铁')">
    <input type="text" @keyup.enter="sayHi"><!-- .enter可以限制触发的按键为回车 -->
</div>

<script>
    var app = new Vue({
        el: "#app",
        methods: {
            doIt: function (p1, p2) {
                console.log("做it");
                console.log(p1);
                console.log(p2);
            },
            sayHi: function () {
                alert("吃了没");
            }
        },
    })
</script>
```







#### v-show

作用：根据表达式的真假切换元素的显示和隐藏

指令后面的内容最终都会解析为布尔值，值为true元素显示，值为false元素隐藏。

原理：修改元素的display，实现隐藏。

```vue
<div id="app">
    <img src="地址" v-show="true">
    <img src="地址" v-show="isShow">
    <img src="地址" v-show="age>=18">
</div>

<script>
    var app = new Vue({
        el: "#app",
        data: {
            isShow: false,
            age:16
        }
    })
</script>
```





#### v-if

作用：根据表达式的真假，切换元素的显示和隐藏（操作dom元素，直接从dom树中删除添加）

```vue
<div id="app">
    <p v-if="true">我是一个p标签</p>
    <p v-if="isShow">我是一个p标签</p>
    <p v-if="表达式">我是一个p标签</p>
</div>

<script>
    var app = new Vue({
        el: "#app",
        data: {
            isShow: false
        }
    })
</script>
```





#### v-bind

设置元素的属性（比如：src，title，class）

```vue
<div id="app">
    <img v-bind:src="imgSrc">
    <img v-bind:title="imgtitle+'!!!!'">
    <img v-bind:class="isActive?'active':''">
    <img v-bind:class="{active:isActive}">
</div>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            imgSrc: "图片地址",
            imgtitle:"黑马程序员",
            isActive:false,
        }
    })
</script>
```



#### v-for

根据数据生成列表结构

```vue
<div id="app">
    <input type="button" value="添加数据" @click="add">
    <input type="button" value="移除数据" @click="remove">

    <ul>
        <li v-for="item in arr">
            {{item}}
        </li>
        <li v-for="(item,index) in arr">
            {{item}},,,{{index+1}}
        </li>
    </ul>
    <h2 v-for="item in vegetables" v-bind:title="item.name">
        {{item.name}}
    </h2>
</div>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            arr: [1, 2, 3, 4, 5],
            vegetables: [
                { name: "西兰花炒蛋" },
                { name: "蛋炒西兰花" },
            ]
        },
        methods: {
            add: function () {
                this.vegetables.push({ name: "花菜炒蛋" });
            },
            remove: function () {
                this.vegetables.shift();
            }
        }
    })
</script>
```







#### v-model

获取和设置表单元素的值（双向数据绑定）

```vue
<div id="app">
    <input type="text" v-model="message">
    <h2>{{message}}</h2>
</div>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            message: "黑马程序员",
        }
    })
</script>
```





### 网络应用

#### axios的基本使用

```
<body>
    <input type="button" value="get请求" class="get">
    <input type="button" value="post请求" class="post">
    <!-- 官网提供的 axios 在线地址 -->
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <script>
        /*
            接口1:随机笑话
            请求地址:https://autumnfish.cn/api/joke/list
            请求方法:get
            请求参数:num(笑话条数,数字)
            响应内容:随机笑话
        */
        document.querySelector(".get").onclick = function () {
            axios.get("https://autumnfish.cn/api/joke/list?num=3")
                .then(function (response) {
                    console.log(response);
                }), function (err) {
                    console.log(err);

                }
        }
        /*
             接口2:用户注册
             请求地址:https://autumnfish.cn/api/user/reg
             请求方法:post
             请求参数:username(用户名,字符串)
             响应内容:注册成功或失败
         */
        document.querySelector(".post").onclick = function () {
            axios.post("https://autumnfish.cn/api/user/reg",
                { username: "vinvin" }).then(function (response) {
                    console.log(response);
                }), function (err) {
                    console.log(err);

                }
        }
    </script>
</body>
```

