# 数组原型方法forEach()、every()、some()#



# (迭代——非破坏性)

## Array.prototype.forEach(callback,thisValue?)

方法对数组的每个元素执行一次提供的函数。

```javascript
var array1 = ['a', 'b', 'c'];

array1.forEach(function(element) {
  console.log(element);
});

// expected output: "a"
// expected output: "b"
// expected output: "c"
```

**callback**:为数组中每个元素执行的函数，该函数接收三个参数

**thisArg**:可选参数。当执行回调函数时用作 `this` 的值(参考对象)。

## **Array.prototype.every(callback,thisValue?)** 方法测试数组的所有元素是否都通过了指定函数的测试。

+ ## callback

  用来测试每个元素的函数。

+ ## thisArg

  执行 `callback` 时使用的 `this` 值。

```javascript
function isBigEnough(element, index, array) {
  return (element >= 10);
}
var passed = [12, 5, 8, 130, 44].every(isBigEnough);
// passed is false
passed = [12, 54, 18, 130, 44].every(isBigEnough);
// passed is true
```



## **Array.prototype.some(callback,thisValue?)** 方法测试是否至少有一个元素通过由提供的函数实现的测试。

```javascript
function isBiggerThan10(element, index, array) {
  return element > 10;
}

[2, 5, 8, 1, 4].some(isBiggerThan10);  // false
[12, 5, 8, 1, 4].some(isBiggerThan10); // true
```

# （迭代-转换方法——非破坏性）

## Array.prototype.map(callback,thisValue?)创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。

## filter()**方法创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。 



```
callback
```

用来测试数组的每个元素的函数。返回 `true` 表示该元素通过测试，保留该元素，`false` 则不保留。它接受一下三个参数：

- `element`

  数组中当前正在处理的元素。

- `index`可选

  正在处理的元素在数组中的索引。

- `array`可选

  调用了 `filter` 的数组本身。

`thisArg`可选

执行 `callback` 时，用于 `this` 的值。