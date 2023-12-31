# Object

- 取消某一个变量对于原对象的引用，**不会影响到另一个变量**。但是，这种引用**只局限于对象**，如果两个变量指向同一个**原始类型**的值。那么，变量这时都是**值的拷贝**。

```js
var o1 = {};
var o2 = o1;

o1 = 1;
o2; // {}
```

- 如果行首是一个大括号,一律解释为代码块。

```js
{
  console.log(123);
} // 123
```

- 如果要解释为对象，最好在大括号前加上圆括号。因为圆括号的里面，只能是表达式，所以确保大括号只能解释为对象。

```js
({ foo: 123 }) // 正确
({ console.log(123) }) // 报错
```

- 对象 obj 的数字键，**加不加引号都可以**，因为会被自动转为字符串。

```js
var obj = {
  0.7: "Hello World",
};

obj["0.7"]; // "Hello World"
obj[0.7]; // "Hello World"
```

- **数值键名不能使用点运算符**（因为会被当成小数点），只能使用方括号运算符.

```js
var obj = {
  123: 'hello world'
};

obj.123 // 报错
obj[123] // "hello world"
```
