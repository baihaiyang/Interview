# 前端开发知识点
## HTML&CSS：
	对Web标准的理解、浏览器内核差异、兼容性、hack、CSS基本功：布局、盒子模型、选择器优先级、
	HTML5、CSS3、Flexbox

## JavaScript：
    数据类型、运算、对象、Function、继承、闭包、作用域、原型链、事件、RegExp、JSON、Ajax、
	DOM、BOM、内存泄漏、跨域、异步装载、模板引擎、前端MVC、路由、模块化、Canvas、ECMAScript 6、Nodejs

## 其他：
    移动端、响应式、自动化构建、HTTP、离线存储、WEB安全、优化、重构、团队协作、可维护、易用性、SEO、UED、架构、职业生涯、快速学习能力

# CSS类
## 假设高度已知，请写出三栏布局，其中左栏、右栏宽度各为100px，中间自适应。
请写出五到七种方案，并说出各种方案的优缺点和兼容性
1. float+margin 经典的包括圣杯布局和双飞翼布局;此方式不等高，而且会使用定位，扩展性差。
2. inline-block+marin+(calc) 三个并列排放都在一行,中间的宽度是calc(100%-240px) ，减去两边的宽度和加上margin值；另一种是在主体中添加一层div，然后设置margin，主体margin 0 -100px，center margin：0 120px；此方式不等高，使用定位，扩展性差。
3. table 设置con为display：table，左右和主体都是table-cell，左右宽度固定，中间自适应，并且等高。
4. position 纯定位，con设置position:absolute; 左右和主体都是relative，左右定宽，左右分别设置left和right，中间设置left、right一起设置。给con高度，高度固定。
5. flex 弹性盒模型布局：设置con的display：flex；左右高度固定，中间flex：1； 但是只能在支持flex的浏览器中使用。等高。
6. grid 栅格布局：设置con为display：grid；设置gird-template-clomuns：100px 1fr 100px; 两边固定，中间自适应，等高。
## 左侧菜单栏占300px，右侧内容可以根据浏览器自适应。根据此要求，编写html css代码
1. float+margin:左边浮动，主体设置marginLeft
2. table: 设置con的display为table，所有的子元素都是table-cell，左边定宽，等高
3. flex: 设置con为display为flex，左边定宽，右边flex为1，等高
4. grid: 设置con的display为grid，grid-template-columns: 100px 1fr; 等高；
## CSS选择器又哪些？有哪些新特性？有哪些伪类？

## 清除浮动的几种方式，优缺点
1. 给父元素设置高度，但是这样的话如果内容是动态的，有可能出现滚动条。
2. 给每一个子元素后边加一个div或者br标签，设置clear：both;清除浮动，但是会增加页面标签。代码冗余。
3. 使用伪类，设置父元素after伪类，clear：both； 配合zoom属性使用。
## 图片如何实现垂直剧中的

## css hack你知道哪些？

## 谈谈你对CSS盒模型的认识
- 标准模型和IE模型的区别?
- CSS是如何设置这两种模型?
- JS如何设置和获取盒模型对应的宽和高?
- 什么是优雅降级和渐进增强?


## 谈谈你对BFC的了解
- 什么是BFC?
- 如何创建BFC?
- BFC使用场景?


# JS类

## DOM事件
- DOM事件级别有哪些?
- 描述DOM事件捕获和冒泡的具体流程?
- `Event`对象的常见应用场景?
- 事件委托是什么？
- 事件冒泡,e.target和e.currentTarget的区别
- 浏览器的兼容问题(js)

## JS原生
- JS中有哪些数据类型
- 什么是闭包？闭包作用？在工作中是如何应用的?
- JS实现继承的几种方式?
- 创建对象的三种方式?
- `new Person()`时发生了什么?
- 什么是深拷贝和浅拷贝？自己不用`JSON.parse`实现一个深拷贝的方法
- 手工模拟完整的bind方法
- 什么是节流和防抖？
- 上拉刷新和下拉加载的实现原理？
- 写一个验证邮件的正则表达式
- 事件绑定和普通事件的区别（可以举例说明）
- javascript 模版引擎用过哪些？实现原理是什么？
- 合并两个对象
- 动态向一个div中插入1000个div标签，如何实现？（考性能）
- html5新特性
- 严格模式和非严格模式的区别
- 对于js中浮点数计算会丢失精度的问题，你有什么解决思路？

## JQuery
- jquery.extend , jquery.fn.extend的区别
- 谈一下jquery中的bind，live，delegate，on区别
- document.ready和document.load和$(function(){})有什么区别？
- $.data()和$('#aaa').data()各自作用是什么？有什么区别

## ES6
- 什么时候应该用箭头函数？什么时候不能用？
－ 请写出ES6中Array.isArray()的实现代码
- 如何在项目中解析处理es6和es7代码
- Promise常用方法，Promise.race的作用，then方法里reject和catch的区别

## 工程化
- 什么叫模块化？你用过哪些模块化解决方案？
- 什么叫组件化？你在工作中是如何实现组件化的？
- gulp和webpack的相同点和不同点?
- 什么是热加载?

## 框架
- 前端路由的实现原理
- `MVVM`框架解决了什么问题？带来了什么问题？
- 浏览器地址栏里面的'＃' 如何清楚？mode共有几个参数，参数有什么区别？
- vue中父组件如何给子组件传递值
- react的优缺点
- React组件中props和state有什么区别？
- 什么是JSX
- 说一下angular、vue、react的相同点和不同点?各适用于什么样的项目场景?
- React中不同组件传递数据的方式有哪些？至少说出三种
- 请描述React的组件加载生命周期函数以及`shouldComponentUpdate`方法的实际使用场景?

## HTTP
- HTTP报文的组成部分
- GET和POST的区别
- HTTP常见状态码
- 什么是Restful API?
- HTTPS和HTTP的区别是什么?
- 从在浏览器中输入URL到页面渲染出来都经过了什么过程？
- JSON和JSONP 区别是什么？JSONP的原理是？
- 用过那些跨域技术
- ajax的参数

## 前后端通信
- 什么是同源策略及限制?
- 前后端如何通信?
- 用原生JS模拟一下`jquery`的`ajax`方法
- 跨域通信的几种方式?

## 安全
- `CSRF`的原理以及如何防御
- `XSS`的原生和如何防御

## 渲染机制
- 什么是`DOCTYPE`及作用?标准模式和兼容模式有什么区别?
- 浏览器是如何渲染页面的?
- 什么是重排？什么时候会触发重排?
- 什么是重绘？什么时候会触发重绘?

## JS运行机制
- 如何理解JS的单线程
- 什么是`Event Loop`,请简述其过程

## 服务器
- 如何在web应用中在实现权限控制?
- Web服务器、应用服务器、Web容器、反向代理服务器的区别和联系?

## 错误处理
- 前端错误的分类?
- 程序出现bug了，你是如何调试的?
- 如何分类捕获不同的错误?
- 如何把生产环境的错误上报？

## 页面性能
- 前端性能优化的方法有哪些？至少说出10种以上
- 如何实现JS的异步加载? `async`和`defer`的区别是什么?

## 缓存
- Expires和Cache-Control是如何工作的？
- Last-Modified和Etag是如何工作的？
- 请描述`cookie`、`sessionStorage`和`localStorage`的区别

# 项目问题
- 介绍一下你的项目？这个项目有哪些模块？你负责哪些模块？
- 你在项目中的角色
- 你觉得在项目中做的最出彩的点有哪些？
- 遇到过哪些非常难以解决的问题？最终是如何解决的？
- 如果你是项目负责人，你会如何分配任务？如何保证按时完成？如何让成员够持续成长？

# 正常非技术问题
- 请你自我介绍一下你自己？
- 你觉得你个性上最大的优点是什么？
- 说说你最大的缺点？
- 你对加班的看法？
- 在五年的时间内，你的职业规划？
- 你朋友对你的评价？
- 你还有什么问题要问我的吗？
- 你的业余爱好是什么？
- 你为什么从上家公司离职?

# 故意挖坑的问题
- 你的直属上级和顶级上级对一件事情的意见不一致，你会听谁的意见？
- 如果部门开发的时候和你的主管发生了争吵，你会如何处理？
- 与上级意见不一致，你将怎么办？
- 你喜欢跟什么样的主管共事？
- 我们为什么要聘用你?
- 你没有工作经验如何能胜任这份工作？
- 你最崇拜的人是谁?
- 你有创业的想法吗？

## 代码运行结果，并解释
```javascript
if(!("a" in window)){
  var a = 1;
}
console.log(a);
```

```javascript
function MyObj(){
  this.p.pid++;
}
MyObj.prototype.p = {'pid':0}
MyObj.prototype.getNum = function(num){
  return this.p.pid+num;
}
var _obj1 = new MyObj();
var _obj2 = new MyObj();
console.log(_obj1.getNum(1)+_obj2.getNum(2))
```

```javascript
var func = (function(a){
  this.a = a;
  return function(a){
    a+=this.a;
    return a;
  }
})(function(a,b){
  return a;
}(1,2));
func(4);
```


```javascript
function Foo() {
 getName = function () { alert (1); };
 return this;
}
Foo.getName = function () { alert (2);};
Foo.prototype.getName = function () { alert (3);};
var getName = function () { alert (4);};
function getName() { alert (5);}

//请写出以下输出结果：
Foo.getName();
getName();
Foo().getName();
getName();
new Foo.getName();
new Foo().getName();
new new Foo().getName();
```


```javascript
for(var i=0;i<10;i++){
       alert(i);
       break;
   }
   alert(i);

   for(var i=0;i<10;i++){
      continue;
      alert(i);
   }
   alert(i)
```

```javascript
function C1(name){
	if(name) this.name = name;
}
function C2(name){
this.name =name;
}
function C3(name){
 this.name = name ||'join';
}
C1.prototype.name='Tom';
C2.prototype.name='Tom';
C3.prototype.name='Tom';
alert(new C1().name)+(new C2().name)+(new C3().name);

```

```javascript
var a=1;
Var obj ={
   “name”:”tom”
}
function fn(){
   var a2 = a,
   obj2 = obj,
   a2 =a,
   obj2.name =”jack”
}
fn();
console.log(a);
console.log(obj);
```

每个人必须建立自己的github地址将答案，放到github上，并且将答案抄在纸上（加深记忆 防止粘贴），晚上之前必须`每个人`都交上来，大家不许互相讨论，可以采用google和百度等手段，
目的：校验自己的不足查缺补漏，学会自我查找问题，提升解决问题的能力。
