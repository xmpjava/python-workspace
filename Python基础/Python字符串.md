## 字符串

所谓**字符串**，就是由零个或多个字符组成的有限序列，一般记为。在Python程序中，如果把单个或多个字符用单引号或者双引号包围起来，就可以表示一个字符串。

```Python
s1 = 'hello, world!'
s2 = "hello, world!"
# 以三个双引号或单引号开头的字符串可以折行
print(s1, s2, end='')
```

可以在字符串中使用`\`（反斜杠）来表示转义，也就是说`\`后面的字符不再是它原来的意义，例如：`\n`不是代表反斜杠和字符n，而是表示换行；而`\t`也不是代表反斜杠和字符t，而是表示制表符。所以如果想在字符串中表示`'`要写成`\'`，同理想表示`\`要写成`\\`。可以运行下面的代码看看会输出什么。

```Python
s1 = '\'hello, world!\''
s2 = '\n\\hello, world!\\\n'
print(s1, s2, end='')
```

在`\`后面还可以跟一个八进制或者十六进制数来表示字符，例如`\141`和`\x61`都代表小写字母`a`，前者是八进制的表示法，后者是十六进制的表示法。也可以在`\`后面跟Unicode字符编码来表示字符，例如`\u9a86\u660a`代表的是中文“骆昊”。运行下面的代码，看看输出了什么。

```Python
s1 = '\141\142\143\x61\x62\x63'
s2 = '\u9a86\u660a'
print(s1, s2)
```

如果不希望字符串中的`\`表示转义，可以通过在字符串的最前面加上字母`r`来加以说明

```Python
s1 = r'\'hello, world!\''
s2 = r'\n\\hello, world!\\\n'
print(s1, s2, end='')
```

## 双色球选号

```Python
from random import randrange, randint, sample


def display(balls):
    """
    输出列表中的双色球号码
    """
    for index, ball in enumerate(balls):
        if index == len(balls) - 1:
            print('|', end=' ')
        print('%02d' % ball, end=' ')
    print()


def random_select():
    """
    随机选择一组号码
    """
    red_balls = [x for x in range(1, 34)]
    selected_balls = []
    selected_balls = sample(red_balls, 6)
    selected_balls.sort()
    selected_balls.append(randint(1, 16))
    return selected_balls


def main():
    n = int(input('机选几注: '))
    for _ in range(n):
        display(random_select())


if __name__ == '__main__':
    main()
```
