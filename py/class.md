# 1. 类、对象、方法、函数和属性的区别和理解
- 类： 采用 Class 作为关键字进行定义的代码块，表示的是一种类别
- 对象： 实例化之后的类，对类中的形参进行了赋值，赋予其真正的含义或数值
- 方法： 使用 def 作为关键词，定义在类内的函数
- 函数： 使用 def 作为关键词，但是没有在类内进行定义，即 定义在类外
- 属性： 类内的称呼，其实就是类内的变量，同一个类内的不同方法内的变量都是这个类的属性，也就是这个类的变量


## 主要区别【定义和使用的位置】：
函数和方法都是函数，定义在类内叫做方法，定义在类外或者单独使用叫做函数；
属性和变量其实都是变量，定义在类内叫做属性，定义在类外或者单独使用叫做变量；

类 就像数学中的集合，也像一个大的函数，只不过这个函数里面有很多小的函数（这些小函数就是类内的方法），是一个抽象的概念，类只有实例化之后才具有意义，而实例化的类叫做对象，这里就变成了一个具体的实物。


```py
#!/usr/bin/python
# -*- coding: utf-8 -*-

class Person:
    num=1   # 类的属性，使用前需要对其进行声明，否则会报错
    print("您实例化了Person类，初始化的num=",num)
    def setName(self,name):
        self.name=name       # 第一个内部是类内部的属性
    def getName(self):
        return self.name
    def count(self):
        self.num+=1   # 使用之前已经对其进行了声明

```
解释：
首先，我们创建了一个 类，而这个类的名字叫做 Person，然后在这个 Person代码块 下，定义了 setName、 getName 和 count 三个函数，因为定义的这三个函数在代码块内，所有我们称之为 Person类 的 三个方法（分别是：setName方法、 getName 方法和 count 方法 ）
而对于 setName 方法下面的 变量name, count方法下面的变量num ，我们都可以称之为 类 Person 下面的属性，而类在进行使用时，我们需要对其进行实例化，具体实例化的例子如下：
```py
#!/usr/bin/python
# -*- coding: utf-8 -*-

# Person类的实例化
p=Person()    

# 调用setName和getName方法
p.setName("小猴")
print(p.getName())

# 不调用的时候，查看count方法的属num性
print("num="+str(p.num))

# 调用count方法时，查看count方法的属num性
p.count()
print("num="+str(p.num))

# 再次调用count方法时，查看count方法的属num性
p.count()
print("num="+str(p.num))

```

# 2.实例化
```py
class person:
    def __init__(self):
        print("Person created")
        self.name = "Unknown"

    def say_hello(self):
        print(f"Hello, my name is {self.name}")

person1 = person  # person1 现在是指向 person 类的引用
person2 = person()  # person2 是 person 类的一个实例

# 使用 person1 创建一个新的实例
new_person = person1()

# 使用 person2 调用方法
person2.say_hello()
```
### 第一种情况: person1 = person
在这种情况下，person1 被设置为指向 person 类本身的一个引用。这意味着 person1 变量现在是一个类对象，而不是一个类的实例。你可以使用 person1 来创建新的 person 类的实例，或者访问类的方法和属性（如果它们是类级别的）。

### 第二种情况: person2 = person()
这种方式创建了一个 person 类的新实例，并将其赋值给 person2。person() 调用了 person 类的默认构造函数（也就是 __init__ 方法），如果没有提供任何参数，则使用默认构造函数创建一个新实例。






































