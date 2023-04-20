---
description: 并且、或者、绝不能
---

# 【修订中】005.逻辑条件

什么第三种好了，上节课我们帮助一个家庭实现了和睦，这节课我们作为美好生活创建者，来帮助另一个家庭实现和睦

{% hint style="info" %}
问题：小A同学马上就要期中考试了，可是他的心思不放在复习上，而是想去参加游戏公司举办的一个音乐会，他想和同学一起去上海看演出

请帮助小A同学编写一个Python程序，打印购票流程

回答：（提示见下面的自然语言描述的逻辑图）
{% endhint %}

如图：

```python
print('打开购票网站')

# 你实现的代码
```

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## 并且

上面的复习我们只使用了一个条件，但如果没有父母的支持，恐怕小A同学的上海之行只能是美好的希望

在Python里我们如何实现并且这种条件呢？

```python
tickets_avialable = True
parent_approved = True

if tickets_avialabe and parent_approved:
    print('有票并且父母支持')
```

and在英文里是并且的意思，它是一个逻辑操作符，只有在左右条件都成立的情况下才返回True

{% hint style="info" %}
问题：用Python打印 True and True，True and False，False and True，False and False看看都是什么结果

回答：<截图发送在微信群>
{% endhint %}

课堂练习

{% hint style="info" %}
问题：小A同学没有考虑同学是否一起有时间去，那么请帮助他增加这个条件，只有在<mark style="color:orange;">**有票并且同学有时间去并且父母们都同意**</mark>的情况下，才能开始快乐之旅

回答：<编写程序截图发送在微信群>
{% endhint %}

### 作业批注

最简单的写法其实是这样

```python
def tour(tickets_avialable, classmates_avialable, parents_approved):
    if tickets_avialable and classmates_avialable and parents_approved:
        print('集齐3颗龙珠，愿望达成！')
        
# 有票，同学有时间，父母们同意
print('理想情况：')
tour(True, True, True)

# 没票， 同学有时间，父母们同意
print('看运气：')
tour(False, True, True)
```

木木同学写的逻辑是这样的

```python
# 程序 005.01
def tour(tickets_avialable, classmates_avialable, parents_approved):
    if classmates_avialable and parents_approved:
        print('集齐2颗龙珠')
    if tickets_avialable:
        print('3颗龙珠，愿望达成！')
    else:
        print('没票哭唧唧')
        
# 有票，同学有时间，父母们同意
print('理想情况：')
tour(True, True, True)

# 没票， 同学有时间，父母们同意
print('看运气：')
tour(False, True, True)

# 有票，同学有时间，但父母们不同意
print('羡慕别人家孩子')
tour(True, True, False)
```

把不同的条件打印一下：

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption><p>情况</p></figcaption></figure>

第三种情况其实是去不了的，那么，到底为什么会出bug呢？

这就回到了第三课我们讲的缩进，条件语句里的代码块缩进对应着不同的条件执行，比如

```python
if first_condition:
    print('第一个条件满足')
    if second_condition:
        print('第一个条件满足并且第二个条件满足')
if third_condition:
    print('因为缩进发生了变化，这里的第一个条件无论满足与否，都会执行')
```

回到程序员笑话

```python
# 自然语言的模糊性会导致不同的程序员有不同的理解
def met_seller(flag, obj):
    if flag:
        print(f'遇到{obj}的')
    else:
        print(f'没遇到{obj}的')
    return flag
    
def buy_something(count, obj):
    print(f'买了{count}个{obj}')

# 遇到卖包子和西瓜的
if met_seller(True, '包子'):
    buy_something(3, '包子')
    if met_seller(True, '西瓜'):
        buy_something(1, '西瓜')
        
# 没遇到卖包子的，但遇到卖西瓜的
if met_seller(False, '包子'):
    buy_something(3, '包子')
    if met_seller(True, '西瓜'):
        buy_something(1, '西瓜')
        
# 没遇到卖包子的，但遇到卖西瓜的
if met_seller(False, '包子'):
    buy_something(3, '包子')
if met_seller(True, '西瓜'):
    buy_something(1, '西瓜')
```

后2个组合条件一模一样，但缩进不同，输出也不同，这是Python编程里常会出bug的地方，同学们一定要多注意：

{% hint style="info" %}
<mark style="color:yellow;">Python里的缩进会影响代码块处于不同的逻辑分支</mark>，所以木木同学的程序一旦条件组合发生变化，就会出问题（程序员其实多数情况下是在处理条件来保证确定性，而AI其实用概率的方式来输出结果，这就是人工智能不能完全取代程序员的原因）

问题：请同学们修改程序005.01，确保所有条件组合下都是没有bug的

回答：<使用自己的编辑器或 python.twinsant.com完成作业并截图>
{% endhint %}
