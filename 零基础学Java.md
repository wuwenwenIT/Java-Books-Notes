[TOC]

# 一、基础知识

#### 1. Java具有的特性

- 简单性

- 可移植性

  > 解决Java直接编译成的二进制码，在Windows系统可以运行，但是可能无法在Linux运行，为此Java先生成字节码，再JVM（Java虚拟机）来解释执行，将字节码转成不同操作系统可以识别的二进制码。
  
- 安全性

- 并发性（多线程）

####  2. JDK

> JDK 是 Java Development ToolKit 的简称，也就是 Java 开发工具包。JDK 是整个 Java 的核心，包括 Java 运行环境（Java Runtime Envirnment，简称 JRE），Java 工具（比如 javac、java、javap 等等），以及 Java 基础类库（比如 rt.jar）。
>
> - bin：包含了最主要的是编译器（javac.exe）
>
> - include：Java 和 JVM 交互用的头文件
>
> - lib：类库
> - jre：Java 运行环境
>
> JDK 有三种类型。
>
> - J2SE：Standard Edition，标准版，是我们通常用的一个版本，从 JDK 5.0 开始，改名为 Java SE。
>
> - J2EE：Enterprise Edition，企业版，从 JDK 5.0 开始，改名为 Java EE。
>
> - J2ME：Micro Edition，主要应用于移动设备、嵌入式设备，从 JDK 5.0 开始，改名为 Java ME。

  #### 3.IntelliJ IDEA 和 Eclipse 

> IntelliJ IDEA 和 Eclipse 是Java的集成开发工具
>
> - Eclipse适合入门
> - IntelliJ IDEA适合企业开发

>- class 关键字：用于在Java中声明一个类
>- public：一个表示可见性的访问修饰符
>- static：可以声明任何一个方法，被static修饰后的方法称之为静态方法，无需为其创建对象就可以调用。
>- void ：不需要返回任何值
>- main：主方法，程序运行的入口
>- String [ ] args: 将传递的参数打印到控制台 
>  - System是java.lang包中的final类，包括标准输入、输出、错误输出流等。
>  - out 是System类的静态成员字段，类型是PrintStream，它与主机的标准输出控制台进行映射。
>  - println是PrintStream类的一个方法，通过print方法并添加一个换行符实现的

#### 3. 字节码

> - IDEA默认 Fernflower 反编译工具将字节码文件 （后缀.class，即源代码编译后的文件）反编译成我们看得懂的Java代码。Show Bytecode
>
> - 字节码并不是机器码，操作系统无法直接识别，需要在操作系统上安装不同版本的Java虚拟机（JVM）来识别，通常情况下安装不同版本的JDK（Java Development Kit，Java开发工具包），JDK里面包含JRE（Java Runtime Environment，Java运行环境），JRE包含JVM。
>
>   ![](https://github.com/wuwenwenIT/Typora_textbook/raw/master/assets/1.png)
>

##### git的基本理论

![](https://github.com/wuwenwenIT/assets/raw/master/image-20210117171211406.png)

#### 4. Java虚拟机

![01](https://github.com/wuwenwenIT/assets/raw/master/image-20210117195758828.png)

##### HotSpot

>技术优势在于 **热点代码探测技术** 和 **准确式内存管理技术** 
>
>-  **热点代码探测技术** ：通过执行计数器找出最具有编译价值的代码，如何通知即时编译器以方法为单位进行编译，解释器就可以不再逐行翻译为机器码，而是将一整个方法的字节码翻译成机器码再执行。

##### Java虚拟机的内部：

- 类加载器（Class Loader）
- 运行时数据区（Runtime Data Areas）
- 执行引擎（Excution Engine）

![](https://github.com/wuwenwenIT/assets/raw/master/image-20210117211228061.png)

##### 类加载器

 类加载器是Java虚拟机的一个子系统，用于加载类文件。

##### 运行时数据区

![image-20210117211621643](零基础学Java.assets/image-20210117211621643.png)

>- PC寄存器（PC Register）,程序计数器
>- JVM栈，和PC寄存器一样，JVM栈也是线程私有的，每个JVM线程都有自己的栈
>- 堆Heap ，可以提供各条线程共享的运行时内存区域
>- 方法区 Method area ，是所有线程共享的，所以访问方法区信息的方法必须是线程安全的
>- 运行时常量池（Runtime Constant Pool），当一个方法或者变量被引用时，JVM通过运行时常量区查找方法或者变量在内存的实际地址。

#### 5. Java变量

1. 局部变量

2. 成员变量

   new可以创建一个类的实例（对象）

3. 静态变量

   static 声明的变量为静态变量（类变量），可以直接被类访问，无需创建类的实例

4. 常量

   常量名大写，常量的值一旦给定无法改变

#### 6. Java中的数据类型

> 1. 基本数据类型
>
>    基本数据类型是Java语言操作数据的基础，有8种，分别为：boolean, char, byte, short, int, long, float, double.
>
>    ![image-20210117214107139](零基础学Java.assets/image-20210117214107139.png)
>
>    Java 使用的是Unicode 字符集，而不是ASCII字符集。
>
> 2. 引用数据类型
>
>    数组、类、接口
>
>    null，经常有“空指针异常”，NullPointerException，引用数据类型的默认值为null，包括数组和接口。
>
>    接口类型的引用变量，无法new一个；只有引用数据类型，才能用new实现它的类的对象。
>
> 3. 区别：
>
>    - 基本数据类型
>
>      > 1. 变量名指向具体的数值
>      > 2. 基本数据类型存储在栈上
>
>    - 引用数据类型
>
>      > 1. 变量名指向的是存储对象的内存地址，在栈上
>      > 2. 内存地址指向的对象存储在堆上
>
>    - 堆heap，堆栈也是栈，堆是在程序运行时在内存申请的空间，是个动态过程。
>
>    - 栈stack， 会与CPU直接关联，访问速度快，必须明确知道栈区的东西的生命周期。

1. ASCII

   ASCII有256种，A65，a97，

2. Unicode 

   UTF-8，UTF-16

3. 三元运算符

        min = (a<b)?a:b;

4. 48个关键词

    > 3个保留字true false null   
    > ###### 1).访问修饰符的关键字（共3个）
    > ​    public       公有的          可跨包，（默认选择）
    > protected   受保护的        当前包内可用
    > private     私有的          当前类可用
    >
    > ###### 2).定义类、接口、抽象类和实现接口、继承类的关键字、实例化对象（共6个）
    >
    > class       类      public class A(){}  花括号里有已实现方法体，类名需要与文件名相同
    > interface   接口     public interface B(){}  花括号里有方法体，但没有实现，方法体句子后面是英文分号“:”结尾
    > abstract     声明抽象         public abstract class C(){} 介于类与接口中间，可以有也可以没有已经实现的方法体
    > implements   实现             用于类或接口实现接口public class A  interface B(){}
    > extends     继承             用于类继承类 public class A extends D(){}
    > new         创建新对象 A a=new A();  A表示一个类
    >
    > ###### 3).包的关键字（共2个）
    >
    > import       引入包的关键字   当使用某个包的一些类时，仅需类名 然后使用ctrl+shift+o或者选定类名（类或属性或方法）按住ctrl+单击 即可自动插入类所在的包。
    > 如：JFrame 快捷键之后自动加入。import javax.swing.JFrame;
    > package     定义包的关键字   将所有有关的类放在一个包类以便查找修改等。如：package javake.flycat.draw002;
    >
    > ###### 4).数据类型的关键字（共12个）
    >
    > byte      字节型     8bit
    > char          字符型           16bit
    > boolean    布尔型
    > short 短整型           16bit
    > int          整型     32bit
    > float        浮点型           32bit
    > long          长整型           64bit
    > double      双精度           64bit
    > void         无返回           public void A(){}   其他需要返回的经常与return连用  
    > null     空值
    > true     真
    > false     假
    >
    > ###### 5).条件循环（流程控制）（共12个）
    >
    > if     如果     if(){} 如果小括号里面怎么怎么样 花括号就怎么怎么样
    > else     否则，或者 常与if连用，用法相同
    > while 当什么的时候 while 怎么样就do什么    while(){}
    > for 满足三个条件时 for ( ; ; ){}
    > switch 开关 switch(表达式){
    > case 常量表达式1:语句1;
    > ....
    > case 常量表达式2:语句2;
    > default:语句;
    > }
    >
    >
    > default 就是如果没有符合的case就执行它,default并不是必须的.
    > case后的语句可以不用大括号.
    > switch语句的判断条件可以接受int,byte,char,short,不能接受其他类型.
    > case 返回开关里的结果
    > default 默认
    > do 运行 长与while连用
    > break 跳出循环
    > continue 继续 中断本次循环，并并开始下一次
    > return 返回 return 一个返回值类型
    > instanceof实例 一个二元操作符，和==，>，<是同一类的。测试它左边的对象是否是它右边的类的实例，返回boolean类型的数据
    >
    > ###### 6).修饰方法、类、属性和变量（共9个）
    >
    > 1. static 静态的 属性和方法都可以用static修饰，直接使用类名.属性和方法名。  只有内部类可以使用static关键字修饰，调用直接使用类名.内部类类名进行调用。   
    > 2. static可以独立存在。静态块final 最终的不可 方法和类都可以用final来修饰 
    >    被改变的 final修饰的类是不能被继承的  final修饰的方法是不能被子类重写。
    >    常量的定义：
    >    final修饰的属性就是常量。
    >    super 调用父类的方法 常见public void paint(Graphics g){
    >    super.paint(g); ··· }
    > 3. this 当前类的父 调用当前类中的方法（表示调用这个方法的对象）
    >    类的对象 this.addActionListener(al):等等
    >    native 本地
    >    strictfp 严格,精准 
    >    synchronized 线程,同步
    >    transient 短暂
    >    volatile 易失
    >
    > ###### 7).错误处理（共5个）
    >
    > 1. catch      处理异常 1.try+catch程序的流程是：运行到try块中，如果有异常抛出，则转到catch块去处理。然后执行catch块后面的语句
    > 2. try+catch+finally
    >    程序的流程是：运行到try块中，如果有异常抛出，则转到catch块,catch块执行完毕后，执行finally块的代码，再执行finally
    >    块后面的代码。
    >    如果没有异常抛出，执行完try块，也要去执行finally块的代码。然后执行finally块后面的语句
    > 3. try+finally
    >    程序的流程是：运行到try块中,如果有异常抛出的话，程序转向执行finally块的代码。那末finally块后面的代码还会被执行吗？
    >    不会！因为你没有处理异常，所以遇到异常后，执行完finally后，方法就已抛出异常的方式退出了。
    >    这种方式中要注意的是，由于你没有捕获异常，所以要在方法后面声明抛出异常
    > 4. try 捕获异常
    >    finally 有没有异常都执行
    >    throw 抛出一个 一些可以导致程序出问题的因素,比如书写错误,逻辑错误或者是api的应用错误等等. 为了防止程序的崩溃就要预先检测这些因素,
    >    异常对象 所以java 使用了异常这个机制.
    >    在java中异常是靠 "抛出" 也就是英语的"throw" 来使用的,意思是如果发现到什么异常的时候就把错误信息 "抛出"
    > 5. throws 声明一个异 把异常交给他的上级管理，自己不进行异常处理
    >    常可能被抛出
    >
    > ###### 8).不知道是什么（共2个）
    >
    > enum 枚举，列举型别
    > assert 断言
    >
    > const   常量，常数 用于修改字段或局部变量的声明。它指定字段或局部变量的值是常数，不能被修改
    > goto 转到 指定跳转到标签，找到标签后，程序将处理从下一行开始的命令。

    continue : 当我们需要在for循环或者do while循环中跳到下一个循环的时候，可以用continue，通常用于跳过指定条件下的循环体，如果循环是嵌套的，仅跳过当前循环。

# 二、对象和类

#### 命名规则

1. 包（package）

   - 全部小写，含有分隔符，包名统一使用单数形式

2. 类（class）

   - 必须大写字母开头，使用驼峰式命名分格

3. 接口（interface）

   - 必须大写开头，最好是个形容词，不要省略成单词的首字母

4. 字段（field）和变量（variable）

   - 必须以小写字母开头，避免去子类和父类的成员变量之间采用完全相同的命名。

5. 常量（constant）

   - 全部大写字母，可以含数字，不能数字开头

6. 方法（method）

   - 必须小写字母开头

   - 常见前缀

     > 获取单个对象：get
     >
     > 获取多个对象：list
     >
     > 获取统计值：count
     >
     > 插入：save / insert
     >
     > 删除：remove/ delete
     >
     > 修改：updata