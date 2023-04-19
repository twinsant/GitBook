---
description: 并且、或者、绝不能
---

# 【修订中】005.逻辑条件

好了，上节课我们帮助一个家庭实现了和睦，这节课我们作为美好生活创建者，来帮助另一个家庭实现和睦

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
