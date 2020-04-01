### day17 js进阶1

#### 17.1 Function函数

##### 17.1.1 基本介绍

​	函数的参数（或更确切地说，各参数的名称）首先出现，而函数体在最后。所有参数都写成字符串形式。	

```javascript
var sum = new Function('a', 'b', 'return a + b');
```

​	如果所要新建的函数没有参数，那么new Function()只有一个函数体参数

```javascript
var sayHi = new Function('alert("Hello")');

sayHi(); // Hello
```

这个方式与其他方式最主要的不同点在于，函数是由在运行时传入的字符串创建的。

##### 17.1.2  函数的声明方式

```javascript
function  fn(){}

var fn = function(){}

var fn = new Function("a","b","return a+b");

function(){}();

```

##### 17.1.3 作为值的函数

通过return返回的函数名的函数就是作为值的函数；

```javascript

function foo(){
	var a=10;
	return function(){
		a *=2;
		return a;
	};
}
var f=foo();

```

##### 17.1.4 arguments

在函数内部，有两个特殊的对象：arguments和this,arguments是一个数组对象，包含传入函数中的所有参数，

主要用途是保存函数参数，但这个对象还有一个名叫callee的属性，该属性是一个指针，指向拥有这个arguments对象的函数。

```javascript

	function sum1(n1,n2){
				console.log("arguments:",arguments,"arguments.length:",arguments.length);
	}
	function sum2(){
				console.log("arguments:",arguments,"arguments.length:",arguments.length);
				console.log("callee:",arguments.callee);
	}
	sum1(1,2);

```





