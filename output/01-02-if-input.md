
## if 条件判断

### 条件判断

1.单向判断: if 1.双向判断: if…else(不需加条件，表示其他)… 1.多向判断: if…elif…(else…)

**note**: …的内容需要缩进。

### if嵌套

作为嵌套，需在上一层if的基础上缩进。

``` r
include_graphics(here::here("figure/01-02-if.png"))
```

![](D:/python_tutoring/figure/01-02-if.png)<!-- -->

## input()函数

### 有问有答，有来有往

如果不输入，input()大门会一直等待被输入。

### 赋值后使用

``` python
number=input('请输入今天你吃的苹果数量：')
print(number)
```

**note**: 返回类型为str。若需要整数型，可以转换类型：int(input())。

### 交互沟通

``` python
#赋值：
number=input('请输入今天你吃的苹果数量：')

#进入嵌套式条件判断：
if int(number)<2:
  print('您今日的进食不过量。')
  if int(number)==0:
    print('您今日需要吃个苹果。')
  else:
    print('您今日吃的苹果刚刚好，么么哒。')
else:
  print('您再吃就会变成猪，会被杀掉的。')

print('反正无论你吃几个苹果，都改变不了你是猪的本质哈哈哈哈哈。判断完毕。')
```
