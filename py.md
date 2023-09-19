

# 1.输出函数print

```python
#输出到控制台
print(11) #直接输出数字
print(3+1) #结果输出4，表达式输出结果
print('hello') #输出字符串需要加单引号或者双引号
print(”hello“)
print('hello','world') #不换行输出
#输出到文件内
fp=open('D:/text.txt','a+') #a+在文件后面追加
print('hello',file=fp) #file=fp才会保存在文件中
fp.close()#关闭文件
```

# 2.转义字符与原字符

```python
print('hello\nworld')#\n换行
print('hello\tworld')#\t补空格对齐四字节
print('helloooo\tworld')
print('hello\rworld') #\r回车，输出world会覆盖hello
print('hello\bworld')#\b退格，会覆盖掉 o
print('http:\\\\www.baidu.com')#每两个斜线只会输出一个斜线
print('老师说:\'大家好\'') # '(单引号)前加\，才会输出，否则报错
#在输出前加r或R会使转义字符失效
print(r'hello\nworld')
print(r'hello\nworld\\')#输出结尾不能是单个反斜杠
```

# 3.二进制与字符编码

- 8bit=1Byte
- print(chr(0b100111001011000)) #输出二进制对于的字符，0b表示后面是二进制
- print(ord('乘'))#输出'乘'的十进制编码

# 4.标识符和保留字

- 标识符，即命的名字


```python
import keyword
print(keyword.kwlist) # 输出保留字
```

# 5.变量

![image-20230910183844628](.\image-20230910183844628.png)

```python
'''    三部分组成，标识，类型，值    
变量存储的是一个对象的引用'''
name='玛丽亚' #直接赋值
print(name) #print变量名称
print('标识',id(name))
print('类型',type(name))
print('值',name)
#多次赋值后后变量名会指向新的空间
name='玛丽' #直接赋值
print('标识',id(name))
print('类型',type(name))
print('值',name)
```

## 数据类型

### 整数int

```python
#可以表示正数、负数、0
n1=90
n2=-8
n3=0
print(n1,type(n1),n2,type(n2),n3,type(n3))
#默认是十进制数
print('二进制',0b11001101) #表示二进制前+0b
print('八进制',0o574) #表示八进制前+0o
print('十六进制',0x1EAF) #表示十六进制前+0x
```

### 浮点float

```python
a=4.548
print(a,type(a))
#存储浮点数和计算存在一定误差
print(1.1+2.2) #输出3.3000000000000003
#导入decimal
from decimal import Decimal
print(Decimal('1.1')+Decimal('2.2')) #输出3.3
```

### 布尔bool

```python
#表示真假  True真、False假
#True=1、False=0
f1=True
f2=False
#计算式中直接作整数
print(f1+1) #输出2
print(f2+1) #输出1
```

### 字符串str

```python
str1='helloworld'
str2="helloworld"
#三组引号可以换行显示
str3='''hello
world'''
str4="""hello
world"""
print(str1,type(str1))
print(str1,type(str2))
print(str1,type(str3))
print(str1,type(str4))
```

## 数据类型转换

### #str()

```python
name='张三'
age=20
print('我叫'+name+'今年'+str(age)+'岁') #+连接符，str()将其他类型转换成字符串
a=10
b=195.5
c=False
print(str(a),str(b),str(c),type(a),type(str(a))) #原数据类型不变
```

### #int()

```python
s1='128'
f1=98.5
s2='76.77'
c1=True
s3='hello'
print(int(s1),type(int(s1)))	#纯数字字符串可以转换为整数
print(int(f1)) #浮点类型转换仅保留整数部分
#print(int(s2)) 报错，存在小数点，即非数字符号
print(int(c1)) #转换成1
#print(int(s3)) 报错，存在非数字符号
```

### #float()

```python
s1='128.98'
s2='76'
ff=True
s3='hello'
i=98
print(float(s1)) # 数字字符串直接转换
print(float(s2)) #转换成76.0
print(float(ff)) #转换成1.0
#print(float(s3))  无法转换非数字符号
print(float(i)) #转换成98.0
```

# 6.注释

- 单行，例：

```py
#此处是注释
```

- 多行，例:

```python
'''此处
是
注释'''
```

- 中文编码注释：

```python
#encoding=gbk
```

# 7.输入函数input

```python
#输入值类型是str
present=input(' 大圣想要什么礼物呢') #单引号内是提示内容
print(present,type(present)) # 结果是str类型
a=input('输入一个数')
a=int(a)
b=input('输入另一个数')
b=int(b)
print('a+b=',a+b) #需要进行类型转换
```

```python
#或者
a=int(input('输入一个数'))
b=int(input('输入另一个数'))
print('a+b=',a+b) #在输入赋值时进行类型转换
```

# 8.运算符

## 算术运算符

```python
print(1+1) #加法
print(2-4) #减法
print(5*7) #乘法
print(1/3) #除法
print(11//7) #整除（不做四舍五入）向下取整
print(11%7) #取余，余数=被除数-除数*商
print(2**3) #幂运算，例：2的3次方
#包含负数的取余和整除
print(9//4) #2
print(-9//-4) #2
print(9//-4) #-3
print(-9//4) #-3
print(9%4) #1
print(9%-4) #-3，9-(-4)*(-3)=-3
print(-9%4) #3，-9-4*(-3)=3
```

## 赋值运算符

- 赋值顺序，从右到左

```python
#链式赋值
a=b=c=20 
print(a,id(a),b,id(b),c,id(c)) #三个变量指向同一空间
```

```python
#参数赋值
a=20
a+=30 #a=a+30
print(a)
a-=10 #a=a-10
print(a)
a*=2 #a=a乘2
print(a)
a/=3 #a=a/3，到此处a变为float类型
print(a)
a//=2 #a=a//2
print(a)
a%=3 #a=a%3
print(a)
```

```python
#解包赋值
a,b,c=20,30,40 #等号两侧变量和值数量须相同
print(a,b,c)
```

```python
#变量交换值
a,b=10,20
print(a,b)
a,b=b,a
print(a,b)
```

##  比较运算符

```python
a,b=10,20
print('a=',a,'b=',b)
print('a>b?',a>b) #比较结果是bool类型
print('a<b?',a<b)
print('a<=b?',a<=b)
print('a>=b?',a>=b)
print('a==b?',a==b) #比较运算符，比较的是值(value)
print('a!=b?',a!=b)
```

```python
#比较标识(id)
a=10
b=10
print('a==b?',a==b) #结果为True
print('a is b?',a is b) #结果为True
#另一例
list1=[11,22,33,44]
list2=[11,22,33,44]
print('list1==list2?',list1==list2)  #-->True
print('list1 is list2?',list1 is list2)  #-->False
print('list1 is not list2?',list1 is not list2)  #-->True
```

## 布尔运算符

```python
a,b=1,2
#and 和运算符
print('a==1 and b==2?',a==1 and b==2) #True and True-->True
print('a==1 and b<2?',a==1 and b<2)  #True and False-->False
print('a!=1 and b==2',a!=1 and b==2) #False and True-->False
print('a!=1 and b!=2',a!=1 and b!=2) #False and False-->False
#or 或运算符
print('a==1 or b==2',a==1 or b==2) #True or True-->True
print('a==1 or b<2',a==1 or b<2)  #True or False-->True
print('a!=1 or b==2',a!=1 or b==2) #False or True-->True
print('a!=1 or b!=2',a!=1 or b!=2) #False or False-->False
```

```python
#not 对bool取反
f=True
ff=False
print('f->',f,'not f-->',not f) #-->False
print('ff->',ff,'not ff-->',not ff) #-->True
```

```python
#in 与 not in包含与不包含
s='helloworld'
print('h in s?','h' in s) #-->True
print('x in s?','x' in s) #-->False
print('w not in s?','w' not in s)  #-->False
print('x not in s?','x' not in s)  #-->True
```

## 位运算符

- 数据转换成二进制数计算

```python
#&按位与
print('4&8=',4&8)  #结果是0，即，4->100,8->1000,100&1000->0000
```

```python
#|按位或
print('4|8=',4|8)  #结果是12，即，4->100,8->1000,100|1000->1100
```

```python
#<<左移  
print('4<<1=',4<<1) #结果8，即，4->100,左移1位得到1000，左移位数可改
```

```python
#>>右移
print('4>>1=',4>>1) #结果2，即，4->100,右移1位得到010，右移位数也可改
```

## 运算符优先级

- 算术运算符 -->位运算符 --> 比较运算符 --> 布尔运算符 -->赋值运算符

![image-20230910144509664](.\image-20230910144509664.png)

# 9.程序的组织结构

## 顺序结构

- 代码顺序自上而下

### 对象的布尔值

- 一切对象都有一个布尔值，获取对象布尔值使用bool()
- 以下对象的布尔值为False:Flase、数值0、None、空字符串、空列表、空元组、空字典、空集合。其他对象的bool值为True

```py
print('False=',bool(False)) #Flase
print('0=',bool(0)) #数值0
print('0.0=',bool(0.0)) #数值0.0
print('None=',bool(None)) #None
print('\'\'=',bool('')) #空字符串
print('\"\"=',bool("")) #空字符串
print('[]=',bool([])) #空列表
print('list()=',bool(list())) #空列表
print('()=',bool(())) #空元组
print('tuple()=',bool(tuple())) #空元组
print('{}=',bool({})) #空字典
print('dict()=',bool(dict())) #空字典
print('set()=',bool(set())) #空集合
#以上bool值为False
print('8=',bool(8)) #结果为True
print('helloworld=',bool('helloworld')) #结果为True
```

## 选择结构

- 程序根据判断条件的布尔值选择性地执行部分代码

### 单分支结构

```py
#判断取款
money=1000 #余额
s=int(input('请输入取款金额')) # 输入取款金额
#判断余额是否充足
if money>=s:
    money=money-s
    print('取款成功，余额为：',money)
```

### 双分支结构

```py
#判断整数奇偶
num=int(input('输入一个整数')) 
#条件判断
if num%2==0:
    print(num,'是偶数')
else:
    print(num,'是奇数')
```

### 多分支结构

```py
#输入成绩判断等级
score=int(input('请输入分数'))
#条件判断
if score>=90 and score<=100:
    print(score,'为A')
elif score>=80 and score<90:
    print(score,'为B')
elif 70<=score<80: #python特点写法
    print(score,'为C')
elif 60<=score<70:
    print(score,'为D')
elif score>=0 and score<60:
    print(score,'为E')
else:
    print('对不起，请输入有效成绩')
```

### if嵌套

```py
#会员与非会员打折
answer=input('您是会员吗？ y/n')
money=float(input('请输入您的购物金额'))
if answer=='y':
    if money>=200:
        print('付款金额为:',money*0.8)
    elif money>=100:
        print('付款金额为:',money*0.9)
    else:
        print('付款金额为:',money)
else:
    if money>=200:
        print('付款金额为:',money*0.95)
    else:
        print('付款金额为:',money)
```

### 条件表达式

```py
#输入两个数比较大小
num1=int(input('输入第一个整数'))
num2=int(input('输入第二个整数'))
if num1>=num2:
    print(num1,'大于等于',num2)
else:
    print(num1,'小于',num2)
#使用条件表达式进行比较
print(str(num1)+'大于等于'+str(num2)  if num1>=num2 else  str(num1)+'小于'+str(num2))
```

## pass语句

- 什么都不做，只是一个占位符，用到需要写语句的地方

```py
#判断是否是会员
answer=input('您是会员吗？ y/n')
if answer=='y':
    pass
else:
    pass
```

## 内置函数range（）

- 用于生成整数序列
- 返回值是迭代器对象
- 优点：内存只需要存储start、stop、step值

```py
#range(stop)，步长为1生成
r=range(10)
print(r) #输出为range(0,10)
print(list(r)) #输出为[0,1,2,...,9]
```

```py
#range(start,stop) 开区间，步长为1生成
r=range(1,10)
print(list(r)) #输出为[1,2,...,9]
```

```py
#range(start,stop,step) #步长为step生成
r=range(1,10,2)
print(list(r)) #输出为[1,3,5,7,9]
print('10 in r?',10 in r) #判断10是否在序列中
```

## 循环结构

### while循环

- 判断N+1次，条件为True执行N次

```py
a=1
'''while 条件表达式：
		条件执行体'''
while a<10:
    print(a)
    a+=1
```

```py
#计算0~4累加和
times=0
result=0
while times<5:
    result=result+times
    times+=1
print('0~4累加和为：',result)
```

```py
#计算1~100之间的偶数
a=1
sum=0
while a<=100:
    if a%2==0:  #该行为：if a%2，则就是奇数和
        sum=sum+a
    a+=1
print('结果为:',sum)
```

### for-in循环

- in表达从（字符串、序列等）中依次取值，又称遍历
- for-in遍历的对象必须是可迭代对象

```py
for item in 'Python': #第一次取值为P，再赋给item，依次取值赋值
    print(item)
```

```py
#输出结果为依次打印0~9
for i in range(10):
    print(i)
```

- 如果在循环体中不需要使用到自定义变量，可将自定义变量写为"_"

```py
#五次打印
for _ in range(5):
    print('helloworld')
```

```py
#计算1~100偶数和
sum=0
for item in range(1,101):
    if item%2==0:
        sum=sum+item
print('1~100偶数和为：',sum)
```

```py
#输出100~999的水仙花数
for item in range(100,1000):
    a=item%10 #个位
    b=item//10%10 #十位
    c=item//100 #百位
    #判断
    if a**3+b**3+c**3==item:
        print(item)
```

### 流程控制语句

#### break

- 结束当前循环，退出循环结构

```py
#录入密码，最多输入3次
for item in range(3):
    pwd=input('请输入密码')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        print('密码错误')
```

```py
#使用while循环
a=0
while a<3:
    pwd=input('请输入密码')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        print('密码错误')
```

#### continue

- 结束当前循环，进入下一次循环

```py
#输出1~50之间输出所有5的倍数
for item in range(1,51):
    if item%5:
        continue
    print(item)
```

#### else

- 在循环中，跳出循环后进行else语句

```py
#搭配for使用
for item in range(3):
    pwd=input('请输入密码')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        print('密码错误')
else:
    print('对不起，三次密码均输入错误')  
```

```py
#搭配while使用
a=0
while a<3:
    pwd=input('请输入密码')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        print('密码错误')
    a=a+1
else:
    print('对不起，三次密码均输入错误')  
```

### 嵌套循环

- 循环结构中又嵌套了另外的完整循环结构

```py
#输出一个3行4列的举行
for i in range(1,4): #三行
    for j in range(1,5): #四列
        print('*',end='\t') #不换行输出
    print() #换行
```

```py
#输出9*9的乘法表
for i in range(1,10): #三行
    for j in range(1,10): #四列
        if i>=j:
            print(str(j)+'*'+str(i)+'='+str(i*j),end='\t') #不换行输出
    print() #换行
```

- 二重循环中的break和continue仅用于控制本层循环

```py
for i in range(5):
    for j in range(1,11):
        if j%2==0:
            break #仅影响内层循环，不影响外层
        print(j)
```

```py
for i in range(5):
    for j in range(1,11):
        if j%2==0: #仅输出奇数
            continue #仅影响内层循环，不影响外层
        print(j,end='\t') 
    print()
```

# 10.列表

## 概念和特点

![image-20230910183804762](.\image-20230910183804762.png)

- 列表可以存储多个元素，程序可以方便地对这些数据进行整体操作

- 相当于C语言的数组

- 列表的特点

  - 列表元素按顺序有序排序
  - 索引映射唯一一个数据

  |      |         |         | 列表 |      |         |      |
  | :--: | :-----: | :-----: | :--: | :--: | :-----: | :--: |
  | 索引 |   -6    |   -5    |  -4  |  -3  |   -2    |  -1  |
  | 数据 | 'hello' | 'world' | 123  | 98.6 | 'world' | 125  |
  | 索引 |    0    |    1    |  2   |  3   |    4    |  5   |
  
  - 列表可以存储重复数据
  - 列表可以混存不同数据类型
  - 动态分配和回收内存

```py
lst=['hello','world',98] #使用中括号创建，不同元素之间用逗号隔开，列表可以混存不同数据类型
lst2=list(['hello','world',98]) #使用内置函数创建列表
print(id(lst))
print(type(lst)) #类型为list
print(lst) #打印出来是有序排序
print(lst[0],lst[1],lst[2]) #索引映射唯一数据
```

## 列表操作部分

### 获取元素索引

- 使用index ()函数

```py
lst=['hello','world','98','hello']
print(lst.index('hello'))  #列表存在相同元素则返回第一个索引
#print(lst.index('Python'))  #错误信息'Python' is not in list
print(lst.index('hello',1,4)) #返回值3，指定范围内查找，1~4不包括4
```

### 获取列表的单个元素

```py
lst=['hello','world',98,'world',234]
print(lst[2]) #获取索引为2
print(lst[-4]) #获取索引为-4
#print(lst[10]) #错误信息list index out of range
```

### 切片操作

- 切片的结果：原列表切片的拷贝
- 切片范围： [start,stop)

```py
#步长为正数
lst=[10,20,30,40,50,60,70,80]
print(lst[1:6:1]) #start:stop:step；起始索引为1，不写默认为0，终止为6（不包括6），不填默认为最大索引，步长为1，不填则步长默认为1；输出20,30,40,50,60
print('原列表',id(lst))
lst2=lst[1:6:1]
print('切片列表',id(lst2))#两id不一样，切片的结果：原列表切片的拷贝
```

```py
#步长为负数
lst=[10,20,30,40,50,60,70,80]
print(lst[::-1])#默认start最后一个索引，stop第一个索引
print(lst[6:0:-2])#索引从6开始，步长-2，不包括0
```

### 列表元素判断

- in和not in

```py
lst=[10,20,'python','hello']
print(10 in lst) #10是否在列表中
print(20 not in lst) #20是否不在列表中
print('p' not in lst) #输出结果为False
# 将lst元素依次赋给item，并打印
for item in lst:
    print(item)
```

### 列表元素增加

- append (),extend()

```py
lst=[10,20,30]
print('添加元素之前',lst,id(lst))
lst.append(100)#向列表末尾添加一个元素
print('添加元素之后',lst,id(lst)) #列表id不变，没有新增列表对象
lst2=['hello','world']
#lst.append(lst2) #lst2以一个元素接在lst后面：[10, 20, 30, 100, ['hello', 'world']] 2037345607872
lst.extend(lst2) #lst2的多个元素接在lst后面：[10, 20, 30, 100, 'hello', 'world'] 2037345602176
print('添加元素之后',lst,id(lst))
```

- insert(),切片

```py
lst=[10,20,30]
lst2=['hello','world']
print('添加元素之前',lst,id(lst))
lst.insert(2,100)#任意位置添加一个元素
lst.insert(2,lst2) #lst2以一个元素添加在索引2后面
print('添加元素之后',lst,id(lst)) #列表id不变，没有新增列表对象
lst3=[True,False,974]
lst[1:]=lst3 #切掉索引1及之后的元素，再加上lst3
print(lst)
```

### 列表元素删除

- remove(),pop(),切片,clear(),del

```py
lst=[10,20,30,40,50,30,20]
lst.remove(30) #移除值为30的元素，并且只移除一个，存在多个相同元素只删除索引第一个
print(lst)
#若元素不存在会报错
lst.pop(1)#移除索引为1的元素，若索引不存在会报错
print(lst)
lst.pop() #不指定参数会删除最后一个元素
print(lst)
#切片删除会产生新的列表对象，原列表不会改变 
new_lst=lst[1:3] #新建对象的元素为索引为[1,3)的元素
print(new_lst)
#不产生新列表对象删除
lst[1:3]=[] #用空列表替代索引为[1,3)的元素
print(lst)
#清除所有元素
new_lst.clear()
print(new_lst) #输出为[]
#删除列表
del lst
#print(lst) #此时输出报错 name 'lst' is not defined
```

### 列表元素修改

```py
lst=[10,20,30,40]
print('原列表', lst)
#一次修改一个值
lst[2]=100
print('修改索引2的值',lst)
#修改多个元素
lst[1:3]=[300,400,500,600]#将索引[1,3)的小列表用另一个列表替代
print('切片修改',lst)
```

### 列表元素排序

- sort()

```py
lst=[20,40,95,12,45]
print('原列表',lst,id(lst))
#sort调用，默认reverse=False,即升序
lst.sort()
print('升序',lst,id(lst))#id不变，没有生成新的列表对象
#指定关键字参数
lst.sort(reverse=True)
print('降序',lst)
```

- sorted ()

```py
lst=[20,40,95,12,45]
print('原列表',lst,id(lst))
#使用内置函数,默认reverse=True，即升序
new_lst=sorted(lst)
#指定关键字参数
lst2=sorted(lst,reverse=True)
print(lst) #原列表不变
print(new_lst)
print(lst2)
```

### 列表生成式

- i for i in range(1,10)
  - i 表示列表元素的表达式，后面是i值的变化规则

```py
lst=[i for i in range(1,10)] #生成1~9的序列
print(lst)
lst=[i*i for i in range(1,10)] #生成i**2的序列
print(lst)
lst=[i*2 for i in range(1,6)] #生成1~5的偶数序列，i*2不影响后面的循环次数
print(lst)
```

# 11.字典

## 概念

- 元素是key-value对

- 与列表一样是可变序列

- 以键值对的方式存储数据，字典是一个无序序列

  - score={'张三':100,'李四':98}
  - 字典名={键:（冒号）值,（逗号）'李四':98}

- 示意图

  - ![image-20230912100416665](.\image-20230912100416665.png)

  - 存储顺序由hash(key)得到，放入字典的键必须是一个不可变序列（不可执行增删改操作的序列）。

- 实现原理：与查字典类似，根据key查找value所在的位置

## 特点

- Key不允许重复

```py
d={'name':'zhangsan','name':'lisi'}
print(d) #只会返回{'name':'lisi'}
```

- value可以重复

```py
d={'name2':'zhangsan','name':'zhangsan'}
print(d) #返回{'name2': 'zhangsan', 'name': zhangsan'}
```

- 字典中的key是不可变序列

```py
lst=[10,20,30]
d={lst:100}
print(d) #会报错，lst是可变序列，unhashable type: 'list'
```

- 大小可以根据需要动态伸缩
- 会浪费较大的内存，空间换时间的数据结构

## 字典操作部分

### 字典创建

```py
#使用{}创建字典
score={'zhangsan':100,'lisi':98,'wangwu':45}
print(score)
print(type(score)) #返回类型'dict'
```

```py
#使用dict()函数创建字典
student=dict(name='Jack',age=20)
print(student)
```

```py
#创建空字典
d={}
print(d)
```

### 获取字典中的元素

- 使用score[key] ,使用score.get(key) [score为定义的字典名]
  - 区别：第一种方法若字典没有对应的key，会报错；第二种若字典没有对应的key，会返回None，或者自定义返回值

```py
score={'zhangsan':100,'lisi':98,'wangwu':45}
print(score)
print(score['zhangsan'])
#print(socre['chenliu']) #会报错
print(score.get('zhangsan'))
print(score.get('chenliu'))#返回None
print(score.get('chenliu',999)) #返回999
```

### 判断和增删改

- in 与not in 判断字典内是否存在key

```py
score={'zhangsan':100,'lisi':98,'wangwu':45}
print('zhangsan' in score) #返回True
print('zhangsan' not in score) #返回False
```

- del 与 clear 删除字典元素

```py
score={'zhangsan':100,'lisi':98,'wangwu':45}
del score['zhangsan'] #删除key值为'zhangsan'的键值对
print(score)
score.clear() #清空
print(score) 
```

- 新增与修改

```py
score={'zhangsan':100,'lisi':98,'wangwu':45}
score['chenliu']=52 #新增在最后
print(score)
score['chenliu']=65 #修改操作
print(score)
```

### 视图操作

```py
#keys()
score={'zhangsan':100,'lisi':98,'wangwu':45}
keys=score.keys() #得到的是一个视图
print(keys) 
print(type(keys)) #返回'dict_keys'
print(list(keys)) #list将视图转变成列表
print(type(list(keys)))
#values()
values=score.values()
print(values)
print(type(values)) #类型'dict_values'
#items()
items=score.items()
print(items)  
print(type(items)) #类型'dict_items'
print(list(items)) #转换之后的列表元素是元组，由()括上
```

字典元素遍历

```py
score={'zhangsan':100,'lisi':98,'wangwu':45}
for item in score: #是将字典score的key赋给item，类型str
    print(item,type(item))
    print(score[item],score.get(item)) #打印Value
```

### 字典生成式

- 内置函数zip()

  - 用于可迭代的对象作为参数，将对象中对应的元素打包成一个元组，然后返回由这些元组组成的列表

  ```py
  items=['fruit','book','other']
  prices=[98,75,65,878] #创建的字典d以列表小的长度为准
  d={item.upper():price for item,price in zip(items,prices)} #upper是将其item均改为大写字母，zip打包成元组赋给item和price
  print(d)
  ```

  

# 12.元组和集合

## 什么是元组

- 元组：python内置数据结构之一，是一个不可变序列

  - 设计成不可变序列，在多任务环境下，同时操作对象时不需要加锁

  ![image-20230912123131185](.\image-20230912123131185.png)

  - 元组中对象本身是不可变对象，不能再引用其他对象

  - 如果元组中的对象是可变对象，可变对象的引用不许改变，数据可以改变

    ```py
    t=(10,[20,30],9)
    print(t)
    print(type(t))
    print(t[0],type(t[0]),id(t[0]))
    print(t[1],type(t[1]),id(t[1]))
    print(t[2],type(t[2]),id(t[2]))
    #t[1]=100 #会报错，元组不允许修改元素
    t[1].append(100)
    print(t[1],type(t[1]),id(t[1])) #元组中的可变对象的数据可变
    ```

- 不可变序列：字符串、元组

  - 不可变序列没有增删改操作

- 可变序列：列表、字典

  - 可变序列可以执行增删改操作，对象地址不发生更改

```py
#可变序列
lst=[10,54,6] 
print(id(lst))
lst.append(300)
print(id(lst)) #id相同
#不可变序列
s='hello'
print(id(s))
s=s+'world'
print(id(s)) #id不同
```

## 元组的操作

### 元组的创建

```py
#使用()创建元组
t=('python','world',98)
print(t)
print(type(t)) #<class 'tuple'>
t2='python','world',98 #也可以省略小括号
print(t2)
print(type(t2)) #<class 'tuple'>
#只包含一个元组的元素，需要使用逗号和小括号，否则是其他类型
t3=(10,)
print(type(t3)) #<class 'tuple'>
t4=(10)
print(type(t4)) #<class 'int'>
```

```py
#使用内置函数tuple()创建
t1=tuple(('python','world',98))
print(t1)
print(type(t1)) #<class 'tuple'>
```

```py
#空元组
t1=()
t2=tuple()
print('空元组',t1,t2)
```

### 元素的遍历

```py
t = ('python', 'world', 98)
# 第一种，索引
print(t[0])
print(t[1])
print(t[2])
# print(t[3]) #会报错，tuple index out of range
# for in 遍历
for item in t:
    print(item)
```

## 什么是集合

- 可变类型序列
- 没有Value的字典

## 集合的操作

### 集合的创建

```py
#直接使用{}创建
s={5,5,7,6,1,2,4,4}
print(s.type(s)) #{1, 2, 4, 5, 6, 7} <class 'set'>  不允许存在相同的值
```

```py
#使用内置函数set()
s1=set(range(6))
print(s1,type(s1)) #{0, 1, 2, 3, 4, 5} <class 'set'>
s2=set([1,5,7,8,4,1,2])
print(s2,type(s2))  #{1, 2, 4, 5, 7, 8} <class 'set'>
s3=set((1,2,5,4,65,64)) #集合中元素是无序的
print(s3,type(s3))  #{64, 65, 1, 2, 4, 5} <class 'set'>
s4=set('python')
print(s4) #{'h', 'y', 'o', 't', 'p', 'n'}
s5=set({12,54,6,47,9,5,9})
print(s5) #{5, 6, 54, 9, 12, 47}
```

```py
#空集合
s6=set()
print(s6,type(s6)) #set() <class 'set'>
```

### 集合的判断

- in与not in

```py
s={45,8,9,4,5,1,10}
print('10 in s?',10 in s) #True
print('5 not in s?',5 not in s) #False
```

集合的新增

- add() 与 update()
  - add()新增一个元素
  - update()新增多个元素，并且可以写入集合、序列、元组

```py
s={45,8,9,4,5,1,10}
print(s)
s.add(80) #添加一个元素
print(s)
s.update({100,64}) #添加多个元素
print(s)
s.update([54,659,41])
s.update((78,621,14))
print(s)
```

### 集合的删除

- remove()：删除指定元素

```py
s={45,8,9,4,5,1,10}
print(s)
s.remove(45)
print(s)
#s.remove(100) #若元素不存在，会抛出KeyError
```

- discard()：删除指定参数

```py
s={45,8,9,4,5,1,10}
print(s)
s.discard(45)
print(s)
s.discard(100) #不会报错，有则删没有则不进行操作
print(s)
```

- pop()：删除打印出集合顺序的第一个元素

```py
s={45,8,9,4,5,1,10}
print(s)
s.pop() #删除打印出集合的第一个元素
print(s)
s.pop() #删除打印出集合的第一个元素
print(s)
#s.pop(5) #报错，pop()不能指定参数
```

- clear()：清空集合

```py
s={45,8,9,4,5,1,10}
print(s)
s.clear() #清空集合
print(s) 
```

### 集合的数学操作

- 交集

  - 调用intersection() 或者 &
  - 不改变原集合

  ```py
  s1={1,2,3,4,5}
  s2={4,7,6,5}
  s3=s1.intersection(s2)
  s4=s1&s2
  print(s3,s4) #{4, 5} {4, 5}
  ```

- 并集

  - 调用 union() 或者 |
  - 不改变原集合

  ```py
  s1={1,2,3,4,5}
  s2={4,7,6,5}
  s3=s1.union(s2)
  s4=s1|s2
  print(s3,s4) #{1, 2, 3, 4, 5, 6, 7} {1, 2, 3, 4, 5, 6, 7}
  ```

- 差集

  - 调用 difference 或者 -
  - 不改变原集合

  ```py
  s1={1,2,3,4,5}
  s2={4,7,6,5}
  s3=s1.difference(s2)
  s4=s2-s1
  print(s3,s4) #{1, 2, 3} {6, 7}
  ```

- 对称差集

  - 调用 symmetric_difference()  或者 ^
  - 不改变原集合

  ```py
  s1={1,2,3,4,5}
  s2={4,7,6,5}
  s3=s1.symmetric_difference(s2)
  s4=s1^s2
  print(s3,s4) #{1, 2, 3, 6, 7} {1, 2, 3, 6, 7}
  ```

### 集合生成式

- 与列表生成式类似，将[]改为{}

```py
s={i*i for i in range(10)} 
print(s) #{0, 1, 64, 4, 36, 9, 16, 49, 81, 25} 无序的
```

## 集合间的关系

- 集合是否相等

```py
s1={10,20,30,40}
s2={30,40,10,20}
print('s1==s2?',s1==s2) #True
print('s1!=S2?',s1!=s2) #Flase
```

- 集合包含关系
  - 调用issubset() [判断子集]和issuperset() [判断超集]

```py
s1={2,5,4,7,9,2}
s2={5,7,9}
s3={9,4,7,2,4,99}
print(s2.issubset(s1)) #True,s2是s1的子集
print(s3.issubset(s1)) #False
print(s1.issuperset(s2)) #True,s1是s2的超集；超集：s1有s2的所有元素，同时包含s2没有的元素
print(s1.issuperset(s3)) #False
```

- 集合是否没有交集
  - 调用isdisjoint()

```py
s1={2,5,4,7,9,2}
s2={5,7,9}
s3={9,4,7,2,4,99}
print(s2.isdisjoint(s1)) #有交集为Flase
print(s3.isdisjoint({100,200})) #True
```

# 简单总结表

![image-20230912134221271](.\image-20230912134221271.png)

# 13.字符串

## 字符串的创建和驻留机制

- 驻留机制

  <img src=".\image-20230912140431919-1694780507162-11.png" alt="image-20230912140431919" style="zoom:50%;" />

  - 仅保存一份相同且不可变字符串的方法，如下不会开辟新的空间，即id值相同

  ```py
  a='python'
  b="python"
  c='''python'''
  print(a,id(a)) #三个变量的id相同
  print(b,id(b))
  print(c,id(c))
  ```

  - 交互模式的几种情况(win+R，进入cmd，输入python进入交互模式)

    1. 字符串长度为0或1
    2. 符合标识符的字符串（字母、数字、下划线）
    3. 字符串旨在编译时驻留，而非运行

    ```py
    c='''python'''
    d=''.join(['py','thon'])
    print(c,id(c))
    print(d,id(d)) #id不同
    ```

    4. [-5,256]之间的整数数字

  - pycharm会强制驻留以上的1、2、4种情况

  - join()效率比+高

## 字符串常用操作

### 查询操作

- index()查询第一个位置
  - 如果没有这个元素会报错异常
- rindex()查询最后一个位置
  - 同上
- find()查询第一个位置
  - 如果没有这个元素会返回值-1
- rfind()查询最后一个位置
  - 同上

```py
s='hello,hello'
print(s.index('lo')) #3
print(s.find('lo')) #3
print(s.rindex('lo')) #9
print(s.rfind('lo')) #9
# print(s.index('k')) #ValueError: substring not found
print(s.find('k')) #-1
```

### 大小写转换

- upper()：全转换成大写
- lower()：全转换成小写

```py
s='hello,world'
a=s.upper()
print(s,id(s)) #hello,world 2090246358640
print(a,id(a)) #HELLO,WORLD 2090247860464 id值不同，产生了新的对象，验证了字符串是不可变序列
b=a.lower()
print(b,id(b)) #hello,world， id值与s.id并不同
```

- swapcase()：大写转换成小写、小写转换成大写
- capitalize()：第一个字符大写，其余小写
- title()：每个单词第一个字符大写，其余小写

```py
s='hello,World'
print(s)
a=s.swapcase()
print(a) #HELLO,wORLD
b=s.capitalize()
print(b) #Hello,world
c=s.title()
print(c) #Hello,World
```

### 内容对齐

- center()：居中

```py
s='hello,Python'
print(s.center(20,'*')) # ****hello,Python****  输出字符20的长度，空位填充'*'，第二个参数不填默认为空格
print(s.center(2,'*'))  #hello,Python  输出原字符串
```

- ljust()：左

```py
s='hello,Python'
print(s.ljust(20,'*')) # hello,Python********  输出字符20的长度，空位填充'*'，第二个参数不填默认为空格
print(s.ljust(2,'*'))  #hello,Python  输出原字符串
```

- rjust()：右

```py
s='hello,Python'
print(s.rjust(20,'*')) # ********hello,Python  输出字符20的长度，空位填充'*'，第二个参数不填默认为空格
print(s.rjust(2,'*'))  #hello,Python  输出原字符串
```

- zfill()：右

```py
s='+hello,Python'
print(s.zfill(20)) # +0000000hello,Python  输出字符20的长度，空位填充0，而且0填充在‘+’或者‘-’后面
print(s.zfill(2))  #+hello,Python  输出原字符串
```

### 字符串劈分

- split()：从左边开始分割

```py
s='hello world python'
s2='hello|world|python'
lst=s.split() #参数默认，以空格劈分
print(lst) #['hello', 'world', 'python']
lst2=s2.split(sep='|') #以'|'劈分
print(lst2) #['hello', 'world', 'python']
lst3=s2.split(sep='|',maxsplit=1) #劈分一段后，剩余未劈分为一段
print(lst3)#['hello', 'world|python']
```

- rsplit()：从右边开始分割

```py
s='hello world python'
s2='hello|world|python'
lst=s.rsplit() #参数默认，以空格劈分
print(lst) #['hello', 'world', 'python']
lst2=s2.rsplit(sep='|') #以'|'劈分
print(lst2) #['hello', 'world', 'python']
lst3=s2.rsplit(sep='|',maxsplit=1) #劈分一段后，剩余未劈分为一段
print(lst3)#['hello|world', 'python']，与第一个不同
```

### 判断字符串

- isidentifier()：判断是否是合法的标识符（字母（汉字）、数字、下划线）

```py
s='hello,python'
print(s.isidentifier()) #False,因为‘,’不是合法的
```

- isspace()：判断是否由全部空白字符组成（回车、换行、水平制表符）

```py
print('\n'.isspace()) #True
```

- isalpha()：判断是否全部由字母（汉字）组成

```py
print('张三avb'.isalpha()) #True
```

- isdecimal()：判断是否十进制数

```py
print('4561'.isdecimal()) #True
print('0x4e4'.isdecimal()) #False
```

- isnumeric()：判断是否数字

```py
print('四Ⅳ④'.isnumeric()) #True
print('467'.isnumeric()) #True
```

- isalnum()：判断是否是字母（汉字）和数字组成

```py
print('646sa'.isalnum()) #True
print('张三5465as'.isalnum()) #True
```

- endswith()：判断字符串以什么结尾

```py
ch='145453.sa'
if ch.endswith('3.sa'):
    print(1)
else:
    print(0)
```



### 替换与合并

- replace()

```py
s='hello,Python,Python,Python'
print(s.replace('Python','Java')) #hello,Java,Java,Java  两个参数用法，默认全换
print(s.replace('Python','Java',2))# hello,Java,Java,Python，三参数，最后为替换次数
```

- join ()

```py
lst=['Hello','Java','Python']
print('I'.join(lst)) #HelloIJavaIPython,用‘I’连接这个列表
t=('Hello','Java','Python')
print(' '.join(t)) #Hello  Java  Python,用'  '连接这个元组
print('*'.join('python')) #p*y*t*h*o*n
```

### 比较操作

- 运算符：>,>=,<,<=,==,!=

- 规则：依次比较，比较的字符原始值（ascll码）

  ps：is和not is比较的是id，以上比较的value（即原始值）

```py
print('apple'>'app') #True
print('apple'>'banana') #False
print(ord('a'),ord('b')) #97 98获取原始值，即ascll码
print(chr(97)) #a,打印原始值对应的符号
```

### 切片操作

- 字符串不具备增删改等操作，切片会产生新的对象

```py
s='hello,python'
print(s) #hello,python
s1=s[:5] #没有起始位置，从0开始切
print(s1) #hello
s2=s[6:] #没有指定结束位置，从起始位置切到最后
print(s2) #python
s3=s1+'!'+s2
print(s3) #hello!python

print(s[1:9:2]) #el,y  以1开始，结束位置9（不包含9），步长2（没有指定步长默认2）
print(s[::-1]) #nohtyp,olleh,步长可以为负，从最后一个开始，到第一个字符，索引类似列表
```

### 格式化字符串

- %号、{数字}、f-string

```py
name='zhangsan'
age=20
print('我叫%s,age%d' %(name,age)) #我叫zhangsan,age20
print('我叫 {0}，age{1}'.format(name,age)) #我叫 zhangsan，age20
print(f'我叫{name},age{age}') #我叫zhangsan,age20
format_title='{:^6}\t{:^12}\t{:^8}\t{:^10}\t{:^10}\t{:^8}' #:^6此处的含义是六个占位符然后居中
print(format_title.format('学号','姓名','英语成绩','Python成绩','Java成绩','总成绩'))
```

- 精度等

```py
print('%10d' %99) #10 表示总宽度为10
print('%10.3f' % 3.1415926) #3.142,表示三位小数，四舍五入

print('{0:.3}'.format(3.1415926)) #3表示三位数
print('{0:10.3f}'.format(3.1415926)) #表示三位小数，总宽度是10
```

### 字符串解码编码

- 编码

```py
s='天涯共此时'
print(s.encode(encoding='GBK')) #GBK编码中，一个中文两个字节；b'\xcc\xec\xd1\xc4\xb9\xb2\xb4\xcb\xca\xb1'
print(s.encode(encoding='UTF-8')) #UTF-8中一个中文三个字节；b'\xe5\xa4\xa9\xe6\xb6\xaf\xe5\x85\xb1\xe6\xad\xa4\xe6\x97\xb6'
```

- 解码

```py
s='天涯共此时'
byte=s.encode(encoding='GBK') #byte是一个二进制数据
print(byte.decode(encoding='GBK')) #天涯共此时
byte=s.encode(encoding='UTF-8')
print(byte.decode(encoding='UTF-8')) #只能对应的解码
```

# 14.函数

- 概念同C类似（以下简单的例子）

```py
#函数建立和调用
def calc(a, b):
    c = a + b
    return c
print(calc(10,20))
```

## 参数

### 参数传递

```py
def calc(a, b):  # a,b形参，位置在函数定义处
    c = a + b
    return c
print(calc(10, 20))  # 实参，位置在函数调用处；此处是位置实参
print(calc(b=20, a=10)) # 此处是关键词传参，其中a，b是关键词参数（形参名称）
```

- 不可变对象在函数体的修改不会影响实参的值，如果是可变对象，在函数体内的修改会影响到实参的值（下例）

![image-20230912192423903](.\image-20230912192423903.png)

```py
def fun(arg1,arg2):
    print('arg1=',arg1)
    print('arg2=',arg2)
    arg1=100
    arg2.append(10)
    print('arg1=',arg1)
    print('arg2=',arg2)
n1=11
n2=[22,33,44]
print('n1=',n1)
print('n2=',n2)
fun(n1,n2)
print('n1=',n1)
print('n2=',n2)
'''执行结果
n1= 11
n2= [22, 33, 44]
arg1= 11
arg2= [22, 33, 44]
arg1= 100
arg2= [22, 33, 44, 10]
n1= 11
n2= [22, 33, 44, 10]
'''
```

### 函数定义默认参数

- 定义函数时设定默认值，当调用函数时没有给定实参，就会使用默认值

```py
def fun(a, b=10):
    print(a, b)


fun(100)  # 100 10
fun(20, 30)  # 20 30
# 例如print
print('hello')  # 默认会换行
print('hello', end='\t') # 设定是否换行
print('world')
```

### 个数可变的位置参数

```py
def fun(*args): #只能写一个*args
    print(args)
#返回的元组
fun(10) #(10,)
fun(10,60) #(10, 60) 
```

### 个数可变的关键字形参

```py
def fun1(**args): #只能写一个**args
    print(args)
#返回字典
fun1(a=10) #{'a': 10}
fun2(a=10,b=5,c=90) #{'a': 10, 'b': 5, 'c': 90}
```

```py
def fun1(*args1,**args2):
    pass
'''def fun2(**args2,*args2):
    pass
    这一情况会报错，所以个数可变的位置参数需要在个数可变的关键字形参前面
'''
```

### 总结

![image-20230912200202608](.\image-20230912200202608.png)

```py
def fun(a, b, c):  # 形参
    print('a=', a)
    print('b=', b)
    print('c=', c)
    return


def fun1(a, *, b, c):  # a之后的只能用关键字形参
    print('a=', a)
    print('b=', b)
    print('c=', c)
    return


fun(10, 20, 30)  # 传参
lst = [11, 22, 33]  # [11,22,33]
print(*lst)  # 11 22 33
fun(*lst)  # 函数调用时，列表中每个元素转换成位置实参
fun(a=100, c=300, b=200)  # 关键字实参
dic = {'a': 100, 'b': 200, 'c': 300}
fun(**dic)  # 字典的键值对转换为关键字实参
fun(10, c=87, b=4)  # 混合，只能前面是位置实参，而且必须含顺序，后面关键字实参
fun1(64, c=54, b=25)  # 混合，后两个只能关键字实参

def fun7(a,b=10,*args,**args2):
    pass
```

## 返回值

- 函数如果没有返回值，可以省略return
- 如果一个返回值，返回原类型
- 如果多个返回值，返回元组（下例）

​		ps：是否设置返回值视情况而定

```py
#分出奇数偶数
def fun(num):
    odd=[]
    even=[]
    for i in num:
        if i%2:
            odd.append(i)
        else:
            even.append(i)
    return odd,even
#调用
lst=[10,29,34,23,44,53,55]
print(fun(lst)) #([29, 23, 53, 55], [10, 34, 44]) 是一个元组
```

## 变量作用域

- 局部变量
- 全局变量

```py
def fun(a, b):
    c = a + b  # a,b,c均为局部变量
    global d
    d = a - b  # d使用global定义是全局变量
    print(c)
    return


fun(10, 20)
# print(a,b,c) #报错
print(d) # 此处d可使用


def fun2(a):
    print(a)
    return


name = 'zhangsan'
print(name)  # name为一个全局变量，函数内外都可使用
fun2(name)
```

# 递归函数

- 缺点：占用内存大

```py
#计算阶乘
def fac(n):
    if(n==1):
        return 1
    else:
        return n*fac(n-1)
print(fac(6))
```

```py
# 斐波那契数列
def fib(n):
    if (n == 1 or n == 2):
        return 1
    else:
        return fib(n - 1) + fib(n - 2)
for i in range(1,7):
    print(fib(i))
```

# 15.bug

- 异常处理

  - 多个except结构

  ```py
  try:
      n1 = int(input('请输入一个整数'))
      n2 = int(input('请输入另一个整数'))
      result = n1 / n2
      print('result=' + str(result))
  except ZeroDivisionError:
      print('除数不允许是0')
  except ValueError:
      print('只能输入数字')
  except BaseException as e: #避免遗漏出现的异常
      print(e)
  print('end')
  ```

  - try...except...else

  ```py
  try:
      n1 = int(input('请输入一个整数'))
      n2 = int(input('请输入另一个整数'))
      result = n1 / n2
  except BaseException as e:  # e是出错原因
      print(e)
  else:
      print('result=' + str(result))
  finally:
      print('无论是否异常，都会执行的一段代码')
  ```

- 常见异常类型

| 序号 |     异常类型      |              描述              |
| :--: | :---------------: | :----------------------------: |
|  1   | ZeroDivisionError | 除（或取模）零（所有数据类型） |
|  2   |    IndexError     |   序列中没有此索引（index）    |
|  3   |     KeyError      |        映射中没有这个键        |
|  4   |     NameError     | 未声明/初始化对象（没有属性）  |
|  5   |    SyntaxError    |         Python语法错误         |
|  6   |    ValueError     |          传入无效数据          |

- tranceback模块的使用

```py
import traceback

try:
    print('-----------')
    print(1 / 0)
except:
    traceback.print_exc()
```

# 16.类与对象

- 编程思想

![image-20230916103412361](.\image-20230916103412361.png)

- 类
  - 类别，多个类似事物组成的群体的统称，能够帮我们快速理解和判断事物的性质。
  - 数据类型
    - 不同的数据类型属于不同类
    - 使用内置函数type()查看数据类型
  - 对象
    - 100、99等都是int类，个例称为对象。

## 类的创建

- 基本格式

```py
class Student:  # Student为类的名称，由一个或多个单词组成，每个单词首字母大写，其余小写
    pass

print(id(Student))
print(type(Student)) #<class 'type'>
print(Student) #<class '__main__.Student'>
```

```py
class Student:  # Student为类的名称，由一个或多个单词组成，每个单词首字母大写，其余小写
    native_pace = 'chongqing'  # 直接写在类里面的变量，称为类熟悉

    def __init__(self, name, age):
        self.name = name  # self.name称为实体属性，进行赋值操作，将局部变量name赋值给实体属性
        self.age = age

    # 类里面定义的叫实例方法
    def eat(self):
        print('学生在吃饭')

    # 静态方法
    @staticmethod
    def method():  # 里面不写self
        print("我使用了staticmethod进行修饰，是静态方法")

    # 类方法
    @classmethod
    def cm(cls):
        print('我使用了classmethod修饰，是类方法')


# 类之外定义的叫函数
def drink():
    print('学生在喝水')

```

- 实例对象

  - 类属性
  - 构造函数
  - 实例方法
  - 类方法
  - 静态方法

  ![image-20230916114838535](.\image-20230916114838535.png)

- 动态绑定属性

  ![image-20230916121932678](.\image-20230916121932678.png)

```py
class Student:  # Student为类的名称，由一个或多个单词组成，每个单词首字母大写，其余小写，Student叫类对象
    native_pace = 'chongqing'  # 直接写在类里面的变量，称为类属性

    def __init__(self, name, age):  # 初始化方法,类的构造函数
        self.name = name  # self.name称为实例变量，进行赋值操作，将局部变量name赋值给实体属性，共有的属性
        self.age = age

    # 类里面定义的叫实例方法
    def eat(self):
        print('学生在吃饭')

    # 静态方法
    @staticmethod
    def method():  # 里面不写self
        print("我使用了staticmethod进行修饰，是静态方法")

    # 类方法
    @classmethod
    def cm(cls):
        print('我使用了classmethod修饰，是类方法')


# 类之外定义的叫函数
def drink():
    print('学生在喝水')


# 创建Student类的对象，stu1是实例对象
stu1 = Student('张三', 20)
print(id(stu1))
print(type(stu1))
print(stu1)  # 输出的stu1的内存16进制数
print('------------------')
# Student是类对象
print(id(Student))  # 与stu1不同
print(type(Student))
print(Student)
print('------------------')
#实例方法使用，对象名.方法
stu1.eat() #学生在吃饭，
print(stu1.name)
print(stu1.age)
print('------------------')
#另一使用方法
Student.eat(stu1) #类名.方法（类的对象）--->方法定义处的self
print('------------------')
#类属性使用方法
stu2=Student('lisi',25)
print(Student.native_pace)
print(stu1.native_pace)
Student.native_pace='tianjing' #修改了类对象里面的类属性，类里面的native_pace是共享的
print(stu1.native_pace)
print(stu2.native_pace)  #tianjing
print('------------------')
#类方法使用
Student.cm()
#静态方法使用
Student.method()
#动态绑定属性
stu1.gender='女'
print(stu1.gender) #女，只适用于当前绑定的stu1
#print(stu2.gender) #报错
print('------------------')
#动态绑定方法
def show():
    print('定义在类外的叫函数')
stu1.show=show #给stu1绑定show函数为类方法
stu1.show()
#stu2.show() #报错
```

## 面向对象

- 封装：提高安全性

  - 将数据（属性）和行为（方法）包装到类对象中

  ```py
  class Student:
      def __init__(self, name, age):
          self.name = name
          self.__age = age
      def show(self): #可以在内部使用
          print(self.__age)
  stu = Student('zhangsan', 50)
  stu.show()
   #print(stu.__age) #会报错
  print(dir(stu)) #获取可使用的方法
  print(stu._Student__age) #可以通过这种方式在类外强行使用
  ```

- 继承：提高代码复用

  - Python支持多继承
  - 方法重写

  ```py
  class Person:  # 不写默认继承object
      def __init__(self, name, age):
          self.name = name
          self.age = age
  
  
      def info(self):
          print(self.name, self.age)
  
  
  class Student(Person):
      def __init__(self, name, age, stu_id):
          super().__init__(name, age)  # 调用父类的方法
          self.stu_id = stu_id
          super().info() #在实例方法和初始函数里面可用
      def info(self):
          super().info()
          print(self.stu_id)
  class Teacher(Person):
      def __init__(self, name, age, tea_year):
          super().__init__(name, age)
          self.tea_year = tea_year
  
  
  stu = Student('zhangsan', 12, '1001')
  tea = Teacher('lisi', 50, 20)
  stu.info()  # zhangsan 12 zhangsan 12 1001
  tea.info()  # lisi 50
  ```

  ```py
  #多继承
  class A:
      pass
  
  
  class B:
      pass
  
  
  class C(A, B):
      pass
  ```

  - object类

  ```py
  class Student:
      def __init__(self, name, age):
          self.name = name
          self.age = age
  
      def __str__(self): #__str__是对对象的描述，重写默认的方法，不修改返回值是id
          return '我的名字是%s,今年%d岁' % (self.name, self.age)
  
  stu = Student('张三', 45)
  print(dir(stu)) #返回所有可用的方法
  print(stu) #print是会调用__str__()
  ```

- 多态：提高程序可扩展和可维护性

```py
class Animal(object):
    def eat(self):
        print('动物会吃')
class Dog(Animal):
    def eat(self):
        print('狗会吃骨头')
class Cat(Animal):
    def eat(self):
        print('猫吃鱼')
class Person(object):
    def eat(self):
        print('人吃五谷杂粮')
def fun(obj):
    obj.eat()
# 不同的类都可以调用fun函数
fun(Cat())
fun(Dog())
fun(Animal())
fun(Person())
```

## 特殊属性和方法

![image-20230916154316701](.\image-20230916154316701.png)

- 特殊属性

```py
class A:
    pass
class B:
    pass
class C(A,B):
    def __init__(self,name):
        self.name=name
x=C('Jack')  #x是C类型的实例对象
print(x.__dict__)  #查看实例对象属性的字典
print(C.__dict__)  #查看类对象属性和方法的字典
print(x.__class__)  #查看实例对象所属的类
print(C.__bases__)  #查看C类的父类
print(C.__base__)  #查看C类的第一个父类
print(C.__mro__)  #查看类的层次结构
print(A.__subclasses__())  #查看类的子类的列表
```

- 特殊方法

```py
a=20
b=100
print(a+b)
print(a.__add__(b)) #120 加法的特殊方法

class Student:
    def __init__(self,name):
        self.name=name
    def __add__(self, other):  #需要定义这个特殊方法才可以相加
        return self.name+other.name
    def __len__(self):
        return len(self.name)
stu1=Student('zhangsan')
stu2=Student('lisi')
stu3=Student('wangwu')
s=stu1+stu2 #实现两个对象的加法（名字加法）
#s=stu1+stu2+stu3 #仅能是两个对象相加，否则报错
print(s)

lst=[11,22,33,44]
print(len(lst))
print(lst.__len__()) #4,求长度 的特殊方法
print(len(stu1))
```

```py
class Person:
    def __new__(cls, *args, **kwargs):
        print('__new__执行，cls的id值为{0}'.format(id(cls)))
        obj=super().__new__(cls)
        print(' 创建的对象id为{0}'.format(id(obj)))
        return obj
    def __init__(self,name,age):
        print('__init__执行,self的id值为{0}'.format(id(self)))
        self.name=name
        self.age=age

print('object这个类对象的id为{0}'.format(id(object)))
print('Person这个类对象的id为{0}'.format(id(Person)))

p=Person('zhangsan',20)
print('p这个Person实例对象的id为{0}'.format(id(p)))
```

![image-20230916172404987](.\image-20230916172404987.png)

## 类的赋值与拷贝

- 类的赋值

![image-20230916183821943](.\image-20230916183821943.png)

```py
class Cpu:
    pass
class Disk:
    pass
class Computer:
    def __init__(self,cpu,disk):
        self.cpu=cpu
        self.disk=disk

#变量的赋值
cpu1=Cpu()
cpu2=cpu1
print(cpu1,id(cpu1))
print(cpu2,id(cpu2))  #两个变量指向的地址相同

#浅拷贝
disk=Disk()
computer=Computer(cpu1,disk)
import copy
computer2=copy.copy(computer)
print(computer,computer.cpu,computer.disk)
print(computer2,computer2.cpu,computer2.disk) #computer不同，但后两个相同，后两个为子对象

#深拷贝
computer3=copy.deepcopy(computer)
print(computer3,computer3.cpu,computer3.disk) #三项的地址都与computer不同
```

- 浅拷贝：拷贝时，对象包含的子对象内容不拷贝，因此，源对象和拷贝对象会引用同一个子对象（代码如上）

![image-20230916185421403](.\image-20230916185421403.png)

- 深拷贝：拷贝时，对象以及对象的子对象都会拷贝，对象以及子对象的地址都不同

<img src=".\image-20230916185910688.png" alt="image-20230916185910688" style="zoom:67%;" />

# 17.模块(Modules)

- 导入模块

```py
'''
import math #关于数学运算的模块   import [模块名称]
print(id(math))
print(type(math))
print(math)
print(math.pi)
print(dir(math))
print(math.ceil(9.001)) #向上取整
print(math.floor(9.999)) #向下取整
'''

from math import pi #from模块import函数/变量/类
import math
print(pi) #导入指定内容后可直接用
print(pow(2,3)) #这个是builtins的模块
print(math.pow(2,3)) # 这个是math模块
```

- 导入自定义模块

  - 文件夹选择 Mark Directory as -->Source Root

    ```py
    #calc.py
    def add(a, b):
        return a + b
    
    
    def div(a, b):
        return a / b
    ```

    ```py
    #demo1.py
    # 在此文件中导入calc
    '''
    import calc
    print(calc.add(10,20))
    print(calc.div(8,4))
    '''
    
    from calc import add
    
    print(add(84, 6))
    ```

## 以主程序运行

- 见下例

```py
#calc.py
def add(a, b):
    return a + b
if __name__ == '__main__':  # 只有当运行calc.py时才会运行此语句，如果没有这一句，运行demo.py会输出30
    print(add(10, 20))
```

```py
#demo.py
from calc import add
print(add(84, 6))
```

## Python中的包

- 包是一个分层次的目录结构，将功能相近的模块组织在同一目录下

  - 作用：

    - 代码规范
    - 避免模块名称冲突（不同包的模块名称可以相同）

  - 包与目录的区别

    - 包含\__init__.py文件的目录称为包
    - 目录里通常不包含\__init__.py文件

  - 包的导入

    import 包名.模块名

- 文件包含

![image-20230916195628977](.\image-20230916195628977.png)

```py
#module1.py
a=10

#calc.py
def add(a, b):
    return a + b
if __name__ == '__main__':  # 只有当运行calc.py时才会运行此语句
    print(add(10, 20))
    
#demo1.py
#demo中导入package1包
import package1.module1 as ma #ma是指packag1（包名）.module1（模块名）的别名
print(ma.a)
#导入带有包的模块时注意
#import后面只能跟包名/模块名
import package1
import calc
#from ...(包/模块)import ...(模块/函数/变量等)
from package1 import module1
from package1.module1 import a
from calc import add
```

## 常用内置模块

![image-20230916195837447](.\image-20230916195837447.png)

## 第三方模块

- file --> setting --> python interpreter --> 点+号，搜索需要安装的模块 --> 在python文件中 import 模块名称

```py
import time

import schedule
def job():
    print('haha--------')
    
schedule.every(3).seconds.do(job)
while True:
    schedule.run_pending()
    time.sleep(1)
```

# 18.文件

## 编码格式

![image-20230916202050733](.\image-20230916202050733.png)

- Python解释器使用Unicode（内存）
- .py文件在磁盘上使用UTF-8存储（外存）

## 文件读写

- 原理图

![image-20230916203157840](.\image-20230916203157840.png)

![image-20230916203139773](.\image-20230916203139773.png)

- 内置函数open()创建文件对象

![image-20230916203431492](.\image-20230916203431492.png)

```py
#简单示例，读取txt文件全部内容
file = open('aaa.txt', 'r',encoding='UTF-8')
print(file.readlines())
file.close()
```

## 文件打开模式

![image-20230916205515273](.\image-20230916205515273.png)

```py
#简单示例，复制图片
src_file=open('IMG_20230818_091716.jpg','rb') #二进制方式
target_file=open('textcopy.jpg','wb')
target_file.write(src_file.read())
target_file.close()
src_file.close()
```

## 常用方法

![image-20230917151311360](.\image-20230917151311360.png)

```py
file1=open('aaa.txt','r',encoding='UTF-8')
print(file1.read(4)) #读取文件内容到某个字符
print(file1.tell()) #返回当前文件指针的位置
file1.seek(0) #将文件指针移动到第某个字节
print(file1.readline()) #读取当前文件指针所指的这一行
file1.seek(0)
print(file1.readlines()) #读取每一行，返回一个列表，每一行作为一个列表的元素

file2=open('b.txt','a') #以追加打开该文件
file2.write('hello') #写入内容
file2.flush() #缓冲区写入文件，但不关闭
file2.writelines(['hello','python']) #不添加换行符写入列表

file1.close() #缓冲区写入文件，同时关闭文件
file2.close()
```

## with语句（上下文管理器）

- 好处：不用再写关闭文件的操作

```py
#只要跳出with之后就会自动关闭文件
print(type(open('aaa.txt','r',encoding='UTF-8')))
with open('aaa.txt','r',encoding='UTF-8') as file:
    print(file.read())
'''
MyContenMgr实现了特殊方法__enter__(),__exit__()称该类对象遵守了上下文管理器协议
该类对象的实例对象，称为上下文管理器
MycontenMgr()
'''

class MyContenMgr():
    def __enter__(self):
        print('enter被调用')
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        print('exit被调用')
    def show(self):
        print('show被调用',1/0)  #即使错误，也会调用exit方法


with MyContenMgr() as file1:
    file1.show()
```

## os模块



![image-20230917160430040](.\image-20230917160430040.png)

```py
#os模块与操作系统相关的一个模块
import os
#打开文件
'''
os.system('notepad.exe')
os.system('calc.exe')
#直接调用可执行文件
os.startfile('IMG_20230818_091716.jpg')
'''
#获取当前文件目录（文件夹
print(os.getcwd())
#返回某个文件的目录[list类型]
print(os.listdir('../demo'))
#创建目录（文件夹
os.mkdir('newdir')
#创建多级目录（文件夹
os.makedirs('A/B/C')
#删除目录,只能删除空目录
os.rmdir('newdir')
#删除多级目录
os.removedirs('A/B/C')
#将path设置为当前的工作目录
os.chdir('C:\\Users\\32035\\PycharmProjects\\pythonProject\\demo')
print(os.getcwd())
```

- os.path模块操作目录相关函数

![image-20230917163017431](.\image-20230917163017431.png)

```py
import os.path
#获取文件的绝对路径
print(os.path.abspath('demo1.py'))
#判断文件是否存在
print(os.path.exists('demo1.py'),os.path.exists('demo2.py'))
#拼接路径和文件名
print(os.path.join('E:\\Python\\465\\123','demo13.py')) #E:\Python\465\123\demo13.py
#分离路径和文件名
print(os.path.split('E:\\Python\\demo13.py'))#('E:\\Python', 'demo13.py')
#分离后缀和其他字符
print(os.path.splitext('E:\\Python\\demo13.py'))#('E:\\Python\\demo13', '.py')
#提取文件名
print(os.path.basename('E:\\Python\\demo13.py')) #demo13.py
#提取路径
print(os.path.dirname('E:\\Python\\demo13.py')) #E:\Python
#判断是否是路径
print(os.path.isdir('E:\\Python\\demo13.py')) #False
```

```py
import os

path = os.getcwd()
lst = os.walk(path)
#获取该目录的所有文件
for dirpath,dirname,filename in lst:
    '''
    print(dirpath) #当前文件地址
    print(dirname) #子文件夹
    print(filename) #当前文件夹的文件名
    print('------------')
    '''
    for dir in dirname:
        print(os.path.join(dirpath,dir))
    for file in filename:
        print(os.path.join(dirpath,file))
    print('------------')
```

# 19.学生管理系统

- 需求分析

![image-20230917195435629](.\image-20230917195435629.png)

- 系统设计

![image-20230917195505577](.\image-20230917195505577.png)

![image-20230917195520517](.\image-20230917195520517.png)

- 主函数设计

![image-20230917195901381](.\image-20230917195901381.png)

- 录入学生信息

![image-20230917200814748](.\image-20230917200814748.png)

- 删除学生信息

![image-20230917203353472](.\image-20230917203353472.png)

- 修改学生信息~~（自己写的代码与delete类似）~~

![image-20230917211435827](.\image-20230917211435827.png)

- 查询学生信息

![image-20230919105810744](.\image-20230919105810744.png)

剩余内容自行阅读代码

- 项目打包

