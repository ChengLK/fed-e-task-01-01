## 题目1
```javaScript
 var a = [];
 for (var i = 0; i < 10; i++) {
   a[i] = function () {
     console.log(i);
   };
 }
 a[6](); // 打印结果： 10
 ```
 #### 答：变量i是var声明的，为全局变量作用域为整个for循环，每一次循环中当i发生改变时， a中每个i值也同时改变了，所以在调用a`[6]`()时，i值是已经循环10次后的变量值10。为了避免出现这个问题，可以使用es2015的let声明方式。
 
 ## 题目2
 ```javaScript
 var tmp = 123；
 if (true) {
 	console.log(tmp)				
 	let tmp；
 }
  ```
#### 答：tmp is not defined，if作用域内使用let声明了tmp，let不会变量提升，所以console.log时tmp还未定义。如果if作用域内没有let tmp，console.log输出123。

## 题目3
```javaScript
 var arr = [12, 34, 32, 89, 4];
 ```
#### 答：es6方法获取数组内最小值：Math.min(...arr)

## 题目4 
#### 答：1、var let const 三种声明变量方式具体差别。2、var为全局作用域有变量提升特性，let和const为块级作用域没有变量提升特性。3、const声明一个只读的常量。一旦声明，常量的值就不能改变。

## 题目5
```javaScript
	var a = 10;
	var obj = {
		a: 20,
		fn () {
			console.log(this.a)  // 输出 20
			setTimeout(() => {
				console.log(this.a) // 输出 20
			})
		}
	}
	obj.fn()  // 输出 20
```
#### 答：输出20，因为箭头函数不会改变this的指向，箭头函数外面this指什么，内部就指什么，所以箭头函数内this.a等与fn函数下this.a，两个输出一样。

## 题目6 
#### 答：symbol类型的用途，每个Symbol实例都是唯一的, 可以使用symbol来作为对象属性名，避免对象属性名冲突，也特别适合做对象的私有属性，不能通过Object.keys()或者for...in来枚举，并且JSON.stringify()会排除symbol。

## 题目7
#### 答： js引用数据类型，他的名字会存入在栈内存中，值存在堆内存中，栈提供一个引用的地址，指向堆内存中的值，浅拷贝就是在栈中复制一个新的名字，但是引用地址还是指向堆中同一个内存，深拷贝就是在堆中也复制出来一个内存存放值，引用的地址引入新的堆内存。

## 题目8
#### 答：js异步编程，不会等待这个任务结束才开始下个任务，解决了单线程JavaScript语言无法同时处理大量耗时任务的问题。
#### Event Loop，负责监听调用栈和消息队列，调用栈内如果没有工作了，就会从消息队列中取出第一个事件压如调用栈。
#### 每一轮任务的执行，都会产生一些任务，会根据api的不同，决定是宏任务还是微任务，如果是宏任务，是要进消息队列，微任务会在本轮末尾执行。

## 题目9
```javaScript
	function promise(value){
	  return new Promise((resolve,reject)=>{
		if(resolve){
			resolve(value);
		}else{
		  throw new Error("throw Error promise");
		}
	  });
	}
	promise('hello').then(function (value){
		var b = value + ' lagou'
		return promise(b)
	}).then(function (value2) {
		var c = value2 + ' I ❤ U'
		return promise(c)
	}).then(function (value3) {
		console.log(value3)
	})
```
## 题目10
#### 答：TypeScript是一门基于 JavaScript 基础之上的编程语言。它是 JavaScript 的超集，包含了 JavaScript 的所有元素，可以载入 JavaScript 代码运行，并扩展了 JavaScript 的语法。TypeScript包含 JavaScript、强大的类型系统、ES6+的支持，最终会被编译成 JavaScript。

## 题目11
#### 答：TypeScript优点，支持ES6+新特性，任何一种JavaScript运行环境都支持，生态更健全、更完善，更适合大型项目开发。
#### TypeScript优点缺点，语言本身多了很多概（接口，泛型，枚举...），提高学习成本，项目初期，会增加开发成本。