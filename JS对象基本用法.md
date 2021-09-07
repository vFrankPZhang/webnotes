# JS对象基本用法

## 内容1：声明对象的两种语法

下面三种方法都可以初始化一个对象：

```js
new Object()

Object.create()

let obj = {}
```



## 内容2：如何删除对象的属性

`delete`命令用于删除对象的属性，删除成功后返回`true`。

```js
var obj = { p: 1 };
Object.keys(obj) // ["p"]

delete obj.p // true
obj.p // undefined
Object.keys(obj) // []
```

上面代码中，`delete`命令删除对象`obj`的`p`属性。删除后，再读取`p`属性就会返回`undefined`，而且`Object.keys`方法的返回值也不再包括该属性。



## 内容3：如何查看对象的属性

查看一个对象本身的所有属性，可以使用`Object.keys`方法。

```js
var obj = {
  key1: 1,
  key2: 2
};

Object.keys(obj);
// ['key1', 'key2']
```



## 内容4：如何修改或增加对象的属性

```js
var obj = {};

obj.foo = 'Hello';
obj['bar'] = 'World';
```

上面代码中，分别使用点运算符和方括号运算符，对属性赋值。

属性已存在为修改，不存在为增加。



## 内容5：'name' in obj和obj.hasOwnProperty('name') 的区别

```js
let obj = {}

obj
{}[[Prototype]]: Objectconstructor: ƒ Object()hasOwnProperty: ƒ hasOwnProperty()isPrototypeOf: ƒ isPrototypeOf()propertyIsEnumerable: ƒ propertyIsEnumerable()toLocaleString: ƒ toLocaleString()toString: ƒ toString()valueOf: ƒ valueOf()__defineGetter__: ƒ __defineGetter__()__defineSetter__: ƒ __defineSetter__()__lookupGetter__: ƒ __lookupGetter__()__lookupSetter__: ƒ __lookupSetter__()__proto__: (...)get __proto__: ƒ __proto__()set __proto__: ƒ __proto__()

'toString' in obj
true

obj.hasOwnProperty('toString')
false
```

.hasOwnProperty()方法只能查看是否是自有属性。

共有属性通过in运算符，也会返回true。