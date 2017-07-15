## 大前端面试题（仅供参考）
#### 一面（电话面试）
##### JavaScript
1. NaN
2. 'number'
3. **基本数据类型：** Boolean | String | Number | Null | Undefined | Symbol **复杂数据类型：** Object
4. undefined(当时一着急回答成Object.prototype，真是脑残- - )
5. NaN
6. arr.splice(1, 1)
7. call和apply的第一个参数是改变某个函数执行时所在的作用域。第二个参数有些不同。call需要将每个值以逗号的形式分隔开，apply则传入数组或类数组对象
8. 两种方法。
```
let arr = [1, 2, 3];
console.log([...arr]);
cosnole.log(Array.prototype.slice.apply(arr));
```
9. let, const。let和var的区别在于var存在变量声明提升的概念，而let没有。const用于定义个常量，但是在定义复杂数据类型时，如给数组push值时，会改变数组的数据结构，而数据类型仍然不变
10. ES6的Promise中then方法的两个回调（异步），Ajax回调
11. 由于Ajax的同源策略的限制（域名、协议、端口号都要相同），因此使用Ajax无法实现跨域请求。但是可以通过JSONP动态生成script标签，将返回的数据放在回调函数内。由于是javascript代码，所以能够正常执行。另一种技术就是CORS（跨域资源共享）。
12.
```
let dc = document;
dc.querySelectorAll('span');
dc.getElementsByTagName('span');
```
13.
```
let dc = document;
dc.querySelectorAll('span')[2];
dc.querySelectorAll('span').item(2);
dc.getElementsByTagName('span')[2];
dc.getElementsByTagName('span').item(2);
```
14.
```
let a = document.querySelector('a');
a.onclick = function () {};
a.addEventListener('click', function () {}, true);
```
15. 事件冒泡 | 事件捕获。事件冒泡是从最具体的元素冒泡到较不具体的元素。事件捕获则相反，会从较不具体的元素向下传播到较具体的元素。
16. 每个回调函数上都一个event事件对象，可以通过调用事件对象的stopPropogation方法阻止事件冒泡，也可以通过return false的方式阻止事件冒泡与默认行为
##### HTTP
17. 4**表示客户端错误，此时主要是url输入错误(当时只回答了这个...)
18. 5**表示服务端错误，此时主要是访问人数过多(当时只回答了这个...)
##### CSS
19. ul > li:nth-child(1)
20. CSS相邻选择符'+'
21. margin、text-align
22. 因为没有固定宽高，当时只回答出了CSS3的flex。CSS好弱，要恶补: (
23.
```
div {
    width: 0;
    height: 0;
    border-left: 10px solid red;
    border-top: 10px solid transparent;
}
```
24. 当时回答了用transition，后面想起来应该使用animation..真的要补CSS知识... :(
25.
```
1. 父元素设置 div.super {overflow: hidden};
2. 父元素最后添加空div，设置div {clear: both};
3. 父元素设置after伪元素，并
div {zoom: 1;}
div:after {display: block; height: 0; visibility: hidden; overflow: hidden; content: '';}
```
26. 当时说的是伪元素对应一个inline元素，而伪类对应的是一个行为吧... 要补CSS知识....
27. 这个就根据自己所做的一些项目回答就好

#### 二面（算法题, 每题只有10分钟）
##### 第一题
我的方法不一定是最好的方法，只提供思路..如果有不同实现方法的朋友可以一起讨论
```
var a = [1, [2, [3, 4]], 5, [6]];
var flatten = function (array) {
    return a.toString().split(/,/g).map(function (val) {
        return +val;
    })
}
```
##### 第二题
```
var arr = [1, 2, 3, 4, 5, 6, 7, 8];

var random = function(array) {
    var i = 0, arr = [];
    while (array.length) {
        var random = Math.floor(Math.random() * array.length + array[0]);
        var index = array.indexOf(random);
        var num = array.splice(index, 1);
        arr.push(num[0]);
    }
    return arr;
}

console.log(random(arr));
```
##### 第三题
```
// 插入排序思想
let arr = ['*', 'd', 'c', '*', 'e', '*', 'a', '*'];
let sort = arr => {
    let i = 0, len = arr.length;
    for (i; i < len; i++) {
        if (arr[i] === '*') {
            arr.splice(0, 0, arr[i]);
            arr.splice(i + 1, 1);
        }
    }
    return arr;
}
console.log(sort(arr));
```
