# jQuery博客

## jQuery如何获取元素

jQuery()函数是一个构造函数，通过把选择表达式放进jQuery()函数（简写为$），得到被选中的元素。

比如通过CSS表达器：

```js
$(document) //选择整个文档
$('#myID') //选择ID为myID的网页元素
$('div.myClass') // 选择class为myClass的div元素
$('input[name=first]') // 选择name属性等于first的input元素
```

或jQuery特有的表达式：

```js
$('a:first') //选择网页中第一个a元素
$('tr:odd') //选择表格的奇数行
$('#myForm :input') // 选择表单中的input元素
$('div:visible') //选择可见的div元素
$('div:gt(2)') // 选择所有的div元素，除了前三个
$('div:animated') // 选择当前处于动画状态的div元素
```



## jQuery的链式操作是怎样的

```js
$('div').find('h3').eq(2).html('Hello');
```

链式操作可以应用在逐层筛选中，比如上面就是先选择div元素，然后从中找到h3元素，然后从中找到第3个h3元素，将其内容改为'Hello'。

背后的原理是每一步jQuery操作都是使用的函数中的api，都返回api本身，为一个jQuery对象，于是可以继续操作返回的对象。

.end()方法，可以使得结果集后退一步。



## jQuery如何创建元素

创建新元素的方法非常简单，只要把新元素直接传入jQuery的构造函数就行了：

```js
$('<p>Hello</p>');
$('<li class="new">new list item</li>');
$('ul').append('<li>list item</li>');
```



## jQuery如何移动元素

第一种方法是使用[.insertAfter()](https://api.jquery.com/insertAfter/)，把div元素移动p元素后面：

```js
$('div').insertAfter($('p'));
```

第二种方法是使用[.after()](https://api.jquery.com/after/)，把p元素加到div元素前面：

```js
$('p').after($('div'));
```

表面上看，这两种方法的效果是一样的，唯一的不同似乎只是操作视角的不同。但是实际上，它们有一个重大差别，那就是返回的元素不一样。第一种方法返回div元素，第二种方法返回p元素。你可以根据需要，选择到底使用哪一种方法。

使用这种模式的操作方法，一共有四对：

```js
.insertAfter()和.after()：在现存元素的外部，从后面插入元素
.insertBefore()和.before()：在现存元素的外部，从前面插入元素
.appendTo()和.append()：在现存元素的内部，从后面插入元素
.prependTo()和.prepend()：在现存元素的内部，从前面插入元素
```



## jQuery如何修改元素属性

jQuery设计思想是通过重载使用同一个函数，来完成取值（getter）和赋值（setter），即"取值器"与"赋值器"合一。到底是取值还是赋值，由函数的参数决定。

```js
$('h1').html(); //html()没有参数，表示取出h1的值
$('h1').html('Hello'); //html()有参数Hello，表示对h1进行赋值
```

常见的取值和赋值函数如下：

```js
[.html()](https://api.jquery.com/html/) 取出或设置html内容
[.text()](https://api.jquery.com/text/) 取出或设置text内容
[.attr()](https://api.jquery.com/attr/) 取出或设置某个属性的值
[.width()](https://api.jquery.com/width/) 取出或设置某个元素的宽度
[.height()](https://api.jquery.com/height/) 取出或设置某个元素的高度
[.val()](https://api.jquery.com/val/) 取出某个表单元素的值
```

