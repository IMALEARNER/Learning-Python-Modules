#!/usr/bin/env python
# -*- coding:utf-8 -*-

###### Title: Python Numpy Note01
##### Time: 19-9-20
##### Author: I'm'a'learner


##################################################
###### 1.1 Numpy数据结构：ndarray（数组）

### 回顾Python内置的常用数据结构：整数，字符串，列表，元组，字典，……
# list:  []  list是一种有序的集合，可以随时添加和删除其中的元素 (可变的有序表)
# tuple: ()  tuple有序，但其中的元素一经初始化便无法修改
# dict: {}   按照key-value的形式存储，dict内部元素存储的顺序与key放入的顺序无关
# set：([])  set和dict类似，也是一组key的集合，但不存储value, key不能重复

### Numpy模块提供的新的数据结构： ndarray
# nd: n dimension，表示对象具有n维
# 数组的索引以0为下标开始
# 存放的数据需要是同一类型

### 创建ndarray的方法:array函数
np.array(object, dtype, copy, order, subok, ndmin)
# object：数组存储的对象（必选）
# dtype: 输出数组的数据类型
# copy：对象是否需要复制
# order：创建数组的样式。C：按行方向，F：按列，A：任意方向（default）
# subok：subok 默认情况下，返回的数组被强制为基类数组。 如果为true，则返回子类
# ndmin: 指定生成数组的最小维度
import numpy as np
a = np.array([1,2,3,4],ndmin=2)
b = np.array([[1,2],[3,4]],dtype = complex)
print(a)   ## [[1 2 3 4]]
print('number of dim:',a.ndim)   ## number of dim: 2
print('shape:', a.shape)  ## shape: (1, 4)
print('size:', a.size)  ## size: 4
print(b)
## [[1.+0.j 2.+0.j]
##  [3.+0.j 4.+0.j]]

### 创建ndarray的其他方法:empty函数/zeros函数/ones函数
numpy.empty(shape, dtype, order)
numpy.zeros(shape, dtype, order)
numpy.ones(shape, dtype, order)
# shape: 制定数组形状
# 数组元素初始值为随机值，需进行人为初始化
import numpy as np
x = np.empty([3,3],dtype=float)
print(x)

### 将其他已有数据转化为ndarray
# asarray函数
numpy.asarray(a, dtype, order)
# a: 任意形式的输入参数。可以是list,tuple,多维ndarray
# 例子：
import numpy as np
x = (1, 2, 3)
a = np.asarray(x)
print(a)  ## [1 2 3]

# frombuffer函数：实现动态数组
numpy.frombuffer(buffer, dtype, count, offset)
# buffer:将任意对象以流的形式读入
# count:读取的数据数量，默认为-1，读取所有数据
# offset:读取的起始位置，默认为0

# fromiter函数：实现可迭代对象
numpy.fromiter(iterable, dtype, count)
# iterable:可迭代对象
# 例子：
import numpy as np
list = range(10)
it = iter(list)
x = np.fromiter(it, dtype=float)
print(x)

### 创建数组-序列
# 创建给定步长序列
numpy.arange(start, stop, step, dtype)
# step：给定步长，默认为1
# 例子：
import numpy as np
x = np.arange(10,19,2)
print(x)  ## [10 12 14 16 18]
# 创建等差序列
np.linspace(start, stop, num, endpoint, retstep, dtype)
# num:等步长的样本数量，默认为50
# endpoint：该值为Ture则数列中中包含stop值。默认True
# retstep： 为True时，生成的数组中会显示间距
# 例子：
import numpy as np
a = np.linspace(1,10,10)
print(a)  ## [ 1.  2.  3.  4.  5.  6.  7.  8.  9. 10.]
# 创建等比序列
np.logspace(start, stop, num=50, endpoint=True, base=10.0, dtype=None)
# stop：序列的终止值为base ** stop
# base: 对数 log 的底数
# 例子：
import numpy as np
a = np.logspace(0,9,10,base=2)
print (a)  ## [  1.   2.   4.   8.  16.  32.  64. 128. 256. 512.]


##################################################
##### 1.2 数组基本属性和函数

### 数组的秩（维数）：ndarray.ndim
import numpy as np
a = np.array([1,2,3,4,5,6])
b = np.array([[1,2],[3,4],[5,6]])
print(a.ndim)  ## 1
print(b.ndim)  ## 2
### 数组的维度：ndarray.shape
# a.reshape(m,n,p)  # 将a变为三个维度，m*n*p矩阵
### 数组元素的个数：ndarrary.size
### 数组元素的字节大小：ndarray.itemsize
### 数组元素的内存信息：ndarray.flags
# 返回与数组及其元素内存信息相关的多个布尔型标记（略）
### 数组元素的实部/虚部：ndarray.real / ndarray.imag


##################################################
##### 1.3 数组元素数据类型

### Numpy支持比Python更多种类的数值类型, 基本可以与C语言提供的数据类型相对应
# bool_, int_, intc, uint64, float64, complex128……
### 每个内建类型都有一个唯一定义它的字符代码
# b:布尔型, i:有符号整型, u:无符号整型, f:浮点型, c:复数浮点型,
# m:时间间隔, M:日期时间, O:对象, S/a:字符串, u:Unicode, v:原始数据

### 控制对象数据类型的函数：dtype函数
numpy.dtype(object, align, copy)
# object: 用以转换数据类型的对象
# align: 如果为True,填充字段使其类似 C 的结构体
# copy: 复制对象,如果为False则引用对象

# 例子：
import numpy as np
dt_int = np.dtype(np.intc)
dt_age = np.dtype([('age',np.int8)])
a = np.array([(10,),(20,),(30,)], dtype = dt_age)
print(dt_int)  ## int32
print(a['age'])  ## [10 20 30]


##################################################
###### 1.4 数组切片和索引


##################################################
##### 太长不看版-函数总结 (待补充)
import numpy as np
np.ndarray()


