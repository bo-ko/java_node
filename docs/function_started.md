# 五、方法入门

## 5.1 概述

**方法：** 就是将一个**功能**抽取出来，把代码单独定义在一个大括号内，形成一个单独的功能。当我们需要这个功能的时候，就可以去调用。这样即实现了代码复用性，也解决了代码冗余的现象。

## 5.2 方法的定义

* **定义格式：**

``` linenums="1"
修饰符 返回值类型 方法名 （参数列表）{
    代码...
    return ；
}
```

**定义格式解释：**

- 修饰符：目前固定写法`public static`。
- 返回值类型：目前固定写法`void`
- 方法名：为我们定义的方法起名，满足标识符规范，用来调用方法。
- 参数列表：目前无参数
- return：方法结束，返回值类型是void，方法大括号内可的return可以不写。

**举例：**

```java linenums="1"
public static void methodName() {
    System.out.println("这是一个方法");
}

```

## 5.3 方法的调用

方法在定义完毕后，方法不会自己运行，必须调用才能执行，我们可以再主方法main中来调用我们自己定义好的方法。在主方法中，直接写要调用的方法名字就可以了。

```java linenums="1"
public static void main(Strint[] args) {
    // 调用定义的方法method
    method();
}

// 定义方法，被main方法调用
public static void method() {
    System.out.println("自定义的方法，需要被main调用");
}
```

## 5.4 方法练习

将三元运算符代码抽取到自定义的方法中，并调用。

```java linenums="1"
public static void main(Strint[] args) {
    // 调用定义的方法operator
    operator();
}

// 定义方法，方法中定义三元运算符
public static void operator() {
    int i = 0;
    i = (1 == 2 ? 100:200);
    System.out.println(i);
    int j = 0;
    j = (3<=4 ? 500:600);
    System.out.println(j);
}
```

!!! warning "注意"
    **方法定义注意事项：**

    * 方法必须定义在一类中方法外
    
    * 方法不能定在另一个方法的里面
    
    ```java linenums="1"
    public class Demo {
        public static void main(Strint[] args) {
        }
        // 正确写法，类中，main方法外面可以定义方法
        public static void method(){}
    }
    ```

    ```java linenums="1"
    public class Demo {
        // 错误写法，一个方法不能定义在另一个方法内部
        public static void main(Strint[] args) {
            // 错误写法， 一个方法不能定义在另一个方法内部
            public static void method() {}
        }
    }
    ```
