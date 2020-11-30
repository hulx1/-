*线程状态** 基本类型及计算

long num6 =3000000L;//(大写L)
float num7=2.5F;
布尔 boolean
强制转换 int num=(int)100L;
布尔类型不能强制转换

取余%
整除/

自增++  +=
自减少--  -=

#### 输入

```java
import java.util.Scanner;
Scanner sc=new Scanner(System.in);
String name=sc.nextLine();
int age=sc.nextInt();
```

#### if for while

max=a>b?a:b;
if for while 和c++用法一致

###  函数

```java
public static int ssum(int a,int b) {
	return a+b;
}
```

小驼峰式命名





### 数组

#####  动态数组

数据类型[] 数组名称=new 数据类型[数组长度]

```java
int[] arrayA=new int[300];
```

整数默认为0
浮点默认为0.0
字符型默认为‘\u0000’
布尔默认为false
引用类型为null

foreach循环：只用于读取数组元素的值，不能修改元素的值

```java
int[] array= {10,20,30};
for(int m:array) {
	System.out.println(m);
}
```

#####  静态数组

数据类型[] 数组名称=new 数据类型[]{元素1，元素2，元素3......}

```java
int[] arrayB=new int[]{5,15,25};
```

省略

```java
int[] arrayC= {10,20,30};
```

##### 数组函数

```java
public static  void printArray(int[] array){
	for(int i=0;i<array.length;i++){
		System.out.println(array[i]);
	}
}
//调用
printArray(array);
```

函数返回数组

```java
public static  int [] printArray(){
	int[] array=new int[10];
	return array;
}
//调用
int result=printArray();
```

##### 对象数组

Person[] array=new Person[3];





### 类

##### 定义类

```java
public class Student {
	String name;
	int age;
	public void eat() {
		System.out.println("eat");
	}
	public void sleep() {
		System.out.println("sleep");
	}
	public void study() {
		System.out.println("study");
	}
}
```



##### 创建对象

1.导包 
import 包名称.类名称;
当于和当前类属于同一包的情况，可省略导包语句
2.创建
类名称 对象名=new 类名称();
Student stu=new Student();
3.使用
使用成员变量：对象名.成员变量名
使用成员方法：对象名.成员方法名(参数)



##### private修饰符

private int age;
一旦用private进行修饰，在本类中可直接访问，超出本类无法访问
用构造和赋值函数解决setXxx,getXxx 布尔型get方法写成isXxx，set不变



##### this

当方法的局部变量和类的成员变量重名的时候在本类方法中访问本类的成员变量/另一个成员方法

```java
public class Student {
	String name;
	public void sayHello(String name) {
		System.out.println(this.name+name);
	}
}
```



##### 构造方法

```java
public Student(){

}
```



##### 一个标准的类

1.所有的成员变量都要用private
2.为每个成员变量编写set和get方法
3.编写一个无参数的构造方法
4.编写一个全参数的构造方法





##### 匿名对象

不设置对象颜色，只能用一次
new 类名称();
new.Person().name;

#### 常用类

java.lang包下的内容不需要导包

##### Random

import java.util.Random;
Random random=new Random();
int num=random.nextInt();
int num=random.nextInt(n);表示范围为[0,n)中取随机数
若左边范围不为0则可以整体进行加减



##### Arraylist

集合长度可以随便改变
Arraylist<E>装在集合中的所有元素全部都是统一的E型，类型只能是引用类型不能是基本类型
如果希望在ArrayList中存储基本类型数据，必须使用包装类

基本类型	   包装类
byte		       Byte
short		     Short
int		          Integer【特殊】
long		       Long
float		       Float
double		   Double
char		        Character
boolean	     Boolean

对于ArrayList集合来说，直接打印得到的不是地址值，而是内容。如果内容是空，得到的是空的中括号
==创建==   ArrayList<String> list=new ArrayList<>();
==添加==  list.add("aaa");
==读取==  list.get(index)   返回此列表中指定位置上的元素。
==删除==  list.remove(index)  删除此列表中指定位置上的元素   
==获取集合长度==  list.size()

##### Math

##### String

字符串拼接 System.out.println("Hello"+"Word");||str="java";System.out.println(str+20);

##### Arrays





#### 继承

单继承（一个类的直接父类只能有唯一一个）
可多级继承（可以有爷爷）



##### super()

子类构造方法中有一个默认隐含的super()调用（无参，有参要自己写），所以一定是先调用父类构造再执行子类构造法
super的父类构造调用，必须是子类构造方法的第一个语句。不能一个子类构造调用多次super构造。

super（）
在子类的成员方法中，访问父类的成员变量/方法/构造方法



##### static修饰

static修饰的成员变量和方法，从属于类。普通变量和方法从属于对象。



#### 抽象

图形（父类）-》正方形（子）
                       -》三角形（子）
                       -》圆形（子）

抽象方法：加上关键字abstract，然后去掉大括号，直接分号结束。
抽象类：抽象方法所在的类必须是抽象类，在class之前写上abstract即可

```java
public abstract class Animal {
	public abstract void eat();
}
```


1.不能直接new抽象对象
2.必须用子类来继承抽象父类
3.子类必须覆盖重写抽象父类中所有的抽象方法（每一个都要） 

### 接口

就是一种公共的规范标准
public interface 接口名称(){
}
包含内容：
常量，抽象方法，默认方法，静态方法，私有方法（注意版本）
1.不能直接使用必须有一个实现类来实现该接口
格式
public class 实现类名称 implements 接口名称{
}
2.接口的实现类必须覆盖重写接口中的所有抽象方法

```java
public interface mymy {
	public abstract void methodAbs1() ;//是抽象方法
	abstract void methodAbs2() ;//是抽象方法
	public  void methodAbs3() ;//是抽象方法
	void methodAbs4() ;//是抽象方法
}（可选择性忽略public/abstract）


public class mymyimpl implements mymy{@Override
	public void methodAbs1() {
		System.out.println("这是第一个方法");
		
	}
@Override
	public void methodAbs2() {
		System.out.println("这是第二个方法");
	}
@Override
	public void methodAbs3() {
		System.out.println("这是第三个方法");
	}
@Override
	public void methodAbs4() {
		System.out.println("这是第四个方法");
	}

}

public class text {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		mymyimpl my=new mymyimpl();
		my.methodAbs1();
		my.methodAbs2();
		my.methodAbs3();
		my.methodAbs4();
	}

}
```



在接口中写默认方法要加关键字default，实现类中可以覆盖
public default void methodDefault() {
	
}

调用只能通过接口名称调用静态方法。mymy.methodDefault();

接口中的私有方法
1.普通私有方法，解决多个默认方法之间重复代码问题
格式：
private 返回值类型 方法名称(参数列表){
	方法体
}
2.静态私有方法，解决多个静态方法之间重复代码问题
private static 返回值类型 方法名称(参数列表){
	方法体
}

接口中也可以有“成员变量”，但是必须使用public static final三个关键字进行修饰
从效果上这其实就是接口的常量，接口中常量的名称，使用完全大写的字母，用下划线进行分隔
public static final int NUM=10;
//一旦赋值不可更改

类能继承多个接口
public class a implements b,c{
}
1.接口没有静态代码块或者构造方法的
2.如果实现类所实现的多个接口当中，存在重复的抽象方法，那么只需要覆盖重写一次即可
3.如果实现类没有覆盖重写所有接口当中的所有抽象方法，那么实现类就必须是一个抽象类
4.如果实现类所实现的多个接口当中，存在重复的默认方法那么实现类一定要对冲突的默认方法进行覆盖重写
5.一个类如果直接父类当中的方法和接口当中的默认方法产生了冲突，优先使用法雷当中的方法

接口与接口之间是多继承的。
public interface a extends b,c{(a,b,c均为接口)
}
多个父接口当中的抽象方法如果重复没关系
多个父接口当中的默认方法如果重复，那么子接口必须进行默认方法的覆盖重写，而且要带着default关键字





### 多态

父类引用指向子类对象
格式：
父类名称 对象名 =new 子类名称（）
接口名称 对象名=new 实现类名称（）
当使用多态方式调用方法时，首先检查父类中是否有该方法，如果没有，则编译错误；如果有，再去调用子类的同名方法。

直接通过对象名访问成员变量：看等号左边是谁，优先用谁，没有则往上找（从子到父为向上找）
间接通过成员方法访问成员变量：看方法属于谁，优先用谁，没有则向上找show 看new那边（子类没有覆盖重写就是父。如果覆盖重写，就是子。）

运行访问成员方法看new的是谁优先用谁，但因为编译看左，运行前编译需要通过，所以父类一定要有该成员方法才能运行

多态的使用：将实现子类直接传入接口类型的方法中从而调用重写的子类方法

```java
public interface USB {
    public abstract void open();
    public abstract void close();
}
```

```java
public class Computer {
    public void powerOn(){
        System.out.println("笔记本开机");
    }
    public void powerOff(){
        System.out.println("笔记本关机");
    }
    public void useDevice(USB usb){
        usb.open();
        usb.close();
    }
}
```

```java
public class Mouse implements USB {

    @Override
    public void open() {
        System.out.println("打开鼠标");
    }

    @Override
    public void close() {
        System.out.println("关闭鼠标");
    }
}
```

```java
public class text {
    public static void main(String[] args) {
        Computer computer=new Computer();
        computer.powerOn();
        computer.powerOff();
        USB usbMouse=new Mouse();
        computer.useDevice(usbMouse);
        computer.powerOff();
    }
}
```



#### 对象的向上转型

对象的向上转型，其实就是多态写法：
格式： 父类名称 对象名=new 子类名称();               Animal animal=new Cat()
含义：右侧创建一个子类对象，把它当做父类来看待使用。 创建了一只猫，当做动物来看待
注意事项：向上转型一定是安全的。从小范围转向了大范围。对象一旦向上转型为父类，那么就永远无法调用子类原本特有的内容。

#### 对象的向下转型（还原）

格式：子类名称 对象名=（子类名称） 父类对象;
含义：将父类对象，还原成为本来的子类对象
Animal animal=new Cat()
Cat cat=(Cat) animal;
必须保证本来创建的是猫才能向下转型成猫

如何才能知道一个父类引用的对象本来是子类
格式：
对象 instanceof 类名称
会return一个布尔值

```java
if(animal instanceof Dog){
	Dog dog=(Dog) animal;
}
```



###  final

final关键字代表最终的、不可变的。
用来修饰类、方法、局部变量、成员变量



##### final修饰类

public final class 类名称{
}
当前这个类不能有任何子类，也就是该类的所有成员方法不能覆盖重写，可以覆盖重写父类



##### final修饰方法

当final修饰一个方法的时候，这个方法就是最终方法，就是不能覆盖重写
public final 返回值类型 方法名称（参数列表）{
}
对于类、方法来说，abstract关键字和final关键字不能同时使用，也就是不能被覆盖重写



##### final修饰局部变量

final int num=10；
一旦赋值就不能修改
基本类型不可变的是数据，引用类型不可变的是地址



##### final修饰成员变量

1.由于成员变量具有默认值，所以用了final后必须直接赋值（在声明的时候赋值）或者构造赋值





### 权限修饰符

四种权限修饰符：
                          public   >   protected   >   默认(default)   >   private
同一个类           YES              YES                    YES              YES
同一个包           YES              YES                     YES               NO
不同包子类       YES              YES                     NO                NO
不同包非子类    YES              NO                     NO                NO



### 内部类

如果一个事物的内部包含另一个事物的内部，那么这就是一个类内部包含另一个类。
例如，身体和心脏的关系；汽车和发动机的关系。
分类：
1、成员内部类
2、局部内部类（包含匿名内部类）

##### 成员内部类

修饰符 class 类名称{
	修饰符 class 内部类名称{
	}
}	
内用外，随意访问；外用内，需要内部对象
}

如何使用成员内部类：
1.间接方式：在外部类的方法当中，使用内部类，然后main只是调用外部类的方法。
2.直接方式：外部类名称.内部类名称 对象名=new外部类名称().内部类名称();

```java
public class Body {//外部类

    public class Heart{//成员内部类

        public void beat() {//内部类的方法
            System.out.println("心脏跳动");
            System.out.println(name);//内访问外可访问
        }
    }
    private String name;
    public void methodBody(){
        System.out.println("外部类的方法");
        Heart heart=new Heart();//方法一
        heart.beat();
    }
}

public class text {
    public static void main(String[] args) {
        Body body=new Body();
        body.methodBody();//方法一
        System.out.println("=============================");
        Body.Heart heart=new Body().new Heart();//方法一
        heart.beat();
    }
}
```

###### 内部类的同名变量访问

```java
//如果出现重名现象，那么格式是：外部类名称.this.外部类成员变量名
public class Outer {//外部类
    int num=10;//外部类的成员变量
    public class Inner{
        int num=20;//内部类成员变量
        public void methodInner() {
            int num=30;//内部方法的局部变量
            System.out.println(num);//30局部变量就近原则
            System.out.println(this.num);//20访问内部类的成员变量
            System.out.println(Outer.this.num);//10访问外部类的成员变量
        }
    }
}
```



##### 局部内部类

如果一个类是定义在一个方法内部的，那么这就是一个局部内部类。
“局部”：只有当前所属的方法才能使用它，出了这个方法外面就不能用了。
定义格式：
修饰符 class 外部类名称{
	修饰符 返回值类型 外部类方法名称（参数列表）{
		class 局部内部类名称{
			//。。。
		}
	}
}

```java
//定义及调用
public class Outer {
    public void methodInner() {
        class Inner{//局部内部类
            int num=10;
            public void methodInner() {
                System.out.println(num);
            }
        }
        Inner inner=new Inner();
        inner.methodInner();
    }
}
public class text {
    public static void main(String[] args) {
        Outer outer=new Outer();
        outer.methodInner();
    }
}
```



###### 权限修饰符

定义一个类的时候，权限修饰符的规则：
1.外部类：public/（default）
2.成员内部类：public/protected/（default）/private
3.局部内部类：什么都不能写
外部类是最外面的类，成员内部类在外部类里面一层的类，局部内部类写在外部类方法里的类。

###### 局部内部类的final

局部内部类，如果希望访问所在方法的局部变量，那么这个局部变量必须是【有效final】
备注：从java8开始，只要局部变量事实不变，那么final关键字可以省略（原因方法结束后出栈局部变量消失，而new出来的对象会在堆中持续存在，知道垃圾回收消失）

```java
public class Outer {
    public  void  methodOuter(){
        final int num=10;
        class MyInner{
            public void methodInner(){
                System.out.println(num);
            }
        }
    }
}
```



##### 匿名内部类

如果接口的实现类（或者是父类的子类）只需要使用唯一的一次，那么这种情况下就可以省略掉该类的定义，而改为使用【匿名内部类】

匿名内部类的定义格式：
接口名称 对象名 = new 接口名称(){
		//覆盖重写所有抽象方法
};

注意：
1.匿名内部类，在==创建对象==的时候，只能使用一次。（创建和obj一样方法的对象也必须重写方法）如果希望多次创建对象，而且类的内容一样的话，那么就必须使用单独定义的实现类。
2.匿名对象，在==调用方法==的时候，只能使用一次。
3.匿名内部类是省略了==实现类/子类名称==，但是匿名对象是省略了==对象名称==。

```java
public interface MyInterface {//抽象类
    void  method();
}

public class DemoMain {
    public static void main(String[] args) {
       MyInterface obj=new MyInterface() {
           @Override
           public void method() {
               System.out.println("匿名对象类实现了方法");
           }
       };
       obj.method();
        
        
        //匿名对象
        new MyInterface() {
            @Override
            public void method() {
                System.out.println("匿名对象类实现了方法");
            }
        }.method();
    }
}
```

### 类作为成员变量

```java
public class Weapon {
    private String code;//武器的代号

    public Weapon() {
    }

    public Weapon(String code) {
        this.code = code;
    }

    public String getCode() {
        return code;
    }

    public void setCode(String code) {
        this.code = code;
    }
}
```

```java
public class Hero {
    private String name;//英雄名字
    private  int age;
    private Weapon weapon;

    public Hero() {
    }

    public Hero(String name, int age, Weapon weapon) {
        this.name = name;
        this.weapon = weapon;
        this.age = age;
    }
    public void attack(){
        System.out.println("年龄为"+age+"的"+name+"用"+weapon.getCode()+"攻击");
    }
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Weapon getWeapon() {
        return weapon;
    }

    public void setWeapon(Weapon weapon) {
        this.weapon = weapon;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
public class text {
    public static void main(String[] args) {
        Hero hh=new Hero();
        hh.setName("盖伦");
        hh.setAge(20);
        Weapon weapon=new Weapon("多兰剑");
        hh.setWeapon(weapon);
        hh.attack();
    }
}
```

### 接口作为成员变量

```java
public interface Skill {
    void use();//释放技能的抽象方法
}
```

```java
public class SkillImpl implements Skill{
    @Override
    public void use() {
        System.out.println("biu~biu~biu~");
    }
}
```

```java
public class Hero {
    private String name;
    private Skill skill;

    public Hero() {
    }

    public Hero(String name, Skill skill) {
        this.name = name;
        this.skill = skill;
    }
    public void attack(){
        System.out.println("我叫"+name+",开始释放技能");
        skill.use();
        System.out.println("释放技能完成");
    }
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Skill getSkill() {
        return skill;
    }

    public void setSkill(Skill skill) {
        this.skill = skill;
    }
}

```

```java
public class text {
    public static void main(String[] args) {
        Hero hero=new Hero();
        hero.setName("艾希");
       // hero.setSkill(new SkillImpl());
        //hero.attack();
        //使用匿名内部类
        Skill skill=new Skill() {
            @Override
            public void use() {
                System.out.println("pia~pia~pia~");
            }
        };
        hero.setSkill(skill);
        hero.attack();
    }
}
```

### Object类

###### 概述

`java.lang.Object`类是Java语言中的根类，即所有类的父类。它中描述的所有方法子类都可以使用。在对象实例化的时候，最终找的父类就是Object。

如果一个类没有特别指定父类，	那么默认则继承自Object类。例如：

```java
public class MyClass /*extends Object*/ {
  	// ...
}
```

#### toString

* `public String toString()`：返回该对象的字符串表示。

toString方法返回该对象的字符串表示，其实该字符串内容就是对象的类型+@+内存地址值。

由于toString方法返回的结果是内存地址，而在开发中，经常需要按照对象的属性得到相应的字符串表现形式，因此也需要重写它。

##### 覆盖重写

如果不希望使用toString方法的默认行为，则可以对它进行覆盖重写。例如自定义的Person类：

```java
public class Person {  
    private String name;
    private int age;

    @Override
    public String toString() {
        return "Person{" + "name='" + name + '\'' + ", age=" + age + '}';
    }

    // 省略构造器与Getter Setter
}
```

在IntelliJ IDEA中，可以点击`Code`菜单中的`Generate...`，也可以使用快捷键`alt+insert`，点击`toString()`选项。选择需要包含的成员变量并确定。

> 小贴士： 在我们直接使用输出语句输出对象名的时候,就是调用了其toString()方法。print（list）



#### equals方法

调用成员方法equals并指定参数为另一个对象，则可以判断这两个对象是否是相同的。
对于基本数据类型，比较的是值。对于引用数据类型，比较的是两个对象的地址值。
null不能调用equals。

```java
public class text {
    public static void main(String[] args) {
        Person p1=new Person();
        Person p2=new Person();
        boolean b1=p1.equals(p2);
        System.out.println(b1);
        p1=p2;
        b1=p1.equals(p2);
        System.out.println(b1);
    }
}
```



##### 覆盖重写

object类的equals方法，默认比较的是两个对象的地址值，没有意义
所以我们要重写equals方法，比较两个对象的属性。
问题：
		隐含一个多态
		多态的弊端：无法使用子类特有的内容（属性和方法）
解决：可以使用向下转型把obj类型转换为Person

```java
//原理
public class Person {
    private String name;
    private int age;

    public boolean equals(Object obj){
        if(obj instanceof Person){
            Person p=(Person)obj;
        	return this.name.equals(p.name)&&this.age==p.age;
        } 
    }
}
```

直接快捷键：点击`Code`菜单中的`Generate...`，也可以使用快捷键`alt+insert`，点击`equals`选项。

#### Objects中的equals

防止出现空指针异常的情况

```java
public class text {
    public static void main(String[] args) {
        String s1=null;
        String s2="abc";
        boolean b2= Objects.equals(s1,s2);
        System.out.println(b2);
    }
}
```





### 日期时间类

------------------------------------------------

#### Date类

---------------------------------------------------------------------

` java.util.Date`类 表示特定的瞬间，精确到毫秒。（要导包）

- long getTime()把日期转换为毫秒值
  返回从标准基准时间（即1970年1月1日00:00:00 GMT）以来的指定毫秒数。

- Date类空参数构造方法
  Date()获取当前系统的日期和时间

- Date类的带参数构造方法
  Date(long date):传递毫秒值，把毫秒值转换为Date提日期

> tips: 由于我们处于东八区，所以我们的基准时间为1970年1月1日8时0分0秒。。

```java
public class text {
    public static void main(String[] args) {
        Date date=new Date();//获取当前时间
        System.out.println(date);
        
        Date date1=new Date(0L);
        System.out.println(date1);
        
        Date date2=new Date();
        long time=date2.getTime();
        System.out.println(time);
    }
}
```





#### DateFormat类

------------------------------------------

`java.text.DateFormat` 是日期/时间格式化子类的抽象类，我们通过这个类可以帮我们完成日期和文本之间的转换,也就是可以在Date对象与String对象之间进行来回转换。

包`java.text.SimpleDateFormat`
`public SimpleDateFormat(String pattern)`：用给定的模式和默认语言环境的日期格式符号构造SimpleDateFormat。

DateFormat类的常用方法有：

- `public String format(Date date)`：将Date对象格式化为字符串。
- `public Date parse(String source)`：将字符串解析为Date对象。

##### 格式规则

常用的格式规则为：

| 标识字母（区分大小写） | 含义 |
| ---------------------- | ---- |
| y                      | 年   |
| M                      | 月   |
| d                      | 日   |
| H                      | 时   |
| m                      | 分   |
| s                      | 秒   |

```java
//格式化
public class text {
    public static void main(String[] args) {
        SimpleDateFormat sdf=new SimpleDateFormat("yyyy年MM月dd日 HH时mm分ss秒");
        Date date=new Date();
        String d=sdf.format(date);
        System.out.println(date);
        System.out.println(d);
    }
}
```

```java
//解析 如果格式不对需要处理异常
public class text {
    public static void main(String[] args) throws ParseException {
        SimpleDateFormat sdf=new SimpleDateFormat("yyyy年MM月dd日 HH时mm分ss秒");
        Date date=sdf.parse("2020年03月30日 20时55分19秒");
        System.out.println(date);
    }
}
```





#### Calendar日历类

`java.util.Calendar`是日历类，在Date后出现，替换掉了许多Date的方法。该类将所有可能用到的时间信息封装为静态成员变量，方便获取。日历类就是方便获取各个时间属性的。

Calendar为抽象类，由于语言敏感性，Calendar类在创建对象时并非直接创建，而是通过静态方法创建，返回子类对象。调用getInstance方法可获取当前时间信息。

```java
public class text {
    public static void main(String[] args) {
        Calendar c=Calendar.getInstance();
        System.out.println(c);
    }
}
```

##### 常用方法

根据Calendar类的API文档，常用方法有：

- `public int get(int field)`：返回给定日历字段的值。
- `public void set(int field, int value)`：将给定的日历字段设置为给定值。
- `public abstract void add(int field, int amount)`：根据日历的规则，为给定的日历字段添加或减去指定的时间量。
- `public Date getTime()`：返回一个表示此Calendar时间值（从历元到现在的毫秒偏移量）的Date对象。

field 可以是以下字段值：

| 字段值       | 含义                                  |
| ------------ | ------------------------------------- |
| YEAR         | 年                                    |
| MONTH        | 月（从0开始，可以+1使用）             |
| DAY_OF_MONTH | 月中的天（几号）                      |
| HOUR         | 时（12小时制）                        |
| HOUR_OF_DAY  | 时（24小时制）                        |
| MINUTE       | 分                                    |
| SECOND       | 秒                                    |
| DAY_OF_WEEK  | 周中的天（周几，周日为1，可以-1使用） |

#### 

==public int get(int field)==

```java
public class text {
    public static void main(String[] args) {
        Calendar c=Calendar.getInstance();
        int year=c.get(Calendar.YEAR);
        int day=c.get(Calendar.DAY_OF_MONTH);
        int mouth=c.get(Calendar.MONTH)+1;
        System.out.println(year+" "+day+" "+mouth);
    }
}
```



==public void set(int field, int value)==

```java
public class text {
    public static void main(String[] args) {
        Calendar c=Calendar.getInstance();
        int mouth1=c.get(Calendar.MONTH);
        c.set(Calendar.MONTH,4);
        int mouth2=c.get(Calendar.MONTH);
        System.out.println(mouth1+" "+mouth2);
        //同时设置年月日，可以使用重载方法
        c.set(1999,7,24);
    }
}
```



==public abstract void add(int field, int amount)==

```java
//正数增加，负数减少
public class text {
    public static void main(String[] args) {
        Calendar c=Calendar.getInstance();
        c.add(Calendar.YEAR,2);
        System.out.println(year);
    }
}
```



==public Date getTime()==

```java
public class text {
    public static void main(String[] args) {
        Calendar c=Calendar.getInstance();
        Date date=c.getTime();
        System.out.println(date);
    }
}
```



### System类

-----------------------------------------------

`java.lang.System`包

- `public static long currentTimeMillis()`：返回以毫秒为单位的当前时间。
- `public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)`：将数组中指定的数据拷贝到另一个数组中。

```java
public class text {
    public static void main(String[] args) {
        long s=System.currentTimeMillis();
        for(int i=0;i<=9999;i++){
            System.out.println(i);
        }
        long e=System.currentTimeMillis();
        System.out.println("程序共耗时"+(e-s)+"毫秒");
    }
}
```

`public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)`
src-源数组
srcPos-源数组中的起始位置
dest-目标数组
destPos-目标数组中的起始位置
length-要复制的数组元素的数量

```java
public class text {
    public static void main(String[] args) {
        int[] src={1,2,3,4,5};
        int[] dest={6,7,8,9,10};
        System.arraycopy(src,0,dest,0,3);
        System.out.println(Arrays.toString(dest));
    }
}
```



### StringBuilder类

--------------------------------

它的内部拥有一个数组用来存放字符串内容，进行字符串拼接时，直接在数组中加入新内容。

#### 构造方法

根据StringBuilder的API文档，常用构造方法有2个：

- `public StringBuilder()`：构造一个空的StringBuilder容器。
- `public StringBuilder(String str)`：构造一个StringBuilder容器，并将字符串添加进去。

```java
public class text {
    public static void main(String[] args) {
        //空参数构造方法
        StringBuilder b1=new StringBuilder();
        System.out.println(b1);
        //带字符串的构造方法
        StringBuilder b2=new StringBuilder("abc");
        System.out.println(b2);
    }
}
```

##### 常用方法

StringBuilder常用的方法有2个：

- `public StringBuilder append(...)`：添加任意类型数据的字符串形式，并返回当前对象自身。
- `public String toString()`：将当前StringBuilder对象转换为String对象。

###### append方法

append方法具有多种重载形式，可以接收任意类型的参数。任何数据作为参数都会将对应的字符串内容添加到StringBuilder中。

```java
public class text {
    public static void main(String[] args) {
        StringBuilder bu1=new StringBuilder();
        bu1.append("abc");
        System.out.println(bu1);
        bu1.append("123").append(1).append(true).append(8.8).append("中");
        System.out.println(bu1);
    }
}
```



###### toString方法

通过toString方法，StringBuilder对象将会转换为不可变的String对象。

```java
public class text{
    public static void main(String[] args) {
        // 链式创建
        StringBuilder sb = new StringBuilder("Hello").append("World").append("Java");
        // 调用方法
        String str = sb.toString();
        System.out.println(str); // HelloWorldJava
    }
}
```



### 包装类

Java提供了两个类型系统，基本类型与引用类型，使用基本类型在于效率，然而很多情况，会创建对象使用，因为对象可以做更多的功能，如果想要我们的基本类型像对象一样操作，就可以使用基本类型对应的包装类，如下：

| 基本类型 | 对应的包装类（位于java.lang包中） |
| -------- | --------------------------------- |
| byte     | Byte                              |
| short    | Short                             |
| int      | **Integer**                       |
| long     | Long                              |
| float    | Float                             |
| double   | Double                            |
| char     | **Character**                     |
| boolean  | Boolean                           |

#### 装箱与拆箱

基本类型与对应的包装类对象之间，来回转换的过程称为”装箱“与”拆箱“：

* 装箱：从基本类型转换为对应的包装类对象。

  * 构造方法：
    	Integer(int value)构造一个新分配的Integer对象，它表示指定的int值
      	Integer(String s)构造一个新分配的Integer对象，类似”100“，”a“会抛出异常

  * 静态方法：
    	static Integer valueOf(int i)
      	static Integer valueOf(String s)

    ```java
    public class text {
        public static void main(String[] args) {
            //构造装箱
            Integer in1=new Integer(1);
            Integer in2=new Integer("23");
            //静态方法
            Integer in3=Integer.valueOf(1);
            Integer in4=Integer.valueOf("45");
        }
    }
    ```

* 拆箱：从包装类对象转换为对应的基本类型。

  * 成员方法：

    ​	int intValue() 以int类型返回该Integer的值

    ```java
    public class text {
        public static void main(String[] args) {
            Integer in=new Integer(2);
            int i=in.intValue();
            System.out.println(i);
        }
    }
    ```

    

#### 自动装箱与自动拆箱

由于我们经常要做基本类型与包装类之间的转换，从Java 5（JDK 1.5）开始，基本类型与包装类的装箱、拆箱动作可以自动完成。

```java
public class text {
    public static void main(String[] args) {
        //自动装箱
        Integer in=1;
        //自动拆箱
        in=in+1;
    }
}
```





#### 基本类型与字符串之间的转换

基本类型->字符串(String)

1.==（常用）==基本类型的值+""
2.包装类toString(参数)
3.String类的静态方法valueOf(参数)

```java
public class text {
    public static void main(String[] args) {
        int i1=100;
        String s1=i1+"";

        String s2=Integer.toString(100);

        String s3=String.valueOf(100);
    }
}
```



字符串(String)->基本类型

使用包装类的静态方法parsexxx("字符串")
`public static byte parseByte(String s)`：将字符串参数转换为对应的byte基本类型。
`public static short parseShort(String s)`：将字符串参数转换为对应的short基本类型。
`public static int parseInt(String s)`：将字符串参数转换为对应的int基本类型。
`public static long parseLong(String s)`：将字符串参数转换为对应的long基本类型。
`public static float parseFloat(String s)`：将字符串参数转换为对应的float基本类型。
`public static double parseDouble(String s)`：将字符串参数转换为对应的double基本类型。
`public static boolean parseBoolean(String s)`：将字符串参数转换为对应的boolean基本类型。

```java
public class text {
    public static void main(String[] args) {
        String s1="1223";
        int i=Integer.parseInt(s1);
    }
}
```



### 集合

集合：集合是java中提供的一种容器，可以用来存储多个数据。

集合和数组的区别

* 数组的长度是固定的。集合的长度是可变的。
* 数组中存储的是同一类型的元素，可以存储基本数据类型值。集合存储的都是对象。而且对象的类型可以不一致。在开发中一般当对象多的时候，使用集合进行存储。

<img src="img\Collection集合体系图.jpg"  />



####  Collection 常用功能

* `public boolean add(E e)`：  把给定的对象添加到当前集合中 。
* `public void clear()` :清空集合中所有的元素,但集合还存在。
* `public boolean remove(E e)`: 把给定的对象在当前集合中删除。
* `public boolean contains(E e)`: 判断当前集合中是否包含给定的对象。
* `public boolean isEmpty()`: 判断当前集合是否为空。
* `public int size()`: 返回集合中元素的个数。
* `public Object[] toArray()`: 把集合中的元素，存储到数组中。

方法演示：

~~~java
import java.util.ArrayList;
import java.util.Collection;

public class Demo1Collection {
    public static void main(String[] args) {
		// 创建集合对象 
    	// 使用多态形式
    	Collection<String> coll = new ArrayList<String>();
    	// 使用方法
    	// 添加功能  boolean  add(String s)
    	coll.add("小李广");
    	coll.add("扫地僧");
    	coll.add("石破天");
    	System.out.println(coll);

    	// boolean contains(E e) 判断o是否在集合中存在
    	System.out.println("判断  扫地僧 是否在集合中"+coll.contains("扫地僧"));

    	//boolean remove(E e) 删除在集合中的o元素
    	System.out.println("删除石破天："+coll.remove("石破天"));
    	System.out.println("操作之后集合中元素:"+coll);
    	
    	// size() 集合中有几个元素
		System.out.println("集合中有"+coll.size()+"个元素");

		// Object[] toArray()转换成一个Object数组
    	Object[] objects = coll.toArray();
    	// 遍历数组
    	for (int i = 0; i < objects.length; i++) {
			System.out.println(objects[i]);
		}

		// void  clear() 清空集合
		coll.clear();
		System.out.println("集合中内容为："+coll);
		// boolean  isEmpty()  判断是否为空
		System.out.println(coll.isEmpty());  	
	}
}
~~~

> tips: 有关Collection中的方法可不止上面这些，其他方法可以自行查看API学习。

#### Iterator迭代器

遍历集合中的元素

```java
public class text {
    public static void main(String[] args) {
        Collection<String> coll=new ArrayList<>();
        coll.add("张三");
        coll.add("李四");
        coll.add("王五");
        coll.add("小红");
        coll.add("小明");
        Iterator<String> it=coll.iterator();
        while(it.hasNext()){//判断还有没有下一个元素
            String e=it.next();//取出元素并往后移一位
            System.out.println(e);
        }
        System.out.println("-----------------------------");
        for(Iterator<String> it2=coll.iterator();it2.hasNext();){
            String e=it2.next();
            System.out.println(e);
        }
    }
}
```



#### 增强for

用来遍历数组和集合的。它的内部原理其实是个Iterator迭代器，所以在遍历的过程中，不能对集合中的元素进行增删操作。

格式：

~~~java
for(元素的数据类型  变量名: Collection集合or数组){ 
  	//写操作代码
}
~~~

它用于遍历Collection和数组。通常只进行遍历元素，不要在遍历的过程中对集合元素进行增删操作。

##### 遍历数组

~~~java
public class text {
    public static void main(String[] args) {
		int[] arr = {3,5,6,87};
       	//使用增强for遍历数组
		for(int a : arr){//a代表数组中的每个元素
			System.out.println(a);
		}
	}
}
~~~

##### 遍历集合

~~~java
public class text {
    public static void main(String[] args) {        
    	Collection<String> coll = new ArrayList<String>();
    	coll.add("小河神");
    	coll.add("老河神");
    	coll.add("神婆");
    	//使用增强for遍历
    	for(String s :coll){//接收变量s代表 代表被遍历到的集合元素
    		System.out.println(s);
    	}
	}
}
~~~



### 泛型

------------------------------------------------

泛型：是一种未知的数据类型，当我们不知道使用什么数据类型的时候，可以使用泛型。

定义及使用

```java
public class GenericClass<E> {
    private E name;
    public GenericClass() {
    }
    public GenericClass(E name) {
        this.name = name;
    }

    public E getName() {
        return name;
    }

    public void setName(E name) {
        this.name = name;
    }
}
```

```java
public class text {
    public static void main(String[] args) {
        //不写泛型默认为Object类型
        GenericClass gc=new GenericClass();
        gc.setName("123");
        Object obj=gc.getName();

        GenericClass<Integer> gc2=new GenericClass<>();
        gc2.setName(12);
        Integer in=gc2.getName();
    }
}
```

#### 含有泛型的方法

定义格式：

~~~
修饰符 <代表泛型的变量> 返回值类型 方法名(参数){  }
~~~

例如，

~~~java
public class GenericMethod {
    //定义一个含有泛型的方法
    public <M> void method01(M m){
        System.out.println(m);
    }
    public static <S> void method02(S s){//阔折号里的字母随意命名
        System.out.println(s);
    }
}
~~~

使用格式：调用方法时，确定泛型的类型
					传递什么类型的参数，泛型就是什么类型

~~~java
public class text {
    public static void main(String[] args) {
        GenericMethod gm=new GenericMethod();
        gm.method01(12);
        gm.method01("1223");

        GenericMethod.method02("232");
    }
}
~~~

#### 含有泛型的接口

定义格式：

~~~
修饰符 interface接口名<代表泛型的变量> {  }
~~~

例如，

~~~java
public interface GenericInterface<E>{
	public abstract void add(E e);
	
	public abstract E getE();  
}
~~~

使用格式：

**1、定义类时确定泛型的类型**

例如

~~~java
public class MyImp1 implements GenericInterface<String> {
	@Override
    public void add(String e) {
        // 省略...
    }

	@Override
	public String getE() {
		return null;
	}
}
~~~

此时，泛型E的值就是String类型。

2、始终不确定泛型的类型，直到创建对象时，确定泛型的类型**

 例如

~~~java
public class MyImp2<E> implements MyGenericInterface<E> {
	@Override
	public void add(E e) {
       	 // 省略...
	}

	@Override
	public E getE() {
		return null;
	}
}
~~~

确定泛型：

~~~java
/*
 * 使用
 */
public class GenericInterface {
    public static void main(String[] args) {
        MyImp2<String>  my = new MyImp2<String>();  
        my.add("aa");
    }
}
~~~

####  泛型通配符

当使用泛型类或者接口时，传递的数据中，泛型类型不确定，可以通过通配符<?>表示。但是一旦使用泛型的通配符后，只能使用Object类中的共性方法，集合中元素自身方法无法使用。

不能创建对象使用只能作为方法的参数使用

```java
public class text{
    public static void main(String[] args) {
        ArrayList<Integer> list01=new ArrayList<>();
        list01.add(1);
        list01.add(2);

        ArrayList<String> list01=new ArrayList<>();
        list01.add("a");
        list01.add("b");
    }
    /*
    定义一个方法，能遍历所有类型的ArrayList集合
     */
    public static void printArray(ArrayList<?> list){
        Iterator<?>it=list.iterator();
        while(it.hasNext()){
            Object o=it.next();
            System.out.println(o);
        }
    }
}
```





### List集合

------------------------------------------------------------------------------------------------------------

`java.util.List`接口继承自`Collection`接口，在List集合中允许出现重复的元素,List集合还有一个特点就是元素有序，即元素的存入顺序和取出顺序一致。

List接口特点：

1. 它是一个元素存取有序的集合。例如，存元素的顺序是11、22、33。那么集合中，元素的存储就是按照11、22、33的顺序完成的）。
2. 它是一个带有索引的集合，通过索引就可以精确的操作集合中的元素（与数组的索引是一个道理）。
3. 集合中可以有重复的元素，通过元素的equals方法，来比较是否为重复的元素。

#### List接口中常用方法

List作为Collection集合的子接口，不但继承了Collection接口中的全部方法，而且还增加了一些根据元素索引来操作集合的特有方法，如下：

- `public void add(int index, E element)`: 将指定的元素，添加到该集合中的指定位置上。
- `public E get(int index)`:返回集合中指定位置的元素。
- `public E remove(int index)`: 移除列表中指定位置的元素, 返回的是被移除的元素。
- `public E set(int index, E element)`:用指定元素替换集合中指定位置的元素,返回值的更新前的元素。

```java
public class text {
    public static void main(String[] args) {
        List<String> list=new ArrayList<>();
        list.add("a");
        list.add("b");
        list.add("c");
        list.add("d");
        System.out.println(list);
        //在c和d之间添加一个itheima
        list.add(3,"itheima");
        System.out.println(list);

        String removeE=list.remove(2);
        System.out.println(list);

        String setE=list.set(1,"A");
        System.out.println(list);
        System.out.println("-----------------------");
        //list集合遍历有3种方法
        //使用普通for循环
        for(int i=0;i<list.size();i++){
            String s=list.get(i);
            System.out.println(s);
        }
        System.out.println("-----------------------");
        //使用迭代器遍历
        Iterator<String> it=list.iterator();
        while(it.hasNext()){
            String s=it.next();
            System.out.println(s);
        }

        System.out.println("-----------------------");
        //增强for
        for (String s : list) {
            System.out.println(s);
        }
    }
}
```



### List集合的子类

------------------------------------------------------------------------

 #### ArrayList集合

`java.util.ArrayList`集合数据存储的结构是数组结构。元素增删慢，查找快，由于日常开发中使用最多的功能为查询数据、遍历数据，所以`ArrayList`是最常用的集合。

许多程序员开发时非常随意地使用ArrayList完成任何需求，并不严谨，这种用法是不提倡的。

#### LinkedList集合

`java.util.LinkedList`集合数据存储的结构是链表结构。查询慢，增删快。LinkedList是一个双向链表。

实际开发中对一个集合元素的添加与删除经常涉及到首尾操作，而LinkedList提供了大量首尾操作的方法。这些方法我们作为了解即可：

* `public void addFirst(E e)`:将指定元素插入此列表的开头。同push。

* `public void addLast(E e)`:将指定元素添加到此列表的结尾。同add。

* `public void push(E e)`:将元素推入此列表所表示的堆栈。同addFirst

  

* `public E getFirst()`:返回此列表的第一个元素。

* `public E getLast()`:返回此列表的最后一个元素。

  

* `public E removeFirst()`:移除并返回此列表的第一个元素。

* `public E removeLast()`:移除并返回此列表的最后一个元素。

* `public E pop()`:从此列表所表示的堆栈处弹出一个元素。

  

* `public boolean isEmpty()`：如果列表不包含元素，则返回true。

```java
public class text {
    public static void main(String[] args) {
        //show01();
       // show02();
        show03();
    }
    private static void show01() {
        LinkedList<String> linked = new LinkedList<>();
        linked.add("a");
        linked.add("b");
        linked.add("c");
        System.out.println(linked);

        //linked.addFirst("www");
        //System.out.println(linked);

        linked.push("www");
        System.out.println(linked);

    }
    private static void show02() {
        LinkedList<String> linked = new LinkedList<>();
        linked.add("a");
        linked.add("b");
        linked.add("c");
        System.out.println(linked);

        if(!linked.isEmpty()){//如果集合为空会报错
            String first=linked.getFirst();
            String last=linked.getLast();
            System.out.println(first+" "+last);
        }
    }
    private static void show03() {
        LinkedList<String> linked = new LinkedList<>();
        linked.add("a");
        linked.add("b");
        linked.add("c");
        System.out.println(linked);
        String first=linked.removeFirst();
        String last=linked.removeLast();
        
    }
}
```



### Set接口

-------------------------------------------------------------------

`java.util.Set`接口继承自`Collection`接口，它与`Collection`接口中的方法基本一致，并没有对`Collection`接口进行功能上的扩充，只是比`Collection`接口更加严格了。

`Set`接口中元素无序，没有索引，并且都会以某种规则保证存入的元素不出现重复。

#### HashSet集合

`java.util.HashSet`是`Set`接口的一个实现类。

特点：
1.存储的元素是不可重复的
2.元素都是无序的(即存取顺序不一致)
3.没有索引，没有带索引的方法，也不能使用普通for循环（可以使用迭代器增强for遍历）
4.底层是一个哈希表结构（查询速度非常快）

#### HashSet存储自定义类型元素

给HashSet中存放自定义类型元素时，需要重写对象中的hashCode和equals方法，建立自己的比较方式，才能保证HashSet集合中的对象唯一

创建自定义Student类

~~~java
public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o)
            return true;
        if (o == null || getClass() != o.getClass())
            return false;
        Student student = (Student) o;
        return age == student.age &&
               Objects.equals(name, student.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }
}
~~~

~~~java
public class HashSetDemo2 {
    public static void main(String[] args) {
        //创建集合对象   该集合中存储 Student类型对象
        HashSet<Student> stuSet = new HashSet<Student>();
        //存储 
        Student stu = new Student("于谦", 43);
        stuSet.add(stu);
        stuSet.add(new Student("郭德纲", 44));
        stuSet.add(new Student("于谦", 43));
        stuSet.add(new Student("郭麒麟", 23));
        stuSet.add(stu);

        for (Student stu2 : stuSet) {
            System.out.println(stu2);
        }
    }
}
执行结果：
Student [name=郭德纲, age=44]
Student [name=于谦, age=43]
Student [name=郭麒麟, age=23]
~~~



#### LinkedHashSet

在HashSet下面有一个子类`java.util.LinkedHashSet`，元素放进去是有序的

```java
public class text {
    public static void main(String[] args) {
        LinkedHashSet<String> linked=new LinkedHashSet<>();
        linked.add("www");
        linked.add("aaa");
        linked.add("sss");
        System.out.println(linked);
    }
}
```



#### 可变参数

使用前提：
	当方法的参数列表数据类型已经确定，但是参数的个数不确定，就可以使用可变参数

使用格式：
	修饰符 返回值类型 方法名(参数类型... 形参名){  }

可变参数的原理：
	可变参数的底层是一个数组，根据传递参数的个数不同，会创建不同长度的数组，来存储这些参数传递的参数个数，可以是0个（不传递），1,2....多个

可变参数的注意事项：
1.一个方法的参数列表，只能有一个可变参数
2.如果方法的参数有多个，那么可变参数必须写在参数列表的末尾

```java
public class text {
    public static void main(String[] args) {
        int i=add(1,2,3,4);
        System.out.println(i);
    }
    /*
        定义计算（0-n）整数和的方法
        已知：计算整数的和，数据类型已经确定int
        但是参数个数不确定，不知道要计算几个参数的和
        add()：创建一个长度为0的数组  new int[0]
        add(10)：创建一个长度为1的数组  new int[]{10}
        add(12,23,45)：创建一个长度为3的数组  new int[]{12,23,45}
     */
    public  static int add(int...arr){
        int sum=0;
        for (int i : arr) {
            sum+=i;
        }
        return sum;
    }
    public  static int add1(Object...obj){}
    
}
```





### Collections

----------------------------------------------------------

#### 常用功能

* `java.utils.Collections`是集合工具类，用来对集合进行操作。部分方法如下：

- `public static <T> boolean addAll(Collection<T> c, T... elements)  `:往集合中添加一些元素。
- `public static void shuffle(List<?> list) 打乱顺序`:打乱集合顺序。
- `public static <T> void sort(List<T> list)`:将集合中元素按照默认规则排序。
- `public static <T> void sort(List<T> list，Comparator<? super T> )`:将集合中元素按照指定规则排序。

```java
public class text {
    public static void main(String[] args) {
        ArrayList<Integer> list=new ArrayList<>();
        Collections.addAll(list,1,2,3,4);//往集合中添加元素
        System.out.println(list);

        Collections.shuffle(list);//打乱集合的元素
        System.out.println(list);

        Collections.sort(list);
        System.out.println(list);
    }
}
```



sort降序排序

```java
public class CollectionsDemo3 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();
        list.add("cba");
        list.add("aba");
        list.add("sba");
        list.add("nba");
        //排序方法  按照第一个单词的降序
        Collections.sort(list, new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                return o2.charAt(0) - o1.charAt(0);
            }
        });
        System.out.println(list);
    }
}
```



sort自定义排序

```java
public class Emp{
    private int empno;
    private String ename;
    public int getEmpno() {
        return empno;
    }
    public void setEmpno(int empno) {
        this.empno = empno;
    }
    public String getEname() {
        return ename;
    }
    public void setEname(String ename) {
        this.ename = ename;
    }
    
    public Emp(int empno, String ename) {
        super();
        this.empno = empno;
        this.ename = ename;
    }
    @Override
    public String toString()
    {
        return "empno:\t"+empno+"\tename:\t"+ename;
    }
}
```

```java
private static void sortEmpByIDefineMode()
    {
        System.out.println("before sort:");
        PrintUtil.showList(empList);
        System.out.println("=========================");
        Collections.sort(empList,new Comparator<Emp>() {

            @Override
            public int compare(Emp o1, Emp o2) {
                /*按员工编号正序排序*/
                return o1.getEmpno()-o2.getEmpno();
                /*按员工编号逆序排序*/
                //return o2.getEmpno()-o1.getEmpno();
                /*按员工姓名正序排序*/
                //return o1.getEname().compareTo(o2.getEname());
                /*按员工姓名逆序排序*/
                //return o2.getEname().compareTo(o1.getEname());
            }
        });
        System.out.println("after sort:");
        PrintUtil.showList(empList);
    }
```

### Map

---------------------

map集合的特点：
1.map集合是一个双列集合，一个元素包含两个 值（一个key，一个value）
2.map集合中的元素，key和value的数据类型可以相同，也可以不同
3.map集合中的元素，key是不允许重复的，value是可以重复的
4.map集合中的元素，key和value是一一对应的

#### map常用子类

* **HashMap<K,V>**：存储数据采用的哈希表结构，元素的存取顺序不能保证一致。由于要保证键的唯一、不重复，需要重写键的hashCode()方法、equals()方法。
* **LinkedHashMap<K,V>**：HashMap下有个子类LinkedHashMap，存储数据采用的哈希表结构+链表结构。通过链表结构可以保证元素的存取顺序一致；通过哈希表结构可以保证的键的唯一、不重复，需要重写键的hashCode()方法、equals()方法。

####  Map接口中的常用方法

Map接口中定义了很多方法，常用的如下：

* `public V put(K key, V value)`:  把指定的键与指定的值添加到Map集合中。
* `public V remove(Object key)`: 把指定的键 所对应的键值对元素 在Map集合中删除，返回被删除元素的值。
* `public V get(Object key)` 根据指定的键，在Map集合中获取对应的值。
* `boolean containsKey(Object key)  ` 判断集合中是否包含指定的键。
* `public Set<K> keySet()`:获取Map集合中所有的键，存储到Set集合中。
* `public Set<Map.Entry<K,V>> entrySet()`: 获取到Map集合中所有的键值对对象的集合(Set集合)。

```java
public class text {
    public static void main(String[] args) {
        show04();
    }
    /*
       public V put(K key, V value):  把指定的键与指定的值添加到Map集合中。
       返回值：key不重复，返回值是null
              key重复，会使用新的value代替map中重复的value，返回被替换的value值
    */
    private static void show01() {
        Map<String,String> map=new HashMap<>();
        String v1=map.put("1","2");
        System.out.println(v1);
        String v2=map.put("1","3");
        System.out.println(v2);
    }
    /*
         public V remove(Object key):把指定的键 所对应的键值对元素 在Map集合中删除，返回被删除元素的值。
         key存在，返回被删除的值
         key不存在，返回null
    */
    private static void show02(){
        Map<String,Integer> map=new HashMap<>();
        map.put("1",1);
        map.put("2",2);
        map.put("3",3);

        map.remove("1");
    }
    /*
        public V get(Object key) :根据指定的键，在Map集合中获取对应的值。
        key存在返回对应的value值
        key不存在返回null
    */
    private static void show03(){
        Map<String,Integer> map=new HashMap<>();
        map.put("1",1);
        map.put("2",2);
        map.put("3",3);
        Integer v1=map.get("1");
        System.out.println(v1);
    }
    /*
         boolean containsKey(Object key) :判断集合中是否包含指定的键。
         包含返回true，不包含返回false
    */
    private static void show04(){
        Map<String,Integer> map=new HashMap<>();
        map.put("1",1);
        map.put("2",2);
        map.put("3",3);
        boolean v1=map.containsKey("1");
        System.out.println(v1);
    }
}
```



#### Map集合遍历键找值方式

键找值方式：即通过元素中的键，获取键所对应的值

分析步骤：

1. 获取Map中所有的键，由于键是唯一的，所以返回一个Set集合存储所有的键。方法提示:`keyset()`
2. 遍历键的Set集合，得到每一个键。
3. 根据键，获取键所对应的值。方法提示:`get(K key)`

```java
public class text {
    public static void main(String[] args) {
        Map<String,Integer> map=new HashMap<>();
        map.put("1",1);
        map.put("2",2);
        map.put("3",3);
        Set<String> set=map.keySet();
        for (String s : set) {//for (String s : map.keySet())
            Integer value=map.get(s);
            System.out.println(s+"="+value);
        }
    }
}
```



#### Entry键值对对象

键值对方式：即通过集合中每个键值对(Entry)对象，获取键值对(Entry)对象中的键与值。

操作步骤与图解：

1.  获取Map集合中，所有的键值对(Entry)对象，以Set集合形式返回。方法提示:`entrySet()`。

2.  遍历包含键值对(Entry)对象的Set集合，得到每一个键值对(Entry)对象。
3.  通过键值对(Entry)对象，获取Entry对象中的键与值。  方法提示:`getkey() getValue()`     

* `public K getKey()`：获取Entry对象中的键。
* `public V getValue()`：获取Entry对象中的值。

```java
public class text {
    public static void main(String[] args) {
        Map<String,Integer> map=new HashMap<>();
        map.put("1",1);
        map.put("2",2);
        map.put("3",3);
        Set<Map.Entry<String,Integer>> set=map.entrySet();
        for (Map.Entry<String, Integer> it : set) {
            System.out.println(it.getKey()+"="+it.getValue());
        }
    }
}
```



#### HashMap存储自定义类型键

map集合保证key唯一：
	当key为自定义类型时，必须重写hashCode方法和equals方法，以保证key唯一

```java
public class Person {
    private String name;
    private  int age;

    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Person person = (Person) o;
        return age == person.age &&
                Objects.equals(name, person.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

```



```java
public class text {
    public static void main(String[] args) {
        HashMap<Person,String> map=new HashMap<>();
        map.put(new Person("女王",13),"英国");
        map.put(new Person("秦始皇",13),"秦国");
        map.put(new Person("普京",13),"俄罗斯");
        map.put(new Person("女王",13),"毛里求斯");
        Set<Person> set=map.keySet();
        for (Person person : set) {
            String s=map.get(person);
            System.out.println(person+"->"+s);
        }
    }
}

```



#### LinkedHashMap

是HashMap的子类，存取顺序一致

```java
public class text {
    public static void main(String[] args) {
        LinkedHashMap<String,String> linked=new LinkedHashMap<>();
        linked.put("a","a");
        linked.put("d","d");
        linked.put("f","f");
        linked.put("e","e");
        linked.put("t","t");
        System.out.println(linked);
    }
}
```

 

#### of

可以给集合一次性添加多个元素

1.of()方法只是Map，List，Set这三个接口的静态方法，其父类接口和子类实现并没有这类方法，比如    HashSet，ArrayList等待；
2.of方法的返回值是一个不能改变的集合，集合不能再使用add，put方法添加元素，会抛出异常。
3.Set接口和Map接口在调用of方法的时候，不能有重复的元素，否则会抛出异常

```java
public class text {
    public static void main(String[] args) {
        List<String> list=List.of("a","b","c");
    }
}
```







### Debug追踪

--------------------------------------------

F8:逐行执行程序
F7:进入到方法中
shift+F8:跳出方法
F9:跳到下一个断点，如果没有下一个断点，那么就结束程序
ctrl+F2:退出debug模式，停止程序



### 异常

-------------------------------------------------

异常 ：指的是程序在执行过程中，出现的非正常的情况，最终会导致JVM的非正常停止。

在Java等面向对象的编程语言中，异常本身是一个类，产生异常就是创建异常对象并抛出了一个异常对象。Java处理异常的方式是中断处理。

> 异常指的并不是语法错误,语法错了,编译不通过,不会产生字节码文件,根本不能运行.

#### 异常体系

异常机制其实是帮助我们**找到**程序中的问题，异常的根类是`java.lang.Throwable`，其下有两个子类：`java.lang.Error`与`java.lang.Exception`，平常所说的异常指`java.lang.Exception`。

![](/img/异常体系.png)

**Throwable体系：**

* **Error**:严重错误Error，无法通过处理的错误，只能事先避免，好比绝症。
* **Exception**:表示异常，异常产生后程序员可以通过代码的方式纠正，使程序继续运行，是必须要处理的。好比感冒、阑尾炎。

**Throwable中的常用方法：**

* `public void printStackTrace()`:打印异常的详细信息。

  *包含了异常的类型,异常的原因,还包括异常出现的位置,在开发和调试阶段,都得使用printStackTrace。*

* `public String getMessage()`:获取发生异常的原因。

  *提示给用户的时候,就提示错误原因。*

* `public String toString()`:获取异常的类型和异常描述信息(不用)。

  

#### 异常分类

* **编译时期异常**:checked异常。在编译时期,就会检查,如果没有处理异常,则编译失败。(如日期格式化异常)
* **运行时期异常**:runtime异常。在运行时期,检查异常.在编译时期,运行异常不会编译器检测(不报错)。(如数学异常)

​    ![](img\异常的分类.png)

### 异常的处理

-------------------------------------------------------------------

Java异常处理的五个关键字：try、catch、finally、throw、throws



#### 	抛出异常throw

throw关键字

作用：
		可以使用throw关键字在指定的方法中抛出指定的异常
使用格式：
		throw new xxxException("异常产生的原因");
注意：
		1.throw关键字必须写在方法的内部
		2.throw关键字后边new的对象必须是Exception或者Exception的子类
		3.throw关键字抛出指定的异常对象，我们就必须处理这个对象
				throw关键字后边创建的是RuntimeException或者是RuntimeException的子类对象，我们可以不处理，默认交给JVM处理（打印异常对象，中断程序）
				throw关键字后边创建的是编译异常（写代码的时候报错），我们就必须处理这个异常，要么throw，要么try...catch

```java
public class text {
    public static void main(String[] args) {
        int[] arr=new int[3];
        int e=getElement(arr,3);
        System.out.println(e);
    }
    public static  int getElement(int[] arr,int index){
        /*
            我们可以对传递过来的参数数组进行合法性校验
            如果数组arr的值是null
            那么我们抛出空指针异常，告知方法使用者“传递的数组的值是null”
        */
        if(arr==null) {
            throw new NullPointerException("传递数组的值是null");
        }
        /*
            我们可以对传递过来的参数index进行合法性校验
            如果index的范围不在数组的索引范围内
            那么我们就抛出数组索引越界异常，告知方法的调用者“传递的索引超出了数组的适用范围”
        */
        if(index<0||index>arr.length-1){
            throw new ArrayIndexOutOfBoundsException("传递的索引超出了数组的使用范围");
        }
        int ele=arr[index];
        return ele;
    }
}
```





#### Objects非空判断

* `public static <T> T requireNonNull(T obj)`:查看指定引用对象不是null。

```java
public class text {
    public static void main(String[] args) {
        method(null);
    }
    public static void method(Object obj){
        /*if(obj==null){
            throw new NullPointerException("传递对象的值是null");
        }*/
        Objects.requireNonNull(obj);
        Objects.requireNonNull(obj,"传递对象的值是null");
    }
}
```



#### 声明异常throws

throws关键字：异常处理的第一种方式，交给别人处理
作用：
		当方法内部抛出异常对象的时候，那么我们就必须处理这个对象
		可以使用throws关键字处理异常对象，会把异常对象声明抛出给方法的调用者处理（自己不处理，给别人处理），最终交给jvm处理--》中断处理

使用格式：在方法声明时使用
	修饰符 返回值类型 方法名（参数列表）throws AAAExcepiton,BBBExcepiton{
			throws new AAAExcepiton("产生原因");
			throws new BBBExcepiton("产生原因");
			.......
	}

注意：
1.throws关键字必须写在方法声明处
2.throws关键字后边声明的异常必须是Excepiton或者Excepiton的子类
3.方法内部如果抛出了多个异常对象，那么throws后边必须也声明多个异常
	如果抛出的多个异常对象有子父类关系，那么直接声明父类异常即可
4.调用了一个声明抛出异常的方法，我们就必须的处理声明的异常
		要么继续使用throws声明抛出，交给方法的调用者处理，最终交给jvm
		要么try...catch自己处理异常

```java
public class text {
    public static void main(String[] args) throws FileNotFoundException,IOException{
        readFile("c:\\a.tx");
    }
    /*
        定义一个方法，对传递的文件路径进行合法性判断
        如果路径不是“c:\a.txt”，那么我们就抛出文件找不到的异常对象，告知方法使用者
        注意：
            FileNotFoundException是编译异常，抛出了编译异常，就必须处理这个异常
            可以使用throws继续声明抛出的FileNotFoundException这个异常对象，让方法的调用者处理
     */
    public static void readFile(String fileName)throws FileNotFoundException,IOException{
        if(!fileName.equals("c:\\a.txt")){
            throw new FileNotFoundException("传递的文件路径不是c:\\a.txt");
        }
        /*
            如果传递的路径不是.txt结尾
            那么我们就抛出IO异常对象，告知方法使用者，文件后缀名不对
         */
        if(!fileName.endsWith(".txt")){
            throw new IOException("文件后缀名不对");
        }
        System.out.println("路径没有问题");
    }
}
```



#### 捕获异常try…catch

try...catch：异常处理的第一种方式，自己处理异常

格式：
try{
     编写可能会出现异常的代码
}catch(定义一个异常的变量，用来接收try中抛出的异常){
     处理异常的代码
     //记录日志/打印异常信息/继续抛出异常
}
....
catch(异常类名 变量名){
}

注意：
1.try中可能会抛出多个异常对象，那么就可以使用多个catch来处理这些异常对象
2.如果try中产生了异常，那么就会执行catch中的异常处理逻辑，执行完毕catch中的处理逻辑，继续执行try...catch之后的代码
如果try中没有产生异常，那么就不会执行catch中异常的处理逻辑，执行完try中的代码，继续执行try...catch之后的代码
3.注意:try和catch都不能单独使用,必须连用。

```java
public class text {
    public static void main(String[] args) throws FileNotFoundException,IOException{
        try{
            readFile("c:\\a.tx");
        }catch (IOException e){//try中抛出声明异常对象，catch就定义什么异常变量，用来接收这个异常对象
            System.out.println("catch-文件后缀名不对");
        }
        System.out.println("后续代码");
    }
    public static void readFile(String fileName)throws FileNotFoundException,IOException{

        if(!fileName.endsWith(".txt")){
            throw new IOException("文件后缀名不对");
        }
        System.out.println("路径没有问题");
    }
}
```



#### finally 代码块

finally：有一些特定的代码无论异常是否发生，都需要执行。

格式：
try{
     编写可能会出现异常的代码
}catch(定义一个异常的变量，用来接收try中抛出的异常){
     处理异常的代码
     //记录日志/打印异常信息/继续抛出异常
}
....
catch(异常类名 变量名){
}finally{
		无论是否出现异常都会执行
}

注意：
1.finally不能单独使用，必须和try一起使用
2.finally一般用于资源释放（资源回收），无论程序是否出现异常，最后都要资源释放

```java
public class text {
    public static void main(String[] args) throws FileNotFoundException,IOException{
        try{
            readFile("c:\\a.tx");
        }catch (IOException e){//try中抛出声明异常对象，catch就定义什么异常变量，用来接收这个异常对象
            System.out.println("catch-文件后缀名不对");
        }finally {
            System.out.println("后续代码");
        }

    }
   
    public static void readFile(String fileName)throws FileNotFoundException,IOException{

        if(!fileName.endsWith(".txt")){
            throw new IOException("文件后缀名不对");
        }
        System.out.println("路径没有问题");
    }
}

```





#### 异常注意事项

1. 多个异常分别处理。
2. 多个异常一次捕获，多次处理。(catch里面定义的异常处理，如果有子父类关系，那么子类的异常变量必须写在上面，否则会报错)
3. 多个异常一次捕获一次处理。

```java
public class text {
    public static void main(String[] args) throws FileNotFoundException,IOException{
        /*//多个异常分别处理。
        try{
            int[] arr={1,2,3};
            System.out.println(arr[3]);
        }catch (ArrayIndexOutOfBoundsException e){
            System.out.println(e);
        }
        try{
            List<Integer> list=new ArrayList<>();
            list.add(1);
            list.add(1);
            list.add(1);
            System.out.println(list.get(3));
        }catch (IndexOutOfBoundsException e){
            System.out.println(e);
        }
        System.out.println("后续代码");*/


        /*//多个异常一次捕获，多次处理。
        try{
            int[] arr={1,2,3};
            System.out.println(arr[3]);
            List<Integer> list=new ArrayList<>();
            list.add(1);
            list.add(1);
            list.add(1);
            System.out.println(list.get(3));
        }catch (ArrayIndexOutOfBoundsException e){
            System.out.println(e);
        }catch (IndexOutOfBoundsException e){
            System.out.println(e);
        }
        System.out.println("后续代码");*/


        //多个异常一次捕获一次处理。
        try{
            int[] arr={1,2,3};
            System.out.println(arr[3]);
            List<Integer> list=new ArrayList<>();
            list.add(1);
            list.add(1);
            list.add(1);
            System.out.println(list.get(3));
        }catch (Exception e){
            System.out.println(e);
        }
    }
}
```



* 运行时异常被抛出可以不处理。即不捕获也不声明抛出。

* 如果finally有return语句,永远返回finally中的结果,避免该情况. 

  ```java
  public class text {
      public static void main(String[] args) throws FileNotFoundException,IOException{
          int a=getA();
          System.out.println(a);
      }
      public static int getA(){
          int a=10;
          try{
              return a;
          }catch (Exception e){
              System.out.println(e);
          }finally {
              a=100;
              return a;
          }
      }
  }
  //执行结果为100
  ```

  

* 如果父类抛出了多个异常,子类重写父类方法时,抛出和父类相同的异常或者是父类异常的子类或者不抛出异常。

* 父类方法没有抛出异常，子类重写父类该方法时也不可抛出异常。此时子类产生该异常，只能捕获处理，不能声明抛出

  ```java
  /*
   * 如果父类抛出了多个异常,子类重写父类方法时,抛出和父类相同的异常或者是父类异常的子类或者不抛出异常。
   * 父类方法没有抛出异常，子类重写父类该方法时也不可抛出异常。此时子类产生该异常，只能捕获处理，不能声明抛出
   */
  public class Fu {
      public void show01() throws NullPointerException,ClassCastException{}
      public void show02() throws IndexOutOfBoundsException{}
      public void show03() throws IndexOutOfBoundsException{}
  
      public void show04(){}
  }
  class Zi extends Fu{
      //子类重写父类方法时,抛出和父类相同的异常
      public void show01() throws NullPointerException,ClassCastException{}
      //子类重写父类方法时,抛出和父类异常的子类
      public void show02() throws ArrayIndexOutOfBoundsException{}
      //子类重写父类方法时,不抛出异常
      public void show03(){}
      //父类方法没有抛出异常，子类重写父类该方法时也不可抛出异常。
      public void show04(){}
      //此时子类产生该异常，只能捕获处理，不能声明抛出
      public void show05(){
          try {
              throw new Exception("编译器异常");
          }catch (Exception e){
              e.printStackTrace();
          }
      }
  }
  ```

  

  

### 自定义异常

自定义异常类：
    java提供的异常类，不够我们使用，需要自己定义一些类

格式：
	public class xxxException extends Exception | RuntimeException{
    		添加一个空参的构造方法
            添加一个带异常信息的构造方法
}

注意：
1.自定义异常类一般都是以Exception结尾，说明该类是一个异常类
2.自定义异常类，必须继承Exception或者RuntimeException
		继承Exception：那么自定义的异常类就是一个编译期异常，如果方法内部抛出了编译器异常，就必须处理这个异常，要么throws，要么try...catch
		继承RuntimeException：那么自定义的异常类就是一个运行期异常，无需处理，交给虚拟机处理（中断）

```java
public class RegisterException extends Exception{
    public RegisterException() {
        super();
    }

    public RegisterException(String message) {
        super(message);
    }
}
```



```java
public class text {
    static String[] s={"张三","李四"};
    public static void main(String[] args) throws RegisterException {
        Scanner sc=new Scanner(System.in);
        String name=sc.nextLine();
        check(name);
    }

    private static void check(String name) throws RegisterException {
        //1
       /* for (String s1 : s) {
            if(name.equals(s1)){
                throw new RegisterException("用户名已经注册");
            }
        }
        System.out.println("注册成功");*/
        //2
        for (String s1 : s) {
            if(name.equals(s1)){
                try {
                    throw new RegisterException("用户名已经注册");
                }catch (RegisterException e){
                    e.printStackTrace();
                    return;//结束方法
                }
            }
        }
        System.out.println("注册成功");
    }
}
```



### 多线程

-----------------------------------------------------

#### 并发与并行

* 并发：指两个或多个事件在同一个时间段内发生。
* 并行：指两个或多个事件在同一时刻发生（同时发生）。

#### 线程与进程

* **进程**：是指一个内存中运行的应用程序，每个进程都有一个独立的内存空间，一个应用程序可以同时运行多个进程；进程也是程序的一次执行过程，是系统运行程序的基本单位；系统运行一个程序即是一个进程从创建、运行到消亡的过程。

* **线程**：线程是进程中的一个执行单元，负责当前进程中程序的执行，一个进程中至少有一个线程。一个进程中是可以有多个线程的，这个应用程序也可以称之为多线程程序。 



#### 创建线程类Thread

Java中通过继承Thread类来**创建**并**启动多线程**的步骤如下：
1.定义Thread类的子类，并重写该类的run()方法，该run()方法的方法体就代表了线程需要完成的任务,因此把run()方法称为线程执行体。
2.创建Thread子类的实例，即创建了线程对象
3.调用线程对象的start()方法来启动该线程

java程序属于抢占式调度，哪个线程的优先级高，哪个线程就先执行；同一个优先级，随机选择一个执行

```java
public class TestThread1 extends Thread{
    @Override
    public void run() {
        //run方法线程体
        for(int i=0;i<10;i++){
            System.out.println("我在看代码----"+i);
        }
    }
    public static void main(String[] args) {
        //main线程，主线程
        TestThread1 testThread1=new TestThread1();//创建一个线程对象
        testThread1.start();//调用start()方法开启线程


        for(int i=0;i<600;i++){
            System.out.println("我在学习多线程----"+i);
        }
    }
}
```



#### Thread类常用方法

public String getName() :获取当前线程名称。 

public void start() :导致此线程开始执行; Java虚拟机调用此线程的run方法。 

public void run() :此线程要执行的任务在此处定义代码。 

public static void sleep(long millis) :使当前正在执行的线程以指定的毫秒数暂停（暂时停止执行）。 

public static Thread currentThread() :返回对当前正在执行的线程对象的引用。 



==public String getName() :获取当前线程名称。==

```java
package yy;
//创建线程方式一：继承Threadlei，重写run()，调用start
public class TestThread extends Thread{
    @Override
    public void run() {
        //获取线程名称
        String name=getName();
        System.out.println(name);
        //第二种方法
        Thread t=Thread.currentThread();
        System.out.println(t.getName());
    }
}
```

```java
package yy;

public class test {
    public static void main(String[] args) {
        TestThread mt=new TestThread();
        mt.start();

    }
}

```

==public static void sleep(long millis)== :使当前正在执行的线程以指定的毫秒数暂停（暂时停止执行）。 

```java
public class test {
    public static void main(String[] args) {
        for (int i=0;i<=60;i++){
            System.out.println(i);
            try{
                Thread.sleep(1000);
            }catch (InterruptedException e){
                e.printStackTrace();
            }
        }
    }
}
```



#### 创建线程的第二种方法`Runnable` 接口

因为 Java 只支持单继承，所以如果想要实现多线程，应该首先考虑实现 Runnable 接口，因为接口可以多实现，多继承。这就避免了类的单继承的局限性。

采用 java.lang.Runnable 也是非常常见的一种，我们只需要重写run方法即可。 

步骤如下： 
1.定义Runnable接口的实现类，并重写该接口的run()方法，该run()方法的方法体同样是该线程的线程执行体。 
2.创建Runnable接口的实现类对象。
3.创建thread类对象，构造方法中传递Runnable接口的实现类对象
4.调用线程对象的start()方法来启动线程

```java
public class RunnableImpl implements Runnable{
    @Override
    public void run() {
        for (int i=0;i<20;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}
```

```java
public class test {
    public static void main(String[] args) {
        RunnableImpl run=new RunnableImpl();
        Thread t=new Thread(run);
        t.start();
        for (int i=0;i<600;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}
```





#### 匿名内部类方式实现线程的创建

匿名：没有名字
内部类：写在其他类内部的类
匿名内部类：简化代码
		把子类继承父类，重写父类的方法，创建子类对象合一步完成
		把实现类实现类接口，重写接口中的方法，创建实现类对象合成一步完成
匿名内部类的最终产物：子类/实现类对象，而这个类没有名字

格式：
		new 父类/接口(){
				重复父类/接口中的方法
};

```java
public class test {
    public static void main(String[] args) {
        new Thread(){
            @Override
            public void run() {
                for(int i=0;i<20;i++){
                    System.out.println("1:"+Thread.currentThread().getName()+i);
                }
            }
        }.start();
        //线程的接口Runnable
        //Runnable r=new RunnableImpl()
        Runnable r=new Runnable(){
            @Override
            public void run() {
                for(int i=0;i<20;i++){
                    System.out.println("2:"+Thread.currentThread().getName()+i);
                }
            }
        };
        new Thread(r).start();

        new Thread(new Runnable(){
            @Override
            public void run() {
                for(int i=0;i<20;i++){
                    System.out.println("3:"+Thread.currentThread().getName()+i);
                }
            }
        }).start();
    }
}
```



### **线程安全** 

```java
package yy;
/*
    卖票案例
 */
public class RunnableImpl implements Runnable{
    private int ticket=100;
    @Override
    public void run() {
        while (true){
            if(ticket>0){
                //提高安全问题出现的概率，让程序睡眠
                try {
                    Thread.sleep(10);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println(Thread.currentThread().getName()+"-->正在卖哪张票"+ticket+"张票");
                ticket--;
            }
        }
    }
}

```



```java
public class test {
    public static void main(String[] args) {
        RunnableImpl run=new RunnableImpl();
        Thread t0=new Thread(run);
        Thread t1=new Thread(run);
        Thread t2=new Thread(run);
        t1.start();
        t0.start();
        t2.start();
    }
}
```



可能出现有几个线程同时在打印同一张票



#### **线程同步** 

窗口1线程进入操作的时候，窗口2和窗口3线程只能在外等着，窗口1操作结束，窗口1和窗口2和窗口3才有机会进入代码去执行。也就是说在某个线程修改共享资源的时候，其他线程不能修改该资源，等待修改完毕同步之后，才能去抢夺CPU 

三种方式完成同步操作：
1.同步代码块。 
2.同步方法。 
3.锁机制。 

##### 同步代码块

注意：
1.通过代码块中的锁对象，可以使用任意的对象。
2.但是必须保证多个线程使用的锁对象是同一个
3.锁对象的作用：
			把同步代码块锁住，只让一个线程在同步代码块中执行
格式：
	synchronized(同步锁){ 
		需要同步操作的代码 
	}



```java
public class RunnableImpl implements Runnable{
    private int ticket=100;
    Object obj=new Object();
    @Override
    public void run() {
        while (true){
            synchronized (obj){
                if(ticket>0){
                    try {
                        Thread.sleep(10);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    System.out.println(Thread.currentThread().getName()+"-->正在卖哪张票"+ticket+"张票");
                    ticket--;
                }
            }
        }
    }
}
```



```java
public class test {
    public static void main(String[] args) {
        RunnableImpl run=new RunnableImpl();
        Thread t0=new Thread(run);
        Thread t1=new Thread(run);
        Thread t2=new Thread(run);
        t1.start();
        t0.start();
        t2.start();
    }
}
```



##### 同步方法

使用步骤：
1.把访问了共享数据的代码抽取出来，放到一个方法中
2.在方法上添加synchronized修饰符

格式：
public synchronized void method(){ 

可能会产生线程安全问题的代码 

}

```java
public class RunnableImpl implements Runnable{
    private int ticket=100;
    Object obj=new Object();
    @Override
    public void run() {
        while (true){
            payTicket();
        }
    }
    public synchronized void payTicket(){
        if(ticket>0){
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName()+"-->正在卖哪张票"+ticket+"张票");
            ticket--;
        }
    }
}
```



```java
public class test {
    public static void main(String[] args) {
        RunnableImpl run=new RunnableImpl();
        Thread t0=new Thread(run);
        Thread t1=new Thread(run);
        Thread t2=new Thread(run);
        t1.start();
        t0.start();
        t2.start();
    }
}

```



##### Lock锁 

Lock锁也称同步锁，加锁与释放锁方法化了，如下： 

public void lock() :加同步锁。 

public void unlock() :释放同步锁。 

使用步骤：
1.在成员位置创建一个Reentrantlock对象
2.在可能会出现安全问题的代码前调用lock接口中的方法lock获取锁
3.在可能会出现安全问题的代码后调用lock接口中的方法unlock获取锁

### 线程状态 

------------------------------------------------------

| 线程状态 | 导致状态发生条件 |
| :----- | -----: |
| NEW(新建) |线程刚被创建，但是并未启动。还没调用start方法。 |
| Runnable(可 运行) | 线程可以在java虚拟机中运行的状态，可能正在运行自己代码，也可能没有，这取决于操 作系统处理器。 |
|Blocked(锁阻 塞) | 当一个线程试图获取一个对象锁，而该对象锁被其他的线程持有，则该线程进入Blocked状 态；当该线程持有锁时，该线程将变成Runnable状态。 |
| Waiting(无限 等待) | 一个线程在等待另一个线程执行一个（唤醒）动作时，该线程进入Waiting状态。进入这个 状态后是不能自动唤醒的，必须等待另一个线程调用notify或者notifyAll方法才能够唤醒。 |
|Timed Waiting(计时 等待) | 同waiting状态，有几个方法有超时参数，调用他们将进入Timed Waiting状态。这一状态 将一直保持到超时期满或者接收到唤醒通知。带有超时参数的常用方法有Thread.sleep 、 Object.wait。 |
| Teminated(被 终止) | 因为run方法正常退出而死亡，或者因为没有捕获的异常终止了run方法而死亡。|



![](img\线程状态图.png)

#### Timed Waiting（计时等待）

其实当我们调用了sleep方法之后，当前执行的线程就进入到“休眠状态”，其实就是所谓的Timed Waiting(计时等待)

wait（long m）和sleep一样传入毫秒

![](img\计时等待.png)

####  

#### BLOCKED（锁阻塞）

![](img\锁阻塞.png)

#### Waiting（无限等待）

创建一个顾客线程（消费者）：告知老板要的包子的种类和数量，调用wait方法，放弃cpu的执行，进入到waiting状态（无限等待）
创建一个老板进程（生产者）：花了5秒左做包子，做好包子后，唤醒

注意：
	顾客和老板线程必须使用同步代码块包裹起来，保证等待和唤醒只有一个在执行
	同步使用的锁对象必须保证唯一
	只有锁对象才能调用wait和notify

```java
public class test {
    public static void main(String[] args) {
        //创建锁对象，保证唯一
        Object obj=new Object();
        //创建一个顾客线程
        new Thread(){
            @Override
            public void run() {
                //保证等待和唤醒的线程只能有一个执行，需要使用同步技术
                synchronized (obj){
                    System.out.println("告知老板要的包子和数量");
                    //调用wait方法，放弃cpu的执行，进入waiting状态（无限等待）
                    try {
                        obj.wait();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    //唤醒之后执行的代码
                    System.out.println("吃");
                }
            }
        }.start();
        //创建一个老板进程
        new Thread(){
            @Override
            public void run() {
                //花了5秒做包子
                try {
                    Thread.sleep(5000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                //保证等待和唤醒的线程只能有一个执行，需要使用同步技术
                synchronized (obj){
                    System.out.println("老板5秒钟之后做好包子，告知顾客");
                    obj.notify();
                }
            }
        }.start();
    }
}

```



唤醒所有对象监视器obj.notifyAll();

![](img\无限等待.png)

### 等待唤醒机制

多个线程在处理同一个资源，并且任务不同时，需要线程通信来帮助解决线程之间对同一个变量的使用或操作。 就是多个线程在操作同一份数据时， 避免对同一共享变量的争夺。也就是我们需要通过一定的手段使各个线程能有效的利用资源。而这种手段即—— **等待唤醒机制。**





**调用wait和notify方法需要注意的细节**

1. wait方法与notify方法必须要由同一个锁对象调用。因为：对应的锁对象可以通过notify唤醒使用同一个锁对象调用的wait方法后的线程。
2. wait方法与notify方法是属于Object类的方法的。因为：锁对象可以是任意对象，而任意对象的所属类都是继承了Object类的。
3. wait方法与notify方法必须要在同步代码块或者是同步函数中使用。因为：必须要通过锁对象调用这2个方法。

#### 生产者与消费者问题

等待唤醒机制其实就是经典的“生产者与消费者”的问题。

就拿生产包子消费包子来说等待唤醒机制如何有效利用资源：

~~~java
包子铺线程生产包子，吃货线程消费包子。当包子没有时（包子状态为false），吃货线程等待，包子铺线程生产包子（即包子状态为true），并通知吃货线程（解除吃货的等待状态）,因为已经有包子了，那么包子铺线程进入等待状态。接下来，吃货线程能否进一步执行则取决于锁的获取情况。如果吃货获取到锁，那么就执行吃包子动作，包子吃完（包子状态为false），并通知包子铺线程（解除包子铺的等待状态）,吃货线程进入等待。包子铺线程能否进一步执行则取决于锁的获取情况。
~~~



```java
public class BaoZi {
    String pi;
    String xian;
    boolean flag=false;
}
```



```java
public class BaoZiPu extends Thread{
    private BaoZi bz;

    public BaoZiPu(BaoZi bz) {
        this.bz = bz;
    }

    @Override
    public void run() {
        int count=0;
        synchronized(bz){
            if(bz.flag==true) {
                try {
                    wait();
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
            //被唤醒之后执行，包子铺生产包子
            //增加一些趣味性：交替生产两种包子
            if(count%2==0){
                bz.pi="薄皮";
                bz.xian="三鲜馅";
            }else{
                bz.pi="冰皮";
                bz.xian="牛肉馅";
            }
            count++;
            System.out.println("包子铺正在生产："+bz.pi+bz.xian+"包子");
            try {
                sleep(3000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            bz.flag=true;
            //唤醒吃货线程，让吃货线吃包子
            bz.notify();
            System.out.println("包子铺已经生产"+bz.pi+bz.xian+"包子");
        }
    }
}
```

```java
public class ChiHuo extends Thread{
    private BaoZi bz;

    public ChiHuo(BaoZi bz) {
        this.bz = bz;
    }

    @Override
    public void run() {
        synchronized (bz){
            if(bz.flag==false){
                try {
                    bz.wait();
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
            System.out.println("吃货正在吃："+bz.pi+bz.xian+"包子");
            bz.flag=false;
            bz.notify();
            System.out.println("吃货吃完了："+bz.pi+bz.xian+"包子");
        }
    }
}

```



```java
public class test {
    public static void main(String[] args) {
        BaoZi bz=new BaoZi();
        new BaoZiPu(bz).start();
        new ChiHuo(bz).start();
    }
}
```



### 线程池

-----------------------------------------------------

**线程池：**其实就是一个容纳多个线程的容器，其中的线程可以反复使用，省去了频繁创建线程对象的操作，无需反复创建线程而消耗过多资源

Java里面线程池的顶级接口是`java.util.concurrent.Executor`

Executors类中有个创建线程池的方法如下：

* `public static ExecutorService newFixedThreadPool(int nThreads)`：返回线程池对象。(创建的是有界线程池,也就是池中的线程个数可以指定最大数量)
  参数：int nThreads：创建线程池中包含的线程数量
  返回值： ExecutorService接口，返回的是 ExecutorService接口的实现类对象，我们可以使用 ExecutorService接口（多态）

方法如下：

* `submit(Runnable task)`:获取线程池中的某一个线程对象，并执行

- `void shutdown()`关闭/销毁线程池的方法

使用线程池中线程对象的步骤：

1. 创建线程池的工厂类Executors里面提供的静态方法newFixedThreadPool生产一个指定线程数量的线程池。
2. 创建一个类，实现Runnable接口，重写run方法，设置线程任务
3. 调用ExecutorService中的方法submit，传递线程任务（实现类），开启线程，执行run方法。
4. 关闭线程池(一般不做)。



```java
public class RunnableImpl implements Runnable{
    @Override
    public void run() {
        System.out.println(Thread.currentThread().getName()+"创建了一个新的进程");
    }
}
```

```java
public class test {
    public static void main(String[] args) {
        ExecutorService es= Executors.newFixedThreadPool(2);
        es.submit(new RunnableImpl());
        es.submit(new RunnableImpl());
        es.submit(new RunnableImpl());
        //线程池会一直开启，使用完线程，会自动把线程归还给线程池，线程可以继续使用
    }
}

```





### Lambda表达式

-----------------------------------------


函数式编程思想:

​	只要能获取到结果,谁去做的,怎么做的都不重要,重视的是结果,不重视过程

#### 冗余的Runnable代码

当需要启动一个线程去完成任务时，通常会通过`java.lang.Runnable`接口来定义任务内容，并使用`java.lang.Thread`类来启动该线程。代码如下：

```java
public class Demo01Runnable {
	public static void main(String[] args) {
    	// 匿名内部类
		Runnable task = new Runnable() {
			@Override
			public void run() { // 覆盖重写抽象方法
				System.out.println("多线程任务执行！");
			}
		};
		new Thread(task).start(); // 启动线程
	}
}
```

本着“一切皆对象”的思想，这种做法是无可厚非的：首先创建一个`Runnable`接口的匿名内部类对象来指定任务内容，再将其交给一个线程来启动。

代码分析

对于`Runnable`的匿名内部类用法，可以分析出几点内容：

- `Thread`类需要`Runnable`接口作为参数，其中的抽象`run`方法是用来指定线程任务内容的核心；
- 为了指定`run`的方法体，**不得不**需要`Runnable`接口的实现类；
- 为了省去定义一个`RunnableImpl`实现类的麻烦，**不得不**使用匿名内部类；
- 必须覆盖重写抽象`run`方法，所以方法名称、方法参数、方法返回值**不得不**再写一遍，且不能写错；
- 而实际上，**似乎只有方法体才是关键所在**。



#### Lambda写法

```java
public class test {
    public static void main(String[] args) {
        //使用匿名内部类
        new Thread(new Runnable(){
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName()+"创建了一个新的进程");
            }
        }).start();
        //使用lambda表达式，实现多线程
        new Thread(()->{//空括号里填参数
                System.out.println(Thread.currentThread().getName()+"创建了一个新的进程");
            }
        ).start();
    }
}
```

```java
public class test {
    public static void main(String[] args) {
        ILove i = (int a) ->{
                System.out.println("i love you");
        };
        //简化一
        i = (a) ->{
            System.out.println("i love you");
        };
        //简化括号
        i = a ->{
            System.out.println("i love you");
        };
        //去掉花括号多行不可
        //多个参数也可以去掉参数类型，要去掉就都去掉但要加括号
        i = a-> System.out.println("i love you");

    }
}
interface ILove{
    void love(int a);
}
```



##### 匿名内部类的好处与弊端

一方面，匿名内部类可以帮我们**省去实现类的定义**；另一方面，匿名内部类的语法——**确实太复杂了！**



##### 语义分析

仔细分析该代码中的语义，`Runnable`接口只有一个`run`方法的定义：

* `public abstract void run();`

即制定了一种做事情的方案（其实就是一个函数）：

* **无参数**：不需要任何条件即可执行该方案。
* **无返回值**：该方案不产生任何结果。
* **代码块**（方法体）：该方案的具体执行步骤。

同样的语义体现在`Lambda`语法中，要更加简单：

```java
() -> System.out.println("多线程任务执行！")
```

* 前面的一对小括号即`run`方法的参数（无），代表不需要任何条件；
* 中间的一个箭头代表将前面的参数传递给后面的代码；
* 后面的输出语句即业务逻辑代码。

#### Lambda标准格式

Lambda省去面向对象的条条框框，格式由**3个部分**组成：

* 一些参数
* 一个箭头
* 一段代码

Lambda表达式的**标准格式**为：

```
(参数类型 参数名称) -> { 重写接口的抽象方法的方法体 }
```

格式说明：

* 小括号内的语法与传统方法参数列表一致：无参数则留空；多个参数则用逗号分隔。
* `->`是新引入的语法格式，代表指向动作。
* 大括号内的语法与传统方法体要求基本一致。

#### Lambda的参数和返回值

```
需求:
    使用数组存储多个Person对象
    对数组中的Person对象使用Arrays的sort方法通过年龄进行升序排序
```

下面举例演示`java.util.Comparator<T>`接口的使用场景代码，其中的抽象方法定义为：

* `public abstract int compare(T o1, T o2);`

当需要对一个对象数组进行排序时，`Arrays.sort`方法需要一个`Comparator`接口实例来指定排序的规则。假设有一个`Person`类，含有`String name`和`int age`两个成员变量：

```java
public class Person { 
    private String name;
    private int age;
    
    // 省略构造器、toString方法与Getter Setter 
}
```

传统写法

如果使用传统的代码对`Person[]`数组进行排序，写法如下：

```java
import java.util.Arrays;
import java.util.Comparator;

public class Demo06Comparator {
    public static void main(String[] args) {
      	// 本来年龄乱序的对象数组
        Person[] array = {
        	new Person("古力娜扎", 19),
        	new Person("迪丽热巴", 18),
       		new Person("马尔扎哈", 20) };

      	// 匿名内部类
        Comparator<Person> comp = new Comparator<Person>() {
            @Override
            public int compare(Person o1, Person o2) {
                return o1.getAge() - o2.getAge();
            }
        };
        Arrays.sort(array, comp); // 第二个参数为排序规则，即Comparator接口实例

        for (Person person : array) {
            System.out.println(person);
        }
    }
}
```

这种做法在面向对象的思想中，似乎也是“理所当然”的。其中`Comparator`接口的实例（使用了匿名内部类）代表了“按照年龄从小到大”的排序规则。

代码分析

下面我们来搞清楚上述代码真正要做什么事情。

- 为了排序，`Arrays.sort`方法需要排序规则，即`Comparator`接口的实例，抽象方法`compare`是关键；
- 为了指定`compare`的方法体，**不得不**需要`Comparator`接口的实现类；
- 为了省去定义一个`ComparatorImpl`实现类的麻烦，**不得不**使用匿名内部类；
- 必须覆盖重写抽象`compare`方法，所以方法名称、方法参数、方法返回值**不得不**再写一遍，且不能写错；
- 实际上，**只有参数和方法体才是关键**。

Lambda写法

```java
import java.util.Arrays;

public class Demo07ComparatorLambda {
    public static void main(String[] args) {
        Person[] array = {
          	new Person("古力娜扎", 19),
          	new Person("迪丽热巴", 18),
          	new Person("马尔扎哈", 20) };

        Arrays.sort(array, (Person a, Person b) -> {
          	return a.getAge() - b.getAge();
        });

        for (Person person : array) {
            System.out.println(person);
        }
    }
}
```



#### 练习：使用Lambda标准格式（无参无返回）

```java
public class test {
    public static void main(String[] args) {
        invokeCook(()->{
            System.out.println("cook");
        });
    }
    private static void invokeCook(Cook cook) {
        cook.makeFood();
    }
}
interface Cook {
    void makeFood();
}
```





#### 练习：使用Lambda标准格式（有参有返回）

```java
public class test {
    public static void main(String[] args) {
        invokeCalc(1, 2, new Calculator() {
            @Override
            public int calc(int a, int b) {
                return a+b;
            }
        });

        invokeCalc(10,20,(a,b)->{
            return a+b;
        });
    }
    public static void invokeCalc(int a,int b,Calculator c){
        int sum=c.calc(a,b);
        System.out.println(sum);
    }
}

interface Calculator{
    //定义一个计算两个int整数和方法并返回结果
    int calc(int a,int b);
}
```

#### Lambda省略格式

凡是根据上下文推导出来的内容，都可以省略书写
可以省略的内容：
1.（参数列表）：括号中参数列表的数据类型，可以省略不写
2.（参数列表）：括号中如果参数只有一个，那么类型和（）都可以省略
3.（一些代码）：如果{}中的代码只有一行，无论是否有返回值，都可以省略（{}，return，分号）注意：要省略{}，return，分号必须一起省略

```java
public class test {
    public static void main(String[] args) {
        ArrayList<String> list01=new ArrayList<>();
        ArrayList<String> list02=new ArrayList<>();
        new Thread(()-> System.out.println(Thread.currentThread().getName()+"创建了一个新的进程")).start();
    }

}
```

####  Lambda的使用前提

Lambda的语法非常简洁，完全没有面向对象复杂的束缚。但是使用时有几个问题需要特别注意：

1. 使用Lambda必须具有接口，且要求**接口中有且仅有一个抽象方法**。
   无论是JDK内置的`Runnable`、`Comparator`接口还是自定义的接口，只有当接口中的抽象方法存在且唯一时，才可以使用Lambda。
2. 使用Lambda必须具有**上下文推断**。
   也就是方法的参数或局部变量类型必须为Lambda对应的接口类型，才能使用Lambda作为该接口的实例。

> 备注：有且仅有一个抽象方法的接口，称为“**函数式接口**”。





### File类

---------------------------------------------

java.io.File` 类是文件和目录路径名的抽象表示，主要用于文件和目录的创建、查找和删除等操作。

我们可以使用File类的方法：
				创建一个文件/文件夹
				删除文件/文件夹
				获取文件/文件夹
				判断文件/文件夹是否存在
				对文件夹进行遍历
				获取文件的大小

重点：记住这三个单词
			file：文件
			directory：文件夹/目录
			path：路径

#### 静态方法

static String pathSeparator 与系统有关的路径分隔符，为了方便，它被表示为一个字符串。
static char  pathSeparatorChar与系统有关的路径分隔符

static String  separator与系统有关的默认名称分隔符，为了方便，它被表示为一个字符串。
static char separatorChar与系统有关的默认名称分隔符。

```java
public class test {
    public static void main(String[] args) {

        String pathSeparator = File.pathSeparator;
        System.out.println(pathSeparator);//路径分隔符 windows：分号; linux：冒号:

        String separator = File.separator;
        System.out.println(separator);//文件名称分隔符  windows：反斜杠\ linux：正斜杠/

        System.out.println("C:"+File.separator+"devalop"+File.separator+"a"+File.separator+"a.txt");
    }
}
```



#### 绝对路径和相对路径

路径：
		绝对路径：是一个完整路径
				以盘符（ C: , D: ）开始的路径
					C:\ \a.txt
		相对路径：是一个简化的路径
				相对指的是相对于当前项目的根目录
				C:\ \Users\ \itcast\ \123.txt--->简化为：123.txt（可以省略项目的根目录）

注意：
		1.路径是不区分大小写的
		2.路径中的文件名称分隔符window使用反斜杠，反斜杠是转义字符，两个反斜杠代表一个普通的反斜杠



#### 构造方法

* `public File(String pathname) ` ：通过将给定的**路径名字符串**转换为抽象路径名来创建新的 File实例。  
* `public File(String parent, String child) ` ：从**父路径名字符串和子路径名字符串**创建新的 File实例。
* `public File(File parent, String child)` ：从**父抽象路径名和子路径名字符串**创建新的 File实例。  

```java
public class test {
    public static void main(String[] args) {
        //show1();
        //show2("C:\\","a.txt");
        show3();
    }
    /*
        public File(String pathname)
        String pathname:字符串路径名称
        路径可以是以文件结尾，也可以是以文件夹结尾
        路径可以是相对路径，也可以是绝对路径
        路径可以是存在也可以是不存在
        创建File对象，只是把字符串路径封装为File对象，不考虑路径的真假情况
    */
    private static void show1() {
        File f1=new File("C:\\Users\\itcast\\IdeaProjects\\a.txt");
        System.out.println(f1);
    }
    /*
        public File(String parent, String child)
        参数：把路径分成了两部分
        String parent：父路径
        String child：子路径
        好处：父路径和子路径，可以单独书写，使用起来非常灵活
     */
    private static void show2(String parent,String child){
        File file=new File(parent,child);
        System.out.println(file);
    }
    /*
        好处：
            父路径是File类型，可以使用File的方法对路径进行一些操作，再使用路径创建对象
     */
    private static void show3(){
        File patent=new File("C:\\");
        File file=new File(patent.,"hello.java");
        System.out.println(file);
    }
}
```



#### 常用方法

* `public String getAbsolutePath() ` ：返回此File的绝对路径名字符串。
* ` public String getPath() ` ：获取构造方法中的路径。 
* `public String getName()`  ：获取构造方法传递路径的结尾部分（文件/文件夹）
* `public long length()`  ：返回由此File表示的文件的长度。获取的是构造方法指定的文件的大小，以字节为单位。
  文件是没有大小的

```java
public class test {
    public static void main(String[] args) {
        show01();
        show02();
        show03();
        show04();
    }

    private static void show01() {
        File f1=new File("C:\\Users\\Administrator\\IdeaProjects\\a.txt");
        String absolutePath1 = f1.getAbsolutePath();
        System.out.println(absolutePath1);
        File f2=new File("a.txt");
        String absolutePath2 = f2.getAbsolutePath();
        System.out.println(absolutePath2);
    }
    private static void show02() {
        File f1=new File("C:\\Users\\Administrator\\IdeaProjects\\a.txt");
        File f2=new File("a.txt");
        String path1 = f1.getPath();
        String path2 = f2.getPath();
        System.out.println(path1);
        System.out.println(path2);
    }
    private static void show03() {
        File f1=new File("C:\\Users\\Administrator\\IdeaProjects\\a.txt");
        File f2=new File("C:\\Users\\Administrator\\IdeaProjects");
        String name1 = f1.getName();
        String name2 = f2.getName();
        System.out.println(name1);
        System.out.println(name2);
    }
    private static void show04() {
        File f1=new File("C:\\Users\\Administrator\\a.txt");
        long length = f1.length();
        System.out.println(length);
    }
}
```



#### 判断功能的方法

- `public boolean exists()` ：此File表示的文件或目录是否实际存在。

- `public boolean isDirectory()` ：构造方法中给的路径是否以文件夹结尾。路径不存在返回false。

- `public boolean isFile()` ：构造方法中给的路径是否以文件结尾。路径不存在返回false。

  ```java
  public class test {
      public static void main(String[] args) {
          //show01();
          show02();
      }
  
      private static void show01() {
          File f1=new File("C:\\Users\\Administrator\\a.txt");
          System.out.println(f1.exists());
          File f2=new File("a.txt");
          System.out.println(f2.exists());
      }
      private static void show02() {
          File f1=new File("C:\\Users\\Administrator\\IdeaProjects\\a.txt");
          File f2=new File("C:\\Users\\Administrator\\a.txt");
          if(f1.exists()){//判断路径是否存在
              System.out.println(f1.isDirectory());
              System.out.println(f1.isFile());
          }
          if(f2.exists()){//判断路径是否存在
              System.out.println(f2.isDirectory());
              System.out.println(f2.isFile());
          }
      }
  }
  ```

  

#### 创建删除功能的方法

- `public boolean createNewFile()` ：当且仅当具有该名称的文件尚不存在时，创建一个新的空文件。 返回值是布尔值。文件本来不存在，新建文件后返回true。文件存在，返回false。

- `public boolean delete()` ：删除由此File表示的文件或目录。  

- `public boolean mkdir()` ：创建单级文件夹。

- `public boolean mkdirs()` ：既可以创建单级文件夹，也可以创建多级文件夹

  ```java
  /*
  - public boolean createNewFile()` ：当且仅当具有该名称的文件尚不存在时，创建一个新的空文件。
  - `public boolean delete()` ：删除由此File表示的文件或目录。
  - `public boolean mkdir()` ：创建单级文件夹。
  - `public boolean mkdirs()` ：既可以创建单级文件夹，也可以创建多级文件夹
   */
  public class test {
      public static void main(String[] args) throws IOException {
          //show01();
          //show02();
          show03();
      }
      /*
      public boolean createNewFile()` 当且仅当具有该名称的文件尚不存在时，创建一个新的空文件。
      返回值是布尔值。
      true文件本来不存在，新建文件后返回。
      false文件本来存在。
      注意：
          1.此方法只能创建文件，不能创建文件夹
          2.创建文件的路径必须存在。否则会抛出异常
       */
      private static void show01() throws IOException {
          File f1=new File("C:\\Users\\Administrator\\a.txt");
          boolean b1=f1.createNewFile();
          System.out.println(b1);
          File f2=new File("C:\\Users\\Administrator\\b.txt");
          boolean b2=f2.createNewFile();
          System.out.println(b2);
      }
      /*
      public boolean mkdir() ：创建单级文件夹。
      public boolean mkdirs()：既可以创建单级文件夹，也可以创建多级文件夹
      返回值是布尔值。
      true文件本来不存在，新建文件夹后返回。
      false文件本来存在。构造方法中的路径不存在返回false
      注意：
          1.此方法只能创建文件夹，不能创建文件
       */
      private static void show02() {
          File f1=new File("C:\\Users\\Administrator");
          File f2=new File("aa\\11\\22");
          boolean b1=f1.mkdir();
          boolean b2=f2.mkdirs();
          System.out.println(b1);
          System.out.println(b2);
      }
      /*
          public boolean delete()：删除由此File表示的文件或目录。
          返回值:布尔值。
          true:文件/文件夹删除成功，返回true
          false：文件夹中有内容，不会直接删除返回false
          注意：delete方法是直接在硬盘删除文件，不走回收站，删除要谨慎
       */
      private static void show03() {
          File f1=new File("aa\\11\\22");
          boolean b1 = f1.delete();
          System.out.println(b1);
      }
  }
  
  ```

  

#### 目录的遍历

* `public String[] list()` ：返回一个String数组，表示该File目录中的所有子文件或目录。


* `public File[] listFiles()` ：返回一个File数组，表示该File目录中的所有的子文件或目录。  

注意：
    list方法和listFiles方法遍历的是构造方法中给出的目录
    如果构造方法中给出的目录不存在，会抛出空指针异常
    如果构造方法中给出的路径不是一个目录，会抛出空指针异常

```java
public class test {
    public static void main(String[] args) {
        //show01();
        show02();

    }
    /*
        public String[] list() ：返回一个String数组，表示该File目录中的所有子文件或目录
        遍历构造方法中给出的目录，会获取目录中所有文件/文件夹的名称，把获取到的多个名称存储到一个String类型的数组中
     */
    private static void show01()  {
        File f1=new File("C:\\Users\\Administrator");
        String[] arr=f1.list();
        for (String s : arr) {
            System.out.println(s);
        }
    }
    /*
        public File[] listFiles() ：返回一个File数组，表示该File目录中的所有的子文件或目录
        遍历构造方法中给出的目录，会获取目录中所有文件/文件夹，把文件/文件夹封装为File对象，多个File对象存储到File数组中
     */
    private static void show02() {
        File f1=new File("C:\\Users\\Administrator");
        File[] files = f1.listFiles();
        for (File f : files) {
            System.out.println(f);
        }
    }
}
```



#### 递归打印多级目录

```java
public class test {
    public static void main(String[] args) {
        File f1=new File("aa");
        f1.mkdirs();
        show(f1);
    }

    private static void show(File f) {
        File[] files=f.listFiles();
        for (File ff : files) {
            String f1=ff.getAbsolutePath();
            System.out.println(f1);
            File f2=new File(f1);
            show(ff);
        }
    }
}
```

#### 文件搜索	

搜索`D:\aaa` 目录中的`.java` 文件。

**分析**：

1. 目录搜索，无法判断多少级目录，所以使用递归，遍历所有目录。
2. 遍历目录时，获取的子文件，通过文件名称，判断是否符合条件。

**代码实现**：

```java
public class DiGuiDemo3 {
    public static void main(String[] args) {
        // 创建File对象
        File dir  = new File("D:\\aaa");
      	// 调用打印目录方法
        printDir(dir);
    }

    public static void printDir(File dir) {
      	// 获取子文件和目录
        File[] files = dir.listFiles();
      	
      	// 循环打印
        for (File file : files) {
            if (file.isFile()) {
              	// 是文件，判断文件名并输出文件绝对路径
                if (file.getName().endsWith(".java")) {
                    System.out.println("文件名:" + file.getAbsolutePath());
                }
            } else {
                // 是目录，继续遍历,形成递归
                printDir(file);
            }
        }
    }
}
```

#### 文件过滤器优化

File[] listFiles(FileFilter filter)
`java.io.FileFilter`接口:是File的过滤器。 用于抽象路径名（File对象）的过滤器
作用：用来过滤文件（File对象）
boolean accept(File pathname)  `：测试pathname是否应该包含在当前File目录中，符合则返回true。
参数：使用ListFiles方法遍历目录，获取的每一个文件对象

File[] listFiles(FilenameFilter filter)
java.io.FilenameFilter接口：实现此接口的类实例可用于过滤文件名
作用：用来过滤文件名称
boolean accept(File dir,String name)  ：测试指定文件是否包含在某一文件列表中
参数：File fir：构造方法中传递的被遍历的目录
			String name：使用ListFiles方法遍历目录，获取的每一个文件/文件夹的名称

注意：两个过滤器是没有实现类的，需要我们自己写实现类，重写过滤的方法accept，在方法中自己定义过滤的规则

```java
public class FileFilterImpl  implements FileFilter {
    @Override
    public boolean accept(File pathname) {
        if(pathname.isDirectory())
            return true;
        return pathname.getName().toLowerCase().endsWith(".java");
    }
}
```

```java
public class test {
    public static void main(String[] args) {
        File f1=new File("aa");
        //f1.mkdirs();
        show(f1);
        //String s=f1.getName();
        //System.out.println(s.endsWith(".java"));
    }

    private static void show(File f) {
        File[] files=f.listFiles(new FileFilterImpl());//传递过滤器对象
        for (File ff : files) {
            if(ff.isDirectory()){
                show(ff);
            }
            else{
                System.out.println(ff);
            }
        }
    }
}
```



#### Lambda优化

```java
public class test {
    public static void main(String[] args) {
        File f1=new File("aa");
        //f1.mkdirs();
        show(f1);
        //String s=f1.getName();
        //System.out.println(s.endsWith(".java"));
    }

    private static void show(File f) {
        File[] files=f.listFiles((File pathname)->{
            return pathname.getName().toLowerCase().endsWith(".java")||pathname.isDirectory();
        });//传递过滤器对象
        for (File ff : files) {
            if(ff.isDirectory()){
                show(ff);
            }
            else{
                System.out.println(ff);
            }
        }
    }
}
```





### 字节流

-----------------------------------------



####  字节输出流【OutputStream】

`java.io.OutputStream `抽象类是表示字节输出流的所有类的超类
定义了一些子类共性的成员方法：

* `public void close()` ：关闭此输出流并释放与此流相关联的任何系统资源。  
* `public void flush() ` ：刷新此输出流并强制任何缓冲的输出字节被写出。  
* `public void write(byte[] b)`：将 b.length字节从指定的字节数组写入此输出流。  
* `public void write(byte[] b, int off, int len)` ：从指定的字节数组写入 len字节，从偏移量 off开始输出到此输出流。  
* `public abstract void write(int b)` ：将指定的字节输出流。



#### FileOutputStream类

`OutputStream`的子类`java.io.FileOutputStream `类是文件输出流
作用：把内存中的数据写出到硬盘的文件中。

##### 构造方法

* `public FileOutputStream(File file)`：创建一个向指定 File对象表示的文件中写入数据的文件输出流。
* `public FileOutputStream(String name)`： 创建一个向具有指定名称的文件中写入数据的输出文件流。

写入原理（内存->硬盘）
java程序--->JVM（java虚拟机）--->OS调用写数据的方法--->把数据写到文件中

字节输出流的使用步骤：
		1、创建一个FileOutputStream对象，构造方法中传递写入数据的目的地
		2、调用FileOutputStream对象中的方法write，把数据写入到文件中
		3、释放资源（流使用会占用一定的内存，使用完毕要把内存清空，提高程序的效率）

```java
public class text {
    public static void main(String[] args) throws IOException {
        FileOutputStream fos=new FileOutputStream("a.txt");
        fos.write(97);//只要处理这个异常，这个是父类
        fos.close();
    }
}
```



##### 写出字节数据

1、写出字节数组：`public void write(byte[] b)`
一次写多个字节：
		如果写的第一个字节是正数（0--127），那么显示的时候会查询ASCII
		如果写的第一个字节是负数，那第一个字节会和第二个字节，两个字节组成一个中文显示，查询系统默认码表

2、写字节数组的一部分：`write(byte[] b, int off, int len)` ,每次写出从off索引开始，len个字节

```java
public class text {
    public static void main(String[] args) throws IOException {
        FileOutputStream fos=new FileOutputStream(new File("a.txt"));
        byte[] bytes={-65,-66,67,68,69};
        fos.write(bytes);//只要处理这个异常，这个是父类

        fos.write(bytes,1,2);

        /*
            写入字符的方法：可以使用String类中的方法把字符串转换为字节数组
            getBytes():把字符串转换为字节数组
         */
        byte[] bytes1 = "你好".getBytes();
        System.out.println(Arrays.toString(bytes1));
        fos.write(bytes1);
        fos.close();
    }
}
```



##### 数据追加续写

- `public FileOutputStream(File file, boolean append)`： 创建文件输出流以写入由指定的 File对象表示的文件。  

- `public FileOutputStream(String name, boolean append)`： 创建文件输出流以指定的名称写入文件。  

  参数：apend：追加写开关
  true：创建对象不会覆盖原文件，继续在文件的末尾追加写数据；false：创建一个新文件，覆盖原文件

  换行符号：window：\r\n
  					linux:/n
  					mac:/r

  ```java
  public class text {
      public static void main(String[] args) throws IOException {
          //追加
          FileOutputStream fos=new FileOutputStream("aa\\a.txt",true);
          for (int i=0;i<10;i++){
              fos.write("你好".getBytes());
              fos.write("\r\n".getBytes());
          }
          fos.write("你好".getBytes());
          fos.close();
      }
  }
  ```

  

#### 字节输入流【InputStream】

`java.io.InputStream `抽象类是表示字节输入流的所有类的超类，可以读取字节信息到内存中。它定义了字节输入流的基本共性功能方法。

- `public void close()` ：关闭此输入流并释放与此流相关联的任何系统资源。    
- `public abstract int read()`： 从输入流读取数据的下一个字节。 
- `public int read(byte[] b)`： 从输入流中读取一些字节数，并将它们存储到字节数组 b中 。

####  FileInputStream类

`java.io.FileInputStream `类是文件输入流，从文件中读取字节。

##### 构造方法

* `FileInputStream(File file)`： 通过打开与实际文件的连接来创建一个 FileInputStream ，该文件由文件系统中的 File对象 file命名。 
* `FileInputStream(String name)`： 通过打开与实际文件的连接来创建一个 FileInputStream ，该文件由文件系统中的路径名 name命名。  

当你创建一个流对象时，必须传入一个文件路径。该路径下，如果没有该文件,会抛出`FileNotFoundException` 。

##### 读取字节数据

1、读取字节：`read`方法，每次可以读取一个字节的数据，提升为int类型，读取到文件末尾，返回`-1`

```java
public class text {
    public static void main(String[] args) throws IOException {
        FileInputStream fis=new FileInputStream("aa\\a.txt");
        /*int len = fis.read();
        System.out.println(len);
        len = fis.read();
        System.out.println(len);
        len = fis.read();
        System.out.println(len);
        len = fis.read();
        System.out.println(len);//没了返回-1*/
        int len=0;
        while((len=fis.read())!=-1){
            System.out.println((char)len);
        }
        fis.close();
    }
}
```



2、`int read(byte[] b)`每次读取b的长度个字节到数组中，返回读取到的有效字节个数，读取到末尾时，返回`-1` 

```java
/*
    String类的构造方法：
        String(byte[] bytes):把字节数组转换为字符串
        String(byte[] bytes，int offset,int length)把字节数组的一部分转换为字符串 offset：开始索引 length：长度
 */
public class text {
    public static void main(String[] args) throws IOException {
        FileInputStream fis=new FileInputStream("aa\\a.txt");
        /*byte[] bytes=new byte[3];
        int len=fis.read(bytes);
        System.out.println(len);//读取字符串的个数
        System.out.println(new String(bytes));*/
        byte[] bytes=new byte[1024];
        int len=0;
        while((len=fis.read(bytes))!=-1){
            System.out.println(new String(bytes,0,len));
        }
        fis.close();
    }
}

```



#### 字节流练习：图片复制

```java
public class text {
    public static void main(String[] args) throws IOException {
        FileInputStream fis=new FileInputStream("C:\\1.jpg");
        FileOutputStream fos=new FileOutputStream("D:\\1.jpg");
        byte[] bytes=new byte[1024];
        int len=0;
        while((len=fis.read(bytes))!=-1){
            fos.write(bytes,0,len);
        }
        fos.close();//流的关闭原则：先开后关，后开先关。
        fis.close();
    }
}
```





### 字符流

-----------------------------------------------------------------

当使用字节流读取文本文件时，可能会有一个小问题。就是遇到中文字符时，可能不会显示完整的字符，那是因为一个中文字符可能占用多个字节存储。

#### 字符输入流【Reader】

java.io.Reader`抽象类是表示用于读取字符流的所有类的超类，可以读取字符信息到内存中。它定义了字符输入流的基本共性功能方法。

- `public void close()` ：关闭此流并释放与此流相关联的任何系统资源。    
- `public int read()`： 从输入流读取一个字符。 
- `public int read(char[] cbuf)`： 从输入流中读取一些字符，并将它们存储到字符数组 cbuf中 。

####  FileReader类

##### 构造方法

- `FileReader(File file)`： 创建一个新的 FileReader ，给定要读取的File对象。   
- `FileReader(String fileName)`： 创建一个新的 FileReader ，给定要读取的文件的名称。  

构造和读取的方法

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileReader fr=new FileReader("aa\\a.txt");
        int len=0;
        while((len=fr.read())!=-1){
            System.out.print((char)len);
        }

        
        char[] cs=new char[1024];
        len =0;
        while((len=fr.read(cs))!=-1){
            System.out.println(new String(cs,0,len));
        }
        fr.close();
    }
}
```



#### 字符输出流【Writer】

`java.io.Writer `抽象类是表示用于写出字符流的所有类的超类，将指定的字符信息写出到目的地。它定义了字节输出流的基本共性功能方法。

- `void write(int c)` 写入单个字符。
- `void write(char[] cbuf) `写入字符数组。 
- `abstract  void write(char[] cbuf, int off, int len) `写入字符数组的某一部分,off数组的开始索引,len写的字符个数。 
- `void write(String str) `写入字符串。 
- `void write(String str, int off, int len)` 写入字符串的某一部分,off字符串的开始索引,len写的字符个数。
- `void flush() `刷新该流的缓冲。  
- `void close()` 关闭此流，但要先刷新它。 

#### FileWriter类

`java.io.FileWriter `类是写出字符到文件的便利类。构造时使用系统默认的字符编码和默认字节缓冲区。

##### 构造方法

- `FileWriter(File file)`： 创建一个新的 FileWriter，给定要读取的File对象。   
- `FileWriter(String fileName)`： 创建一个新的 FileWriter，给定要读取的文件的名称。  

当你创建一个流对象时，必须传入一个文件路径，类似于FileOutputStream。

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileWriter fw=new FileWriter("aa\\a.txt");
        fw.write(96);//把数据写入到内存缓冲区
        fw.flush();
        fw.close();
    }
}
```

##### 关闭和刷新

因为内置缓冲区的原因，如果不关闭输出流，无法写出字符到文件中。但是关闭的流对象，是无法继续写出数据的。如果我们既想写出数据，又想继续使用流，就需要`flush` 方法了。

* `flush` ：刷新缓冲区（把内存缓冲区的数据刷新到文件中），流对象可以继续使用。
* `close `:先刷新缓冲区，然后通知系统释放资源。流对象不可以再被使用了。

##### 写数据的其他方法

1.**写出字符数组** ：`void write(char[] cbuf)`  和`write(char[] cbuf, int off, int len)` 

2.**写出字符串**：`write(String str)` 和 `write(String str, int off, int len)` ，每次可以写出字符串中的数据，更为方便

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileWriter fw=new FileWriter("aa\\a.txt");
        char[] cs={'a','b','c','d','e'};
        fw.write(cs);
        fw.write(cs,1,3);
        fw.write("你好");
        fw.write("你好程序员",2,3);
        fw.close();
    }
}

```

#####  续写和换行

操作类似于FileOutputStream

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileWriter fw=new FileWriter("aa\\a.txt",true);
        fw.write("\r\n你好");
        fw.close();
    }
}
```





### IO异常的处理

----------------------------------------------------------------------------------------

JDK7前处理

之前的入门练习，我们一直把异常抛出，而实际开发中并不能这样处理，建议使用`try...catch...finally` 代码块，处理异常部分，代码使用演示：

```java
public class t2xt {
    public static void main(String[] args) {
        FileWriter fw=null;
        try{
            fw=new FileWriter("aa\\a.txt",true);
            fw.write("\r\n你好");

        }catch (IOException e){
            System.out.println(e);
        }finally {
            if(fw!=null){
                try {
                    fw.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
}
```

JDk7新特性（扩展）

在try的后边可以增加一个（），在括号中可以定义流对象
那么这个流对象的作用域就在try中有效
try中的代码执行完毕，会自动把流对象释放，不用写finally

```java
public class t2xt {
    public static void main(String[] args) {
        try{
            FileInputStream fis=new FileInputStream("C:\\1.jpg");
            FileOutputStream fos=new FileOutputStream("D:\\1.jpg");
            byte[] bytes=new byte[1024];
            int len=0;
            while((len=fis.read(bytes))!=-1){
                fos.write(bytes,0,len);
            }
        }catch (IOException e){
            System.out.println(e);
        }
    }
}

```

JDk9新特性（扩展）
try的前边可以定义流对象
在try后边的（）中可以直接引入流对象的名称
在try代码执行完毕的时候，流对象也可以释放掉，不用写finally
格式：
A a=new A();
B b=new B();
try(a,b){
	可能会产出异样的代码
}catch(异常类变量 变量名){
	异常处理逻辑
}

```java
Properties 类表示了一个持久的属性集。Properties 可保存在流中或从流中加载。public class t2xt {
    public static void main(String[] args) throws FileNotFoundException {
        FileInputStream fis=new FileInputStream("C:\\1.jpg");
        FileOutputStream fos=new FileOutputStream("D:\\1.jpg");
        try(fis;fos){
            byte[] bytes=new byte[1024];
            int len=0;
            while((len=fis.read(bytes))!=-1){
                fos.write(bytes,0,len);
            }
        }catch (IOException e){
            System.out.println(e);
        }
    }
}
```



### 属性集

------------------------------------------------------

`java.util.Properties ` 继承于` Hashtable` 
`Properties` 类表示了一个持久的属性集。`Properties` 可保存在流中或从流中加载。
Properties集合是一个唯一和IO流相结合的集合
		可以使用Properties集合中的方法store，把集合中的临时数据，持久化写入到硬盘中存储
		可以使用Properties集合中的方法load，把硬盘中保存的文件（键值对），读取到集合中使用
属性列表中每个键及其对应值都是一个字符串。
		Properties集合是一个双列集合，key和value默认都是字符串

#### Properties类

##### 构造方法

- `public Properties()` :创建一个空的属性列表。

##### 基本的存储方法

- `public Object setProperty(String key, String value)` ： 保存一对属性。  
- `public String getProperty(String key) ` ：通过key获取值
- `public Set<String> stringPropertyNames() ` ：返回此属性列表中的键集，其中该键及其对应值是字符串。相当于map集合中的keySet方法

```java
public class t2xt {
    public static void main(String[] args)  {
        Properties prop=new Properties();//创建
        prop.setProperty("张三","123");//添加数据
        prop.setProperty("张四","153");
        prop.setProperty("张无","133");

        /*
            使用stringPropertyNames()把Properties集合中的键取出，存储到一个Set集合中
         */
        Set<String> set=prop.stringPropertyNames();
        for (String key : set) {
            // getProperty(String key) `
            String value=prop.getProperty(key);
            System.out.println(key+"=>"+value);
        }
    }
    /*
        使用Properties集合存储数据，遍历取出Properties集合中的数据
     */
}
```



##### store

void store(OutputStream out, String comments)
void store(Writer writer, String comments)
参数：
		OutputStream out：字节输出流，不能写中文
		Writer writer：字符输出流，可以写中文
		 String comments：注释，用来解释说明保存的文件是做什么用的；不能使用中文，会产生乱码默认是Unicode；一般使用“”空字符串

使用步骤：
1、创建Properties集合对象，添加数据
2、创建字节输出流/字符输出流对象，构造方法中绑定要输出的目的地
3、使用Properties集合中的方法store，把集合中的临时数据持久化写到硬盘中存储
4、释放资源

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        Properties prop=new Properties();//创建
        prop.setProperty("张三","123");//添加数据
        prop.setProperty("张四","153");
        prop.setProperty("张无","133");

        FileWriter fw=new FileWriter("aa\\a.txt");
        prop.store(fw,"save data");
        fw.close();
    }
}
```





##### load

把硬盘中保存的文件（键值对），读取到集合中使用

void load(InputStream inStream)
void load(Reader reader)
参数：
		InputStream inStream：字节输出流，不能读取中文
		Reader reader：字符输出流，可以读中文

使用步骤：
1、创建Properties集合对象，添加数据
2、使用Properties集合中的方法load读取保存键值对的文件
3、遍历Properties集合
注意：
		1、存储键值对的文件中，键与值默认的链接符号可以使用=，空格（其他符号）
		2、存储键值对的文件中，可以使用#进行注释，被注释的键值对不会再被读取
		3、存储键值对的文件中，键与值默认都是字符串，不用再加引号

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        Properties prop=new Properties();//创建

        prop.load(new FileReader("aa\\\\a.txt"));
        Set<String> set = prop.stringPropertyNames();
        for (String key : set) {
            String value = prop.getProperty(key);
            System.out.println(key+"="+value);
        }
    }
}

```



### 缓冲流

缓冲流,也叫高效流，是对4个基本的`FileXxx` 流的增强，所以也是4个流，按照数据类型分类：

* **字节缓冲流**：`BufferedInputStream`，`BufferedOutputStream` 
* **字符缓冲流**：`BufferedReader`，`BufferedWriter`

缓冲流的基本原理，是在创建流对象时，会创建一个内置的默认大小的缓冲区数组，通过缓冲区读写，减少系统IO次数，从而提高读写的效率。

#### 字节缓冲流

##### 构造方法

* `public BufferedInputStream(InputStream in)` ：创建一个 新的缓冲输入流。 
* `public BufferedOutputStream(OutputStream out)`： 创建一个新的缓冲输出流。



   java.io.BufferedOutputStream extends OutputStream

   ###### BufferedOutputStream

:字节缓冲输出流，java.io.BufferedOutputStream extends OutputStream

**继承自父类的共性成员方法**:

public void close() ：关闭此输出流并释放与此流相关联的任何系统资源。
public void flush() ：刷新此输出流并强制任何缓冲的输出字节被写出。
public void write(byte[] b)：将 b.length字节从指定的字节数组写入此输出流。
public void write(byte[] b, int off, int len) ：从指定的字节数组写入 len字节，从偏移量 off开始输出到此输出流。
public abstract void write(int b) ：将指定的字节输出流。

 **构造方法**:
 ` BufferedOutputStream(OutputStream out)  `创建一个新的缓冲输出流，以将数据写入指定的底层输出流。
` BufferedOutputStream(OutputStream out, int size) ` 创建一个新的缓冲输出流，以将具有指定缓冲区大小的数据写入指定的底层输出流。
参数:
       OutputStream out:字节输出流
           我们可以传递FileOutputStream,缓冲流会给FileOutputStream增加一个缓冲区,提高FileOutputStream的写入效率
       int size:指定缓冲流内部缓冲区的大小,不指定默认

**使用步骤(重点)**:
    1.创建FileOutputStream对象,构造方法中绑定要输出的目的地
    2.创建BufferedOutputStream对象,构造方法中传递FileOutputStream对象对象,提高FileOutputStream对象效率
    3.使用BufferedOutputStream对象中的方法write,把数据写入到内部缓冲区中
    4.使用BufferedOutputStream对象中的方法flush,把内部缓冲区中的数据,刷新到文件中
    5.释放资源(会先调用flush方法刷新数据,第4部可以省略)

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileOutputStream fos=new FileOutputStream("aa\\a.txt");
        BufferedOutputStream bos=new BufferedOutputStream(fos);
        bos.write("我把数据写入到内部缓冲区".getBytes());
        bos.flush();
        bos.close();
    }
}
```





    ###### BufferedInputStream

:字节缓冲输入流，java.io.BufferedInputStream extends InputStream

**继承自父类的成员方法**:
    int read()从输入流中读取数据的下一个字节。
    int read(byte[] b) 从输入流中读取一定数量的字节，并将其存储在缓冲区数组 b 中。
    void close() 关闭此输入流并释放与该流关联的所有系统资源。

**构造方法**:
    BufferedInputStream(InputStream in) 创建一个 BufferedInputStream 并保存其参数，即输入流 in，以便将来使用。
    BufferedInputStream(InputStream in, int size) 创建具有指定缓冲区大小的 BufferedInputStream 并保存其参数，即输入流 in，以便将来使用。
    参数:
        InputStream in:字节输入流
            我们可以传递FileInputStream,缓冲流会给FileInputStream增加一个缓冲区,提高FileInputStream的读取效率
        int size:指定缓冲流内部缓冲区的大小,不指定默认

**使用步骤(重点)**:
    1.创建FileInputStream对象,构造方法中绑定要读取的数据源
    2.创建BufferedInputStream对象,构造方法中传递FileInputStream对象,提高FileInputStream对象的读取效率
    3.使用BufferedInputStream对象中的方法read,读取文件
    4.释放资源

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        FileInputStream fis=new FileInputStream("aa\\a.txt");
        BufferedInputStream bis=new BufferedInputStream(fis);
        int len=0;
        while((len=bis.read())!=-1){
            System.out.println((char)len);
        }
        bis.close();
    }
}
```



#### 字符缓冲流

##### BufferedWriter

:字符缓冲输出流, java.io.BufferedWriter extends Writer

**继承自父类的共性成员方法**:

    - void write(int c) 写入单个字符。
        - void write(char[] cbuf)写入字符数组。
        - abstract  void write(char[] cbuf, int off, int len)写入字符数组的某一部分,off数组的开始索引,len写的字符个数。
        - void write(String str)写入字符串。
        - void write(String str, int off, int len) 写入字符串的某一部分,off字符串的开始索引,len写的字符个数。
        - void flush()刷新该流的缓冲。
        - void close() 关闭此流，但要先刷新它。

**构造方法**

​    BufferedWriter(Writer out) 创建一个使用默认大小输出缓冲区的缓冲字符输出流。
​    BufferedWriter(Writer out, int sz) 创建一个使用给定大小输出缓冲区的新缓冲字符输出流。
​    参数:
​        Writer out:字符输出流
​            我们可以传递FileWriter,缓冲流会给FileWriter增加一个缓冲区,提高FileWriter的写入效率
​        int sz:指定缓冲区的大小,不写默认大小

**特有的成员方法**

​    void newLine() 写入一个行分隔符。会根据不同的操作系统,获取不同的行分隔符
​    换行:换行符号
​    windows:\r\n
​    linux:/n
​    mac:/r
**使用步骤**:
​    1.创建字符缓冲输出流对象,构造方法中传递字符输出流
​    2.调用字符缓冲输出流中的方法write,把数据写入到内存缓冲区中
​    3.调用字符缓冲输出流中的方法flush,把内存缓冲区中的数据,刷新到文件中
​    4.释放资源

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        BufferedWriter bw=new BufferedWriter(new FileWriter("aa\\a.txt"));
        for(int i=0;i<10;i++){
            bw.write("你好");
            //bw.write("\r\n");
            bw.newLine();
        }
        bw.flush();
        bw.close();
    }
}
```

##### BufferedReader

:字符缓冲输入流，java.io.BufferedReader extends Reader

**继承自父类的共性成员方法:**
    int read() 读取单个字符并返回。
    int read(char[] cbuf)一次读取多个字符,将字符读入数组。
    void close() 关闭该流并释放与之关联的所有资源。

 **构造方法:**
    BufferedReader(Reader in)  创建一个使用默认大小输入缓冲区的缓冲字符输入流。
    BufferedReader(Reader in, int sz)     创建一个使用指定大小输入缓冲区的缓冲字符输入流。
    参数:
        Reader in:字符输入流
            我们可以传递FileReader,缓冲流会给FileReader增加一个缓冲区,提高FileReader的读取效率

 **特有的成员方法:**
    String readLine() 读取一个文本行。读取一行数据
行的终止符号:通过下列字符之一即可认为某行已终止：换行 ('\n')、回车 ('\r') 或回车后直接跟着换行(\r\n)。
    返回值:
        包含该行内容的字符串，不包含任何行终止符，如果已到达流末尾，则返回 null

**使用步骤**:
    1.创建字符缓冲输入流对象,构造方法中传递字符输入流
    2.使用字符缓冲输入流对象中的方法read/readLine读取文本
    3.释放资源

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        BufferedReader br=new BufferedReader(new FileReader("aa\\a.txt"));
        String line;
        while((line=br.readLine())!=null){
            System.out.println(line);
        }
    }
}
```

#### 练习：对文件文本进行排序

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        HashMap<String,String> map=new HashMap<>();
        BufferedReader br=new BufferedReader(new FileReader("aa\\a.txt"));
        BufferedWriter bw=new BufferedWriter(new FileWriter("aa\\b.txt"));
        String line;
        while((line=br.readLine())!=null){
            String[] arr=line.split("\\.");
            map.put(arr[0],arr[1]);
        }
        for(String key:map.keySet()){
            String value=map.get(key);
            line=key+"."+value;
            bw.write(line);
        }
        bw.close();
        br.close();
    }
}

```



### 转换流

--------------------------------------

解决由编码引起的乱码

#### OutputStreamWriter类

java.io.OutputStreamWriter extends Writer
OutputStreamWriter: 是字符流通向字节流的桥梁：可使用指定的 charset 将要写入流中的字符编码成字节。(编码:把能看懂的变成看不懂)

**继续自父类的共性成员方法:**
    -void write(int c) 写入单个字符。
    -void write(char[] cbuf)写入字符数组。
    -abstract  void write(char[] cbuf, int off, int len)写入字符数组的某一部分,off数组的开始索引,len写的字符个数。
    -void write(String str)写入字符串。
    -void write(String str, int off, int len) 写入字符串的某一部分,off字符串的开始索引,len写的字符个数。
    -void flush()刷新该流的缓冲。
    -void close() 关闭此流，但要先刷新它。

**构造方法:**
OutputStreamWriter(OutputStream out)创建使用默认字符编码OutputStreamWriter。 OutputStreamWriter(OutputStream out, String charsetName) 创建使用指定字符集的 OutputStreamWriter。
参数:
      OutputStream out:字节输出流,可以用来写转换之后的字节到文件中
      String charsetName:指定的编码表名称,不区分大小写,可以是utf-8/UTF-8,gbk/GBK,...不指定默认使用UTF-8

**使用步骤:**
        1.创建OutputStreamWriter对象,构造方法中传递字节输出流和指定的编码表名称
        2.使用OutputStreamWriter对象中的方法write,把字符转换为字节存储缓冲区中(编码)
        3.使用OutputStreamWriter对象中的方法flush,把内存缓冲区中的字节刷新到文件中(使用字节流写字节的过程)
        4.释放资源

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        OutputStreamWriter osw=new OutputStreamWriter(new FileOutputStream("aa\\a.txt"),"utf-8");
        osw.write("你好");
        osw.flush();
        osw.close();
    }
}
```



####  InputStreamReader

java.io.InputStreamReader extends Reader
InputStreamReader:是字节流通向字符流的桥梁：它使用指定的 charset 读取字节并将其解码为字符。(解码:把看不懂的变成能看懂的)

**继承自父类的共性成员方法:**
    int read() 读取单个字符并返回。
    int read(char[] cbuf)一次读取多个字符,将字符读入数组。
    void close() 关闭该流并释放与之关联的所有资源。

**构造方法:**
InputStreamReader(InputStream in) 创建一个使用默认字符集的 InputStreamReader。
InputStreamReader(InputStream in, String charsetName) 创建使用指定字符集的InputStreamReader。
参数:
    InputStream in:字节输入流,用来读取文件中保存的字节
    String charsetName:指定的编码表名称,不区分大小写,可以是utf-8/UTF-8,gbk/GBK,...不指定默认使用UTF-8

**使用步骤:**
    1.创建InputStreamReader对象,构造方法中传递字节输入流和指定的编码表名称
    2.使用InputStreamReader对象中的方法read读取文件
    3.释放资源
 注意事项:
    构造方法中指定的编码表名称要和文件的编码相同,否则会发生乱码

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        InputStreamReader isr=new InputStreamReader(new FileInputStream("aa\\a.txt"),"utf-8");
        int len=0;
        while ((len=isr.read())!=-1){
            System.out.println((char)len);
        }
        isr.close();
    }
}
```



#### 练习：转换文件编码

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        OutputStreamWriter osw=new OutputStreamWriter(new FileOutputStream("aa\\a.txt"),"utf-8");
        InputStreamReader isr=new InputStreamReader(new FileInputStream("aa\\b.txt"),"GBK");
        int len=0;
        while((len=isr.read())!=-1){
            osw.write((char)len);
        }
        osw.flush();
        osw.close();
        isr.close();
    }
}
```



### 序列

![](img\3_xuliehua.jpg)

#### ObjectOutputStream类

java.io.ObjectOutputStream extends OutputStream
ObjectOutputStream:对象的序列化流
作用:把对象以流的方式写入到文件中保存

**构造方法:**

ObjectOutputStream(OutputStream out) 创建写入指定 OutputStream 的 ObjectOutputStream。
参数:
    OutputStream out:字节输出流
**特有的成员方法:**
    void writeObject(Object obj) 将指定的对象写入 ObjectOutputStream。

**使用步骤:**
    1.创建ObjectOutputStream对象,构造方法中传递字节输出流
    2.使用ObjectOutputStream对象中的方法writeObject,把对象写入到文件中
    3.释放资源

```java
/*
    序列化和反序列化的时候,会抛出NotSerializableException没有序列化异常
    类通过实现 java.io.Serializable 接口以启用其序列化功能。未实现此接口的类将无法使其任何状态序列化或反序列化。
    Serializable接口也叫标记型接口
        要进行序列化和反序列化的类必须实现Serializable接口,就会给类添加一个标记
        当我们进行序列化和反序列化的时候,就会检测类上是否有这个标记
            有:就可以序列化和反序列化
            没有:就会抛出 NotSerializableException异常
    去市场买肉-->肉上有一个蓝色章(检测合格)-->放心购买-->买回来怎么吃随意

 */
public class Person implements Serializable {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

```java
public class t2xt {
    public static void main(String[] args) throws IOException {
        ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream("aa\\a.txt"));
        oos.writeObject(new Person("张三",13));
        oos.close();
    }
}
```



#### ObjectInputStream类

java.io.ObjectInputStream extends InputStream
ObjectInputStream:对象的反序列化流
作用:把文件中保存的对象,以流的方式读取出来使用

**构造方法:**
`ObjectInputStream(InputStream in)`创建从指定 InputStream 读取的 ObjectInputStream。
 参数:
        InputStream in:字节输入流
**特有的成员方法:**
    Object readObject() 从 ObjectInputStream 读取对象。

**使用步骤:**
    1.创建ObjectInputStream对象,构造方法中传递字节输入流
    2.使用ObjectInputStream对象中的方法readObject读取保存对象的文件
    3.释放资源
    4.使用读取出来的对象(打印)

 readObject方法声明抛出了ClassNotFoundException(class文件找不到异常)
 当不存在对象的class文件时抛出此异常
 反序列化的前提:
    1.类必须实现Serializable
    2.必须存在类对应的class文件

```java
//Person类同上
public class t2xt {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
        ObjectInputStream ois=new ObjectInputStream(new FileInputStream("aa\\a.txt"));
        Object o = ois.readObject();
        ois.close();
        System.out.println(o);
    }
}
```

#### transient关键字

 static关键字:静态关键字
        静态优先于非静态加载到内存中(静态优先于对象进入到内存中)
        被static修饰的成员变量不能被序列化的,序列化的都是对象
        private static int age;
        oos.writeObject(new Person("小美女",18));
        Object o = ois.readObject();
        Person{name='小美女', age=0}

transient关键字:瞬态关键字
    被transient修饰成员变量,不能被序列化
    private transient int age;
    oos.writeObject(new Person("小美女",18));
    Object o = ois.readObject();
    Person{name='小美女', age=0}

抛出`InvalidClassException`异常

解决方案：加入序列版本号

```java
public class Employee implements java.io.Serializable {
     // 加入序列版本号
     private static final long serialVersionUID = 1L;
     public String name;
     public String address;
     // 添加新的属性 ,重新编译, 可以反序列化,该属性赋为默认值.
     public int eid; 

     public void addressCheck() {
         System.out.println("Address  check : " + name + " -- " + address);
     }
}
```



#### 练习：序列化集合

```java
/*
    练习：序列化集合
        当我们想在文件中保存多个对象的时候
        可以把多个对象存储到一个集合中
        对集合进序列化和反序列化
    分析:
        1.定义一个存储Person对象的ArrayList集合
        2.往ArrayList集合中存储Person对象
        3.创建一个序列化流ObjectOutputStream对象
        4.使用ObjectOutputStream对象中的方法writeObject,对集合进行序列化
        5.创建一个反序列化ObjectInputStream对象
        6.使用ObjectInputStream对象中的方法readObject读取文件中保存的集合
        7.把Object类型的集合转换为ArrayList类型
        8.遍历ArrayList集合
        9.释放资源
 */
public class t2xt {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
        ArrayList<Person> list=new ArrayList<>();
        list.add(new Person("张三",13));
        list.add(new Person("张四",19));
        list.add(new Person("张五",17));
        list.add(new Person("张六",12));
        ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream("aa\\a.txt"));
        oos.writeObject(list);
        ObjectInputStream ois=new ObjectInputStream(new FileInputStream("aa\\a.txt"));
        Object o = ois.readObject();
        ArrayList<Person> list2=(ArrayList<Person>)o;
        for (Person p : list2) {
            System.out.println(p);
        }
        ois.close();
        oos.close();


    }
}
```





### 打印流

---------------------------------------

java.io.PrintStream:打印流
PrintStream 为其他输出流添加了功能，使它们能够方便地打印各种数据值表示形式。

**PrintStream特点:**
        1.只负责数据的输出,不负责数据的读取
        2.与其他输出流不同，PrintStream 永远不会抛出 IOException
        3.有特有的方法,print,println
            void print(任意类型的值)
            void println(任意类型的值并换行)

**构造方法:**
        PrintStream(File file):输出的目的地是一个文件
        PrintStream(OutputStream out):输出的目的地是一个字节输出流
        PrintStream(String fileName) :输出的目的地是一个文件路径

 PrintStream extends OutputStream
**继承自父类的成员方法:**
        -public void close() ：关闭此输出流并释放与此流相关联的任何系统资源。
        -public void flush() ：刷新此输出流并强制任何缓冲的输出字节被写出。
        -public void write(byte[] b)：将 b.length字节从指定的字节数组写入此输出流。
        -public void write(byte[] b, int off, int len) ：从指定的字节数组写入 len字节，从偏移量 off开始输出到此输出流。
        -public abstract void write(int b) ：将指定的字节输出流。
注意:
        如果使用继承自父类的write方法写数据,那么查看数据的时候会查询编码表 97->a
        如果使用自己特有的方法print/println方法写数据,写的数据原样输出 97->97

```java
public class t2xt {
    public static void main(String[] args) throws FileNotFoundException {
        PrintStream ps=new PrintStream("aa\\a.txt");
        ps.write(97);
        ps.println(97);
        ps.close();
    }
}
```



可以改变输出语句的目的地(打印流的流向)
    输出语句,默认在控制台输出
    使用System.setOut方法改变输出语句的目的地改为参数中传递的打印流的目的地
        static void setOut(PrintStream out)
          重新分配“标准”输出流。

```java
public class t2xt {
    public static void main(String[] args) throws FileNotFoundException {
        System.out.println("这里是控制台");

        PrintStream ps=new PrintStream("aa\\a.txt");
        System.setOut(ps);//把输出语句的目的地改变为打印流的目的地
        System.out.println("在打印目的地输出");
        ps.close();
    }
}
```



### 网络编程

--------------------------------------------------

**协议分类**

**UDP**：用户数据报协议(User Datagram Protocol)。UDP是无连接通信协议，即在数据传输时，数据的发送端和接收端不建立逻辑连接。不确认接收端是否存在，就会发出数据，同样接收端在收到数据时，也不会向发送端反馈是否收到数据。

特点:数据被限制在64kb以内，超出这个范围就不能发送了。（qq传文件）

**TCP**：先建立连接再通信

- 三次握手：TCP协议中，在发送数据的准备阶段，客户端与服务器之间的三次交互，以保证连接的可靠。
  - 第一次握手，客户端向服务器端发出连接请求，等待服务器确认。
  - 第二次握手，服务器端向客户端回送一个响应，通知客户端收到了连接请求。
  - 第三次握手，客户端再次向服务器端发送确认信息，确认连接。整个交互过程如下图所示。

![](img/4_tcp.jpg)

​    完成三次握手，连接建立后，客户端和服务器就可以开始进行数据传输了。由于这种面向连接的特性，TCP协议可以保证传输数据的安全，所以应用十分广泛，例如下载文件、浏览网页等。

### TCP通信程序

-------------------------------------------------------------------------

TCP通信能实现两台计算机之间的数据交互，通信的两端，要严格区分为客户端（Client）与服务端（Server）。

**两端通信时步骤：**

1. 服务端程序，需要事先启动，等待客户端的连接。
2. 客户端主动连接服务器端，连接成功才能通信。服务端不可以主动连接客户端。

**在Java中，提供了两个类用于实现TCP通信程序：**

1. 客户端：`java.net.Socket` 类表示。创建`Socket`对象，向服务端发出连接请求，服务端响应请求，两者建立连接开始通信。
2. 服务端：`java.net.ServerSocket` 类表示。创建`ServerSocket`对象，相当于开启一个服务，并等待客户端的连接。

#### Socket类 

TCP通信的客户端:向服务器发送连接请求,给服务器发送数据,读取服务器回写的数据
 表示客户端的类:
        java.net.Socket:此类实现客户端套接字（也可以就叫“套接字”）。套接字是两台机器间通信的端点。
        套接字:包含了IP地址和端口号的网络单位

##### 构造方法:
​    Socket(String host, int port) 创建一个流套接字并将其连接到指定主机上的指定端口号。
​    参数:
​        String host:服务器主机的名称/服务器的IP地址
​        int port:服务器的端口号

**成员方法:**
    OutputStream getOutputStream() 返回此套接字的输出流。
    InputStream getInputStream() 返回此套接字的输入流。
    void close() 关闭此套接字。

**实现步骤:**
    1.创建一个客户端对象Socket,构造方法绑定服务器的IP地址和端口号
    2.使用Socket对象中的方法getOutputStream()获取网络字节输出流OutputStream对象
    3.使用网络字节输出流OutputStream对象中的方法write,给服务器发送数据
    4.使用Socket对象中的方法getInputStream()获取网络字节输入流InputStream对象
    5.使用网络字节输入流InputStream对象中的方法read,读取服务器回写的数据
    6.释放资源(Socket)
 注意:
    1.客户端和服务器端进行交互,必须使用Socket中提供的网络流,不能使用自己创建的流对象
    2.当我们创建客户端对象Socket的时候,就会去请求服务器和服务器经过3次握手建立连接通路
        这时如果服务器没有启动,那么就会抛出异常ConnectException: Connection refused: connect
        如果服务器已经启动,那么就可以进行交互了

```java
public class TCPClient {
    public static void main(String[] args) throws IOException {
        //1.创建一个客户端对象Socket,构造方法绑定服务器的IP地址和端口号
        Socket socket = new Socket("127.0.0.1",8888);
        //2.使用Socket对象中的方法getOutputStream()获取网络字节输出流OutputStream对象
        OutputStream os = socket.getOutputStream();
        //3.使用网络字节输出流OutputStream对象中的方法write,给服务器发送数据
        os.write("你好服务器".getBytes());

        //4.使用Socket对象中的方法getInputStream()获取网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();

        //5.使用网络字节输入流InputStream对象中的方法read,读取服务器回写的数据
        byte[] bytes = new byte[1024];
        int len = is.read(bytes);
        System.out.println(new String(bytes,0,len));

        //6.释放资源(Socket)
        socket.close();

    }

}
```





#### ServerSocket

TCP通信的服务器端:接收客户端的请求,读取客户端发送的数据,给客户端回写数据
    表示服务器的类:
        java.net.ServerSocket:此类实现服务器套接字。

##### 构造方法:
​    ServerSocket(int port) 创建绑定到特定端口的服务器套接字。

服务器端必须明确一件事情,必须的知道是哪个客户端请求的服务器
所以可以使用accept方法获取到请求的客户端对象Socket

**成员方法:**
    Socket accept() 侦听并接受到此套接字的连接。

**服务器的实现步骤:**
    1.创建服务器ServerSocket对象和系统要指定的端口号
    2.使用ServerSocket对象中的方法accept,获取到请求的客户端对象Socket
    3.使用Socket对象中的方法getInputStream()获取网络字节输入流InputStream对象
    4.使用网络字节输入流InputStream对象中的方法read,读取客户端发送的数据
    5.使用Socket对象中的方法getOutputStream()获取网络字节输出流OutputStream对象
    6.使用网络字节输出流OutputStream对象中的方法write,给客户端回写数据
    7.释放资源(Socket,ServerSocket)

```java
public class TCPServer {
    public static void main(String[] args) throws IOException {
        //1.创建服务器ServerSocket对象和系统要指定的端口号
        ServerSocket server = new ServerSocket(8888);
        //2.使用ServerSocket对象中的方法accept,获取到请求的客户端对象Socket
        Socket socket = server.accept();
        //3.使用Socket对象中的方法getInputStream()获取网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();
        //4.使用网络字节输入流InputStream对象中的方法read,读取客户端发送的数据
        byte[] bytes = new byte[1024];
        int len = is.read(bytes);
        System.out.println(new String(bytes,0,len));
        //5.使用Socket对象中的方法getOutputStream()获取网络字节输出流OutputStream对象
        OutputStream os = socket.getOutputStream();
        //6.使用网络字节输出流OutputStream对象中的方法write,给客户端回写数据
        os.write("收到谢谢".getBytes());
        //7.释放资源(Socket,ServerSocket)
        socket.close();
        server.close();
    }
}
```



#### TCP文件上传案例

```java
/*
    文件上传案例的客户端:读取本地文件,上传到服务器,读取服务器回写的数据

    明确:
        数据源:c:\\1.jpg
        目的地:服务器

    实现步骤:
        1.创建一个本地字节输入流FileInputStream对象,构造方法中绑定要读取的数据源
        2.创建一个客户端Socket对象,构造方法中绑定服务器的IP地址和端口号
        3.使用Socket中的方法getOutputStream,获取网络字节输出流OutputStream对象
        4.使用本地字节输入流FileInputStream对象中的方法read,读取本地文件
        5.使用网络字节输出流OutputStream对象中的方法write,把读取到的文件上传到服务器
        6.使用Socket中的方法getInputStream,获取网络字节输入流InputStream对象
        7.使用网络字节输入流InputStream对象中的方法read读取服务回写的数据
        8.释放资源(FileInputStream,Socket)
 */
public class TCPClient {
    public static void main(String[] args) throws IOException {
        //1.创建一个本地字节输入流FileInputStream对象,构造方法中绑定要读取的数据源
        FileInputStream fis = new FileInputStream("c:\\1.jpg");
        //2.创建一个客户端Socket对象,构造方法中绑定服务器的IP地址和端口号
        Socket socket = new Socket("127.0.0.1",8888);
        //3.使用Socket中的方法getOutputStream,获取网络字节输出流OutputStream对象
        OutputStream os = socket.getOutputStream();
        //4.使用本地字节输入流FileInputStream对象中的方法read,读取本地文件
        int len = 0;
        byte[] bytes = new byte[1024];
        while((len = fis.read(bytes))!=-1){
            //5.使用网络字节输出流OutputStream对象中的方法write,把读取到的文件上传到服务器
            os.write(bytes,0,len);
        }

        /*
            解决:上传完文件,给服务器写一个结束标记
            void shutdownOutput() 禁用此套接字的输出流。
            对于 TCP 套接字，任何以前写入的数据都将被发送，并且后跟 TCP 的正常连接终止序列。
         */
        socket.shutdownOutput();

        //6.使用Socket中的方法getInputStream,获取网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();

        System.out.println("333333333333333333333");

        //7.使用网络字节输入流InputStream对象中的方法read读取服务回写的数据
        while((len = is.read(bytes))!=-1){
            System.out.println(new String(bytes,0,len));
        }

        System.out.println("444444444444444444  while死循环打印不到");

        //8.释放资源(FileInputStream,Socket)
        fis.close();
        socket.close();
    }
}

```



```java
/*
    文件上传案例服务器端:读取客户端上传的文件,保存到服务器的硬盘,给客户端回写"上传成功"

    明确:
        数据源:客户端上传的文件
        目的地:服务器的硬盘 d:\\upload\\1.jpg

    实现步骤:
        1.创建一个服务器ServerSocket对象,和系统要指定的端口号
        2.使用ServerSocket对象中的方法accept,获取到请求的客户端Socket对象
        3.使用Socket对象中的方法getInputStream,获取到网络字节输入流InputStream对象
        4.判断d:\\upload文件夹是否存在,不存在则创建
        5.创建一个本地字节输出流FileOutputStream对象,构造方法中绑定要输出的目的地
        6.使用网络字节输入流InputStream对象中的方法read,读取客户端上传的文件
        7.使用本地字节输出流FileOutputStream对象中的方法write,把读取到的文件保存到服务器的硬盘上
        8.使用Socket对象中的方法getOutputStream,获取到网络字节输出流OutputStream对象
        9.使用网络字节输出流OutputStream对象中的方法write,给客户端回写"上传成功"
        10.释放资源(FileOutputStream,Socket,ServerSocket)
 */
public class TCPServer {
    public static void main(String[] args) throws IOException {
        //1.创建一个服务器ServerSocket对象,和系统要指定的端口号
        ServerSocket server = new ServerSocket(8888);
        //2.使用ServerSocket对象中的方法accept,获取到请求的客户端Socket对象
        Socket socket = server.accept();
        //3.使用Socket对象中的方法getInputStream,获取到网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();
        //4.判断d:\\upload文件夹是否存在,不存在则创建
        File file =  new File("d:\\upload");
        if(!file.exists()){
            file.mkdirs();
        }


        //5.创建一个本地字节输出流FileOutputStream对象,构造方法中绑定要输出的目的地
        FileOutputStream fos = new FileOutputStream(file+"\\1.jpg");
        //6.使用网络字节输入流InputStream对象中的方法read,读取客户端上传的文件

        System.out.println("11111111111111111111");

        int len =0;
        byte[] bytes = new byte[1024];
        while((len = is.read(bytes))!=-1){
            //7.使用本地字节输出流FileOutputStream对象中的方法write,把读取到的文件保存到服务器的硬盘上
            fos.write(bytes,0,len);
        }

        System.out.println("22222222222222222222222  while死循环打印不到");

        //8.使用Socket对象中的方法getOutputStream,获取到网络字节输出流OutputStream对象
        //9.使用网络字节输出流OutputStream对象中的方法write,给客户端回写"上传成功"
        socket.getOutputStream().write("上传成功".getBytes());
        //10.释放资源(FileOutputStream,Socket,ServerSocket)
        fos.close();
        socket.close();
        server.close();
    }
}
```



优化（多线程）

```java
public class TCPServer {
    public static void main(String[] args) throws IOException {
        //1.创建一个服务器ServerSocket对象,和系统要指定的端口号
        ServerSocket server = new ServerSocket(8888);
        //2.使用ServerSocket对象中的方法accept,获取到请求的客户端Socket对象

        /*
            让服务器一直处于监听状态(死循环accept方法)
            有一个客户端上传文件,就保存一个文件
         */
        while(true){
            Socket socket = server.accept();

            /*
                使用多线程技术,提高程序的效率
                有一个客户端上传文件,就开启一个线程,完成文件的上传
             */
            new Thread(new Runnable() {
                //完成文件的上传
                @Override
                public void run() {
                   try {
                       //3.使用Socket对象中的方法getInputStream,获取到网络字节输入流InputStream对象
                       InputStream is = socket.getInputStream();
                       //4.判断d:\\upload文件夹是否存在,不存在则创建
                       File file =  new File("d:\\upload");
                       if(!file.exists()){
                           file.mkdirs();
                       }

                    /*
                        自定义一个文件的命名规则:防止同名的文件被覆盖
                        规则:域名+毫秒值+随机数
                     */
                       String fileName = "itcast"+System.currentTimeMillis()+new Random().nextInt(999999)+".jpg";

                       //5.创建一个本地字节输出流FileOutputStream对象,构造方法中绑定要输出的目的地
                       //FileOutputStream fos = new FileOutputStream(file+"\\1.jpg");
                       FileOutputStream fos = new FileOutputStream(file+"\\"+fileName);
                       //6.使用网络字节输入流InputStream对象中的方法read,读取客户端上传的文件


                       int len =0;
                       byte[] bytes = new byte[1024];
                       while((len = is.read(bytes))!=-1){
                           //7.使用本地字节输出流FileOutputStream对象中的方法write,把读取到的文件保存到服务器的硬盘上
                           fos.write(bytes,0,len);
                       }


                       //8.使用Socket对象中的方法getOutputStream,获取到网络字节输出流OutputStream对象
                       //9.使用网络字节输出流OutputStream对象中的方法write,给客户端回写"上传成功"
                       socket.getOutputStream().write("上传成功".getBytes());
                       //10.释放资源(FileOutputStream,Socket,ServerSocket)
                       fos.close();
                       socket.close();
                   }catch (IOException e){
                       System.out.println(e);
                   }
                }
            }).start();


        }

        //服务器就不用关闭
        //server.close();
    }
}
```

```java
public class TCPClient {
    public static void main(String[] args) throws IOException {
        //1.创建一个本地字节输入流FileInputStream对象,构造方法中绑定要读取的数据源
        FileInputStream fis = new FileInputStream("c:\\1.jpg");
        //2.创建一个客户端Socket对象,构造方法中绑定服务器的IP地址和端口号
        Socket socket = new Socket("127.0.0.1",8888);
        //3.使用Socket中的方法getOutputStream,获取网络字节输出流OutputStream对象
        OutputStream os = socket.getOutputStream();
        //4.使用本地字节输入流FileInputStream对象中的方法read,读取本地文件
        int len = 0;
        byte[] bytes = new byte[1024];
        while((len = fis.read(bytes))!=-1){
            //5.使用网络字节输出流OutputStream对象中的方法write,把读取到的文件上传到服务器
            os.write(bytes,0,len);
        }

        /*
            解决:上传完文件,给服务器写一个结束标记
            void shutdownOutput() 禁用此套接字的输出流。
            对于 TCP 套接字，任何以前写入的数据都将被发送，并且后跟 TCP 的正常连接终止序列。
         */
        socket.shutdownOutput();

        //6.使用Socket中的方法getInputStream,获取网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();



        //7.使用网络字节输入流InputStream对象中的方法read读取服务回写的数据
        while((len = is.read(bytes))!=-1){
            System.out.println(new String(bytes,0,len));
        }


        //8.释放资源(FileInputStream,Socket)
        fis.close();
        socket.close();
    }
}
```

#### 模拟B\S服务器(扩展知识点)

```java
public class TCPServer {
    public static void main(String[] args) throws IOException {
        //创建一个服务器ServerSocket,和系统要指定的端口号
        ServerSocket server = new ServerSocket(8080);
        //使用accept方法获取到请求的客户端对象(浏览器)
        Socket socket = server.accept();
        //使用Socket对象中的方法getInputStream,获取到网络字节输入流InputStream对象
        InputStream is = socket.getInputStream();


        //把is网络字节输入流对象,转换为字符缓冲输入流
        BufferedReader br = new BufferedReader(new InputStreamReader(is));
        //把客户端请求信息的第一行读取出来 GET /11_Net/web/index.html HTTP/1.1
        String line = br.readLine();
        //把读取的信息进行切割,只要中间部分 /11_Net/web/index.html
        String[] arr = line.split(" ");
        //把路径前边的/去掉,进行截取 11_Net/web/index.html
        String htmlpath = arr[1].substring(1);

        //创建一个本地字节输入流,构造方法中绑定要读取的html路径
        FileInputStream fis = new FileInputStream(htmlpath);
        //使用Socket中的方法getOutputStream获取网络字节输出流OutputStream对象
        OutputStream os = socket.getOutputStream();

        // 写入HTTP协议响应头,固定写法
        os.write("HTTP/1.1 200 OK\r\n".getBytes());
        os.write("Content-Type:text/html\r\n".getBytes());
        // 必须要写入空行,否则浏览器不解析
        os.write("\r\n".getBytes());

        //一读一写复制文件,把服务读取的html文件回写到客户端
        int len = 0;
        byte[] bytes = new byte[1024];
        while((len = fis.read(bytes))!=-1){
            os.write(bytes,0,len);
        }

        //释放资源
        fis.close();
        socket.close();
        server.close();
    }
}

```



浏览器工作原理是遇到图片会开启一个线程进行单独的访问,因此在服务器端加入线程技术。

```java
/*
    创建BS版本TCP服务器
 */
public class TCPServerThread {
    public static void main(String[] args) throws IOException {
        //创建一个服务器ServerSocket,和系统要指定的端口号
        ServerSocket server = new ServerSocket(8080);

        /*
            浏览器解析服务器回写的html页面,页面中如果有图片,那么浏览器就会单独的开启一个线程,读取服务器的图片
            我们就的让服务器一直处于监听状态,客户端请求一次,服务器就回写一次
         */
        while(true){
            //使用accept方法获取到请求的客户端对象(浏览器)
            Socket socket = server.accept();

            new Thread(new Runnable() {
                @Override
                public void run() {
                    try {
                        //使用Socket对象中的方法getInputStream,获取到网络字节输入流InputStream对象
                        InputStream is = socket.getInputStream();
                        //使用网络字节输入流InputStream对象中的方法read读取客户端的请求信息
                        /*byte[] bytes = new byte[1024];
                        int len = 0;
                        while((len = is.read(bytes))!=-1){
                            System.out.println(new String(bytes,0,len));
                        }*/

                        //把is网络字节输入流对象,转换为字符缓冲输入流
                        BufferedReader br = new BufferedReader(new InputStreamReader(is));
                        //把客户端请求信息的第一行读取出来 GET /11_Net/web/index.html HTTP/1.1
                        String line = br.readLine();
                        System.out.println(line);
                        //把读取的信息进行切割,只要中间部分 /11_Net/web/index.html
                        String[] arr = line.split(" ");
                        //把路径前边的/去掉,进行截取 11_Net/web/index.html
                        String htmlpath = arr[1].substring(1);

                        //创建一个本地字节输入流,构造方法中绑定要读取的html路径
                        FileInputStream fis = new FileInputStream(htmlpath);
                        //使用Socket中的方法getOutputStream获取网络字节输出流OutputStream对象
                        OutputStream os = socket.getOutputStream();

                        // 写入HTTP协议响应头,固定写法
                        os.write("HTTP/1.1 200 OK\r\n".getBytes());
                        os.write("Content-Type:text/html\r\n".getBytes());
                        // 必须要写入空行,否则浏览器不解析
                        os.write("\r\n".getBytes());

                        //一读一写复制文件,把服务读取的html文件回写到客户端
                        int len = 0;
                        byte[] bytes = new byte[1024];
                        while((len = fis.read(bytes))!=-1){
                            os.write(bytes,0,len);
                        }

                        //释放资源
                        fis.close();
                        socket.close();
                    }catch (IOException e){
                        e.printStackTrace();
                    }
                }
            }).start();
        }
        //server.close();
    }
}
```



### 函数式接口

----------------------------------

函数式接口:有且只有一个抽象方法的接口,称之为函数式接口
    当然接口中可以包含其他的方法(默认,静态,私有)

函数式接口，即适用于函数式编程场景的接口。而Java中的函数式编程体现就是Lambda，所以函数式接口就是可以适用于Lambda使用的接口。只有确保接口中有且仅有一个抽象方法，Java中的Lambda才能顺利地进行推导。 

只要确保接口中有且仅有一个抽象方法即可： 

```java
修饰符 interface 接口名称 { 
	public abstract 返回值类型 方法名称(可选参数信息); //由于接口当中抽象方法的 public abstract 是可以省略的，所以定义一个函数式接口很简单：
	// 其他非抽象方法内容 
}
```

@FunctionalInterface注解
作用:可以检测接口是否是一个函数式接口
    是:编译成功
    否:编译失败(接口中没有抽象方法抽象方法的个数多余1个)

```java
@FunctionalInterface 
public interface MyFunctionalInterface { 
    void myMethod(); 
}
```

#### 函数式接口的使用

```java
@FunctionalInterface
public interface MyFunctionalInterface {
    void method();
}

```

```java
public class Demo {
    public static void main(String[] args) {
        show(new MyFunctionalInterface() {
            @Override
            public void method() {
                System.out.println("使用匿名内部类重写接口中的抽象方法");
            }
        });
        show(()->{
            System.out.println("使用lambda重写接口中的抽象方法");
        });
        //简化lambda
        show(()-> System.out.println("使用lambda重写接口中的抽象方法"));
    }

    public static void show(MyFunctionalInterface myInter){
        myInter.method();
    }
}
```



#### 函数式接口作为方法的参数

```java
/*
    例如java.lang.Runnable接口就是一个函数式接口，
    假设有一个startThread方法使用该接口作为参数，那么就可以使用Lambda进行传参。
    这种情况其实和Thread类的构造方法参数为Runnable没有本质区别。
 */
public class Demo01Runnable {
    //定义一个方法startThread,方法的参数使用函数式接口Runnable
    public static void startThread(Runnable run){
        //开启多线程
        new Thread(run).start();
    }

    public static void main(String[] args) {
        //调用startThread方法,方法的参数是一个接口,那么我们可以传递这个接口的匿名内部类
        startThread(new Runnable() {
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName()+"-->"+"线程启动了");
            }
        });

        //调用startThread方法,方法的参数是一个函数式接口,所以可以传递Lambda表达式
        startThread(()->{
            System.out.println(Thread.currentThread().getName()+"-->"+"线程启动了");
        });

        //优化Lambda表达式
        startThread(()->System.out.println(Thread.currentThread().getName()+"-->"+"线程启动了"));
    }
}
```





#### 函数式接口作为方法的返回值

```java
public class Demo {
    public static void main(String[] args) {
        String[] arr={"aa","aaaa","aaaaaa","a"};
        System.out.println(Arrays.toString(arr));
        Arrays.sort(arr,getComparator());
        System.out.println(Arrays.toString(arr));
    }
    public static Comparator<String> getComparator(){
        /*return new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                return o2.length()-o1.length();
            }
        };*/
        /*return (String o1, String o2)->{
            return o2.length()-o1.length();
        };*/
        return (o1,o2)-> o2.length()-o1.length();
    }
}
```



### 常用函数是接口

--------------------------------

#### Supplier接口

`java.util.function.Supplier`接口仅包含一个无参的方法： T get() 。用来获取一个泛型参数指定类型的对象数据。

Supplier<T>接口被称之为生产型接口,指定接口的泛型是什么类型,那么接口中的get方法就会生产什么类型的数据

```java
public class Demo {
    public static void main(String[] args) {
        String s=getString(()->"aa");
        System.out.println(s);
    }
    public  static String getString(Supplier<String> sup){
        return sup.get();
    }
}

```

**练习：求数组元素最大值**

```java
public class Demo {
    public static void main(String[] args) {
        int[] arr={100,2,4,67,-34};
        int maxValue=getMax(()->{
            int max=arr[0];
            for (int i : arr) {
                if(max<i){
                    max=i;
                }
            }
            return max;
        });
        System.out.println(maxValue);
    }
    public static int getMax(Supplier<Integer> sup){
        return sup.get();
    }
}
```



#### Consumer接口

`java.util.function.Consumer<T> `接口则正好与Supplier接口相反，它不是生产一个数据，而是**消费**一个数据， 其数据类型由泛型决定。 

抽象方法：accept

Consumer 接口中包含抽象方法 void accept(T t) ，意为消费一个指定泛型的数据。

```java
public class Demo {
    public static void main(String[] args) {
        method("aa",(name)->{
            System.out.println(name);
        });
    }
    public static void method(String name, Consumer<String> con){
        con.accept(name);
    }
}

```







### Stream流 

--------------------------------------

```java
public class Demo {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("张无忌");
        list.add("周芷若");
        list.add("赵敏");
        list.add("张强");
        list.add("张三丰");
        list.stream()
                .filter(s->s.startsWith("张"))
                .filter(s->s.length()==3)
                .forEach(name-> System.out.println(name));
    }
}
```



#### **获取流** 

```java
/*
    java.util.stream.Stream<T>是Java 8新加入的最常用的流接口。（这并不是一个函数式接口。）
    获取一个流非常简单，有以下几种常用的方式：
        - 所有的Collection集合都可以通过stream默认方法获取流；
            default Stream<E> stream​()
        - Stream接口的静态方法of可以获取数组对应的流。
            static <T> Stream<T> of​(T... values)
            参数是一个可变参数,那么我们就可以传递一个数组
 */
public class Demo01GetStream {
    public static void main(String[] args) {
        //把集合转换为Stream流
        List<String> list = new ArrayList<>();
        Stream<String> stream1 = list.stream();

        Set<String> set = new HashSet<>();
        Stream<String> stream2 = set.stream();

        Map<String,String> map = new HashMap<>();
        //获取键,存储到一个Set集合中
        Set<String> keySet = map.keySet();
        Stream<String> stream3 = keySet.stream();

        //获取值,存储到一个Collection集合中
        Collection<String> values = map.values();
        Stream<String> stream4 = values.stream();

        //获取键值对(键与值的映射关系 entrySet)
        Set<Map.Entry<String, String>> entries = map.entrySet();
        Stream<Map.Entry<String, String>> stream5 = entries.stream();

        //把数组转换为Stream流
        Stream<Integer> stream6 = Stream.of(1, 2, 3, 4, 5);
        //可变参数可以传递数组
        Integer[] arr = {1,2,3,4,5};
        Stream<Integer> stream7 = Stream.of(arr);
        String[] arr2 = {"a","bb","ccc"};
        Stream<String> stream8 = Stream.of(arr2);
    }
}
```





#### 常用方法

- **延迟方法**：返回值类型仍然是 Stream 接口自身类型的方法，因此支持链式调用。（除了终结方法外，其余方 法均为延迟方法。） 

- **终结方法**：返回值类型不再是 Stream 接口自身类型的方法，因此不再支持类似 StringBuilder 那样的链式调 用。本小节中，终结方法包括 count 和 forEach 方法。 

##### 逐一处理：forEach

虽然方法名字叫 forEach ，但是与for循环中的“for-each”昵称不同。 

该方法接收一个 Consumer 接口函数，会将每一个流元素交给该函数进行处理。 

```java
/*
    Stream流中的常用方法_forEach
    void forEach(Consumer<? super T> action);
    该方法接收一个Consumer接口函数，会将每一个流元素交给该函数进行处理。
    Consumer接口是一个消费型的函数式接口,可以传递Lambda表达式,消费数据

    简单记:
        forEach方法,用来遍历流中的数据
        是一个终结方法,遍历之后就不能继续调用Stream流中的其他方法
 */
public class Demo02Stream_forEach {
    public static void main(String[] args) {
        //获取一个Stream流
        Stream<String> stream = Stream.of("张三", "李四", "王五", "赵六", "田七");
        //使用Stream流中的方法forEach对Stream流中的数据进行遍历
        /*stream.forEach((String name)->{
            System.out.println(name);
        });*/

        stream.forEach(name->System.out.println(name));
    }
}

```



##### 过滤：fifilter

可以通过 filter 方法将一个流转换成另一个子集流。

```java
/*
    Stream流中的常用方法_filter:用于对Stream流中的数据进行过滤
    Stream<T> filter(Predicate<? super T> predicate);
    filter方法的参数Predicate是一个函数式接口,所以可以传递Lambda表达式,对数据进行过滤
    Predicate中的抽象方法:
        boolean test(T t);
 */
public class Demo03Stream_filter {
    public static void main(String[] args) {
        //创建一个Stream流
        Stream<String> stream = Stream.of("张三丰", "张翠山", "赵敏", "周芷若", "张无忌");
        //对Stream流中的元素进行过滤,只要姓张的人
        Stream<String> stream2 = stream.filter((String name)->{return name.startsWith("张");});
        //遍历stream2流
        stream2.forEach(name-> System.out.println(name));

        /*
            Stream流属于管道流,只能被消费(使用)一次
            第一个Stream流调用完毕方法,数据就会流转到下一个Stream上
            而这时第一个Stream流已经使用完毕,就会关闭了
            所以第一个Stream流就不能再调用方法了
            IllegalStateException: stream has already been operated upon or closed
         */
        //遍历stream流
        stream.forEach(name-> System.out.println(name));//抛异常
    }
}
```



##### 映射：map

把一种数据类型的数据转换为另一种

```java

/*
    Stream流中的常用方法_map:用于类型转换
    如果需要将流中的元素映射到另一个流中，可以使用map方法.
    <R> Stream<R> map(Function<? super T, ? extends R> mapper);
    该接口需要一个Function函数式接口参数，可以将当前流中的T类型数据转换为另一种R类型的流。
    Function中的抽象方法:
        R apply(T t);
 */
public class Demo04Stream_map {
    public static void main(String[] args) {
        //获取一个String类型的Stream流
        Stream<String> stream = Stream.of("1", "2", "3", "4");
        //使用map方法,把字符串类型的整数,转换(映射)为Integer类型的整数
        Stream<Integer> stream2 = stream.map((String s)->{
            return Integer.parseInt(s);
        });
        //遍历Stream2流
        stream2.forEach(i-> System.out.println(i));
        //Stream.concat(oneStream,twoStream).map(name->new Person(name)).forEach(p-> System.out.println(p));
    }
}
```



##### 统计个数：count

正如旧集合 Collection 当中的 size 方法一样，流提供 count 方法来数一数其中的元素个数
返回值类型：long

```java
/*
    Stream流中的常用方法_count:用于统计Stream流中元素的个数
    long count();
    count方法是一个终结方法,返回值是一个long类型的整数
    所以不能再继续调用Stream流中的其他方法了
 */
public class Demo05Stream_count {
    public static void main(String[] args) {
        //获取一个Stream流
        ArrayList<Integer> list = new ArrayList<>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        list.add(6);
        list.add(7);
        Stream<Integer> stream = list.stream();
        long count = stream.count();
        System.out.println(count);//7
    }
}
```



##### 取用前几个：limit 

```java
/*
    Stream流中的常用方法_limit:用于截取流中的元素
    limit方法可以对流进行截取，只取用前n个。方法签名：
    Stream<T> limit(long maxSize);
        参数是一个long型，如果集合当前长度大于参数则进行截取；否则不进行操作
    limit方法是一个延迟方法,只是对流中的元素进行截取,返回的是一个新的流,所以可以继续调用Stream流中的其他方法
 */
public class Demo06Stream_limit {
    public static void main(String[] args) {
        //获取一个Stream流
        String[] arr = {"美羊羊","喜洋洋","懒洋洋","灰太狼","红太狼"};
        Stream<String> stream = Stream.of(arr);
        //使用limit对Stream流中的元素进行截取,只要前3个元素
        Stream<String> stream2 = stream.limit(3);
        //遍历stream2流
        stream2.forEach(name-> System.out.println(name));
    }
}

```



##### 跳过前几个：skip 

```java
/*
    Stream流中的常用方法_skip:用于跳过元素
    如果希望跳过前几个元素，可以使用skip方法获取一个截取之后的新流：
    Stream<T> skip(long n);
        如果流的当前长度大于n，则跳过前n个；否则将会得到一个长度为0的空流。
 */
public class Demo07Stream_skip {
    public static void main(String[] args) {
        //获取一个Stream流
        String[] arr = {"美羊羊","喜洋洋","懒洋洋","灰太狼","红太狼"};
        Stream<String> stream = Stream.of(arr);
        //使用skip方法跳过前3个元素
        Stream<String> stream2 = stream.skip(3);
        //遍历stream2流
        stream2.forEach(name-> System.out.println(name));
    }
}
```



##### 组合：concat

```java
/*
    Stream流中的常用方法_concat:用于把流组合到一起
    如果有两个流，希望合并成为一个流，那么可以使用Stream接口的静态方法concat
    static <T> Stream<T> concat(Stream<? extends T> a, Stream<? extends T> b)
 */
public class Demo08Stream_concat {
    public static void main(String[] args) {
        //创建一个Stream流
        Stream<String> stream1 = Stream.of("张三丰", "张翠山", "赵敏", "周芷若", "张无忌");
        //获取一个Stream流
        String[] arr = {"美羊羊","喜洋洋","懒洋洋","灰太狼","红太狼"};
        Stream<String> stream2 = Stream.of(arr);
        //把以上两个流组合为一个流
        Stream<String> concat = Stream.concat(stream1, stream2);
        //遍历concat流
        concat.forEach(name-> System.out.println(name));
    }
}
```



### 方法引用

--------------------------------

```java
public interface Printable {
    void print(String s);
}

public class Demo {
    public static void main(String[] args) {
        printString((s)-> System.out.println(s));
        printString(System.out::println);//方法引用
    }
    public static void printString(Printable p){
        p.print("Hello");
    }
}
```



#### 通过对象名引用成员方法

```java
public interface Printable {
    void print(String s);
}
```

```java
public class MethodRerObject {
    public void printUpperCaseString(String str){
        System.out.println(str.toUpperCase());
    }
}
```

```java
public class Demo {
    public static void main(String[] args) {
        printString((s)-> {
            MethodRerObject obj=new MethodRerObject();
            obj.printUpperCaseString(s);
        });
        MethodRerObject obj=new MethodRerObject();
        printString(obj::printUpperCaseString);//方法引用
    }
    public static void printString(Printable p){
        p.print("Hello");
    }
}

```



#### 通过类名引用静态成员

```java
@FunctionalInterface
public interface Calcable {
    int calsAbs(int number);
}

```

```java
public class Demo {
    public static void main(String[] args) {
        int number=method(-3,n->{return Math.abs(n);});
        int number2=method(-10,Math::abs);
    }
    public static int method(int number,Calcable c){
        return c.calsAbs(number);
    }
}
```



#### 通过super引用父类的成员方法

```java
@FunctionalInterface
public interface Greetable {
    //定义一个见面的方法
    void greet();
}
```

```java
/*
    定义父类
 */
public class Human {
    //定义一个sayHello的方法
    public void sayHello(){
        System.out.println("Hello 我是Human!");
    }
}
```

```java
/*
    定义子类
 */
public class Man extends Human{
    //子类重写父类sayHello的方法
    @Override
    public void sayHello() {
        System.out.println("Hello 我是Man!");
    }

    //定义一个方法参数传递Greetable接口
    public void method(Greetable g){
        g.greet();
    }

    public void show(){
        //调用method方法,方法的参数Greetable是一个函数式接口,所以可以传递Lambda
        /*method(()->{
            //创建父类Human对象
            Human h = new Human();
            //调用父类的sayHello方法
            h.sayHello();
        });*/

        //因为有子父类关系,所以存在的一个关键字super,代表父类,所以我们可以直接使用super调用父类的成员方法
       /* method(()->{
            super.sayHello();
        });*/

      /*
           使用super引用类的成员方法
           super是已经存在的
           父类的成员方法sayHello也是已经存在的
           所以我们可以直接使用super引用父类的成员方法
       */
      method(super::sayHello);
    }

    public static void main(String[] args) {
        new Man().show();
    }
}

```



#### 通过this引用成员方法

```java
@FunctionalInterface
public interface Richable {
    void buy();
}
```

```java

public class Husband {
    public void buyHouse(){
        System.out.println("买");
    }
    public void marry(Richable r){
        r.buy();
    }
    public void soHappy(){
        marry(()->{
            this.buyHouse();
        });
        marry(this::buyHouse);
    }

    public static void main(String[] args) {
        new Husband().soHappy();
    }
}
```



#### 类的构造器的引用

```java
public interface PersonBuilder {
    Person buliderPerson(String name);
}
```

```java
public class Person {
    private String name;
    public Person() {
    }
    public Person(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
}

```

```java

public class Demo {
    public static void main(String[] args) {
        printName("sds",(name)->{
            return new Person(name);
        });
        printName("sds",Person::new);
    }
    public static void printName(String name,PersonBuilder pb){
        Person person=pb.buliderPerson(name);
        System.out.println(person.getName());
    }
}
```



#### 数组的构造器的引用

```java
@FunctionalInterface
public interface ArrayBuilder {
    int[] builderArray(int length);
}
```



```java
public class Demo {
    public static void main(String[] args) {
        int arr[]=createArray(10,len->{
            return new int[len];
        });
        int arr1[]=createArray(10,int[]::new);
    }
    public static int[] createArray(int length,ArrayBuilder ab){
        return ab.builderArray(length);
    }
}

```



### Junit单元测试

-----------------------------------------

Junit使用：白盒测试
 * 步骤：
     1. 定义一个测试类(测试用例)
         *建议：
         	*测试类名：被测试的类名Test		CalculatorTest
         	*包名：xxx.xxx.xx.test		cn.itcast.test

     2. 定义测试方法：可以独立运行
         *建议：
         	*方法名：test测试的方法名		testAdd()  
         	*返回值：void
         	*参数列表：空参

     3. 给方法加@Test
     4. 导入junit依赖环境

*判定结果：
	*红色：失败
	*绿色：成功
	*一般我们会使用断言操作来处理结果
		*Assert.assertEquals(期望的结果,运算的结果);

*补充：
	*@Before:
		*修饰的方法会在测试方法之前被自动执行
	*@After:
		*修饰的方法会在测试方法执行之后自动被执行

```java
import cn.itcast.junit.Calculator;
public class CalculatorTest 
     /*
     	初始化方法：
        用于资源申请，所有测试方法在执行之前都会先执行该方法
     */
    @Before
    public void init(){
        System.out.println("init...");
    }

    /*
       释放资源方法：
       在所有测试方法执行完后，都会自动执行该方法
     */
    @After
    public void close(){
        System.out.println("close...");
    }


     /*
       测试add方法
     */
    @Test
    public void testAdd(){
       // System.out.println("我被执行了");
        //1.创建计算器对象
        System.out.println("testAdd...");
        Calculator c  = new Calculator();
        //2.调用add方法
        int result = c.add(1, 2);
        //System.out.println(result);

        //3.断言  我断言这个结果是3
        Assert.assertEquals(3,result);

    }

    @Test
    public void testSub(){
        //1.创建计算器对象
        Calculator c  = new Calculator();
        int result = c.sub(1, 2);
        System.out.println("testSub....");
        Assert.assertEquals(-1,result);
    }
}
```



### 反射

--------------------------

框架：半成品软件。可以在框架的基础上进行软件开发，简化编码
反射：将类的各个组成部分封装为其他对象，这就是反射机制。反射是框架设计的灵魂

 好处：
		1. 可以在程序运行过程中，操作这些对象。
		2. 可以解耦，提高程序的可扩展性。

#### 获取Class对象：

​	1.Class.forName("全类名")：将字节码文件加载进内存，返回Class对象
​		*多用于配置文件，将类名定义在配置文件中。读取文件，加载
​	2.类名.class：通过类名的属性class获取
​		*多用于参数的传递
​	3.对象.getClass()：getClass()方法在Object类中定义着。
​		*多用于对象的获取字节码的方式

*结论：
	同一个字节码文件(*.class)在一次程序运行过程中，只会被加载一次，不论通过哪一种方式获取的Class对象都是同一个。

```java
public class Demo {
    public static void main(String[] args) throws ClassNotFoundException {
        //1.Class.forName("全类名")
        Class<?> cls1 = Class.forName("yy.Person");
        System.out.println(cls1);
        //2.类名.class
        Class cls2 = Person.class;
        System.out.println(cls2);
        //3.对象.getClass()
        Person p=new Person();
        Class cls3 = p.getClass();
        System.out.println(cls3);

        System.out.println(cls1==cls2);//true
        System.out.println(cls1==cls3);//true
    }
}
```



#### Class对象功能：

- 获取功能

  **1.获取成员变量们**
	  *Field[] getFields() ：获取所有public修饰的成员变量
	  *Field getField(String name)   获取指定名称的 public修饰的成员变量

​	  *Field[] getDeclaredFields()  获取所有的成员变量，不考虑修饰符
​	  *Field getDeclaredField(String name)获取指定名称的成员变量，不考虑修饰符  

​		  ** Field：成员变量**
​				**获取后可进行的操作：**
​						1、设置值：void set(Object obj, Object value)  
​						2、获取值：get(Object obj) 
​						3、忽略访问权限修饰符的安全检查：setAccessible(true):暴力反射

```java
public class Demo {
    public static void main(String[] args) throws Exception {
        Class personClass = Person.class;
        Field[] fields = personClass.getFields();
        for (Field field : fields) {
            System.out.println(field);
        }
        System.out.println("------------------------");
        Field a = personClass.getField("a");
        //获取成员变量a的值
        Person p=new Person();
        Object value = a.get(p);
        System.out.println(value);
        //设置成员变量a的值
        a.set(p,"张三");
        System.out.println(a.get(p));
        System.out.println("=============================");
        Field[] declaredFields = personClass.getDeclaredFields();
        for (Field declaredField : declaredFields) {
            System.out.println(declaredField);
        }
        Field d = personClass.getDeclaredField("d");
        //私有的需要忽略访问权限修饰符的安全检查
        d.setAccessible(true);//暴力反射
        Object value2 = d.get(p);
        System.out.println(value2);
    }
}
```



**2.获取构造方法们**
	*Constructor<?>[] getConstructors()  
	*Constructor<T> getConstructor(类<?>... parameterTypes)  

​	*Constructor<T> getDeclaredConstructor(类<?>... parameterTypes)  
​	*Constructor<?>[] getDeclaredConstructors()  

​	**Constructor:构造方法**
​		**创建对象：**
​			*T newInstance(Object... initargs)  
​			*如果使用空参数构造方法创建对象，操作可以简化：Class对象的newInstance方法

```java
public class Demo {
    public static void main(String[] args) throws Exception {
        Class personClass = Person.class;
        Constructor constructor = personClass.getConstructor(String.class, int.class);
        System.out.println(constructor);
        Object person = constructor.newInstance("张三", 23);
        System.out.println(person);

        System.out.println("--------------------------");

        Constructor constructor1 = personClass.getConstructor();
        System.out.println(constructor1);
        Object person1 = constructor1.newInstance();
        System.out.println(person1);

        Object o = personClass.newInstance();//如果使用空参数构造方法创建对象，操作可以简化
        System.out.println(o);
    }
}
```



**3.获取成员方法们：**
	*Method[] getMethods()  
	*Method getMethod(String name, 类<?>... parameterTypes)  

​	*Method[] getDeclaredMethods()  
​	*Method getDeclaredMethod(String name, 类<?>... parameterTypes)  

​	**Method：方法对象**
​		**执行方法：**
​			*Object invoke(Object obj, Object... args) //运行方法 
​			获取方法名称：String getName:获取方法名

```java
public class Demo {
    public static void main(String[] args) throws Exception {
        Class personClass = Person.class;
        //获取指定名称的方法
        Method eat_method = personClass.getMethod("eat");
        Person p=new Person();
        //执行方法
        eat_method.invoke(p);

        Method eat_method2 = personClass.getMethod("eat", String.class);//方法名，参数类型
        //执行方法
        eat_method2.invoke(p,"饭");

        System.out.println("-------------------------");

        //获取所有public修饰的方法
        Method[] methods = personClass.getMethods();
        for (Method method : methods) {
            System.out.println(method);
            String name=method.getName();
            System.out.println(name);
        }
        //获取类名
        String className=personClass.getName();
        System.out.println(className);
    }
}
```



**4.获取全类名**
	*String getName()  

* 案例：
	*需求：写一个"框架"，不能改变该类的任何代码的前提下，可以帮我们创建任意类的对象，并且执行其中任意方法
		*实现：
			1. 配置文件
			2. 反射
		*步骤：
			1. 将需要创建的对象的全类名和需要执行的方法定义在配置文件中
			2. 在程序中加载读取配置文件
			3. 使用反射技术来加载类文件进内存
			4. 创建对象
			5. 执行方法
	
			1. 配置文件
			2. 反射
		*步骤：
			1. 将需要创建的对象的全类名和需要执行的方法定义在配置文件中
			2. 在程序中加载读取配置文件
			3. 使用反射技术来加载类文件进内存
			4. 创建对象
			5. 执行方法

```java
public class Demo {
    public static void main(String[] args) throws Exception {
        //创建Properties对象
        Properties pro=new Properties();
        //获取class目录下的配置文件
        ClassLoader classLoader = Demo.class.getClassLoader();
        InputStream is = classLoader.getResourceAsStream("pro.properties");
        pro.load(is);
        //获取配置文件中定义的数据
        String className=pro.getProperty("className");
        String methodName = pro.getProperty("methodName");
        //加载该类进内存
        Class cls = Class.forName(className);
        Object obj = cls.newInstance();
        Method method=cls.getMethod(methodName);
        method.invoke(obj);
    }
}
```





### 注解

------------------------------------------

注解是以“@注释名”在代码中存在的，还可以添加一些参数值，例如@SuppressWarnings(value="unchecked")

**JDK中预定义的一些注解**
	*@Override	：检测被该注解标注的方法是否是继承自父类(接口)的
	*@Deprecated：该注解标注的内容，表示已过时
	*@SuppressWarnings：压制警告
	*一般传递参数all  @SuppressWarnings("all")

#### 自定义注解
​	格式：
​		元注解
​		public @interface 注解名称{
​			属性列表;
​		}

*本质：注解本质上就是一个接口，该接口默认继承Annotation接口
	*public interface MyAnno extends java.lang.annotation.Annotation {}

*属性：接口中的抽象方法
	*要求：

​		1.属性的返回值类型有下列取值
​			*基本数据类型
​			*String
​			*枚举
​			*注解
​			*以上类型的数组

​		2.定义了属性，在使用时需要给属性赋值

​				(1).如果定义属性时，使用default关键字给属性默认初始化值，则使用注解时，可以不进行属性的赋值。

​				(2).如果只有一个属性需要赋值，并且属性的名称是value，则value可以省略，直接定义值即可。

​				(3).数组赋值时，值使用{}包裹。如果数组中只有一个值，则{}可以省略



#### 元注解

*元注解：用于描述注解的注解
	*@Target：描述注解能够作用的位置
			ElementType取值：
				TYPE：可以作用于类上
				METHOD：可以作用于方法上
				FIELD：可以作用于成员变量上
	*@Retention：描述注解被保留的阶段
		*@Retention(RetentionPolicy.RUNTIME)：当前被描述的注解，会保留到class字节码文件中，并被JVM读取到
	*@Documented：描述注解是否被抽取到api文档中
	*@Inherited：描述注解是否被子类继承

```java
@Target(value = {ElementType.TYPE,ElementType.METHOD})
@Retention(RetentionPolicy.RUNTIME)//一般都用这个值
@Documented
@Inherited
public @interface MyAnno3 {
}

```

*在程序使用(解析)注解：获取注解中定义的属性值

1.获取注解定义的位置的对象  （Class，Method,Field）
2.获取指定的注解
	*getAnnotation(Class)
	//其实就是在内存中生成了一个该注解接口的子类实现对象

	public class ProImpl implements Pro{
		public String className(){
			return "cn.itcast.annotation.Demo1";
		}
		public String methodName(){
			return "show";
		}
	}
	
3. 调用注解中的抽象方法获取配置的属性值

```java
@Pro(className = "yy.Demo1",methodName = "show")
public class Demo {
    public static void main(String[] args) throws Exception {
        //1.解析注解
        //获取该类的字节码文件对象
        Class<Demo> demoClass = Demo.class;
        //2.获取上边注释对象
        Pro an = demoClass.getAnnotation(Pro.class);//其实就是在内存中生成了一个该注解接口的子类实现对象
         /*
            public class ProImpl implements Pro{
                public String className(){
                    return "yy.Demo1";
                }
                public String methodName(){
                    return "show";
                }
            }
 */
        //3.调用注解对象中定义的抽象方法，获取返回值
        String className = an.className();
        String methodName = an.methodName();
        System.out.println(className);
        System.out.println(methodName);

        Class cls = Class.forName(className);
        Object obj = cls.newInstance();
        Method method=cls.getMethod(methodName);
        method.invoke(obj);
    }
}
```



#### 案例

案例：简单的测试框架
小结：
	1. 以后大多数时候，我们会使用注解，而不是自定义注解
	2. 注解给谁用？
		1. 编译器
		2. 给解析程序用
	3. 注解不是程序的一部分，可以理解为注解就是一个标签

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface Check {
}
```

```java
/**
 * 小明定义的计算器类
 */
public class Calculator {

    //加法
    @Check
    public void add(){
        System.out.println("1 + 0 =" + (1 + 0));
    }
    //减法
    @Check
    public void sub(){
        System.out.println("1 - 0 =" + (1 - 0));
    }
    //乘法
    @Check
    public void mul(){
        System.out.println("1 * 0 =" + (1 * 0));
    }
    //除法
    @Check
    public void div(){
        System.out.println("1 / 0 =" + (1 / 0));
    }


    public void show(){
        System.out.println("永无bug...");
    }

}
```

```java
public class Demo {
    public static void main(String[] args) throws Exception {
        //1.创建计算器对象
        Calculator c=new Calculator();
        //2.获取字节码文件对象
        Class cls = c.getClass();
        //3.获取所有方法
        Method[] methods = cls.getMethods();
        int number=0;//出现异常的次数
        BufferedWriter bw=new BufferedWriter(new FileWriter("bug.txt"));
        for (Method method : methods) {
            //4.判断方法上是都有Check注解
            if(method.isAnnotationPresent(Check.class)){
                //5.有，执行
                try{
                    method.invoke(c);
                }catch (Exception e){
                    //6.捕获异常
                    //记录到文件中
                    number++;
                    bw.write(method.getName()+"方法出异常了");
                    bw.newLine();
                    bw.write("异常的名称:"+e.getCause().getClass().getSimpleName());
                    bw.newLine();
                    bw.write("异常的原因:"+e.getCause().getMessage());
                    bw.newLine();
                    bw.write("----------------------");
                    bw.newLine();
                }
            }
        }
        bw.write("本次测试一共出现 "+number+" 次异常");
        bw.flush();
        bw.close();
    }
}
```

