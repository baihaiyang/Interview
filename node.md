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
- *通用选择器：选择所有元素，不参与计算优先级
- #X id选择器：选择id值为X的元素
- .X 类选择器：选择class包含X的元素
- X Y后代选择器：选择满足X选择器的后代节点中满足Y选择器的元素
- X元素选择器： 选择所有标签为X的元素
- :link,:visited,:focus,:hover,:active 连接状态：选择特定状态的链接元素
- X + Y 直接兄弟选择器：在X之后第一个兄弟节点中选择满足Y选择器的元素
- X > Y 子选择器：选择X的子元素中满足Y选择器的元素
- X ~ Y 兄弟：选择X之后所有兄弟节点中满足Y选择器的元素
- [attr] :选择所有设置了attr属性的元素
- [attr=value] :选择属性值刚好为value的元素
- [attr~=value] :选择属性值为空白符分隔，其中一个的值刚好是value的元素
- [attr|=value] :选择属性值刚好为value或者以value-开头的元素
- [attr^=value] :选择属性值以value开头的元素
- [attr$=value] :选择属性值以value结尾的元素
- [attr*=value] :选择属性值中包含value的元素
- [:checked] :选择单选框，复选框，下拉框中选中状态下的元素
- X:after，X::after：after伪元素，选择元素虚拟子元素（元素的最后一个元素）
- :hover ：鼠标进入状态的元素
- :not(selector): 选择不符合selector的元素
- ::first-letter: 伪元素，选择块元素第一行的第一个字母
- ::first-line : 伪元素，选择块元素的第一行
- :nth-child(an + b) : 伪类，选择前面有an+b - 1个兄弟节点的元素，其中n>=0
- :nth-last-child(an + b): 伪类，选择后面有an+b - 1个兄弟节点的元素，其中n>=0
- X:nth-of-type(an+b): 伪类，X为选择器，解析得到元素标签，选择前面有an+b-1个相同标签兄弟节点的元素
- X:nth-last-of-type(an+b): 伪类，X为选择器，解析得到元素标签，选择后面有an+b-1个相同标签兄弟节点的元素
- X:first-child: 伪类，选择满足X选择器的元素，并且这个元素是其父节点的第一个元素
- X:last-child: 伪类，选择满足X选择器的元素，并且这个元素是其父节点的最后一个元素
- X:only-child: 伪类，选择满足X选择器的元素，并且这个元素是其父节点的唯一一个子元素
- X:only-of-type: 伪类，选择X选择器的元素，解析得到的所有元素标签，如果该元素没有相同类型的兄弟节点是选中它
- X:first-of-type: 伪类，选择X选择器的元素，解析得到的元素标签，如果该元素是此类型的元素的第一个兄弟，选中它。
## 清除浮动的几种方式，优缺点
1. 给父元素设置高度，但是这样的话如果内容是动态的，有可能出现滚动条。
2. 给每一个子元素后边加一个div或者br标签，设置clear：both;清除浮动，但是会增加页面标签。代码冗余。
3. 使用伪类，设置父元素after伪类，clear：both； 配合zoom属性使用。
## 图片如何实现垂直剧中的
1. table-cell:设置div的display为table-cell,vertical-align:middle;text-align:center; img标签垂直居中。
2. position: 设置div的position:relative; 设置img标签position：absolute; left: 50%; top: 50%; margin-left: 负宽度的一半，margin-top：负高度的一办，但是只能用在一直宽高的图片中。
3. css3的box：设置divstyle：text-align: center;display: -webkit-box;-webkit-box-align: center;-webkit-box-pack: center;display: -moz-box;-moz-box-align: center;-moz-box-pack: center;display: -o-box;-o-box-align: center;-o-box-pack: center;display: -ms-box;-ms-box-align: center;-ms-box-pack: center;display: box;box-align: center;box-pack: center;
## css hack你知道哪些？
1. 属性前缀法(即内部类hack)："-"减号是IE6专属hack，"\9"是IE6、7、8、9、10都生效，"\0"是IE8、9、10都生效，"\9\0"是 只对IE9、10生效。
2. 条件注释法：<!--[if IE]>只有IE浏览器显示<--[endif]>，<!--[if IE 6]>只有IE6显示<--[endif]>，<!--[if gte IE 6]>IE6及以上版本浏览器显示<--[endif]>，<!--[if ! IE 8]>不是IE8的其他IE浏览器显示<--[endif]>
3. 选择器前缀法：*html *前缀只对IE6生效；*+html *+前缀只对IE7生效；@media screen\9{...}只对IE6/7生效；@media \0screen {body { background: red; }}只对IE8有效；@media \0screen\,screen\9{body { background: blue; }}只对IE6/7/8有效；@media screen\0 {body { background: green; }} 只对IE8/9/10有效；@media screen and (min-width:0\0) {body { background: gray; }} 只对IE9/10有效
## 谈谈你对CSS盒模型的认识
盒模型就是指box的content padding margin border
- 标准模型和IE模型的区别?
1. 标准模式盒模型的width和height指的是content的宽高，IE盒模型的width和height指的是content加上border和padding的总和。标准模式适用于现在的绝大多数浏览器，IE模型只适用于IE6及以下的浏览器中。
- CSS是如何设置这两种模型?
1. css新增属性：box-sizing，content-box是默认值，指的是按照标准模式盒模型展示，border-box指的是怪异模式，按照IE盒模型展示。
- JS如何设置和获取盒模型对应的宽和高?
#### 获取：
1. element.style.width/height：此种方式只能获取元素行内样式，不能获取style标签中的样式和外联的css文件中的样式
2. element.currentStyle.width/height：此方式是IE独有的方式
3. window.getComputedStyle(element).width/height：此种方式是兼容性比较好的方式。
4. element.offsetWidth/offsetHeight：此种方式是通用性最强的一中获取方式。
#### 设置：
只能通过style设置
- 什么是优雅降级和渐进增强?
1. css属性，有很多新属性是旧版本的浏览器不支持，这时候在开发的过程中就会出现一个问题，是先考虑低版本浏览器还是先考虑主流浏览器，所以出现两种观点或者说方式。1. 优雅降级：就是开发的时候主要还是考虑当前主流浏览器的效果，低版本浏览器的兼容问题后期进行适当处理。2.渐进增强：在开发时，首先保证所有浏览器的展示效果都没问题，然后逐渐完善效果和功能，向更高的浏览器更好的效果前进。

## 谈谈你对BFC的了解
- 什么是BFC?
1. BFC是块级格式化上下文，就是页面中相对独立的一个区域。BDC的原理(渲染规则)：1、BFC里边的元素，在垂直反向会发生边距重叠现象。2、BFC在页面中独立的容器，里边的元素不会影响外面的元素，同样外边的元素也不会影响里边的元素怒。3、BFC区域不去旁边的float box区域重叠，可以用来消除浮动带来的影响。4、计算BFC的高度时，浮动的子元素也会参与计算。
- 如何创建BFC?
1. overflow属性不为visible，可以是hidden或者auto。
2. float 中，属性不为none，只要是设置了浮动，当前元素就创建了BFC。
3. position中，属性石absolute或者fixed，当前元素生成BFC。
4. display属性设置为：inline-block、table-cell、table-caption、flex、inline-flex
- BFC使用场景?
1. 解决margin重叠
2. 解决float重叠
3. 清除浮动


# JS类

## DOM事件
#### DOM事件级别有哪些?
- DOM0级事件：在元素的事件属性绑定一个函数，缺点是不能绑定多个函数，后绑定的函数会覆盖先绑定的函数
- DOM2级事件：addEventListener和removeEventListener两个函数添加事件，IE8及以下需要用attachEvent和detachEvent实现
- DOM3级事件：DOM3级事件在DOM2级事件的基础上添加了更多的事件类型，全部类型如下：1.UI事件，当用户与页面上的元素交互时触发，如：load、scroll。2.焦点事件，当元素获得或失去焦点时触发，如：blur、focus。3.鼠标事件，当用户通过鼠标在页面上执行操作时触发如：dbclick、mouseup。4.滚轮事件，当使用鼠标滚轮或类似设备时触发如：mousewheel。5.文本事件，当在文档中输入文本是触发，如：textInput。6.键盘事件，当用户通过键盘在页面上执行操作时触发如：keydown、keypress。7.合成事件，当为IME(输入法编辑器)输入字符时触发，如：compositionstart。8.变动事件，当底层DOM结构发生变化时触发，如：DOMsubtreeModified
#### 描述DOM事件捕获和冒泡的具体流程?
- 事件捕获：是事件从上到下发生，事件从最外层document开始触发，到点击的标签元素。
- 事件冒泡：事件从下到上发生，从点击的元素标签开始触发到document为止。
#### `Event`对象的常见应用场景?
- Event对象实在事件发生时产生的默认形参，event对象包含一些属性和方法，同时还有一些IE独有的属性。
#### 事件委托是什么？
- 事件委托就是根据事件冒泡的原理，把事件绑定到目标的父元素或者其他祖先元素上，触发执行效果。事件委托优点：1、可以提高js性能，提高事件的处理速度，减少内存的占用。2、动态添加dom元素，不需要修改事件绑定。
#### 事件冒泡,e.target和e.currentTarget的区别
- 事件委托中，e.target指的是当前点击的标签，e.currentTarget指的是this，绑定事件的元素。
#### 浏览器的兼容问题(js)
- 浏览器宽高问题：网页可见区域宽：document.body.clientWidth || document.documentElement.clientWidth; 网页可见区域高：document.body.clientHeight || document.documentElement.clientHeight; 整个网页的宽：document.body.scrollWidth || document.documentElement.scrollWidth; 整个网页的高：document.body.scrollHeight || document.doacumentElement.scrollHeight; 网页被卷去的高：document.body.scrollTop || document.documentELement.scrollTop; 网页左边卷去的距离：document.body.scrollLeft || document.docuemntElement.scrollLeft;
- event事件问题：e = event || window.event;
- DOM节点相关问题：获取下一个兄弟节点：ele.nextElementSibling和ele.nextSibling; 获取上一个兄弟节点：ele.previousElementSibling和ele.previousSibling; 获取第一个子节点：ele.firstElementChild和ele.firstChild; 获取最后一个子节点：ele.lastElementChild和ele.lastChild
- document.getELementsByCLassName问题：IE678不支持getElementsByClassName,通过另一种方式去实现该方法，获取所有元素，判断是否包含当前class，包含的话放到一个数组中，然后获取完所有包含改类名的元素后，返回当前数组。
- 获取元素的非行间样式值：object当前元素，oCss样式值：IE下：object.currentStyle[oCss];非IE下：getComputedStyule(object,null)[oCss]
- 事件监听和事件移除，IE下使用attachEvent和detachEvent，其他使用addEventListener和removeEventListener。
- 阻止事件传播：e.stopPropagation()或者e.cancelBubble = true;
- 阻止默认事件：e.preventDefault()或者e.returnValue = 'false';
- Event对象中的target：获取target的兼容写法：e.target || e.srcElement; 鼠标来的地方：e.relatedTarget || e.formELement; 鼠标去的地方：e.relatedTarget || e.toElement;
- 火狐中的鼠标滚轮事件：火狐：监听DOMMoustScroll事件，非火狐：document.onmousewheel

## JS原生
#### JS中有哪些数据类型
- String、Number、Boolean、null、undefined五种基本数据类型。Object是复杂数据类型。
#### 什么是闭包？闭包作用？在工作中是如何应用的?
- 1、外部函数定义的内部函数就是闭包。2、可以让函数外部获取到函数内部的值，还可以抑制保留函数内部的变量。3、比如给某些对象添加实例方法，封装相关的功能集。
#### JS实现继承的几种方式?
- js实现继承有六种方式：1、原型链继承：利用原型让一个引用类型继承另一个引用类型的属性和方法。2、借用构造函数继承：在子类型内部调用父类的构造函数，使用call或者apply可以在新创建的对象上执行父类构造函数。3、组合继承：将原型链继承和构造函数继承整合在一起，发挥二者长处。4、原型式继承：借助原型可以利用已有的对象创建新对象，同时还不必须因此创建自定义的类型。5、寄生式继承：创建一个仅用来封装继承过程的函数，在该函数内部以某种方式增强对象，最后再像真正使她做了所有工作一样返回他。6、寄生组合式继承。
#### 创建对象的三种方式?
- 1、通过字面量形式创建对象。2、通过构造函数形式创建对象。3、通过new Object()创建对象。
#### `new Person()`时发生了什么?
- 1、创建一个对象。2、将构造函数中的this指向该对象。3、将构造函数的原型指向对象的原型，这样对象就有了构造函数中的方法。4、执行构造函数中的代码。
#### 什么是深拷贝和浅拷贝？自己不用`JSON.parse`实现一个深拷贝的方法
- 深拷贝就是把所有的属性方法重新那一份放在新对象上，浅拷贝就是指拷贝引用，拷贝前后指向的都是同一个东西。深拷贝就是遍历所有的属性方法，然后创建新对象，给新对象添加同样的属性方法，返回新对象。
#### 手工模拟完整的bind方法
```
Function.prototype.myBind = function(context){
  var that = this,
  slice = Array.prototype.slice,
  args = slice.apply(arguments,[1]),
  Func = Function(){},
  bound = function(){
    return that.apply(context instanceof Func ? this : this || window, args.contact(Array.propotype.slice.apply(arguments, [0])));
  };
  Func.prototype = that.prototype;
  bound.prototype = new Func();
  return bound;
}
```
#### 什么是节流和防抖？
- throttle:函数节流是指需要间隔一定时间触发回调来控制函数调用频率。让函数有规律的调用，但不要太频繁，而是每隔一段时间调用一次。比如：我们可以让scroll中的回调函数每隔500ms调用一次，而不是每触发一次滚动就进行一次函数调用。函数节流是降低事件回调函数的执行频率，当事件一直被触发时，回调函数将以某个频率不断地执行。
- debounce:函数防抖是指对于连续的事件响应我们只需要执行一次回调。比如：注册用户名验证或者下拉模糊搜索：这类效果一般是在像搜索框中输入字符时，从后台服务器拉取相应的验证结果或者模糊查询的结果，通常做法是在键盘抬起keyup时触发某个函数，用来向后端请求数据，但是如果每次抬起都进行一次请求，那我们搜索过程中就会进行超级超级多的请求，而我们实际需要的只是对最后一次键盘抬起时输入框中的文字进行请求，所有解决方式：在键盘抬起后的一段时间中，如果不进行按键操作，就执行回调函数。通俗来讲就是说用户输入不间断的时候，暂时不执行回调函数，当用户输入间隔超过一定时间的时候才执行回调函数。函数防抖是在某时间结束后的一段时间内，如果不在触发该事件，就执行相应的回调函数。
#### 上拉刷新和下拉加载的实现原理？
#### 写一个验证邮件的正则表达式
- ^[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$; 包含汉字：^[A-Za-z0-9\u4e00-\u9fa5]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$
#### 事件绑定和普通事件的区别（可以举例说明）
- 普通事件会覆盖，就是通常所说的DOM0级事件。时间绑定的话可以绑定多个事件，不会覆盖。
#### javascript 模版引擎用过哪些？实现原理是什么？
- 模板引擎：artTemplate，其他没用过的xtemplate、mustache、handlebars.js、doT、underscore.template
- 实现原理：1、正则匹配替换 2、拼接成字符串 3、使用Function函数把字符串变成js代码执行
#### 合并两个对象
#### 动态向一个div中插入1000个div标签，如何实现？（考性能）
#### html5新特性
#### 严格模式和非严格模式的区别
#### 对于js中浮点数计算会丢失精度的问题，你有什么解决思路？

## JQuery
#### jquery.extend , jquery.fn.extend的区别
#### 谈一下jquery中的bind，live，delegate，on区别
#### document.ready和document.load和$(function(){})有什么区别？
#### $.data()和$('#aaa').data()各自作用是什么？有什么区别

## ES6
#### 什么时候应该用箭头函数？什么时候不能用？
#### 请写出ES6中Array.isArray()的实现代码
#### 如何在项目中解析处理es6和es7代码
#### Promise常用方法，Promise.race的作用，then方法里reject和catch的区别

## 工程化
#### 什么叫模块化？你用过哪些模块化解决方案？
#### 什么叫组件化？你在工作中是如何实现组件化的？
#### gulp和webpack的相同点和不同点?
#### 什么是热加载?

## 框架
#### 前端路由的实现原理
#### `MVVM`框架解决了什么问题？带来了什么问题？
#### 浏览器地址栏里面的'＃' 如何清楚？mode共有几个参数，参数有什么区别？
#### vue中父组件如何给子组件传递值
#### react的优缺点
#### React组件中props和state有什么区别？
#### 什么是JSX
#### 说一下angular、vue、react的相同点和不同点?各适用于什么样的项目场景?
#### React中不同组件传递数据的方式有哪些？至少说出三种
#### 请描述React的组件加载生命周期函数以及`shouldComponentUpdate`方法的实际使用场景?

## HTTP
#### HTTP报文的组成部分
#### GET和POST的区别
#### HTTP常见状态码
#### 什么是Restful API?
#### HTTPS和HTTP的区别是什么?
#### 从在浏览器中输入URL到页面渲染出来都经过了什么过程？
#### JSON和JSONP 区别是什么？JSONP的原理是？
#### 用过那些跨域技术
#### ajax的参数

## 前后端通信
#### 什么是同源策略及限制?
#### 前后端如何通信?
#### 用原生JS模拟一下`jquery`的`ajax`方法
#### 跨域通信的几种方式?

## 安全
#### `CSRF`的原理以及如何防御
#### `XSS`的原生和如何防御

## 渲染机制
#### 什么是`DOCTYPE`及作用?标准模式和兼容模式有什么区别?
#### 浏览器是如何渲染页面的?
#### 什么是重排？什么时候会触发重排?
#### 什么是重绘？什么时候会触发重绘?

## JS运行机制
#### 如何理解JS的单线程
#### 什么是`Event Loop`,请简述其过程

## 服务器
#### 如何在web应用中在实现权限控制?
#### Web服务器、应用服务器、Web容器、反向代理服务器的区别和联系?

## 错误处理
#### 前端错误的分类?
#### 程序出现bug了，你是如何调试的?
#### 如何分类捕获不同的错误?
#### 如何把生产环境的错误上报？

## 页面性能
#### 前端性能优化的方法有哪些？至少说出10种以上
#### 如何实现JS的异步加载? `async`和`defer`的区别是什么?

## 缓存
#### Expires和Cache-Control是如何工作的？
#### Last-Modified和Etag是如何工作的？
#### 请描述`cookie`、`sessionStorage`和`localStorage`的区别

# 项目问题
#### 介绍一下你的项目？这个项目有哪些模块？你负责哪些模块？
#### 你在项目中的角色
#### 你觉得在项目中做的最出彩的点有哪些？
#### 遇到过哪些非常难以解决的问题？最终是如何解决的？
#### 如果你是项目负责人，你会如何分配任务？如何保证按时完成？如何让成员够持续成长？

# 正常非技术问题
#### 请你自我介绍一下你自己？
#### 你觉得你个性上最大的优点是什么？
#### 说说你最大的缺点？
#### 你对加班的看法？
#### 在五年的时间内，你的职业规划？
#### 你朋友对你的评价？
#### 你还有什么问题要问我的吗？
#### 你的业余爱好是什么？
#### 你为什么从上家公司离职?

# 故意挖坑的问题
#### 你的直属上级和顶级上级对一件事情的意见不一致，你会听谁的意见？
#### 如果部门开发的时候和你的主管发生了争吵，你会如何处理？
#### 与上级意见不一致，你将怎么办？
#### 你喜欢跟什么样的主管共事？
#### 我们为什么要聘用你?
#### 你没有工作经验如何能胜任这份工作？
#### 你最崇拜的人是谁?
#### 你有创业的想法吗？

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


