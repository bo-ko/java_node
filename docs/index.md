# 一、Java 常量

## 1.1 概述

常量：是指在java程序中固定不变的数据。

## 1.2 分类

|类型|含义|举例|
|---|----|---|
|整数常量|所有的整数|0, 1, -1|
|小数常量|所有小数|0.1, -0.2, 2.6|
|字符常量|单引号引起来, 只能写一个字符, 必须有内容|'a', '呵', '1'|
|字符串常量|双引号引起来, 可以写多个字符, 也可以不写|"A", "呵呵", ""|
|布尔常量|只有两个值|true, false|
|空常量|只有一个值|null|

## 1.3 例子

需求：输出各种类型的常量

```java
public class ConstantDemo {
    public static void main(String[] args) {
        // 输出整数常量
        System.out.println(123);
        // 输出小数常量
        System.out.println(0.123);
        // 输出字符常量
        System.out.println('a');
        // 输出字符串常量
        System.out.println("abc");
        // 输出布尔常量
        System.out.println(true);
    }
}
```