## 数据结构

> 栈

```Python
stack = [1,2,3,4]

stack.append(6)
res = stack.pop()
```

> Queue

python中的四种队列

```Python
from collections import deque
queue = deque(["A", "B", "C", "D"])

queue.append("E")
res = queue.popleft()
```

> 字典

遍历字典: https://zhuanlan.zhihu.com/p/33033288

```Python
dic = {"A":1, "B":2}

dic["C"] = 1 

dic["E"] #如果没有当前key会报错
>>> KeyError: 'E'
dic.get("E") #如果没有当前key会返回None
>>>None

del dic["A"]

lsit(dic.keys())
>>> ["A", "B"]

sorted(dic)
>>> ["A", "B"]

"A" in dic
>>> True

d1.update({'b' : 'foo', 'c' : 12})#和另一个链表融合
```

> 集合

**{ }** 或者 **set()**创建集合

注意：创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

```Python
basket = set()
basket = {"A", "B", "C"}
a = set('abracadabra')
>>>{'b', 'r', 'a', 'c', 'd'}

basket.add()
basket.remove(x) //不存在会报错
basket.discard(x) //不存在不会报错
```

## 列表

### 列表基本操作

```Python
全0:
    a = [0] * 26
    a = [0 for i in range(26)]
顺序增加:
    b = list(range(26))
```



### 列表初始化 \*号的bug

```python
a = [[0]*5]*5

a[0][0] = 3

#结果
[
    [3,0,0,0,0],
    [3,0,0,0,0],
    [3,0,0,0,0],
    [3,0,0,0,0],
    [3,0,0,0,0]
]
```

因为\*号可能底层的实现和浅拷贝有关

## 链表





## 细节

> class Solution //class 小写

> class内函数 + "self"

> 5/3 = 1.6666    5//3 = 1

> 排序

sorted返回新列表

```python
narr = sorted(arr)
```

sort()函数对原函数进行更改

```python
arr.sort()
```

> ::

```python
a[start:end:step]
a[1:3]
a[1:] 
a[:]
反转数组:a[::-1] //没有前两个参数 步长为-1
```

> left = 1, right = 2 会报错会把等号后面当成几句话

解决:

分两行

or

left, right = 1, 2 

```python
class Solution:
    def singleNumber(self, nums) -> int:
        dic = {}
        for i in range(len(nums)):
            if i in dic:
                dic[nums[i]] += 1
            dic[nums[i]] = 1
        for (key, val) in dic.items():
            if val == 1:
                return key
```



## \!r

https://docs.python.org/zh-cn/3/library/string.html#format-string-syntax

会先对值调用`repr()`

```python
return 'Node({!r})'.format(self._value)
```



## yield

https://blog.csdn.net/mieleizhi0522/article/details/82142856

https://python3-cookbook.readthedocs.io/zh_CN/latest/c04/p03_create_new_iteration_with_generators.html