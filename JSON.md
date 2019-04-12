# JSON（JavaScript Object Notation）

+ **JavaScript 对象表示法**

+ **是轻量级的文本数据交换格式**

+ **更小、更快，更易解析**

+ **是一种数据格式，不是编程语言**

  虽然具有相同的语法形式，但 JSON 并不从属于 JavaScript
   并不是只有 JavaScript 才使用 JSON，JSON 只是一种数据格式
   很多编程语言都有针对 JSON 的解析器和序列化器



## JSON语法

+ **并列的数据之间用逗号（", "）分隔**
+ **并列数据的集合（数组）用方括号("[]")表示**
+ **映射用冒号（": "）表示**
+ **映射的集合（对象）用大括号（"{}"）表示**
+ 字符串必须加**双引号**

![1555002607281](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555002607281.png)

### JSON 语法可以表示以下三种类型的值

》**简单值** 

+ 与 JavaScript 语法相同，可以在 JSON 中表示字符串、数值、布尔值和 null。

+ JSON 不支持 JavaScript 中的特殊值 undefined。

》**对象** 

+ 一种复杂数据类型，表示一组**无序**的键值对。
+ 键值对中的值可以是任意类型——简单值、对象或数组。

》**数组** 

+ 一种复杂数据类型，表示一组**有序**的值的列表。
+ 数组的值可以是任意类型——简单值、对象或数组。



### JSON与JS对象

+ **JavaScript Object Notation，JS对象标记**

+ JSON 是 JavaScript 对象的字符串形式的表示法，使用文本表示 JavaScript  对象的信息，**本质是一个字符串**

~~~javascript
var obj = {a:'Hello',b:'world'};//这是一个对象，注意键名也是可以使用引号包裹的
var json = {"a":"Hello","b":"world"};//这是一个JSON字符串，本质是一个字符串
~~~





### JSON静态方法

#### JSON.stringify(object [,replacer [,space] ] )方法   JS-->JSON

+ 把 **JavaScript 对象**格式转化为 **JSON 字符串**
+ undefined 值会被忽略
+ **object：指定转换对象**
+ **replacer**：参数过滤器为数组时，结果只包含数组中列出的属性

![1555004006001](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004006001.png)

+ replacer：参数过滤器为**函数**时，需接受两个参数，属性键名和属性值

![1555004035315](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004035315.png)

+ **space**:参数为**数值**时，表示每个级别缩进的空格数

![1555004377346](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004377346.png)

+ **space**：参数为**字符串**时，使用字符串作为缩进字符

![1555004455316](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004455316.png)



#### JSON.parse(json [,reviver])方法  JSON-->JS

+ 把**JSON字符串**解析为原生**JavaScript对象**
+ **json：参数必须是有效的 JSON，否则会报错**

![1555004814952](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004814952.png)

+ **reviver**：参数过滤器为**函数**时，需接受两个参数，属性键名和属性值

![1555004947110](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555004947110.png)