## js压缩、混淆和加密
* 最近看到有些论坛在讨论js压缩、混淆和加密的问题，特意找了些资料看了下，现在总结一下：

* 1.关于三者的定义与区别

* 压缩：删除 Javascript 代码中所有注释、跳格符号、换行符号及无用的空格，从而压缩 JS 文件大小，优化页面加载速度。

* 混淆：经过编码将变量和函数原命名改为毫无意义的命名（如function(a,b,c,e,g)等），以防止他人窥视和窃取 Javascript 源代码，也有一定压缩效果。

* 加密：一般用eval方法加密，效果与混淆相似，也做到了压缩的效果。  

 从定义中可以看出，压缩的主要目的是消除注释等无用字符，达到精简js代码，减小js文件大小的目的，这也是页面优化的一种方式；而混淆和加密的目的比较接近，都是为了防止他人直接查看源码，对代码（如重要的api等）起保护作用，但这也只是增加了阅读代码的代价，也就是所谓的防君子不防小人。但是当混淆和加密联合使用时，如先混淆在加密（或者先加密再混淆）时，破解时间就会增加。关于js的加密，可以参考这篇文章：http://www.cnblogs.com/top5/archive/2009/08/07/1540860.html

2.demo

下面以更直观的方式来体会一下这四种方式（压缩、混淆、加密、混淆&加密）的不同。

源js代码如下：


复制代码
 1 /* 这个是一个类 */
 2 
 3 function xx(num, str) {
 4     //说明
 5     var a = num;
 6     this.aa = a;
 7     this.bb = function() {alert(str);}
 8     this.cc = function() {
 9         for (var i = 0; i < 10; i++) {
10             document.title = i;
11         }
12     }
13     this.yy = new yy();
14     function xxf() {
15         alert("xxf");
16         if ((/\{\d+\}/).test("a\sdf{2}ab"))
17             alert("{\\d} is match!");
18     }
19 }
20 xx.prototype.dd = function(){
21     alert("dd");
22     a.yy.ll();
23     var fnx = function(i) {
24         this.ab = i;
25         this.aa = function(){
26             alert(this.ab);
27         }
28     }
29     var f1 = new fnx(1);
30     f1.aa();
31 }
32 
33 function yy(){
34     alert('yy');
35 }
36 yy.prototype.ll = function() {
37     alert("yyll");
38 }
39 
40 var a = new xx(100, "hello"), b = new xx(0, "ttyp");
41 eval("a.aa=20");
42 a.bb();
43 b.dd();
44 alert(a.aa);
45 
46 var k = 9;
47 function kk() {
48     var k = 0;
49     alert(k);
50 }
51 kk();
52 alert(k);
53 //输入结果alert:"yy"->"yy"->"hello"->"dd"->"yyll"->"12"->"20"->"0"->"9"
复制代码
（1）经过压缩后的代码如下：

1 function xx(num,str){var a=num;this.aa=a;this.bb=function(){alert(str)};this.cc=function(){for(var i=0;i<10;i++){document.title=i}};this.yy=new yy();function xxf(){alert("xxf");if((/\{\d+\}/).test("a\sdf{2}ab"))alert("{\\d} is match!")}};xx.prototype.dd=function(){alert("dd");a.yy.ll();var fnx=function(i){this.ab=i;this.aa=function(){alert(this.ab)}};var f1=new fnx(1);f1.aa()};function yy(){alert('yy')};yy.prototype.ll=function(){alert("yyll")};var a=new xx(100,"hello"),b=new xx(0,"ttyp");eval("a.aa=20");a.bb();b.dd();alert(a.aa);var k=9;function kk(){var k=0;alert(k)};kk();alert(k);
压缩后与源码相比只是少了注释、空格、换行等。

（2）经过混淆后的代码如下：

1 function xx(d,e){var f=d;this.aa=f;this.bb=function(){alert(e)};this.cc=function(){for(var g=0;g<10;g++){document.title=g}};this.yy=new yy();function xxf(){alert("xxf");if((/\{\d+\}/).test("a\sdf{2}ab"))alert("{\\d} is match!")}};xx.prototype.dd=function(){alert("dd");a.yy.ll();var fnx=function(e){this.ab=e;this.aa=function(){alert(this.ab)}};var d=new fnx(1);d.aa()};function yy(){alert('yy')};yy.prototype.ll=function(){alert("yyll")};var a=new xx(100,"hello"),b=new xx(0,"ttyp");eval("a.aa=20");a.bb();b.dd();alert(a.aa);var c=9;function kk(){var d=0;alert(d)};kk();alert(c);
混淆后除了少了注释、空格和换行等，参数也被a，b，c，d，e等字符代替，提高了阅读的难度。

（3）经过加密后的代码如下：

1 eval(function(p,a,c,k,e,d){e=function(c){return(c<a?"":e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--)d[e(c)]=k[c]||e(c);k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1;};while(c--)if(k[c])p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c]);return p;}('3 e(o,l){5 a=o;6.8=a;6.p=3(){4(l)};6.B=3(){A(5 i=0;i<y;i++){x.z=i}};6.7=c 7();3 j(){4("j");t((/\\{\\d+\\}/).s("a\\u{2}g"))4("{\\\\d} w v!")}};e.r.f=3(){4("f");a.7.h();5 n=3(i){6.g=i;6.8=3(){4(6.g)}};5 m=c n(1);m.8()};3 7(){4(\'7\')};7.r.h=3(){4("D")};5 a=c e(F,"H"),b=c e(0,"G");E("a.8=C");a.p();b.f();4(a.8);5 k=9;3 q(){5 k=0;4(k)};q();4(k);',44,44,'|||function|alert|var|this|yy|aa||||new||xx|dd|ab|ll||xxf||str|f1|fnx|num|bb|kk|prototype|test|if|sdf|match|is|document|10|title|for|cc|20|yyll|eval|100|ttyp|hello'.split('|'),0,{}))
加密后除了有混淆的作用外，有些代码被加密了，进一步提高了阅读的难度。

（4）经过混淆&加密后的代码如下

1 eval(function(p,a,c,k,e,d){e=function(c){return(c<a?"":e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--)d[e(c)]=k[c]||e(c);k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1;};while(c--)if(k[c])p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c]);return p;}('4 i(d,e){5 f=d;6.8=f;6.p=4(){3(e)};6.s=4(){t(5 g=0;g<y;g++){G.F=g}};6.7=h 7();4 l(){3("l");x((/\\{\\d+\\}/).v("a\\u{2}j"))3("{\\\\d} w r!")}};i.o.k=4(){3("k");a.7.m();5 n=4(e){6.j=e;6.8=4(){3(6.j)}};5 d=h n(1);d.8()};4 7(){3(\'7\')};7.o.m=4(){3("E")};5 a=h i(A,"z"),b=h i(0,"B");D("a.8=C");a.p();b.k();3(a.8);5 c=9;4 q(){5 d=0;3(d)};q();3(c);',43,43,'|||alert|function|var|this|yy|aa|||||||||new|xx|ab|dd|xxf|ll|fnx|prototype|bb|kk|match|cc|for|sdf|test|is|if|10|hello|100|ttyp|20|eval|yyll|title|document'.split('|'),0,{}))
3.浏览器是怎么解析混淆和加密后的js代码的

其实变量名只要是Unicode字符就行了，对于js引擎来说都是一样的，只是人类觉得他们不同而已。

4.js压缩工具
在线代码格式化:
http://jsbeautifier.org/

JS混淆加密压缩 
http://tool.chinaz.com/js.aspx

在线UglifyJS：
http://marijnhaverbeke.nl/uglifyjs/

在线Closure Compressor：(请FQ)
http://closure-compiler.appspot.com/home

在线YUI Compressor：
http://tool.oschina.net/jscompress
