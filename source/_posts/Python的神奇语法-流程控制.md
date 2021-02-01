---
title: Python的神奇语法-流程控制
date: 2021-01-30 14:53:20
cover_image:  /img/python_yufa.png
cover_image_alt: Python的神奇语法
---

## 基本语法

python是没有大括号划分作用域，python用的是缩进来控制，所以要非常注意缩进的书写。

### if 

python的if语句的基本形式是：

``` python
if 判断条件：
    执行语句……
else：
    执行语句……
```

在python里`else if`是`elif ` ：

``` python
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```

而且python 是没有`switch`语句的。

基本用例：

``` python
num = 5     
if num == 3:            # 判断num的值
    print ('boss' )       
elif num == 2:
    print ('user')
elif num == 1:
    print ('worker')
elif num < 0:           # 值小于零时输出
    print ('error')
else:
    print ('roadman')     # 条件均不成立时输出
```

python里的 `&&` 和 `||`是 `and` 和 `or`，python用英文来代替。（这个我觉得很不错，少敲了shift）

``` python
num = 9
if num >= 0 and num <= 10:    # 判断值是否在0~10之间
    print ('hello')
# 输出结果: hello
 
num = 10
if num < 0 or num > 10:    # 判断值是否在小于0或大于10
    print ('hello')
else:
    print ('undefine')
# 输出结果: undefine
 
num = 8
# 判断值是否在0~5或者10~15之间
if (num >= 0 and num <= 5) or (num >= 10 and num <= 15):    
    print ('hello')
else:
    print ('undefine')
# 输出结果: undefine
```

也可以在同行使用if：

``` python
var = 100 
 
if ( var  == 100 ) : print ("变量 var 的值为100")
 
print ("Good bye!")
#输出
#变量 var 的值为100
#Good bye!
```

### while

Python while执行过程

![img](https://s3.ax1x.com/2021/01/30/ykismD.gif)

基本形式：

``` python
    count = 0
    while (count < 9):
        print ('The count is:', count)
        count = count + 1

    print ("Good bye!")
```

运行结果:

``` python
The count is: 0
The count is: 1
The count is: 2
The count is: 3
The count is: 4
The count is: 5
The count is: 6
The count is: 7
The count is: 8
Good bye!
```

Python也是可以用continue和break来跳过循环的。

``` python
# continue 和 break 用法
i = 1
while i < 10:   
    i += 1
    if i%2 > 0:     # 非双数时跳过输出
        continue
    print (i)         # 输出双数2、4、6、8、10
 
i = 1
while 1:            # 循环条件为1必定成立
    print (i)         # 输出1~10
    i += 1
    if i > 10:     # 当i大于10时跳出循环
        break
```

循环使用 else 语句

在 python 中，while … else 在循环条件为 false 时执行 else 语句块：

``` python
    count = 0
    while count < 5:
        print(count, " is  less than 5")
        count = count + 1
    else:
        print(count, " is not less than 5")
```

类似 if 语句的语法，如果你的 while 循环体中只有一条语句，你可以将该语句与while写在同一行中。

``` python
    flag = 1

    while (flag): print('Given flag is really true!')

    print ("Good bye!")
```

### for

for的基本语法

```python
for iterating_var in sequence:
   statements(s)
```
实例：

```python
for letter in 'Python':  # 第一个实例
    print('当前字母 :', letter)
fruits = ['banana', 'apple', 'mango']
for fruit in fruits:  # 第二个实例
    print('当前水果 :', fruit)
print( "Good bye!")
```

输出

``` python
当前字母 : P
当前字母 : y
当前字母 : t
当前字母 : h
当前字母 : o
当前字母 : n
当前水果 : banana
当前水果 : apple
当前水果 : mango
Good bye!
```

另外还有通过索引遍历：

``` python
fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
   print ('当前水果 :', fruits[index])
print ("Good bye!")
```

输出：

```python
当前水果 : banana
当前水果 : apple
当前水果 : mango
Good bye!
```
在 python 中，for … else 表示这样的意思，for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。
```python
for num in range(10, 20):  # 迭代 10 到 20 之间的数字
    for i in range(2, num):  # 根据因子迭代
        if num % i == 0:  # 确定第一个因子
            j = num / i  # 计算第二个因子
            print('%d 等于 %d * %d' % (num, i, j))
            break  # 跳出当前循环
    else:  # 循环的 else 部分
        print(num, '是一个质数')
```

输出:

```python
10 等于 2 * 5
11 是一个质数
12 等于 2 * 6
13 是一个质数
14 等于 2 * 7
15 等于 3 * 5
16 等于 2 * 8
17 是一个质数
18 等于 2 * 9
19 是一个质数
```