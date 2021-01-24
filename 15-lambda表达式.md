## Lambda表达式

#### 说明

```xml
对java语言补充
支持函数式编程 也称为闭包
将程序代码看作数学中的函数 ，函数本身作为另一个函数的蚕食 返回值
通过匿名内部类 实现通用方法 java8中 使用Lambda表达式代替匿名内部类

lambda 可访问成员变量 静态 实例都可以
不能修改局部成员变量

Lambda 作为参数使用 作为参数传递给方法  需要声明参数的类型为函数式接口类型
eg:
display((a, b) -> a-b, n1, n2);

public static void display(Calallable calc, int n1, int n2){
    System.out.print(calc.calculatInt(n1, n2));
}
```

#### 语法

##### 标准语法

```java
(参数列表) -> {
    //Lambda 表达式体
}
```

##### 基本形式

```java
result = (int a, int b) -> {return a + b; };

```

##### 省略形式

```java
// 省略参数类型
result = (a, b) -> {return a + b; };

//省略参数小括号 当Lambda表达式中的参数只有一个时  可以省略参数小括号
result = (int a ) -> {return a* a; };
result = a -> {return a * a; }; //省略模式

//省略return和大括号  当Lambda表达式中只有一条语句 可省略return 和大括号
result = a - > {return a* a;};
resutl = a -> a* a; // 省略模式


```

#### 方法引用 双冒号::

```xml
java 8 新增双冒号运算符   不是调用方法 没有直接使用

方法引用：
	静态方法引用：类型名:: 静态方法 
	eg： display(LambdaDemo::add, n1, n2);
	实例方法引用：实例名:: 实例方法
	eg: classDemo d = new classDemo();
		display(d::sub, n1, n2);

并没有调用方法 只是将引用传递  给display方法 在display中真正调用方法

```





#### 参考：

```java
方法调用
person -> person.getAge();
可以替换成
Person::getAge

x -> System.out.println(x)
可以替换成
System.out::println

创建对象
() -> new ArrayList<>();
可以替换为
ArrayList::new
    
https://www.cnblogs.com/yanlong300/p/9209243.html

https://www.cnblogs.com/three-fighter/p/13326627.html
详细操作：
```



