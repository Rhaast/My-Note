## javascirpt basic

* ��һ������ĩβ׷�����ݵļ�㷽����ͨ��push()���ܡ�
```js  
  var arr = [1,2,3];
    arr.push(4);
    //arr is now [1,2,3,4].
```
 
* ɾ�����������һ�������Ĺ��ܣ���.pop()
    var myArray = [["John",23],["cat",2]];
    var removedFromMyArray =myArray.pop();
    
3��ɾ�������е�һ�������Ĺ��ܣ���.shift()
    var myArray = [["John", 23], ["dog", 3]];
    var removedFromMyArray = myArray.shift();
 
4��.unshift()���ܿ������.shift()ʹ�ã�������ӱ�ɾ���ĵ�һ��Ԫ�ء�
    var ourArray = ["Stimpson", "J", "cat"];
    ourArray.shift(); // ourArray now equals ["J", "cat"]
    ourArray.unshift("Happy"); 
    // ourArray now equals ["Happy", "J", "cat"]
 
5��������ά���飬ÿ���������еĵ�һ��Ԫ��Ӧ�ð���һ���������Ƶ��ַ������ڶ���Ԫ��Ӧ���Ǵ������������֡�
    var myList = [["phone",1],
             ["computer",2],
             ["kindle",3],
             ["ipad",4],
             ["swatch",5]];
             
6����JavaScript�У����ǿ��Խ����뻮��Ϊ�����õĲ��֣���Ϊ������
�����Ǻ�����һ�����ӣ�
    function functionName() {
                        console.log("Hello World");
    }
 
7�������������ı����Լ������������оֲ�������Ҳ����˵������ֻ���Ǹ������пɼ���
    function myTest() {
                        var loc = "foo";
                        console.log(loc);
    }
    myTest(); // "foo"
    console.log(loc); // "undefined"
    
8��������ͬ���Ƶı��ر�����ȫ�ֱ������ǿ��ܵġ�ִ�д˲���ʱ�����ر���������ȫ�ֱ�����
   var someVar = "Hat";
   function myFun() {
   var someVar = "Head";
   return someVar;
}
9�����ǿ��Խ�ֵ���ݵ��������ĺ����С�����ʹ�÷�����佫ֵ�Ӻ����д��ء�
    function plusThree(num) {
      return num + 3;
    }
    var answer = plusThree(5); // 8
    
10����һ�����������ǲ����͡�����ֵ����ֻ������ֵ��true��false�����ǻ����϶���С���أ����е����ǡ����������ǡ�OFF����������״̬�ǻ���ġ�
ע��
����ֵ�Ӳ�������д���ַ�����true���͡�false�����ǲ�����������JavaScript��û�����⺬��
 
11��JavaScript���кܶ�Ƚ��������������Щ����������һ������true��falseֵ��
�������������ǵȺ������==�����������Ƚ�����ֵ�����������Ȼ�false���򷵻�true��ע�⣬��ʽ��ͬ�ڸ�ֵ��=���������������ұߵ�ֵ��ֵ����ߵı�����
    function equalityTest(myVal) {
           if (myVal == 10) {
            return "Equal";
                        }
          return "Not Equal";
    }
 
12���ϸ���ȣ�= =��������������=���Ķ�Ӧ��������������ͬ���ϸ���Ȳ��ԱȽ�Ԫ�ص��������ͺ�ֵ
function testStrict(val) {
  if (val===7) { // Change this line
    return "Equal";
  }
  return "Not Equal";
}