## javascirpt basic

* 1、对一个数组末尾追加数据的简便方法是通过push()功能。
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

* 13、不等式运算符（！=）与相等运算符相反。它的意思是“不相等”，在相等返回true时返回false，反之亦然。与相等运算符一样，不等式运算符将在比较时转换值的数据类型。

```js
1 != 2      // true
1 != "1"    // false
1 != '1'    // false
1 != true   // false
0 != false  // false
```

* 14、严格的不等式算子（！=）与严格相等运算符相反。它的意思是“严格不相等”，在严格相等返回true时返回false，反之亦然。严格的不等式不会转换数据类型。

```js
3 !== 3   // false
3 !== '3' // true
4 !== 3   // true
```
* 15、有时你需要一次测试不止一件事。逻辑和运算符（&&）返回true，当且仅当它的左、右操作数为真时才返回。
如果将if语句嵌套在另一个语句中，则可以实现同样的效果：
```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```
只返回“是”，如果数字介于6和9之间（包括6和9）。同样的逻辑可以写为：
```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```
* 16、逻辑或操作符（| |）返回true，如果操作数是真实的。否则，它返回false。
```js
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```
或者

```js
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```
* 17、如果有许多选项可供选择，请使用开关语句。开关语句测试一个值，可以有许多case语句，它定义了各种可能的值。语句从第一个匹配的case值执行，直到遇到中断。

```js
function caseInSwitch(val) {
var answer = "";
// Only change code below this line
switch (val){
case 1:
answer = "alpha";
break;
case 2:
answer = "beta";
break;
case 3:
answer = "gamma";
break;
case 4:
answer = "delta";
break;
}

// Only change code above this line
return answer;
}

// Change this value to test
caseInSwitch(1);
```
* 18、在转换语句中，您可能无法指定所有可能的值作为case语句。相反，您可以添加默认语句，如果没有匹配的case语句，则将执行该语句。将其视为if / if链中的最后一条语句。默认语句应该是最后一个例子。
```js
function switchOfStuff(val) {
  var answer = "";
  // Only change code below this line
  switch(val){
    case "a":
      answer ="apple"; 
      break;
      
    case "b":
      answer="bird"; 
      break;
      
    case "c":
      answer="cat"; 
      break;
      
    default:
      answer="stuff"; 
      break;
      
  }
  
  
  // Only change code above this line  
  return answer;  
}

// Change this value to test
switchOfStuff(1);

```
* 19、如果从一个开关语句的case中省略了break，则在遇到中断之前执行以下case语句。如果具有相同输出的多个输入，可以在像这样的开关语句中表示它们：
```js
function sequentialSizes(val) {
  var answer = "";
  // Only change code below this line
  switch(val){
    case 1:
    case 2:
    case 3:
    answer = "Low";
    break;
    case 4:
    case 5:
    case 6:
    answer = "Mid";
    break;
    case 7:
    case 8:
    case 9:
    answer = "High";
  
  }
  
  
  // Only change code above this line  
  return answer;  
}

// Change this value to test
sequentialSizes(1);

```
* 20 如果有许多选项可供选择，那么切换switch语句可以比许多链式if语句更容易编写。以下：
```js
function chainToSwitch(val) {
  var answer = "";
  // Only change code below this line
  
  if (val === "bob") {
    answer = "Marley";
  } else if (val === 42) {
    answer = "The Answer";
  } else if (val === 1) {
    answer = "There is no #1";
  } else if (val === 99) {
    answer = "Missed me by this much!";
  } else if (val === 7) {
    answer = "Ate Nine";
  }
  
  // Only change code above this line  
  return answer;  
}
```
可替换为
```js

function chainToSwitch(val) {
var answer = "";
  
switch (val) {
case "bob":
answer = "Marley";
break;
case 42:
answer = "The Answer";
break;
case 1:
answer = "There is no #1";
break;
case 99:
answer = "Missed me by this much!"; 
break; 
case "John":
answer = "";
break;
case 156:
answer = ""; 
break;
default:
answer = "Ate Nine";
} 
return answer; 
}
// Change this value to test
chainToSwitch(7);
```
