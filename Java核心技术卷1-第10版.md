[TOC]

# Java 核心技术 卷1 第10版

## 1. Java 程序设计概述

- 简单性
- 面向对象
  - 与C++面向对象的特性相同
- 分布式
  - 有一个丰富的例程库，用于处理HTTP和FTP之类的TCP/IP协议
  - Java应用程序可以通过URL 打开和访问网络上的对象，快捷程序相当于访问本地文件一样
- 健壮性
- 安全性
  - Java适用于网络/分布式环境，可以构建防范病毒、防篡改的系统，例如：
    - 运行时堆栈溢出，如蠕虫和病毒常用的攻击手段
    - 破坏自己的进程空间之外的内存
    - 未经授权读写文件
- 体系结构中立
  - 只要有Java运行时系统，编译后的代码可以在许多处理器运行
  - 精心设计的字节码可以很容易地在任何机器上解释执行，还可以动态地翻译成本地机器代码
- 可移植性
  - Java规范中没有“依赖具体实现”的地方，基本数据类型的大小以及有关运算都做了明确的说明，例如：
    - Java中的 int 永远为32位的整数，但是C/C++，中int可能为16或32位整数
    - 唯一的限制是，short类型的大小 =< int类型的大小 =< long int类型的大小
    - 数据类型具有固定的大小，就消除代码移植时令人头疼的问题
    - 二进制数据以固定的格式进行存储和传输，消除了字节顺序的困扰
    - 字符串是用标准的 Unicode 格式存储 
- 解释型
  - Java解释器可以在任何移植了解释器的机器上执行Java字节码
- 高性能
  - 即时编译器可以监控经常执行哪些代码，并优化这些代码以提高速度
  - 更为复杂的优化是消除函数调用（即内联）
- 多线程
  - 多线程可以带来更好的交互响应和实时行为
  - Java是第一个支持并发程序设计的主流语言
  - 多核处理器
- 动态性
  - Java比C++更具有动态性
  - 库中可以自由地添加新方法和实例变量，对客户端没有任何影响
    - 例如：从Internet 下载代码，然后在浏览器上运行
- Java applet 与 Internet
  - 用户从Internet 下载 Java 字节码，在网上运行的Java程序称为applet

---



## 2. Java 程序设计环境

- 下载 JDK，Java开发工具包
- 设置 JDK
- 使用集成开发环境
  - Eclipse
  - Myeclipse
  - IntelliJ IDEA
  - Jbuilder
  - Jdeveloper
  - Netbeans
  - JCreator
- Java 的版本
  - Java SE 是 java 平台标准版
  - Java EE 是 java 平台企业版
  - Java ME 是 java 平台微机版，多用于开发手机移动端
- Java 开发
  - Java的源代码是*.java 的纯文本文件
  - JDK是Java的开发包，可以将*.java 文件编译成可执行Java程序
  - 可执行Java程序需要JVM才可以运行
  - JRE包含JVM
  - JDK包含JRE
- 常见DOS命令
  - cmd 弹出dos命令窗口
  - d: 切换到D盘
  - dir 显示当前所有文件夹
  - cd 文件夹名称，进入文件夹
  - cd.. 回退
  - cd Java视频 \\ \\ day 01，进入多级目录
  - cd\，多级回退
  - cls 清屏
  - exit 退出dos命令行
- Hello World 流程图
  - HelloWorld.java → HelloWorld.class → 0010100011...→  程序
  - ​        源文件         →        字节码文件    →         机器码      →  程序

---



## 3. Java 的基本程序设计结构

- 一个简单的Java应用程序

- 注释

  - 单行注释：//注释文字
  - 多行注释：/* 注释文字 */
  - 文档注释：/** 注释文字 **/

- 关键字

  - 全部小写
  - 有特殊颜色标记
  - 关键字分类
    - 定义数据类型：class, interface, byte, short, int, long, float, double, char, boolean, void
    - 定义数据类型值：true, false, null
    - 定义流程控制：if, else, switch, case, default, while, do, for, break, continue, return 
    - 定义访问权限修饰符：private, protected, public
    - 定义类、函数、变量修饰符：abstract, final, static, synchronized
    - 定义类与类之间关系：extends, implements
    - 定义建立实例及引用实例，判断实例：new, this, super, instanceof
    - 用于异常处理：try, catch, finally, throw, throws
    - 用于包：package, import
    - 其他修饰符关键字：native, strictfp, transient, volatile, assert

- 数据类型

- 常量

  - 其值不改变的
  - 字符串常量 “Hello”
  - 整数常量  12，-23
  - 小数常量  12.23
  - 字符常量  ‘a’
  - 布尔常量  true， false
  - 空常量  null

- 变量

  - 是内存中的一小块区域，程序执行过程中，其值在一定范围内变化

    - B是字节，bit是比特、位

    - 1B = 8 bit
    - 1KB=1024 B
    - 1MB =1024KB

  - 数据类型（单位，B）

    - 基本数据类型

      > 数值型：
      >
      > - 整数型：byte 1, short 2, int 4, long 8
      > - 浮点型：float 4, double 8
      > - 整数默认int，浮点数默认double
      > - 定义long类型，建议加L；定义float类型，建议加F
      >
      > 字符型：
      >
      > - char 2
      >
      > 布尔型：
      >
      > - boolean 1

    - 引用数据类型

      > 类：class
      >
      > 接口：inerface
      >
      > 数组：[ ]

  - 变量名

    - 标志符：给包、类、方法、变量起名的符号

    - Unicode 字符，数字、英文大小写、汉字，下划线_，美元符$

    - 数字不能开头，不能是Java中的关键字

    - 常见命名规则：

      >1. 包（其实就是文件夹，对相似的类进行管理）
      >   - 全部小写，多级包 . 隔开
      >   - 例如：com, com.itheima
      >2. 类
      >   - 一个单词首字母大写，如：Student，Car
      >   - 多个单词每个单词首字母大写，如：HelloWorld
      >3. 方法和变量
      >   - 一个单词首字母小写，如：age(), show()
      >   - 多个单词，从第二个单词的首字母大写，如：maxAge(), getAge()

  - 初始化值

    ```java
    public class VariableDemo{
        public static void main (String[] args){
            //定义byte
            byte b = 10;
            System.out.println(b);
            
            //定义short
            short s = 100;
            System.out.println(s);
            
            //定义int
            int i = 10000;
            System.out println(i);
            
            //定义long
            long l = 1000000000000L;
            System.out.println(l);
            
            //定义float
            float f = 12.34F;
            System.out.println(f);
            
            //定义double
            double d = 12.34;
            System.out.println(d);
            
            //定义char
            char c = 'a';
            System.out.println(c);
            
            //定义boolean
            boolean bl = true;
            System.out.println(bl);
        }
    }
    ```

    - 注意事项：
      1. 变量未赋值不能直接使用
      2. 变量只在所属范围内有效，变量属于它所在的代码块，{ }
      3. 一行可以定义多个变量，但是不建议

- 运算符

  - 类型转换：隐式转换、强制转换

    - 隐式转换：

      - byte, short, char → int → long → float → double，从小到大可以，如 byte 和 int，结果为 int
      - byte，short，char 之间不转换，他们参与运算首先转换为 int 

    - 强制转换

      - 目标类型 变量名 = （目标类型）（被转换的数据）

        ```
        int a = 10;
        byte b = 20;
        
        byte d = (byte)a + b;//原本d应该为int，利用强制类型转换
        ```

        

  - ![image-20210121164013140](Java核心技术卷1-第10版.assets/image-20210121164013140.png)

  - 使用算术运算法+ - * / ，默认整数，否则浮点数运算

  - 快捷键：

    - main，Alt + /
    - syso,    Alt + /

  - 运算符分类：

    > 1. 算数运算符：+，-，*，/（整数相除只有整数，要想得小数，必须有浮点数参与），%，++，--
    >    - ‘A’ 65   ‘a’  97  ‘0’  48
    > 2. 赋值运算符：+=，-= ,...
    >    - 扩展的赋值运算符，隐含强制类型转换
    > 3. 关系运算符：==，!=, <=, >=,...
    >    - 结果都是boolean类型，true , false
    > 4. 逻辑运算符：& |  ^  !    && ||
    >    -  &与&&的区别：&，左边无论真假，右边都进行运算；&&，左边为真，右边参与运算，左边为假，右边不参与运算
    >    -  ^ 异或，相同为false ，不同为true
    > 5. 三元运算符：关系表达式 ？ 表达式1 ： 表达式2
    >    - true，就返回   表达式1
    >    - false，就返回   表达式2

- 字符串

  - 子串 substring(0,3) //从0开始，取3个字符

    - s="" ; //为空字符串

  - 拼接 “S”+“M”

  - 不可变字符串

    - 字符“Hello”是不可变的，但是greeting是可以变的

    - ```java
      String greeting = "Hello World"
      greeting = greeting.substring(0,3)+"p!";
      ```

    - 字符串**不是**字符型数组，而**是**类似于 char* 指针，在堆区中不使用的内存将会自动进行垃圾回收

  - 检测字符串是否相等

    - s.equals(t); // s 与 t 是否相等，true，false、

    - 不能用C++的string类重载了==检测共享的字符串是否相等，系统会出错

    - 应该用 if(greeting.compareTo("Hello")== 0) 代替 if(greeting.substring(0,3) == "Hel")

      ![image-20210121222103878](Java核心技术卷1-第10版.assets/image-20210121222103878.png)

      ![image-20210121222118070](Java核心技术卷1-第10版.assets/image-20210121222118070.png)

  - 检测空串与Null串

    - 判断是否为空串，if(str.length() == 0) 或 if(str.equals(""))
    - 判断既不是null也不为空串，if(str != null && str.length() != 0 )

  - String API

    - StringBuilder(); //空的字符串构建器
    - int length();//返回构建器中的代码单元数量
    - StringBuilder append(String str);//追加字符串并返回 this
    - StringBuilder append(char c);//追加代码单元并返回 this
    - StringBuilder appendCodePoint(int cp);//追加代码点，并将其转换成一个或两个代码单元并返回 this
    - StringBuilder insert(int offset,String str);//在offset位置插入一个字符串并返回 this
    - StringBuilder delete(int startIndex, int endIndex);//删除偏移量从startIndex 到 endIndex的代码单元并返回this
    - String toString();//返回一个与构建器或缓冲区内容相同的字符串

- Eclipse的使用

  - 先建立项目，然后新建包，再新建类

- 输入输出

- 控制流

  - 顺序结构

  - 选择结构

    - Ctrl + Shift + o 导包快捷键方式

      ```java
      //导入键盘输入的包
      import java.util.Scanner ; 
      
      //创建对象
      Scanner sc = new Scanner(System.in); 
      
      //获取数据
      System.out.println(“请输入数据：”);
      int a = sc.nextInt(); 
      ```

    - if 语句
    - switch 语句（表达式可以是 byte，short，char，int）

  - 循环结构

    - for 必须入口判断成立才能进入循环
    - while 必须入口判断成立才能进入循环
    - do ... while 至少执行一次循环体
    - 跳转语句：
      - break 结束循环     
      - continue 结束一次循环，继续下一次循环

- 大数值

- 数组

  ```java
  //导包
  import java.util.Random;
  
  //创建对象
  Random r = new Random();
  
  //获取随机数
  int num = r.nextInt(10); //获取[0,10)，含0，不含10的随机数
  int num = r.nextInt(10)+1; //获取含1-10的随机数
  ```

  

---



## 4. 对象与类













---



## 5. 继承









---



## 6. 接口





----



## 7. 异常、断言和日志







---



## 8. 泛型程序设计







---



## 9. 集合







----



## 10. 图形程序设计







---



## 11. 事件处理







---



## 12. Swing 用户界面组件







----



## 13. 部署 Java 应用程序







----



## 14. 并发









---



