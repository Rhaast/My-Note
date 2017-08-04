## javascirpt basic

* 对一个数组末尾追加数据的简便方法是通过push()功能。
```js  
  var arr = [1,2,3];
    arr.push(4);
    //arr is now [1,2,3,4].
```
 
* 2、删除数组中最后一个函数的功能，用.pop()

```js
    var myArray = [["John",23],["cat",2]];
    var removedFromMyArray =myArray.pop();
 ```
* 3、删除数组中第一个函数的功能，用.shift()
```js
    var myArray = [["John", 23], ["dog", 3]];
    var removedFromMyArray = myArray.shift();
 ```
* 4、.unshift()功能可以配合.shift()使用，用于添加被删除的第一个元素。

```js
  var ourArray = ["Stimpson", "J", "cat"];
    ourArray.shift(); // ourArray now equals ["J", "cat"]
    ourArray.unshift("Happy"); 
    // ourArray now equals ["Happy", "J", "cat"]
 ```
 
* 5、创建多维数组，每个子数组中的第一个元素应该包含一个带有名称的字符串。第二个元素应该是代表数量的数字。
  
```js
  var myList = [["phone",1],
             ["computer",2],
             ["kindle",3],
             ["ipad",4],
             ["swatch",5]];
```

* 6、在JavaScript中，我们可以将代码划分为可重用的部分，称为函数。
下面是函数的一个例子：
  
```js
  function functionName() {
                        console.log("Hello World");
    }
 ```
 
* 7、函数中声明的变量以及函数参数都有局部作用域。也就是说，它们只在那个函数中可见。
  
```js  
  function myTest() {
                        var loc = "foo";
                        console.log(loc);
    }
    myTest(); // "foo"
    console.log(loc); // "undefined"
 ```
 
* 8、具有相同名称的本地变量和全局变量都是可能的。执行此操作时，本地变量优先于全局变量。
  
```js
  var someVar = "Hat";
   function myFun() {
   var someVar = "Head";
   return someVar;
}
```

* 9、我们可以将值传递到带参数的函数中。可以使用返回语句将值从函数中传回。
  
```js  
  function plusThree(num) {
      return num + 3;
    }
    var answer = plusThree(5); // 8
```

* 10、另一种数据类型是布尔型。布尔值可能只有两个值：true或false。它们基本上都是小开关，其中的真是“开”，假是“OFF”，这两种状态是互斥的。
注：
布尔值从不用引号写。字符串“true”和“false”不是布尔函数，在JavaScript中没有特殊含义
 
* 11、JavaScript中有很多比较运算符。所有这些操作符返回一个布尔true或false值。
最基本的运算符是等号运算符==。相等运算符比较两个值，如果它们相等或false，则返回true。注意，等式不同于赋值（=），它将操作符右边的值赋值给左边的变量。
  
```js
  function equalityTest(myVal) {
           if (myVal == 10) {
            return "Equal";
                        }
          return "Not Equal";
    }
 ```
 
* 12、严格相等（= =）是相等运算符（=）的对应。与相等运算符不同，严格相等测试比较元素的数据类型和值

```js
function testStrict(val) {
  if (val===7) { // Change this line
    return "Equal";
  }
  return "Not Equal";
}
```
