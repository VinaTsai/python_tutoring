
## 列表list1()

### 基本定义

1.用\[\]； 1.可同时包容不同类型的数据

``` python
list11=['小明', 18, 2.1]
print(list11)
```

### 提取元素

1.提取单个元素：偏移量（offset, 从0开始） 1.提取多个元素：**左右空，取到头；取左不取右**。

``` r
include_graphics(here::here("figure/01-03-offset.png"))
```

![](D:/python_tutoring/figure/01-03-offset.png)<!-- -->

``` python
#单个元素
students = ['小明', '小红', '小刚']
print(students[0])
#输出：小明

#多个元素
list1=[1,2,3,4,5]

print(list1[:])
# >> [1,2,3,4,5]
print(list1[2:])
# >> [3,4,5]
print(list1[:2])
# >> [1,2]
print(list1[1:3])
# >> [2,3]
```

### 增／删元素

1.增：

1)  list1.append():括号内只能放入一个元素 (one argument,
    不是索引，而是元素本身的内容)，该元素可以是列表或字典；也可以直接赋值。
2)  list1.extend():在某一列表末尾追加另一列表的值

`append()内只能放置一个元素，且作为一个单独的元素增加；extend()则是作为一个序列增加。`

``` python

list1=[1,2,3,4,5]
list1.append(6)
print(list1)
# >> [1,2,3,4,5,6]


list1.append(6,7)
print(list1)
# >> TypeError
#append() takes exactly one argument (2 given)


list1.append([7,8])
print(list1)
# >> [1,2,3,4,5,6,[7,8]]

#若是extend()
list1.extend([7,8])
print(list1)
# >> [1,2,3,4,5,6,7,8]

list1[7]=9
print(list1)
# >> [1,2,3,4,5,6,[7,8],9]
```

2.删：

1)  del:根据索引删除列表的元素，或者片段，或者整个列表（根据索引删除）。
2)  pop: A.pop(key), key可以是list1偏移量或者dictionary的key (`只能删除一个元素,
    a.pop()默认删除最后一个元素`)

<!-- end list -->

``` python
a=[1,2,3,4,5,6,7]
del a[0]
print(a)
# >> [2,3,4,5,6,7]

#等同于
a.pop(0)
print(a)

del a[2:4]
print(a)
# >> [2,3,6,7]

del a[:] 
print(a)
# >> [ ]
# del a[:] 等同于 del a
```

## 元组tuple()

1.基本定义：用()，若只有一个元素，以`,`结尾，比如tup1(30,) 1.元素提取：采用偏移量，tuple1\[0:\]
1.用法：支持嵌套，argument元素不可变，元素类型可以多样
1.`与list的区别在于，元组tuple的元素不可以变更`

## 字典

### 基本定义

1.用{}表示； 1.用**,**分割元素，有唯一的key，key和值用**:**隔开，值可以不唯一；

``` python
scores={'小明':90,'小红':98, '小刚':90}
print(scores)
print(len(scores))
# >>3
```

**note**:以上的key为’小明’，‘小红’，‘小刚’;len()返回列表或字典的长度。

### 提取元素

字典的索引：用key提取。

``` python
scores={'小明':90,'小红':98, '小刚':90}
print(scores['小明'])
# >> 90
```

### 增／删元素

1.增：dictionaryname\[key\]=value 1.删：del dictionaryname\[key\]

``` python
album={'Jay':'七里香','Jolin':'倒带'}
del album['Jay']
print(album)
# >> {'Jolin':'倒带'}

album['Jay']='安静'
print(album)
# >> {'Jolin':'倒带','Jay':'安静'}
print(album['Jay'])
# >> 安静
```

## 列表和字典的对比

|        |                          列表list\[1,2,3,4\]                          | 元组tuple(1,2,3,4) |                      字典dictionary{‘a’:1,‘b’:2}                      |
| :----: | :-----------------------------------------------------------------: | :--------------: | :-----------------------------------------------------------------: |
|  定位方式  |                           偏移量，list1\[0\]                            | 偏移量，tuple1\[0\]  |                          key, dict\[‘a’\]                           |
|  排列方式  |                               按顺序依次排列                               |     按顺序依次排列      |                               根据key排序                               |
| 增、删、修改 | list.\[new\_key\]=value, append(),extend(); del, pop(); key–\>value |      元素不可更改      | dict.\[new\_key\]=value, append(),extend(); del, pop(); key–\>value |
|  可嵌套   |                                  可                                  |        可         |                                  可                                  |

例子：

``` python
list11=[1,2,3,4,5]
print(list11[2])
# >> 3
dictionary1={'a':1,'b':1,'c':2}
print(dictionary1['a'])
# >> 1

list12=[5,4,3,2,1]
print(list11 == list12)
# >> false
dictionary2={'c':2,'b':1,'a':1}
print(dictionary1 == dictionary2)
# >> true
```

``` python
#add
list1=[1,2,3]
list1[3]=4
print(list1)
# >> [1,2,3,4]
dictionary={'a':1,'b':2}
dictionary['c']=3
print(dictionary)
# >> {'a':1,'b':2,'c':3}

#delete
del list1[3]
print(list1)
# >> [1,2,3]
del dictionary['a']
print(dictionary)
# >> {'b':2,'c':3}

#nest
#先取最外层的定位，再取第二层，...，剥洋葱式解法
numbers=[[1,2,3,4],[5,6,7,8]]
print(numbers[1][3])
# >> 8
groups={'first':{'a':1,'b':2,'c':3},'second':{'d':4,'e':5,'f':6}}
print(groups['second']['e'])
# >> 5
```
