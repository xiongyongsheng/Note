## void 运算符

`void`运算符的作用是执行一个表达式，然后不返回任何值，或者说返回`undefined`。

```javascript
void 0; // undefined
void 0; // undefined
```

上面是`void`运算符的两种写法，都正确。建议采用后一种形式，即总是使用圆括号。因为`void`运算符的优先性很高，如果不使用括号，容易造成错误的结果。比如，`void 4 + 7`实际上等同于`(void 4) + 7`。

下面是`void`运算符的一个例子。

```javascript
var x = 3;
void (x = 5); //undefined
x; // 5
```

这个运算符的主要用途是浏览器的书签工具（Bookmarklet），以及在超级链接中插入代码防止网页跳转。

请看下面的代码。

```html
<script>
  function f() {
    console.log("Hello World");
  }
</script>
<a href="http://example.com" onclick="f(); return false;">点击</a>
```

上面代码中，点击链接后，会先执行`onclick`的代码，由于`onclick`返回`false`，所以浏览器不会跳转到 example.com。

`void`运算符可以取代上面的写法。

```html
<a href="javascript: void(f())">文字</a>
```

下面是一个更实际的例子，用户点击链接提交表单，但是不产生页面跳转。

```html
<a href="javascript: void(document.form.submit())"> 提交 </a>
```
