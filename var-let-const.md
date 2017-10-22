# var 
* `function scope` 函数作用域，如果在函数中声明的变量，外部是访问不到的。
* 声明的变量是可以重新覆盖定义。
```
var a = 4;
function test(){
	var a = 3;
}
console.log(a); // 结果：4
```

# let 
* `block scope` 块级作用域，在大括号中声明的变量，外部是访问不到的。 `const` 类似。

```
var price = 100;
var count = 10;
if(count > 5){
	const discount = price * 0.6;
	console.log(`The discount is ${discount}`); // 结果：The discount is 60
}
console.log(discount); // 结果：Uncaught ReferenceError: discount is not defined
```

* 在同一个作用域下，不能重复定义同一变量，`const` 类似。

# const
* `const` 与 `let` 不同的地方是，`let` 声明的变量是可以改变的，`const` 是不行的。

> 如果是引用类型的值

```
const person = {
	name:'Dp',
	age:30
}
person = {name:'tms'}; // 报错
person.age = 40; // ok
```
ps : 以上的例子一个是改变了对象，一个是改变了对象的属性，如果完全不想更改一个对象，可以使用`Object.freeze(obj)`
