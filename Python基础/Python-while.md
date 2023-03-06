while 循环是一种重复执行代码块直到满足特定条件的方法。例如：

```python
i = 1
while i < 6:
  print(i)
  i += 1
```

此代码将打印从 1 到 5 的数字，每行一个。

Python`while`语句用于重复执行一段代码，只要某个条件为真。`while`Python 语句的基本语法是：

```python
while condition:
    # execute statements while condition is true
```

这里，`condition`是在循环的每次迭代之前计算的表达式。如果条件为真，则执行循环内的语句。语句执行后，再次评估条件，循环继续直到条件为假。

例如，以下代码使用`while`循环打印前 10 个正整数：

```python
i = 1
while i <= 10:
    print(i)
    i += 1
```

此代码将变量初始化`i`为 1，然后进入循环。只要`i`小于或等于 10，循环就会继续。在循环内，`i`打印当前值，然后使用`+=`运算符将其递增 1。循环继续，直到`i`大于 10，此时循环退出。



while 语句时还有另外两个重要的命令 continue，break 来跳过循环，continue 用于跳过该次循环，break 则是用于退出循环，此外"判断条件"还可以是个常值，表示循环必定成立，具体用法如下：

continue 和 break 用法

```python
# continue 和 break 用法
 
i = 1
while i < 10:   
    i += 1
    if i%2 > 0:     # 非双数时跳过输出
        continue
    print i         # 输出双数2、4、6、8、10
 
i = 1
while 1:            # 循环条件为1必定成立
    print i         # 输出1~10
    i += 1
    if i > 10:     # 当i大于10时跳出循环
        break
```

