# if elif else

```python
x=10
if x>10:
    print("x is greater than 10")
elif x==10:
    print("x is equalto 5")
elif x<10:
    print("x is smaller than 10")
else:
    print(f'x is {x}')
```

# 循环

```python
#1到11
for i in range(1, 11):
    print(i)
#1到11，2为步长
for i in range(1, 11, 2):
    print(i)
    my_list = ['a', 'b', 'c', 'd', 'e']
#结合列表
my_list = ['a', 'b', 'c', 'd', 'e']
for i in range(1, len(my_list) + 1):
        print(f"第 {i} 个元素是: {my_list[i - 1]}")
#拆分
for i in "python":
    print(i)
while True:
    print()
```

# print

```python
name="Alice"

age= 18

print("hello.","world")#使用逗号自动在中间加空格
print("hello"+"world")#用加号就没有空格了
print("world",end=' ')

print("my name is {},my age is {}".format(name,age))#使用占位符{}，format里的依次替换

print(f"my name is {name} and my age is {age}")#f-string格式

print("my name is %s and my age is %d" % (name,age))#类似于printf
```

# 常用函数

```python
greeting="hello world"


#增，拼接字符串
greeting+="how are u"
#hello worldhow are u


#删，移，改字符串
greeting=greeting.replace("how are u"," python")
#hello world python


#查找字符串
position=greeting.find("python")
print(position)
#12,空格也算距离


#全部转为大写
upgreeting=greeting.upper()
#HELLO WORLD PYTHON


#全部转为小写
lowergreeting=greeting.lower()
#hello world python


#首字母大写
titlegreeting=greeting.title()
#Hello World Python


#分割字符串（仅分割空格）
split_words=greeting.split(",")
#['hello world python']
split_words=greeting.split()
#['hello', 'world', 'python']


#检查开头 结尾（即是否以括号中为结尾开头），返回值为false ture
is_start=greeting.startswith("hello")
#Ture
is_end=greeting.endswith("world")
#False

#移除两边空白字符
strip_space=greeting.strip()
print(strip_space)


#字符串切片
print(greeting[3])#第四个字符

print(greeting[0:5])#左闭右开

print(greeting[1:])#从第二个到最后

print(greeting[:5])#从最开始到第5个前，01234位，共5个

print(greeting[-1])#取最后一位

print(greeting[1:-2])#从第二个取到倒数第二个之前

print(greeting[0:5:2])#将步长设为2

print(greeting[::-1])#倒叙

#and 类似于&&
bool_word = True and False
print(bool_word)#false

#not 类似于！
print(not bool_word)#true

```

# 列表

```python
#定义列表,中括号
fruits=["apple","banana","charry","orange"]

#增加元素
fruits.append("kiwi")
#['apple', 'banana', 'charry', 'orange', 'kiwi']

#删除
fruits.remove("banana")
#['apple', 'charry', 'orange', 'kiwi']


#改
fruits[0]="grapefriuts"
#['grapefriuts', 'charry', 'kiwi', 'orange']

#列表切片
#['grapefriuts', 'kiwi', 'charry', 'apple']
slice_fruit=fruits[1:4]#从第二个到第4个
#['kiwi', 'charry', 'apple']

slice_fruit2=fruits[:-1]#从0到-1（不包括）
#['grapefriuts', 'kiwi', 'charry']

#排序，字典序
sorted_fruits=sorted(fruits)
print(sorted_fruits)
#['charry', 'grapefriuts', 'kiwi', 'orange']
#反向排序
fruits.sort(reverse=True)
#['orange', 'kiwi', 'grapefriuts', 'charry']


```

# 字典

```python
#字典
person={"name":"john","age":30}

#添加键值对
person["gender"]="male"
#{'name': 'john', 'age': 30, 'gender': 'male'}

#删除键值对
del person["gender"]
#{'name': 'john', 'age': 30}

#修改
person["age"]=40
#{'name': 'john', 'age': 40}

#查看
print(person["name"])

#获取字典的所有键
keys=list(person.keys())
#['name', 'age']

#获取字典的所有值
values=list(person.values())
#['name', 'age'] ['john', 40]
```

# 集合

```python
#集合
odd_numbers={1,3,5,7}
even_numbers={2,4,6,8}

#增加元素
odd_numbers.add(9)
#{1, 3, 5, 7, 9}

#删除元素
odd_numbers.remove(9)#若9不存在，会报错（更严格）
odd_numbers.discard(9)#无论9是否存在，都不报错


#集合不支持修改元素

#查(检查是否有这个元素)
set=3 in odd_numbers
#返回值为False True
print(set)

#集合做差，减去共有的
set1={1,2,4,5}
set2={2,3,5,7}
different=set1-set2
print(different)
#{1, 4}
```

# 元组

```python
#元组(tuple)
point=(10,20)
#元组不可变

ae=(55)#int类型
aa=(33,)#tuple类型
print(type(aa))

#so,加长
new_point=point+aa
print(new_point)
#(10, 20, 33)
```

# 函数参数

```python
#函数
#这种叫必须参数
def say_hello(name):
    print(f"Hello {name}")

#调用
say_hello("Alice")

#默认参数，这里的，a=2,b=4，若传的参数不够，使用默认值
def add(a=2,b=4):
    return a+b
result = add(2)
result=add(b=4)#只给某几个传参
print(result)

#可变参数,会把传的参数封装成一个元组
def sum_numbers(*numbers):
    return sum(numbers)
print(sum_numbers(1,2,3,4))#函数的参数数量大小可更改、


#字典做参数
def inf(**user):
    for key, value in user.items():
        print(f"{key}={value}")
inf(name="Alice",age=25,city="Chicago")
'''name=Alice
age=25
city=Chicago
'''


#参数顺序，混合使用参数时，注意以该顺序
def func(a, b=2, *args,**kwargs):
    print(f"位置参数 a 的值: {a}")
    print(f"默认参数 b 的值: {b}")
    print(f"可变位置参数 args 的值: {args}")
    print(f"字典参数name为 ：{kwargs}")

# 调用函数
func(1, 3, 4, 5, 6,namne="Alice")
'''a 是位置参数，调用函数时第一个值 1 会赋给 a；b 是默认参数，调用时传入的第二个值 3 会覆盖默认值；
而剩下的 4, 5, 6 会被 *args 收集起来，形成一个元组 (4, 5, 6)'''
```

