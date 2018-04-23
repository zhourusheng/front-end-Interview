### 1. javascript 的 typeof 返回哪些数据类型 
    alert(typeof [1,2]); //object 
    alert(typeof 'leipeng'); //string 
    var i = true;  
    alert(typeof i); //boolean 
    alert(typeof 1); //number 
    var a;  
    alert(typeof a); //undefined 
    function a(){;}; 
    alert(typeof a) //function 

### 2. 例举 3 种强制类型转换和 2 种隐式类型转换? 
* 强制（parseInt(),parseFloat(),Number()），数值转换三种方式 
* 隐式（== ,!!） 

### 3. split() 、join() 的区别 
* split()是切割成数组的形式，
* join()后者是将数组转换成字符串 

### 4. 数组方法 pop() push() unshift() shift() 
* Push()在数组尾部添加 
* pop()在数组尾部删除 
* Unshift()在数组头部添加 
* shift()在数组头部删除 

### 5. 事件绑定和普通事件有什么区别 

#### 1.普通添加事件的方法： 
var btn = document.getElementById("hello"); 
btn.onclick = function(){ 
 alert(1); 
} 
btn.onclick = function(){ 
 alert(2); 
}
执行上面的代码只会 alert 2  
 
#### 2.事件绑定方式添加事件： 
var btn = document.getElementById("hello"); 
btn.addEventListener("click",function(){ 
 alert(1); 
},false); 
btn.addEventListener("click",function(){ 
 alert(2); 
},false); 
执行上面的代码会先 alert 1 再 alert 2 

* 普通添加事件的方法不支持添加多个事件，最下面的事件会覆盖上面的，而事件绑定（addEventListener）方式添加事件可以添加多个。 
* addEventListener 不兼容低版本 IE普通事件无法取消 
* addEventLisntener 还支持事件冒泡+事件捕获 

### 11. 添加 替换 插入 删除到某个节点的方法 

* obj.appendChid() 
* obj.insertBefore() 
* obj.replaceChild() 
* obj.removeChild() 

### 14. "=="和"==="的不同 

* 前者会自动转换类型 
* 后者不会

### 15. javascript 的同源策略 

* 一段脚本只能读取来自于同一来源的窗口和文档的属性，这里的同一来源指的是主机名、议
和端口号的组合 

### 18. 已知ID的Input输入框，希望获取这个输入框的输入值，怎么做？(不使用第
三方框架) 

 * document.getElementById(“ID”).value 

### 20. 设置一个已知 ID 的 DIV 的 html 内容为 xxxx，字体颜色设置为黑色(不使用第
三方框架) 
 
<code>
var dom = document.getElementById(“ID”); 
dom.innerHTML = “xxxx” 
dom.style.color = “#000
</code>

### 21. 当一个 DOM 节点被点击时候，我们希望能够执行一个函数，应该怎么做？ 

* 直接在DOM里绑定事件：<div onclick=”test()”></div> 
* 在JS 里通过onclick绑定：xxx.onclick = test 
* 通过事件添加进行绑定：addEventListener(xxx, ‘click’, test) 
* 那么问题来了，Javascript的事件流模型都有什么？ 
* “事件冒泡”：事件开始由最具体的元素接受，然后逐级向上传播 
* “事件捕捉”：事件由最不具体的节点先接收，然后逐级向下，一直到最具体的 
* “DOM事件流”：三个阶段：事件捕捉，目标阶段，事件冒泡 


8. call 和 apply 的区别
call 方法:
语法：call(thisObj，Object1,Object2...)
定义：调用一个对象的一个方法，以另一个对象替换当前对象。
说明：
call 方法可以用来代替另一个对象调用一个方法。call 方法可将一个函数的对象上下文从初始
的上下文改变为由 thisObj 指定的新对象。
如果没有提供 thisObj 参数，那么 Global 对象被用作 thisObj。
apply 方法：
语法：apply(thisObj，[argArray])
定义：应用某一对象的一个方法，用另一个对象替换当前对象。
说明：
如果 argArray 不是一个有效的数组或者不是 arguments 对象，那么将导致一个
TypeError。
如果没有提供 argArray 和 thisObj 任何一个参数，那么 Global 对象将被用作 thisObj，