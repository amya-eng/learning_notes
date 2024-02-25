# 学习顺序 🤯

> - 《python编程：从入门到实践》
> - 《Head-First Python》
> - 《“笨方法”学python3》
> - 《Python Cookbook》
> - 《Python 机器学习基础教程》
> - 《Fluent Python》
> - 《Python 编程》

## 《Python 编程： 从入门到实践》😉

---

- `变量`

变量命名：仅用小写和下划线。

变量`本质`: 指向特定的值。

---

- `字符串`

在字符串中使用变量：f'{varies1} {varies2}'

`更早版本`: ‘{} {}’.format(varies1, varies2)

`注意`：字符串里面可包含/n/t

`删除末尾空白`：str = str.rstrip() # 必须重新赋值

---

- `数`

`大整数`：可用_隔离开来，增加可读性

---

- `你一定会写出让别人觉得很漂亮的代码！`

不要企图编写完美无缺的代码，而是要先编写行之有效的代码，再决定是对其做进一步改
进，还是转而去编写新代码。

---

- `列表`

`索引`：左边从0右边从-1开始

`添加`：list.append(element)

`插入`：list.insert(index, element)

`删除`：del list[index]

`弹出`： list.pop()

`删除并返回`：list.pop(index)

`据值删除`：list.remove(value)

`排序`：list.sort(reverse=True) 降序

`临时排序`：sorted(list)

`反转`：list.reverse()

`长度`: len(list)

`遍历`: for item in list:

`range()函数`：左闭右开   for value in range(1, 6):

可以指定步长

默认从零开始

`转化为列表`：list(range(6))

`统计计算`： min(list), max(list), sum(list)

`列表解析`：squares = [value**2 for value in range(1, 11)]

`切片`：左闭右开

默认：一直到‘头’或一直到‘尾’

`复制`：list2 = list1[:] 无缺点

list2 = list1 缺点：一改全改

---

- `元组`

`不可变的列表`

`定义`：tuple1 = (1,2,3) &nbsp; tuple2 = (1,)

`修改元组`：将元组指向另一个元组

---

- `if`

`单个条件`：if express:

`多条件`： and, or

`包含`: in, not in

`if-elif-else`

---

- `字典`

`访问`：dir[key] #键不存在时报错

dir.get ( key, return_value if not exist [ 默认值：None ] )

`添加`: dir[key] = value

`创建`: dir = {}

`修改`: dir[key] = value

`删除`: del dir[key]

`定义格式`：

```python
favorite_language{
    'jen':'python',
    'sarah':'c',
}
```

`遍历`：

`键值对`: for key, value in dir.items():

`键`: for key in dir.keys():

dir.keys() 返回一个列表。

`值`：for value in dir.values():

`删除重复值`: set(dir.values())

---

`集合`

`创建`: set1 = {1,2,3} set2 = set()

`增加`： set1.add(4) set2.update([1,2,3,4])

`删除`： set1.remove(value)

---

- `嵌套`

经常在列表中包含大量字典，存储不同对象的信息。

字典中包含列表，描述同一对象的不同方面。

在字典中包含字典，描述不同对象的不同方面。

---

- `用户输入`

`input()`: massage = input('prompt words')

获取数值：age = int(input('prompt words))

`循环交互`:

```python
input_= ""
while input_ != 'quit':
    if input_:
        print(input_)
    input_ = input("please input your chose:")
```

`化简`：

```python
active = True
while active:
    input_ = input("please input your chose:")
    if input_ == 'quit':
        active = False
    else
        print(input_)
```

---

- `函数`

`定义与调用`：

```python
def func():
    print('hello, world!')
func()
```

`参数传递`：

关键字参数，位置参数。

定义时若有默认值，往后放。

`在函数中保留原列表`：

直接传入list, 在函数中的修改是永久的，一改全改的。
要想不改，传入list[:], 即原列表的副本。

`传递任意数量的实参`：

def func(arg1, arg2, *args):

函数将接收到的所有参数封装到`元组`args中。明确数量的参数放在前面。

`传递任意数量的关键字实参`:

def func(arg1, arg2, **args):

函数将接收到的所有关键字参数封装到`字典`args中。

---

`模块导入`：

使用as给模块指定别名

导入整个文件: import file

导入一个函数： from file import func1

不推荐使用from file import * : 因为容易导致函数名字重叠而覆盖函数。

---

- `类`：

面向对象编程是最有效的软件编写方法之一。可模拟十分逼真的显示场景。

`命名规则`：驼峰命名法，而不使用下划线。

`属性` 和 `方法`： 属性即self.变量， 方法即self.函数。

`创建类`：

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def sit(self):
        print(f"{self.name} is sitting.")
    def roll(self):
        print(f"{self.name} is rolling.")
```

`创建实例`： my_dog = Dog('dog', 3)

`修改属性的值`： my_dog.name = 'lili' (通过实例来修改)

通过方法来修改：

```python
class Dog:
    def __init__(self, name, age):
        ...
    def rename(self, new_name):
        self.name = new_name
```

my_dog.renmae('lili')

`继承`：

```python
class SmallDog(Dog):
    def __init__(self, name, age):
        """初始化父类的属性和方法。"""
        super().__init__(name, age)
        # 定义新属性
        self.sex = None
    def spark(self, word):
        """定义新方法"""
        print(f"{self.name} spark: {word}")
```

`重写`：
父类某些行为不符合子类。在子类中写一个名字一样的函数即可。

```python
def rename(self, new_name):
    print("small dog don't have name!")
```

`类作类的属性`: 使得类的属性在繁多的情况下更加有条理。

`类中可以再次定义类`

`导入`：

from car import ElectricCar, OilCar

---

- python标准库

`rand类函数`

`choice函数`

---

- `文件`
  
`读取文件`：

```python
with open('test.txt', 'r') as file:        # file：一个文件对象 with: 由python决定并安全关闭文件
    content = file.read()
print(content)
```

该程序打印出来的结果同文件一致。即文件最后如有换行，则打印否则不打印。
倘若要消除换行：print(content.rstrip())

`文件路径`：左撇 反斜杠

之所以不用斜杠，是因为：可能导致转义。

`逐行读取`：

```python
with open('test.txt', 'r') as f:
    for line in f:
        print(line)  # 这个line不包括/n
```

`逐行读取并形成列表`：

```python
with open('test.txt', 'r') as f:
    l = f.readlines()
print(l)
```

`写入文件`：

若'w'的对象存在，则先清空再写。

```python
with open('test.txt', 'w') as f:
    f.write('hello, world!')
```

`多行写入`：

file.write('hello, world!/n')
...

`附加模式`：
'a'
`读写模式`：
'r+'

---

- `异常`

使用错误避免崩溃：

```python
try:
    a = 5/0
except ZeroDivisionError:
    print("you can't divide by zero!")
else
    print(a)        # 如果try代码块成功执行，则执行else代码块
```

常见错误：`ZeroDivisionError`, `FileNotFoundError`

except块也常用：pass 实现静默失败。

`分析文本`：

`分隔符`：

```python
with open('test.txt', 'r') as f:
    content = f.read()
words = content.split()
```

`存储数据`：

json 是一种被多种语言使用的传输格式。

`存`

```python
import json
number = [1,2,3,4,5]
with open('test.json', 'w') as f:
    json.dump(number, f) # 存进文件后数据格式不变，依然是列表的形式
```

`取`

```python
with open('test.json', 'r') as f:
    numbers = json.load(f)
print(numbers)
```

可以在程序间共享数据。

---

- `重构`

写完能运行的程序后进行改进的过程。

将每一段代码按功能划分成不同的函数。

---

- `测试代码`

通过测试，可以让你相信，即使有更多人使用你的代码，也不会出错。

在用户发现错误前，找到它们。

`测试函数`：

`单元测试`， `测试用例`， `全覆盖`

istrianger.py

```python
def IsTrianger(a, b, c):
    if a + b > c and a + c > b and b + c > a:
        return True
    else:
        return False
```

test_istrianger.py

```python
import unittest # 导入模块
from istrianger import IsTrianger # 导入要测试的函数
class t_trianger(unittest.TestCase): # 创建用于测试的类
    def test_trianger(self): # 定义测试的函数：以test_开头的函数自动执行
        answer = IsTrianger(3,4,5)
        self.assertEqual(answer, True) # 对比结果

if __name__ == '__main__':
    unittest.main() # 如果这个文件被测试框架导入，则__name__ != '__main__', 文件不运行。
```

运行测试程序，即可。

若要运行多个测试，定义多个不同的test_...方法即可。

`测试类`

`unittest.TestCase`有很多的断言方法。

先创建类的实例，然后再以测试函数的方式测试类的行为。

`def setUp(self)方法`：可以创建各个test_方法均可以使用的一个实例或多个实例。

---

### 项目1

- 外星人入侵
