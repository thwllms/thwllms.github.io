---
layout:     post
title:      enumerate() and dict.items()
date:       2015-07-12 15:39:00
summary:    Handy Python tidbits.
categories: blog
---

_Updated 8 Mar 2019._

`enumerate` is a handy built-in Python function that sometimes gets overlooked.
It's not life-changing, but it makes things a little cleaner and more concise. 

Let's say you want to loop through a list, but you want to access both the list
items *and* the index value for each item. Here's one way to do it:

{% highlight python %}
>>> my_list = ['a', 'b', 'c']
>>> for index in range(0, len(my_list)):
...     item = my_list[index]
...     print(index, item)
...
0 a
1 b
2 c
{% endhighlight %}

However, you can do the same thing a little more gracefully with `enumerate`:

{% highlight python %}
>>> for index, item in enumerate(my_list):
...     print(index, item)
{% endhighlight %}

`items` is similar to `enumerate`, but for dictionaries. If you were doing
this...

{% highlight python %}
>>> my_dict = {0:'a', 1:'b', 2:'c'}
>>> for key in my_dict.keys():
...     value = my_dict[key]
...     print(key, value)
...
0 a
1 b
2 c
{% endhighlight %}

...try this instead:

{% highlight python %}
# Python 3
>>> for key, value in my_dict.items():
...     print(key, value)
{% endhighlight %}

`items` doesn't exist in Python 2.7, but `iteritems` does the same thing:

{% highlight python %}
# Python 2.7
>>> for key, value in my_dict.iteritems():
...     print(key, value)
{% endhighlight %}

Happy coding!
