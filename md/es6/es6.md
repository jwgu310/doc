
# ES6

## 块级作用域 
使用 let 定义的变量在大括号的外面是访问不到的

## 常量const  常量一旦赋值就不能再修改了
注意const限制的是不能给变量重新赋值，而变量的值本身是可以改变的,下面的操作是可以的

## 模板字符串 
    let desc = `${name} is ${age} old!`;
    
## 剩余操作符
   剩余操作符可以把其余的参数的值都放到一个叫b的数组里面
    
       let rest = function(a,...b){
       console.log(a,b);
      }
       rest(1,2,3);    

##  箭头函数
   箭头函数简化了函数的的定义方式，一般以 "=>" 操作符左边为输入的参数，而右边则是进行的操作以及返回的值inputs=>output
   
      [1,2,3].forEach(val => console.log(val)););
   输入参数如果多于一个要用()包起来，函数体如果有多条语句需要用{}包起来
   箭头函数根本没有自己的this，导致内部的this就是外层代码块的this。 正是因为它没有this，从而避免了this指向的问题。