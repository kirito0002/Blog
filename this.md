# this

## 当前函数的this是在函数被调用执行的时候才确定

+ ## this特点

  + 函数的调用方式决定了this的值，**运行期间**绑定
  + 每次函数调用时this的值可能会不同
  + this不能被赋值
  + this不进行作用域传递

+ ## this的绑定规则：new绑定＞显示绑定＞隐式绑定＞默认绑定

  

  ### 默认绑定

  + **非严格模式**，this会绑定到**全局对象window**上。

    ```javascript
    var a = 2;
    function foo() {
        console.log(this);//Window{}
        console.log(this.a);//2
    }
    foo();//2
    ```

    

  + **严格模式**，this会绑定到**undefined**。

    ```javascript
    var a = 2;
    function foo() {
        "use strict"
        console.log(this);//undefined
        console.log(this.a);//TypeError:Cannot read property "a" of a undefined
    }
    foo();
    ```

  + **函数嵌套时，this绑定**

    + 变量_this、that、self锁定this

    + bind()锁定

      ![1553760102320](https://img.545141.com/images/201903/3df9b00224958b28.png)

  ## 隐式绑定

  + **调用位置是否有上下文对象**

    + 函数作为对象的方法调用时，函数上下文指向这个对象。

      ```javascript
      var a = 100;
      var obj = {
          a:300,
          fun: function(){
              console.log(this.a);
          }
      };
      obj.fun();//300
      ```

    + 数组中存放函数，**被数组索引调用**。this上下文**指向这个数组**

      ```javascript
      function fun(){
          console.log(this.length);
      }
      var length = 10;
      var arr = [100, 200, fun];
      fun();//10
      arr[2]();//3
      ```

  + **隐式绑定——就近原则**

    + 对象属性引用链中只有最顶层或者最后一层就影响调用位置

      ```javascript
      function foo(){
          console.log(this.a);
      }
      var obj2 = {
          a:42;
          foo:foo
      };
      var obj1 = {
          a: 2;
          obj2: obj2 
      };
      obj1.obj2.foo();//42  离obj2最近所以this指向obj2
      ```

      

  

  

  ## 显示绑定

  ###      使用call（）、apply（）、bind（）方法显示改变this的指向为指定对象

  

  

  ## new绑定

  + ### new来调用函数，或者说发生构造函数调用时，会自动执行下面的操作。

    + **创建（或者说构造）一个全新的对象**
    + **这个对象会被执行[[原型]]连接**
    + **这个新对象会绑定到函数调用的this**
    + **如果函数没有返回其他对象，那么new表达式中的函数调用会自动返回this（新对象）**

    ![1553763019680](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1553763019680.png)

  

## 绑定优先级

+ ### new绑定＞显示绑定＞隐式绑定＞默认绑定

+ ### 判断this的顺序

  + **函数是否在new中调用？如果是的话this绑定的是新创建的对象**
  + **函数是否通过call、apply、bind调用？如果是的话this绑定的是指定的对象**
  + **函数是否在某个上下文对象中调用（隐式绑定）？如果是的话，this绑定的是那个上下文对象**
  + **如果都不是的话，使用默认绑定。如果在严格模式下，就绑定到 undefined，否则绑定到全局对象**

