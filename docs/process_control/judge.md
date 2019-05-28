# 一、判断语句

## 1.1 判断语句1--if

- if 语句第一种格式：if

``` linenums="1"
if(关系表达式) {
    语句体;
}
```

+ 执行流程
    - 首先判断关系表达式看其结果是true还是false
    - 如果是true就执行语句体
    - 如果是false就不执行语句体

```flow
st=>start: Start:>http://www.google.com[blank]
e=>end:>http://www.google.com
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?:>http://www.google.com
io=>inputoutput: catch something...

st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
```

```flow
st=>start: 开始
cond=>condition: 条件表达式
io=>inputoutput: 语句体
st->cond
cond(true)->io
```


--8<-- "links.txt"

--8<-- "uml.txt"
