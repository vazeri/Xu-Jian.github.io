---
layout: post
title: Liquid-forloop
tags: Liquid
categories: Jekyll
---

**数组遍历**
~~~
{% for item in array %}
  {{ item }}
{% endfor %}
~~~
{: .language-ruby}

item 可以自定义名字. 只要循环里面和外面一致就可以.




## For loops 循环遍历数组：
~~~
{% for item in array %}    {{ item }}   {% endfor %}
~~~
{: .language-ruby}

每个循环周期，提供下面几个可用的变量：
~~~
forloop.length      # => length of the entire for loop
forloop.index       # => index of the current iteration
forloop.index0      # => index of the current iteration (zero based)
forloop.rindex      # => how many items are still left ?
forloop.rindex0     # => how many items are still left ? (zero based)
forloop.first       # => is this the first iteration ?
forloop.last        # => is this the last iteration ?
~~~
{: .language-ruby}

还有几个属性用来限定循环过程：
limit:int： 限制循环迭代次数  
offset:int： 从第n个item开始迭代  
reversed： 反转循环顺序


循环迭代 Hash散列，item[0]() 是键，item[1]() 是值：
~~~
{% for item in hash %}
  {{ item[0] }}: {{ item[1] }}
{% endfor %}
~~~
{: .language-ruby}


~~~
# array = [1,2,3,4,5,6]
{% for item in array limit:2 offset:2 %}
  {{ item }}
{% endfor %}
# results in 3,4

{% for item in collection reversed %}
  {{item}}
{% endfor %}

{% for post in site.posts limit:20 %}
  {{ post.title }}
{% endfor %}
~~~
{: .language-ruby}

允许自定义循环迭代次数，迭代次数可以用常数或者变量说明：

~~~
# if item.quantity is 4...
{% for i in (1..item.quantity) %}
  {{ i }}
{% endfor %}
# results in 1,2,3,4
~~~
{: .language-ruby}



