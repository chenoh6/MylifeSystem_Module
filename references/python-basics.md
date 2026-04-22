# Python 代码 → 自然语言映射表

## 一、变量与数据类型

### 1. 变量赋值

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `x = 5` | 把数字 5 存入变量 x |
| `name = "Alice"` | 把字符串 "Alice" 存入变量 name |
| `is_valid = True` | 把布尔值 True（真）存入变量 is_valid |
| `data = None` | 变量 data 为空值（未定义） |
| `a, b = 1, 2` | 同时给 a 赋 1，b 赋 2 |
| `x += 1` | 把 x 当前值加 1 再存回 x |
| `x = x + 1` | 同上：读取 x，加 1，再存回 x |

### 2. 常见数据类型

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `int` | 整数类型：1, 2, 100 |
| `float` | 小数类型：1.5, 3.14 |
| `str` | 字符串类型：文本 |
| `bool` | 布尔类型：True / False |
| `list` | 列表类型：[ ]，有序可重复 |
| `dict` | 字典类型：{键: 值}，键值对 |
| `tuple` | 元组类型：( )，有序不可改 |
| `set` | 集合类型：{ }，无序不重复 |

---

## 二、函数定义

### 1. 函数声明模式

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `def hello():` | 定义一个叫 hello 的函数，无参数 |
| `def hello(name):` | 定义函数 hello，接收一个叫 name 的输入 |
| `def add(a, b):` | 定义函数 add，接收 a 和 b 两个输入 |
| `def add(a, b=10):` | 定义函数 add，a 必须传，b 有默认值 10 |
| `def add(*args):` | 定义函数 add，接收任意数量的位置参数 |
| `def config(**kwargs):` | 定义函数 config，接收任意数量的命名参数 |

### 2. 函数返回值

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `return result` | 把 result 作为执行结果输出 |
| `return` | 返回空（相当于返回 None） |
| `return a, b` | 同时返回多个值（组成元组） |

### 3. 完整函数翻译

```python
def add(a, b):
    return a + b
```
**翻译**：定义函数 `add`，把 `a` 和 `b` 传进去，做加法运算，然后返回结果。

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"
```
**翻译**：定义函数 `greet`，接收 `name` 和 `greeting` 两个输入，其中 `greeting` 默认值是 "Hello"。函数返回 "Hello, {名字}!" 的格式化字符串。

```python
def process(*args, **kwargs):
    print(f"位置参数: {args}")
    print(f"命名参数: {kwargs}")
```
**翻译**：定义函数 `process`，用 `*args` 收集所有位置参数成元组，用 `**kwargs` 收集所有命名参数成字典，然后打印出来。

---

## 三、流程控制

### 1. 条件判断

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `if x > 0:` | 如果 x 大于 0 |
| `elif x == 0:` | 否则如果 x 等于 0 |
| `else:` | 以上都不满足 |
| `if a and b:` | 如果 a 和 b 同时成立 |
| `if a or b:` | 如果 a 或 b 任一成立 |
| `if not a:` | 如果 a 不成立 |

### 2. 完整条件翻译

```python
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
else:
    grade = "C"
```
**翻译**：如果 score 大于等于 90，grade 设为 "A"；否则如果大于等于 80，grade 设为 "B"；前面都不满足则 grade 设为 "C"。

---

### 3. 循环遍历

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `for i in range(5):` | 从 0 数到 4，每次取出一个 i |
| `for item in items:` | 从 items 集合中逐个取出 item |
| `for i, v in enumerate(items):` | 遍历 items，同时获取索引 i 和值 v |
| `for k, v in dict.items():` | 遍历字典的每个键值对 |
| `while x > 0:` | 当 x 大于 0 时，持续循环 |
| `break` | 立即跳出整个循环 |
| `continue` | 跳过本次循环，继续下一次 |

### 4. 完整循环翻译

```python
for item in items:
    print(item)
```
**翻译**：从 items 集合中逐个取出元素，每次取出的元素命名为 `item`，然后执行打印操作。

```python
for i in range(10):
    if i == 5:
        break
```
**翻译**：从 0 数到 9，每当数到的数字等于 5 时，立即停止循环。

```python
for i, name in enumerate(students):
    print(f"{i+1}. {name}")
```
**翻译**：遍历 students 列表，同时得到序号 i（从0开始）和内容 name，然后打印 "序号. 名字" 的格式。

---

## 四、类定义

### 1. 类声明模式

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `class User:` | 定义一个叫 User 的类（对象模板） |
| `class User(Animal):` | 定义 User 类，继承自 Animal |
| `def __init__(self, name):` | 创建对象时自动调用的初始化方法 |
| `self.name = name` | 把 name 存入这个对象的 name 属性 |
| `def method(self):` | 定义类的一个方法（行为） |
| `self.method()` | 在类内部调用自身的方法 |

### 2. 完整类翻译

```python
class User:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def say_hello(self):
        print(f"Hello, I'm {self.name}")
```
**翻译**：
- `class User`：定义一个叫 User 的类（用户对象的模板）
- `__init__`：创建 User 对象时自动执行，把 name 和 age 存进对象的属性
- `self.name / self.age`：对象身上的变量，叫属性
- `say_hello`：定义一个叫 say_hello 的行为/方法
- `self.name`：在方法中引用当前对象自身的 name 属性

```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        print("汪汪！")
```
**翻译**：Animal 是父类（基类），Dog 继承 Animal。Dog 重新定义了自己的 speak 方法，"汪汪叫"。

---

## 五、列表/字典操作

### 1. 列表操作

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `items.append(x)` | 把 x 添加到列表末尾 |
| `items.insert(0, x)` | 在索引 0 位置插入 x |
| `items.remove(x)` | 从列表中删除第一个 x |
| `items.pop()` | 弹出并返回列表最后一个元素 |
| `items[0]` | 取列表的第一个元素 |
| `items[-1]` | 取列表的最后一个元素 |
| `items[1:3]` | 切片：取索引 1 到 3（不含3）的元素 |
| `len(items)` | 获取列表长度（元素个数） |

### 2. 字典操作

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `d["name"]` | 读取字典中 name 对应的值 |
| `d["name"] = "Alice"` | 把 name 设为 "Alice" |
| `d.keys()` | 获取所有键 |
| `d.values()` | 获取所有值 |
| `d.items()` | 获取所有键值对 |
| `d.get("name", "匿名")` | 获取 name，不存在则返回"匿名" |

### 3. 推导式模式

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `[x*2 for x in items]` | 从 items 中取出每个 x，乘以2，组成新列表 |
| `[x for x in items if x>0]` | 从 items 中挑出大于0的 x，组成新列表 |
| `{k: v for k, v in d.items()}` | 遍历字典，组成新字典 |
| `{x for x in items}` | 从 items 提取唯一值，组成集合 |

### 4. 推导式翻译

```python
squares = [x**2 for x in range(10)]
```
**翻译**：从 0 到 9 取每个数字 x，计算 x 的平方，组成一个新列表 squares。

---

## 六、异常处理

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `try:` | 尝试执行这段代码 |
| `except ValueError:` | 如果发生 ValueError 错误 |
| `except (ValueError, TypeError):` | 如果发生 ValueError 或 TypeError |
| `except Exception as e:` | 捕获所有异常，并用 e 代表错误对象 |
| `else:` | try 里没出错时执行 |
| `finally:` | 不管有没有出错，最后都执行 |
| `raise ValueError("无效")` | 主动抛出一个 ValueError 异常 |

### 完整异常翻译

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("不能除以零")
finally:
    print("计算结束")
```
**翻译**：尝试执行 10 除以 0，如果发生除零错误，打印提示；无论是否出错，最后都打印 "计算结束"。

---

## 七、文件操作

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `open("file.txt", "r")` | 打开 file.txt 用于读取 |
| `open("file.txt", "w")` | 打开 file.txt 用于写入（会清空） |
| `open("file.txt", "a")` | 打开 file.txt 用于追加 |
| `with open(...) as f:` | 自动管理文件开关的读取/写入 |
| `f.read()` | 读取文件的全部内容 |
| `f.readlines()` | 读取文件，每行作为一个元素 |
| `f.write("text")` | 向文件写入文本 |

### 文件翻译

```python
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()
```
**翻译**：打开 data.txt 用于读取，使用 UTF-8 编码，把文件对象命名为 f，读取全部内容存入 content，读取完毕后自动关闭文件。

---

## 八、导入模块

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `import os` | 导入 os 模块（操作系统功能） |
| `import sys` | 导入 sys 模块（系统相关） |
| `from datetime import datetime` | 从 datetime 模块导入 datetime 类 |
| `from pathlib import Path` | 从 pathlib 导入 Path |
| `import numpy as np` | 导入 numpy 模块，并起个别名叫 np |
| `os.path.join()` | 调用 os 模块里的 path 子模块的 join 函数 |

---

## 九、常用内置函数

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `print(x)` | 把 x 打印/输出到屏幕 |
| `len(x)` | 获取 x 的长度或元素个数 |
| `range(5)` | 生成 0, 1, 2, 3, 4 的数字序列 |
| `enumerate(items)` | 遍历 items，同时得到索引和值 |
| `zip(a, b)` | 把 a 和 b 打包成元组列表 |
| `sorted(items)` | 对 items 排序后返回新列表 |
| `reversed(items)` | 反转 items 的顺序 |
| `sum(items)` | 对 items 求和 |
| `min(items)` / `max(items)` | 求最小值 / 最大值 |
| `abs(x)` | 求 x 的绝对值 |
| `round(x)` | 对 x 四舍五入 |
| `type(x)` | 查看 x 的数据类型 |
| `isinstance(x, int)` | 检查 x 是否为整数类型 |
| `input("请输入:")` | 显示提示，让用户输入内容 |
