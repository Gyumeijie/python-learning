# Object comparisons: "is" vs "=="

This is about the difference in meaning between **equal** and **indentical**. And this difference is crucial to understanding how Python's **is** and **==** operators behave.


```python
>>> a = [1, 2, 3]
>>> b = a

>>> a == b
True

>>> a is b
True
```


```python
>>> c = list(a)
>>> c
[1, 2, 3]

>>> a == c
True

>>> a is c
False
```

So, to recap, let's try and break down the difference between **is** and **==** into two short definitions: 

  - An **is** expression evaluates to ***True*** if two variables point to the same(identical) object.
  > `Address` is concerned
  
  - An **==** expression evaluates to **True** if the objects referred to by the variables are equal(have the same contents).
  > `Content` is concerned
