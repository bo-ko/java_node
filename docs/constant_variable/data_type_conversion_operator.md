# 三、数据类型转换

## 3.1 自动转换

一个`int`类型变量和一个`byte`类型变量进行加法运算，运算结果，变量类型是`int`类型，这就是出现了数据类型的自动转换现象。

**自动转换：** 将取值范围小的类型自动提升为取值范围大的类型。
  
```java linenums="1"
public static void main(String[] args) {
    int i = 1;
    byte b = 2;
    // byte result = b + i // 报错
    // int类型和byte类型运算，结果是int类型
    int result = b + i;
    System.out.println(result);
}
```

* **转换规则：**
范围小的类型向范围大的范围提升，`byte、short、char`运算时直接提升为`int`。
`byte、short、char-->int-->long-->float-->double`

## 3.2 强制类型转换

将`1.6`赋值到`int`类型会产生编译失败

```java linenums="1"
int i = 1.6; // 错误
```

`double`类型内存占8个字节，`int`类型内存占4个字节。`1.6`是`double`类型，取值范围大于`int`。可以理解为`double`是8升的水壶，`int`是4升的水壶，不能把大水壶中的水直接放进小水壶去。想要赋值成功，只有通过强制类型转换，将`double`类型强制转换成`int`类型才能赋值。自动转换是java自动执行的，而强制转换需要我们自己手动执行。

**强制类型转换：** 将`取值范围大的类型`强制转换成`取值范围小的类型`。

**转换格式：**

* 数据类型 变量名 = (数据类型)被转数据值
  
将`1.6`赋值到`int`类型

```java linenums="1"
// doble类型数据强制转换成int类型，直接去掉小数点。
int i = (int)1.6;
```

一个`short`类型与`6`相加，会类型提升，但是想结果赋值给`short`类型变量，就需要强制转换

```java linenums="1"
public static void main(String[] args) {
    // short 类型变量，内存中占2个字节
    short s = 1;
    /* 出现编译失败
       s和1做运算的时候，1是int类型，s会被升为int类型
       s+1后结果是int类型，将结果在赋值会short类型时发生错误
       short内存中占2个字节，int类型占4个字节
       必须将int强制转换成short类型才能完成赋值
     */
     // s = s + 1; // 编译报错
     s = (short)(s + 1); // 正确写法
}
```

!!! warning "注意"
    * 浮点数转成整数，直接取消小数点，可能造成数据损失精度。
    * `int`强制转换成`short`砍掉两个字节，可能造成数据丢失。

```java linenums="1"
// 定义s为short范围内最大值
short s = 32767;
// 运算后，强制转换，砍掉2个字节后会出现不确定的结果
s = (short)(s + 10);
```

## 3.3 ASCII编码表

在char类型int类型计算过程中，char类型的字符先查询编码表，得到97，再和1求和，结果为98。char类型提升为int类型。char类型内存2个字节，int类型内存4个字节。

|字符|数值|
|------|------|
|0|48|
|A|65|
|a|97|
