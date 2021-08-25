# CSS知识总结

## 1.浏览器渲染原理

1. 根据HTML构建HTML树
2. 根据CSS构建CSS树
3. 将两棵树合并成一颗渲染树
4. 根据Layout对页面布局
5. 根据CSS样式绘制元素
6. 根据层叠关系展示上面的元素，最后形成我们看到的页面



## 2.CSS 动画的两种做法（transition 和 animation）

### 2.1.transition

transition用于控制css属性变化的方式。

通常，css属性的改变会立即生效，通过transtion可以控制这种变化。

比如把颜色由白色改成黑色，通过transition，可以控制这个颜色的变化是慢慢的改变而不是立刻改变。

css transition可以让我们控制属性变化的动画，比如什么时候开始变，变多久，怎么变，比如线性即匀速的变化，还是开始快，后来慢等等。



所有的属性都可以通过动画的方式变化并不合理，因此哪些属性可以变是规定好了的。

下面的连接中，列出了可以transition的属性：

[Animatable CSS properties - CSS: Cascading Style Sheets | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)



transition是一个简写属性，可以通过下面4个子属性分别控制属性：

* transition-property

  指定需要transition的属性

* transition-duration

  指定持续时间，可以指定某个属性，可以指定all

* transition-timing-function

  通过function指定过度的中间值

* transition-delay

  指定等待时间

```css
div {
    transition: <property> <duration> <timing-function> <delay>;
}
```



### 2.2.animation

了解了上面的transition，就很好理解animation了。



animation也是一个简写属性，子属性包括：animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, animation-direction, animation-fill-mode和animation-play-state



例子：

```css
/* @keyframes duration | easing-function | delay |
iteration-count | direction | fill-mode | play-state | name */
animation: 3s ease-in 1s 2 reverse both paused slidein;

/* @keyframes name | duration | easing-function | delay */
animation: slidein 3s linear 1s;

/* @keyframes name | duration */
animation: slidein 3s;
```

