# js对象与对象属性

## JavaScript对象

+ 对象是一种**复合值**：将很多值复合在一起（包括原始类型值、对象、函数）
+ 对象是若干**无序属性的集合**，可以直接通过属性名来访问对象的属性（键值对）
+ 函数作为某一个对象的属性时，称其为该对象的方法



查询原型对象符

![1552637798011](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1552637798011.png)

## 数据属性的特性

+ **value**(属性的值)：对应属性的值
+ **writable**(可写特性)：确定属性是否可改写性
+ **configurable**(可配置特性)：确定属性是否删除和其他特性是否可配置
+ **enumerable**(可枚举特性)：属性是否枚举

## 属性描述符

+ 用来查看对象属性的特性的对象，**该对象包含4个属性，对应4个特性**
+ 封装了属性特性的**对象**，方便实现数据属性特性的**设置和查询**

## 设置属性描述符：Object.defineProperty（obj，prop，descriptor）

+ ### obj—要在其上定义属性的对象

+ ### prop—要定义或修改的属性的名称

+ ### descriptor—将被定义或修改的属性描述符

  + value默认为undefined
  + enumerable、writable、configurable默认为false

![1553770429916](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553770429916.png)

![1553770445220](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553770445220.png)



### 字面量定义默认属性特性为true

![1553770721197](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553770721197.png)



## 查询属性描述符：

### 查询对象的一个属性Object.getOwnPropertyDescriptor(obj,prop) 方法

+ 返回指定对象上一个自有属性对应的属性描述符。
+ **obj —— 需要查找的目标对象**
+ **prop —— 目标对象内属性名称**

![1553770822861](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553770822861.png)

### 查询对象的所有属性Object.getOwnPropertyDescriptors(obj)

![1553771945290](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553771945290.png)



## 枚举性

+ ### enumerable：枚举性

  #### 一般来说，系统创建的属性不可枚举，而用户创建的属性可枚举

  通常不应该给内置原型和对象添加属性和方法。如果需要添加，应该设置属性不可枚举，避免破坏现有代码

  #### 枚举的主要目的是判断 for-in 循环中的那些属性应该被忽略

+ #### 枚举性影响的操作

  + for-in 循环
  + Object.keys()
  + JSON.stringify()

+ #### 查询属性的可枚举性obj.propertyIsEnumerable(prop)

  返回一个布尔值，表示指定的属性是否可枚举。

## 可配置性

+ #### configurable：可配置特性
   确定属性是否能删除和其他特性是否可配置

  ![1553773004018](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553773004018.png)

## 定义属性

+ ### 如果属性已经存在，会更新描述符指定的属性特性。但是描述符中的特性没有对应的特性，则特性不变。

![1553773188959](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553773188959.png)

+ ### 如果属性不存在，会创建一个新的属性，它的特性由描述符指定，若果未指定，则使用默认值。

![1553773230945](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553773230945.png)





## 访问器属性的特性

