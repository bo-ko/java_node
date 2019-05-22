# 四、运算符

## 4.1 算数运算符

|算数运算符包括：||
|-----|-----|
|`+`|加法运算，字符串连接运算|
|`-`|减法运算|
|`*`|乘法运算|
|`/`|除法运算|
|`%`|取模运算，两个数字相除取余数|
|`++`、`--`|自增自减运算|

java中，整数使用以上运算符，无论怎么计算，也不会得到小数。

```java
public static void main(Sting[] args) {
    int i = 1234;
    System.out.println(i/1000*1000); // 计算结果是1000
}
```

- `++`运算，变量自己增长1。
- `--`运算，变量自己减少1。
    - 独立运算:
        - 变量在独立运行时，`前加++`和`后++`没有区别

    - 混合运算：
        - 和其他变量放在一起，`前++`和`后++`就产生了不同。
        - 变量`前++`：变量`a`自己加`1`，将加`1`后的结果赋值给`b`，也就是所`a`先计算。`a`和`b`的结果都是`2`。
  
    ```java
    public static void main(String[] args) {
        int a = 1;
        int b = ++a;
        System.out.println(a)  // 计算结果是2
        System.out.println(b)  // 计算结果是2
    }
    ```
    
  - 变量`后++`：变量`a`先把自己的值`1`赋值给变量`b`，此时变量`b`的值是`1`，变量`a`自己再加`1`，`a`的结果是`2`, `b`的结果是`1`.

    
    ```java
    public static void main(String[] args) {
        int a = 1;
        int b = a++;
        System.out.println(a)  // 计算结果是2
        System.out.println(b)  // 计算结果是1
    }
    ```

  - `+`符号在字符串中的操作：

    - `+`符号在遇- `+`符号在遇到字符串的时候，表示连接、拼接的含义。

    - ‵"a" + "b"`的结果是`"ab"`

    ```java
    public static void main(String[] args) {
        System.out.println("5+5=" + 5 + 5);  // 输出5+5=55
    }
    ```

## 4.2 赋值运算符
|赋值运算符包括：||
|---|---|
|`=`|等于号|
|`+=`|加等于|
|`-=`|减等于|
|`*=`|乘等于|
|`/=`|除等于|
|`%=`|取模等|

- 赋值运算符，就是将符号右边的值，赋给左边的变量。

```java
public static void main(String[] args) {
    int i = 5;
    i += 5;  // 计算方式 i = i + 5 变量先加5，再赋值变量i

    System.out.println(i);  // 输出结果是10
}
```

**`+=`符号的扩展**

- 下面的程序有问题吗？

```java
public static void main(String[] args) {
    short s = 1;
    s += 1;
    System.out.println(s);
}
```

**分析：**`s += 1`逻辑上看作是`s = s + 1`计算结果被提升为`int`类型，再向`short`类型赋值时发生错误，因为不能将取值范围大的类型赋值到取值范围小的类型。但是，`s = s + 1进行两次运算`，`+=`是一个运算符，只运算一次，并带有强制转换的特点，也就是说`s = s + 1`就是`s = (short)(s + 1)`，因此程序没有问题编译通过，运行结果是2。

## 4.3 比较运算符


|比较运算符包括：||
|---|---|
|`==`|比较符号两边数据是否相等，相等结果是true。|
|`<`|比较符号左边的数据是否小于右边的数据，如果小于结果是true。|
|`>`|比较符号左边的数据是否大于右边的数据，如果大于结果是true。|
|`<=`|比较符号左边的数据是否小于或等于右边的数据，如果小于或者等于结果是true。|
|`>=`|比较符号左边的数据是否大于或等于右边的数据，如果大于或者等于结果是true。|
|`!=`|不等于符号，如果符号两边的数据不相等，结果是true。|

- 比较运算符，是两个数据之间进行比较，运算结果都是布尔值`true`或者`false`。

```java
public static void main(String[] args) {
   System.out.println(1==1);  // true
   System.out.println(1<2);   // true
   System.out.println(3>4);   // false
   System.out.println(3<=4);  // true
   System.out.println(3>=4);  // false
   System.out.println(3!=4);  // true
}
```

## 4.4 逻辑运算符
|逻辑运算符包括：||
|---|---|
|`&&`短路与|1.两边都是true，结果是true <br>2.一边是false，结果是false<br>短路特点：符号左边是false，右边不再运算|
|`||`短路或|1.两边都是false，结果是false<br>2.一边是ture，结果是true<br>短路特点：符号左边是true，右边不再运算|
|`!`取反|1.!true结果是false<br>2.!false结果是true|

- 逻辑运算符，是用来连接两个布尔类型结果的运算符，运算结果都是布尔值`true`或者`false`

```java
public static void main(String[] args) {
    System.out.println(true && true);    // true
    System.out.println(true && false);   // false
    System.out.println(false && true);   // false，右边不计算
    
    System.out.println(false || false);  // false
    System.out.println(false || true);   // true
    System.out.println(true || false);   // true，右边不计算

    System.out.println(!false);  // true
}
```

## 4.5 三元运算符

**三元运算符格式：**

- 数据类型 变量名 = 布尔类型表达式 ？ 结果1：结果2

**三元运算服计算方式：**

- 布尔类型表达式结果是`true`，三元运算符整体结果为`结果1`，赋值给变量。
- 布尔类型表达式结果是`false`，三元运算符整体结果为`结果2`，赋值给变量。

```java
public static void main(String[] args) {
    int i = (i==2 ? 100 : 200);
    System.out.println(i);  // 200
    int j = (3<=4 ? 500 : 600);
    System.out.println(j);  // 500
}
```

## 4.6 常亮和变量的运算

* 下面的程序有问题吗？

```java
public static void main(String[] args){
    byte b1 = 1;
    byte b2 = 2;
    byte b3 = 1 + 2;
    byte b4 = b1 + b2;
    System.out.println(b3);
    System.out.println(b4);
}
```

**分析：**`b3 = 1 + 2`，`1`和`2`是常亮，为固定不变的数据，再编译的时候（javac编译器），已经确定了`1+2`的结果并没有超过byte类型的取值范围，可以赋值给变量`b3`，因此`b3 = 1 + 2`是正确的。反之，`b4 = b2 + b3`，`b2`和`b3`是变量，变量的值是可变化的，再编译的时候，编译器不能确定`b2+b3`的结果是什么，因此会将结果以`int`类型进行处理，所以`int`类型不能赋值给`byte`类型，因此编译失败。


