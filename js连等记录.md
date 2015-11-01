### 关于js 中全等说明:  
#### 1.连等是先确定所有变量的指针，再让指针指向那个赋值  
<code>  
var a = { n: 1 };     
var b = a;  
a.x = a = { n: 2 } ;    
</code>  
a b同时指向这个对象 { n: 1 } 叫A  
js解析器 在解析到 a.x = a = {n:2} ;  会先去看 a a.x 是不是有引用 有，就不变 没有，给先个undefined  
解析后 赋值  这时候a.x 会让A在加一个x属性 并且指向{ n: 2 } B 而a持有A 变为持有B  
b依然持有A  
参照：  
[js连等赋值问题](http://segmentfault.com/q/1010000002637728)  
[在线js运行时值查看工具](http://pythontutor.com/visualize.html#mode=display)ps:支持java python ruby图形显示 👍  

#### 2.在函数内 使用连等 会让变量变为全局变量  
<code>  
  function test () {  
  var a = b = c = 1;  
  console.log( typeof( a ), a );  
  }  
  test();  
  console.log( typeof( a ), a  ); //会报错  
  console.log( typeof( b ), b ); //输出 number，1
</code>
