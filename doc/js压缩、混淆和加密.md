jsѹ���������ͼ���
���������Щ��̳������jsѹ���������ͼ��ܵ����⣬��������Щ���Ͽ����£������ܽ�һ�£�

1.�������ߵĶ���������

ѹ����ɾ�� Javascript ����������ע�͡�������š����з��ż����õĿո񣬴Ӷ�ѹ�� JS �ļ���С���Ż�ҳ������ٶȡ�

�������������뽫�����ͺ���ԭ������Ϊ�����������������function(a,b,c,e,g)�ȣ����Է�ֹ���˿��Ӻ���ȡ Javascript Դ���룬Ҳ��һ��ѹ��Ч����

���ܣ�һ����eval�������ܣ�Ч����������ƣ�Ҳ������ѹ����Ч����
���Ӷ����п��Կ�����ѹ������ҪĿ��������ע�͵������ַ����ﵽ����js���룬��Сjs�ļ���С��Ŀ�ģ���Ҳ��ҳ���Ż���һ�ַ�ʽ���������ͼ��ܵ�Ŀ�ıȽϽӽ�������Ϊ�˷�ֹ����ֱ�Ӳ鿴Դ�룬�Դ��루����Ҫ��api�ȣ��𱣻����ã�����Ҳֻ���������Ķ�����Ĵ��ۣ�Ҳ������ν�ķ����Ӳ���С�ˡ����ǵ������ͼ�������ʹ��ʱ�����Ȼ����ڼ��ܣ������ȼ����ٻ�����ʱ���ƽ�ʱ��ͻ����ӡ�����js�ļ��ܣ����Բο���ƪ���£�http://www.cnblogs.com/top5/archive/2009/08/07/1540860.html

2.demo

�����Ը�ֱ�۵ķ�ʽ�����һ�������ַ�ʽ��ѹ�������������ܡ�����&���ܣ��Ĳ�ͬ��

Դjs�������£�


���ƴ���
 1 /* �����һ���� */
 2 
 3 function xx(num, str) {
 4     //˵��
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
53 //������alert:"yy"->"yy"->"hello"->"dd"->"yyll"->"12"->"20"->"0"->"9"
���ƴ���
��1������ѹ����Ĵ������£�

1 function xx(num,str){var a=num;this.aa=a;this.bb=function(){alert(str)};this.cc=function(){for(var i=0;i<10;i++){document.title=i}};this.yy=new yy();function xxf(){alert("xxf");if((/\{\d+\}/).test("a\sdf{2}ab"))alert("{\\d} is match!")}};xx.prototype.dd=function(){alert("dd");a.yy.ll();var fnx=function(i){this.ab=i;this.aa=function(){alert(this.ab)}};var f1=new fnx(1);f1.aa()};function yy(){alert('yy')};yy.prototype.ll=function(){alert("yyll")};var a=new xx(100,"hello"),b=new xx(0,"ttyp");eval("a.aa=20");a.bb();b.dd();alert(a.aa);var k=9;function kk(){var k=0;alert(k)};kk();alert(k);
ѹ������Դ�����ֻ������ע�͡��ո񡢻��еȡ�

��2������������Ĵ������£�

1 function xx(d,e){var f=d;this.aa=f;this.bb=function(){alert(e)};this.cc=function(){for(var g=0;g<10;g++){document.title=g}};this.yy=new yy();function xxf(){alert("xxf");if((/\{\d+\}/).test("a\sdf{2}ab"))alert("{\\d} is match!")}};xx.prototype.dd=function(){alert("dd");a.yy.ll();var fnx=function(e){this.ab=e;this.aa=function(){alert(this.ab)}};var d=new fnx(1);d.aa()};function yy(){alert('yy')};yy.prototype.ll=function(){alert("yyll")};var a=new xx(100,"hello"),b=new xx(0,"ttyp");eval("a.aa=20");a.bb();b.dd();alert(a.aa);var c=9;function kk(){var d=0;alert(d)};kk();alert(c);
�������������ע�͡��ո�ͻ��еȣ�����Ҳ��a��b��c��d��e���ַ����棬������Ķ����Ѷȡ�

��3���������ܺ�Ĵ������£�

1 eval(function(p,a,c,k,e,d){e=function(c){return(c<a?"":e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--)d[e(c)]=k[c]||e(c);k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1;};while(c--)if(k[c])p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c]);return p;}('3 e(o,l){5 a=o;6.8=a;6.p=3(){4(l)};6.B=3(){A(5 i=0;i<y;i++){x.z=i}};6.7=c 7();3 j(){4("j");t((/\\{\\d+\\}/).s("a\\u{2}g"))4("{\\\\d} w v!")}};e.r.f=3(){4("f");a.7.h();5 n=3(i){6.g=i;6.8=3(){4(6.g)}};5 m=c n(1);m.8()};3 7(){4(\'7\')};7.r.h=3(){4("D")};5 a=c e(F,"H"),b=c e(0,"G");E("a.8=C");a.p();b.f();4(a.8);5 k=9;3 q(){5 k=0;4(k)};q();4(k);',44,44,'|||function|alert|var|this|yy|aa||||new||xx|dd|ab|ll||xxf||str|f1|fnx|num|bb|kk|prototype|test|if|sdf|match|is|document|10|title|for|cc|20|yyll|eval|100|ttyp|hello'.split('|'),0,{}))
���ܺ�����л����������⣬��Щ���뱻�����ˣ���һ��������Ķ����Ѷȡ�

��4����������&���ܺ�Ĵ�������

1 eval(function(p,a,c,k,e,d){e=function(c){return(c<a?"":e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--)d[e(c)]=k[c]||e(c);k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1;};while(c--)if(k[c])p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c]);return p;}('4 i(d,e){5 f=d;6.8=f;6.p=4(){3(e)};6.s=4(){t(5 g=0;g<y;g++){G.F=g}};6.7=h 7();4 l(){3("l");x((/\\{\\d+\\}/).v("a\\u{2}j"))3("{\\\\d} w r!")}};i.o.k=4(){3("k");a.7.m();5 n=4(e){6.j=e;6.8=4(){3(6.j)}};5 d=h n(1);d.8()};4 7(){3(\'7\')};7.o.m=4(){3("E")};5 a=h i(A,"z"),b=h i(0,"B");D("a.8=C");a.p();b.k();3(a.8);5 c=9;4 q(){5 d=0;3(d)};q();3(c);',43,43,'|||alert|function|var|this|yy|aa|||||||||new|xx|ab|dd|xxf|ll|fnx|prototype|bb|kk|match|cc|for|sdf|test|is|if|10|hello|100|ttyp|20|eval|yyll|title|document'.split('|'),0,{}))
3.���������ô���������ͼ��ܺ��js�����

��ʵ������ֻҪ��Unicode�ַ������ˣ�����js������˵����һ���ģ�ֻ������������ǲ�ͬ���ѡ�

4.jsѹ������
���ߴ����ʽ��:
http://jsbeautifier.org/

JS��������ѹ�� 
http://tool.chinaz.com/js.aspx

����UglifyJS��
http://marijnhaverbeke.nl/uglifyjs/

����Closure Compressor��(��FQ)
http://closure-compiler.appspot.com/home

����YUI Compressor��
http://tool.oschina.net/jscompress