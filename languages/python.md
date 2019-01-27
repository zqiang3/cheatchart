```python
# os
os.environ['PATH']
# dir
dir(xxx)

getattr(o, key)
hasattr(o, key)

```
## 格式限定符

format有着丰富的的“格式限定符”（语法是{}中带:号） 

```python
# 填充与对齐
# ^、<、>分别是居中、左对齐、右对齐，后面带宽度
# :号后面带填充的字符，只能是一个字符，不指定的话默认是用空格填充
print '{:>8}'.format('zhang')
print '{:0>8}'.format('zhang')
print '{:p>8}'.format('zhang')

# 精度常跟类型f一起使用
print '{:5.2f}'.format(1.4578)

# b、d、o、x分别是二进制、十进制、八进制、十六进制
print '{:b}'.format(15)
print '{:o}'.format(15)
print '{:x}'.format(15)
print '{:d}'.format(15)

# 用逗号还能用来做金额的千位分隔符
print '{:,}'.format(1234567)
```



# set

```python
a = t | s  # t和s的并集
a = t & s  # t和s的交集
c = t - s  # 求差集（项在t中，但不在s中）
d = t ^ s  # 对称差集
```

## 排序

```python
sort(...)
    L.sort(cmp=None, key=None, reverse=False)

sorted(...)
    sorted(iterable, cmp=None, key=None, reverse=False)
# key 是带一个参数的函数, 用来为每个元素提取比较值. 默认为 None, 即直接比较每个元素

L.sort()
y = sorted(L)

# 对tuple组成的列表排序
students = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10),]
sorted(students, key=lambda student: student[2])

# 对字典组成的列表排序
drive_list = [
{'uid': 20085399, 'drive_id': 1034, 'use': True, 'expire': False, 'end_time': 200000},
{'uid': 20085399, 'drive_id': 1035, 'use': False, 'expire': False, 'end_time': 300000},
]

drive_list = sorted(drive_list, key=lambda x: (x['use'], x['expire'], x['end_time']), reverse=True)
print drive_list

# 对字典排序
dic = {'a':31, 'bc':5, 'c':3, 'asd':4, 'aa':74, 'd':0}
dict= sorted(dic.iteritems(), key=lambda d:d[0]) d[0]表示字典的键
```

# repr
'p is {0!r}'.format(p)  # !r格式化代码指明输出使用repr()来代替默认的str()

# eval
eval(repr(o))
