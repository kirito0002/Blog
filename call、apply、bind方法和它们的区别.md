# call、apply、bind方法和它们的区别

+ ## call方法

  **call() 方法调用一个函数, 其具有一个指定的 this 值和分别地提供的参数(参数列表) —— fn.call(thisObj,arg1,arg2,...)**

  + **thisObj: 将函数对象中的 this 指向 thisObj 对象**
    + **如果未传递，this 指向全局对象 window**
    + **如果传递为 undefined/null，this 指向全局对象 window**
    + **如果传递为原始值(数字，字符串，布尔值)，this 指向该原始值的包装对象**
  + **arg1,arg2,...: 被调用函数的实参**

  ![1553443851286](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553443851286.png)

+ ## apply方法（会执行调用这个方法的函数里的代码）

  **apply() 方法调用一个函数, 其具有一个指定的 this 值和作为数组提供的参数(参数数组) —— fn.apply(thisObj,[arg1,arg2,...])**

  执行原来的函数，this指向thisObj（执行代码）

  + **thisObj: 将函数对象中的 this 指向 thisObj 对象**
    + **如果未传递，this 指向全局对象 window**
    + **如果传递为 undefined/null，this 指向全局对象 window**
    + **如果传递为原始值(数字，字符串，布尔值)，this 指向该原始值的包装对象**
  + **[arg1,arg2,...] : 被调用函数的实参**

![例子](https://i.imgur.com/su7YX8k.png)

+ ## bind方法

  + **bind() 方法创建一个新的函数，在调用时设置 this 关键字为提供的值。并在调用新函数时，将给定参数列表作为原函数的参数序列的前若干项 —— fn.bind(thisObj,arg1,arg2,...)**
  + **返回值：返回一个原函数的拷贝，并拥有指定的this值和初始参数。**

