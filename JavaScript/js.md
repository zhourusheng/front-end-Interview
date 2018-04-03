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
* 强制（parseInt(),parseFloat(),Number()） 
* 隐式（== ,!!） 

### 3. split() 、join() 的区别 
* 前者是切割成数组的形式，后者是将数组转换成字符串 

### 4. 数组方法 pop() push() unshift() shift() 
* Push()尾部添加 
* pop()尾部删除 
* Unshift()头部添加 
* shift()头部删除 
