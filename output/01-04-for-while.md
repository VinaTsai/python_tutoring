
## for…in…循环语句

`循环：执行重复性或规律性的任务`

1.格式：冒号；缩进；重复执行的job 1.可以作为i的取值：string、list、dictionary（int、float不可以）；

``` python
for i in [1,2,3,4]:
  print(i*5)
#output：5 10 15 20

for i in 5：
  print(i)
# >> error

for i in 5.2:
  print(i)
# >> error

dic={'a':'1','b':'3','c':'5'}
for i in dic:
  print(dic[i])
# >>1 3 5
#这里的i是dic的key，按顺序提取。

for i in 'abc'
  print(i)
# >> a b c
#逐字读取

for i in 'abc'
  print(i)
print(i)
# >> a b c c
#未缩进的print执行的是i在最后的取值，也就是在执行完for循环后，当前的i值。
```

error的部分可以改为：

``` python
for i in str(5)：
  print(i)
# >> 5

for i in str(5.2):
  print(i)
# >> 5 . 2
#逐字读取
```

### 与range()函数配合

1.range(x): 0 \~ x-1 的整数序列; 1.range(a,b):a,…,b-1 （与偏移量一致，取头不取尾）
1.range(a,b,c):a,…,b-1 每个数间隔为c (不填时默认为1)

``` python
for i in range(3):
  print(i)
# >> 0,1,2

for i in range(3):
  print('我真优秀！')
# >> 我真优秀！ 我真优秀！ 我真优秀！
#可以作为重复执行的次数。

for i in range(0,10,3):
  print(i)
# >> 0 3 6 9
```

## while循环

1.先赋值，后进条件，最后执行重复job；

``` python
a=0
while a<5:
  a=a+1
  print(a)
# >> 1 2 3 4 5
```

``` python

man = ''  # 注：''代表空字符串
while man != '有':  #注：!=代表不等于
  man = input('有没有愿意为小龙女死的男人？没有的话就不能出古墓。')
print('小龙女可以出古墓门下山啦~')

#以上表示，如果input部分一直没有出现'有'，则会一直执行while的job；当出现了'有'，就不进入while循环，而是直接执行下一句print。
```

## for…in…和while…异同点

``` r
include_graphics(here::here("figure/01-04-for-while.png"))
```

![](D:/python_tutoring/figure/01-04-for-while.png)<!-- -->

`已知循环次数用for, 未知循环次数用while。`
