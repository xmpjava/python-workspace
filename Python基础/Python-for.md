1、`for` 循环是 Python 中的一种循环结构，用于按照指定的条件重复执行一段代码。`for` 循环的基本语法如下：

```python
for 变量名 in 序列:
    代码块
```

&emsp;&emsp;其中，`序列` 可以是一个列表、元组、集合、字符串、字典等 Python 中的可迭代对象，`变量名` 是每次循环迭代时取出的元素的名称。在循环体中，可以使用 `变量名` 来引用当前迭代的元素。

2、eg：

&emsp;&emsp;以下代码使用 `for` 循环遍历一个列表，并输出每个元素的值：

```python
fruits = ['apple', 'banana', 'orange']
for fruit in fruits:
    print(fruit)
```

3、运行结果为：

```
apple
banana
orange
```

4、在循环体中，可以使用 `break` 关键字来提前结束循环，也可以使用 `continue` 关键字来跳过当前迭代，继续进行下一次迭代。例如，以下代码使用 `break` 关键字在找到第一个质数时结束循环：

```python
for num in range(2, 10):
    for i in range(2, num):
        if num % i == 0:
            break
    else:
        print(num, '是一个质数')
```

运行结果为：

```
2 是一个质数
3 是一个质数
5 是一个质数
7 是一个质数
```

zj：在上面的代码中，我们使用了一个嵌套的 `for` 循环来遍历从 2 到 9 的整数，对于每个数，我们都用一个内部循环来判断它是否为质数。如果找到了第一个质数，就使用 `break` 关键字结束内部循环，并跳到外部循环的下一个数。如果内部循环完全迭代完成，说明当前数是一个质数，就会执行 `else` 语句块中的代码。