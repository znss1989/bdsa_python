# 映射/哈希表

在Python中内置类型dict（即dictionary字典）可以用以实现哈希表，是一种键值对的结合，故与集合（set）一样采用花括弧`{}`（由于其引入早于集合，故`{}`初始化dict而非set）来表示其字面值，可认为能够在常量时间`O(1)`内查询特定键（key）所对应值（value）。其字面值由花括弧包围，并且由逗号`,`分隔的键值对`key: value`所构成。

哈希表dict的初始化有如下两种形式：

```python
my_dict = dict()
my_map = {}
print(len(my_map)) # 0
```

`len`可以返回哈希表中现有元素个数。

添加新的键值对和更新某键的值，有相同的方式，如：

```python
my_map['score'] = 70
my_map['score'] = 100
```

检查哈希表中是否已有某键可以用`in`操作符，如果有的话，可以通过`d[key]`返回对应值，否则抛出KeyError异常。删除操作`del`亦类似。

```python
if 'score' in my_map:
	print(my_map['score'])
	del my_map['score']
```

如果不想检查元素存在与否而直接查得结果，可以用该类的`get(key[, default])`方法，这样如果表中没有所查询的键，则返回`default`值（其默认为`None`）。

dict类型的`keys()`， 'values()'和'items()'可以分别返回哈希表的所有键，所有值和所有键值对以供遍历（即可执行iter()方法）。比如：

```python
for k, v in my_map.items():
    print('{}: {}'.format(k, v))
```

dict还可以用`pop(key[, default])`同时返回一个键对应值，并删除对应键值对。如果查询失败则抛出KeyError异常。

具体可参见[文档](https://docs.python.org/3/library/stdtypes.html#dict-views)。