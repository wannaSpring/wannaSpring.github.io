---
title: Interview-base
date: 2023-02-17 14:45:18
img: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
top: false
hide: false
cover: false
coverImg: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
toc: true
mathjax: false
summary: Interview notes.
categories: Interview
reprintPolicy: cc_by
tags:
  - html
  - css
  - js
---

# html
## 1.页面导入样式时，使用link和@import有什么区别(html)
1. link 属于html提供的标签
2. @import 属于 css 提供的标签
3. link 引入的样式在页面加载时同时加载，而@import是在页面加载完成之后加载
4. link 没有兼容问题，@import则需要在ES5以上版本
5. link 引入的可以通过js操作dom， 而@import 不可以。

## 2.html的元素有哪些（包含H5）？(html)
块元素
- div
- ul
- li
- header 头部
- body 文本内容
- title 标签
- style 样式

行内元素 
- span
- a
- td
- tl
- b
- button

##  3.iframe框架都有哪些优缺点？(html)
Props:
1. 可以用作跨域请求
2. 单个iframe窗口刷新不会影响整体页面

Cons:
1. window.onload 会在所有iframe窗口加载完毕之后再执行
2. iframe 存在多个意味着需要加载多个css\js 文件，因此会加大服务器的负荷。
3. 对搜索不友好
4. 滚动条问题

## 4. HTML5的文件离线储存怎么使用，工作原理是什么？(html)
使用
现有的web框架，例如vue，react等已经将离线存储合并到框架中，因此基本是开箱即用的
原理
当客户端请求服务器时首先注册一个service work，然后利用service work拦截并缓存页面所需要的资源，当离线的时，会优先从service work读取需要的资源。

## 5. 浏览器内多个标签页之间的通信方式有哪些？(html)
同源
1. localstorage
2. cookie

跨域
1. websocket
2. postMessage (iframe 需要和父级页面通讯时可能会用到

## 6. 常见的浏览器内核都有哪些？并介绍下你对内核的理解(html)
浏览器内核分为渲染引擎和js引擎
1. 渲染引擎
用来渲染html,xml或者借助插件渲染pdf文件等，根据html标签生成布局树，渲染树等。
Chrome （webkit）
Safari  （webkit，和Chrome师出同门，但是后续Safari的webkit做了一些单独的改动）
Gecko （C++引擎，firefox）
Trident （IE 内核）
Presto （Opera 内核）

2. js引擎
执行和解析js文件
V8 （chrome）

## 7.html5中的form怎么关闭自动完成(html)
autocomplete = "off"

## 8.为什么HTML5只需要写`<!DOCTYPE HTML>`就可以？(html)
H5之前以DTD保证浏览器的兼容性，还分为严格模式和标准模式，如果不写的话则会变成怪异模式
H5不基于DTD，所以只需要一个根元素即可。

## 9. 怎样在页面上实现一个圆形的可点击区域？(html)
1. div, radius: 50%
2. a, radius: 50%
3. button, radius: 50%
4. canvas 绘制圆，监听canvas

## 10. js放在html的`<body>`和`<head>`有什么区别？(html)
html按照标签顺序执行（未加defer || async标记的情况下），如果加js标签加在head就会导致dom树还没渲染，就加载js的情况。

## 11.说说你对属性data-的理解(html)
data- 是自定义属性，用来暂存非用户输入的值，在js中也能获取。

## 12. 请说说`<script>、<script async>和<script defer>`的区别(html)
script 立即加载
async 加载和渲染同时执行
defer 渲染完成后执行

## 13. 解释下你对GBK和UTF-8的理解？并说说页面上产生乱码的可能原因(html) 
GBK 是中国使用的语言编码标准，包括简体和繁体
UTF-8 是全球通用的语言编码标准，
如果产生乱码，可能是html meta 标签的语言编码和实际使用不一致的情况

## 14. 说说你对`<meta>`标签的理解(html)
1. meta 最常见的用处是用来声明语言编码标准
2. 此外 name:keywords: 配合seo使用

## 15.网页上的验证码是为了解决什么问题？说说你了解的验证码种类有哪些(html)
1. 防止 机器行为 （重复请求，注册）
2. 保护服务器不会接受过多请求
图形，滑动，选字

## 16. DOM和BOM有什么区别(html)
BOM: Browser of model
DOM: Document of model
BOM 是独立于内容于浏览器进行交互的对象，是浏览器提供给js用来和浏览器交互的接口，例如Window对象下的方法，navigation, history,
DOM 是html提供给js的API接口，可以理解为用来操作html元素的接口，例如Document对象下的方法。
![Picsee-20230227162725.png](https://raw.githubusercontent.com/wannaSpring/snapshot/main/Picsee/Picsee-20230227162725aL5CT5.png?token=ALJ6LAVVI4JVZA6BAEC6PTLD7RU22)

## 17. 怪异模式Quirks和标准模式Standards有什么区别(html)

标准模式的宽度就是给定的本身，而怪异模式内容加padding + border而不算上margin
默认情况下浏览器使用的标准模式，而大家一般习惯使用怪异模式，所以只需要使用`border-sizing: border-box`

## 18. cookie, session and storage(BROWSER)
cookie 是一种协议，不属于服务端也不属于客服端，但是通常在服务端产生。
session 后端会话的一种机制
storage 分为localstorage 和sessionstorage
localstorage 是将数据永久存储在本地，存储到了电脑的内存和硬盘中，同源共享
- 不会随着会话的关闭而消失
- 属性名相关的情况下会产生覆写
- 不大于5MB
- 存储的时候存储的是字符串

sessionstorage 会话存储，不能共享，当页面关闭时数据也会消失

cookie 是http协议中的一部分，因为http是无状态协议，因此前后端为了验证是否登陆状态，而使用cookie，前端在获取到cookie后可以将cookie存储在浏览器，并且在每一次请求时在请求头中携带，服务端可以进行验证，以此确认登陆状态

session 是服务器存储的一种机制，服务器不会将session发送给浏览器。当客户端请求登陆时，会将账号密码一并发送给服务端，当服务端验证完成后，会生成一个session文件，之后的每一次请求，服务端会将session-id写入cookie并且将cookie发送给客户端，客户端在请求时将cookie携带发给服务端，服务端解密后得到session- ID，根据session-id去查看session文件，如果匹配则表明登陆成功，。


cookie vs session
存储
- cookie如果不设置过期时间，存储在内存中，随着浏览器关闭而消失，这种称为会话cookie，另外一种则会存储在内存中
- session保存在服务器端

存储大小
- cookie 不超过4kb
- session 没有大小限制

> 详细可参考 https://juejin.cn/post/6844903957916024839

## 19.webSocket怎么做兼容处理？(PROTOCOL)
socket.io:
Adobe flash socket (需要在服务器开一个额外的端口)
Forever iframe
Ajax long polling
Ajax multipart streaming
JSONP polling

## 20.如何让元素固定在页面底部？有哪些比较好的实践？(CSS)
1. abousulte 进行定位放到底部，需要自行计算footer的高度
2. table 使用表格布局进行划分，如果使用margin等会存在很大的麻烦
3. flex 布局，只需要在内容块增加flex:1, footer:0 即可，但是需要处理兼容问题
```html
  .wrapper {
    display: flex;
    flex-direction: column;
    overflow: auto;
  }
  .content {
      flex: 1;
  }
  .footer {
      flex: 0;
  }
```
> https://jelly.jd.com/article/6006b1045b6c6a01506c87e3

## 21. 说说你对WEB标准和W3C的理解与认识？(html)

WEB标准指的是需要符合ECMA和W3C
W3C是针对css,html,js,xml制定的规范开发者的协议和准备

## 22. Form表单是怎么上传文件的？你了解它的原理吗？(html)

`<Input type = file/>`是一个受控元素，使用这个元素可以上传文件，而浏览器在接受到文件后会将文件转为二进制，此时客户端需要和服务端约定好enctype，例如multipart/form-data，服务端在接受到二进制数据后会将其转换为源文件并且保存。

## 23.web workers有用过吗？能帮我们解决哪些问题？(BROWSER)
web workers 是h5提供的能力，提供多线程的能力，如果是运算密集任务可以放到另外一个线程执行，等运算完毕后再发送回主线程。并且可以充分利用多核cpu

## 24.有用过HTML5的webSQL和IndexedDB吗？说说你对它们的理解(HTML)
websql 和 indexdb都是客户端的存储方案，websql已经被放弃，indexdb的特点是：存储空间大，可以使用异步存储模式，存放键值对，支持数据库事务，同时可以存储多种类型包括js对象类型。

## 25. 写个例子说明HTML5在移动端如何打开APP(HTML)
在A标签内实现
- Android 使用deeplink唤起
- ios 使用URL Scheme （目前已经通用ios & abdroid）
  -  [scheme:][//authority][path][?query][#fragment]

本质上就是寻找移动端的注册文件，如果存在则唤起，但是一般我们也可以增加唤起失败，跳转下载页面。
> 详情 https://juejin.cn/post/7097784616961966094

## 26. 网站的TDK该怎么设置？它有什么作用？(HTML)
Title & Describe： 搜索结果时候展现
Keywords:搜索引擎关键字

## 27.说说form-data、x-www-form-urlencoded、raw、binary的区别是什么？(PROTOCOL)
- multipart/form-data 其请求内容格式为Content-Type: multipart/form-data,用来指定请求内容的数据编码格式，一般用来文件上传。
- x-www-form-urlencoded 是默认的post格式，使用URLEncode方法
- raw可以上传多种格式，txt，json，html等
- binary 上传二进制数据

## 28. 使用history路由方式时，你有自己动手配置过服务器端吗？为什么要配服务器端？怎么配(ROUTER)

history 需要配合服务器请求资源，因此需要服务端配合返回一个固定的Index页面
以nginx为例
```javascript
  location / {
    tryfiles: $uri $uri/index.html
  }
```

以上面的 http://www.example.com/post 为例，$uri 会匹配到 post，nginx 发现 dist 目录下下面没有 post 这个文件，也没有 post 这个文件夹，所以最后会返回 dist 目录下的 index.html。这样，index.html 被浏览器加载之后，前端路由就会工作，将用户需要的资源加载出来。而我们 build 出来的 css，js 文件，由于可以被 nginx 正确找到，则不会受到影响。


## 29. history和hash两种路由方式的最大区别是什么？(ROUTER)
history 页面刷新不会重新加载，需要服务端配合，使用pushstate和replacestate来操作url的变化
hash 由hash发生的url变化都会被浏览器记录，hash不会带过服务器，使用hahschange来监听url的变化


## 30. 请问什么是闭包？可以举一个闭包的例子吗？(JS)
闭包的定义是指在一个函数内部定义另一个函数，并且这个内部函数可以访问外部函数的变量。

## 31. 请问什么是原型链？如何实现继承？(JS)
原型链指的是在JavaScript中所有对象都有一个原型对象，这个原型对象也是一个对象，对象又可以通过它的原型对象去访问其他对象，形成了一个链式结构，这个链式结构就是原型链。继承可以通过原型链实现，比如通过将一个对象的原型设置为另一个对象来实现继承。

## 32. 请问什么是 Event Loop？在 JavaScript 中有哪些常见的异步编程方式？ (JS)
Event Loop是JavaScript的异步编程模型之一。它是一个事件循环机制，用于处理JavaScript中的异步事件。JavaScript中的异步事件有两种，一种是宏任务，比如setTimeout、setInterval等；另一种是微任务，比如Promise.then、MutationObserver等。在每一次事件循环中，先执行所有的微任务，再执行一个宏任务，然后再执行下一轮事件循环。async/await也是基于Promise实现的异步编程方式，它也是通过微任务来实现的。

## 33. 请问什么是跨域？如何解决跨域问题？(PROTOCOL)
跨域指的是浏览器不能直接访问其他域名下的资源，它是由浏览器的同源策略所导致的。同源策略要求网页只能够访问与自身所在的域名、协议、端口号相同的资源。解决跨域问题有多种方式，比如JSONP、CORS、代理、WebSocket等。

## 34. 请问如何优化前端性能？可以列举一些常见的优化方案吗？(PERFORMANCE)
前端性能优化可以从多个方面入手，包括代码方面、网络请求方面、渲染方面等。其中一些常见的优化方案包括：使用压缩和混淆工具来减少代码文件的大小，使用CDN加速网络请求，使用浏览器缓存来减少网络请求，使用图片懒加载和无限滚动来减少资源加载次数，避免布局抖动、减少重绘和回流等。

## 35. 请问什么是 Virtual DOM？它和传统 DOM 有什么不同？(HTML)

1. Virtual DOM（虚拟DOM）是指一个虚拟的DOM树，它是以JavaScript对象的形式表示，通过它来操作和更新真实的DOM树.Virtual DOM可以将DOM操作集中处理，避免频繁地操作DOM而导致页面性能下降。在进行DOM操作时，Virtual DOM会对比新旧DOM树的差异，并只更新差异部分，从而提高页面的渲染效率。
2. Virtual DOM和传统DOM的主要不同点在于，Virtual DOM通过JavaScript对象来表示DOM节点和其属性，从而避免了直接操作真实的DOM节点。这样可以提高渲染效率，同时也避免了一些常见的问题，比如浏览器兼容性、性能问题等。

## 请问什么是 Webpack？它的作用是什么？(Webpack)
webpack是一个模块打包工具，它可以将不同类型的文件（js，css，图片等）视为模块，并将他们打包成一个或者多个静态资源文件。此外webpack还提供了强大的插件和loader机制，使得开发者可以方便的进行代码压缩，分割和按需加载等操作。同时可以使用sass，less等预处理器来编写css

## 请问什么是单向数据流？它和双向数据绑定有什么不同？（JS）
单向数据流是指数据从父组件传递给子组件，子组件通过props接收数据，而无法修改父组件的数据。而双向数据绑定在这道题中的意思是指，数据可以在父子组件中双向流动，子组件不仅可以接受数据也可以通过事件的形式修改父组件的数据。在vue中我们可以用v-model实现。在react中，我们可以通过绑定方法的情况进行实现。

## 请问如何实现前端路由？有哪些常见的前端路由框架？（ROUTER）
前端路由指的是通过更改url路径来加载页面，即SPA模式，实现前端路由的方式有两种：一种是Hash（#）模式的路由，另外一种是History API得路由。常见的前端路由框架有react-router和vue router

## 请问如何进行前端安全防范？可以列举一些常见的前端安全攻击方式和防范措施吗？（SAFETY）
常见的安全问题有Xss，csrf等。预防xss攻击可以通过对用户输入的内容和转移来防止恶意脚本注入。预防CSRF攻击可以采用token验证，samesite等属性来防止跨站请求未沾。通过前端可以通过HTTPS，CSP等方式加强页面的安全性。
CSP是Content security policy，可以通过在http相应头中设置csp字段或者在html的meta标签形式来实现。
1. 在http中实现
```javascript
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' https://example.com; img-src 'self' https://example.com;
```

其中，default-src 表示默认情况下，浏览器只能加载来自同源的资源，而 script-src 和 img-src 分别表示可以加载 JavaScript 和图片资源的来源。这里使用的 'self' 表示可以从同源加载资源，而 https://example.com 则表示可以从该域名加载资源。注意，使用 unsafe-inline 可以允许内联脚本的使用，但这可能会增加安全风险。

2. 在 HTML 的 head 中使用 meta 标签，可以使用如下的方式来设置：
```javascript
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' 'unsafe-inline' https://example.com; img-src 'self' https://example.com;">
```

这种方式的设置与上述在 HTTP 响应头中设置 CSP 的方式相似，只不过是使用 meta 标签来设置。
需要注意的是，CSP 的具体设置方式会因为网站的不同而有所差异，因此在实际应用中，需要根据实际情况进行设置。同时，CSP 也需要在网站开发和维护过程中不断进行调整和优化，以保证网站的安全性和可用性。

## 32. 请问浏览器缓存的分类有哪些？如何设置浏览器缓存？(Browser)

浏览器缓存机制确实分为强缓存和协商缓存。其中，强缓存是通过设置HTTP响应头中的Cache-Control和Expires字段来实现的，浏览器可以根据这些字段的值来判断是否可以使用缓存。而协商缓存则是通过设置HTTP响应头中的Last-Modified和ETag字段来实现的，浏览器可以通过这些字段来判断缓存是否过期或者需要重新获取资源。需要注意的是，当Cache-Control和Expires都存在时，Cache-Control优先级更高。

当强缓存失效或者未命中时，浏览器会使用协商缓存来判断是否使用缓存副本，协商缓存会向服务器发送一个请求，询问当前的资源是否发生变化，如果资源未变化，服务器会返回204 NOT modified响应，浏览器可以使用缓存的副本。如果发生变化，服务器会返回新资源，浏览器会存储并且采用新的资源渲染。

如果需要强制使用强缓存，可以在响应中添加HTTP响应头
```
  Cache-control: max-age=xxx
```
xxx表示缓存时间，这告诉浏览器在缓存时间内可以直接从缓存中读取资源，而无需向浏览器发送请求。
强制使用强缓存，如果失败后，无法直接向服务器发送请求，除非清除浏览器缓存或者缓存国旗。所以这种方法只适用于资源更新要求不高的静态网站。




## 33. 请问 React 的生命周期函数有哪些？它们分别在什么时候被触发？(REACT)

react的生命周期分为三大阶段，挂载，更新和卸载。
在挂载阶段有componentwillmount,componentdidmount,componentWillReceiveProps
在更新阶段有componentwillupdate,componentshouldupdate, componentdidupdate
在卸载阶段有componentWillUnmount
需要注意的是，componentWillUpdate和componentDidUpdate并不是渲染执行结束前和渲染结束后的生命周期函数，它们是在组件更新前和更新后被调用的。

在挂载阶段constructor 调用，然后依次调用componentwillmount,render, componentdidmount三个函数。
在组件的props或者state发生变更时调用componentwillreceiveprops,shouldComponentUpdate、componentWillUpdate、render和componentDidUpdate.
在卸载阶段调用componentwillUNmount函数
如果需要实现一个生命周期，我们可以基于react.component进行实现。
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }

  componentWillMount() {
    // 在组件挂载之前调用
  }

  componentDidMount() {
    // 在组件挂载之后调用
  }

  componentWillReceiveProps(nextProps) {
    // 在组件接收到新的props时调用
  }

  shouldComponentUpdate(nextProps, nextState) {
    // 在组件props或state发生变化时判断是否需要重新渲染组件
  }

  componentWillUpdate(nextProps, nextState) {
    // 在组件即将更新时调用
  }

  componentDidUpdate(prevProps, prevState) {
    // 在组件更新完成后调用
  }

  componentWillUnmount() {
    // 在组件卸载时调用
  }

  render() {
    return (
      // 组件的渲染函数
    );
  }
}

```

## 34. 请问算法中的时间复杂度和空间复杂度有什么意义？如何计算一个算法的时间复杂度和空间复杂度？（ALGOITHUM）

空间复杂度是衡量算法所需的空间资源的一般使用大O记法表示，时间复杂度则是表示算法运行所需的时间资源，同样使用大O计法。两者可以帮助我们评估算法的效率，选择最优的算法。
大O记法描述的是算法的渐进复杂度。通常用O(F(n))，来表示空间或者时间复杂度，其中f(n)表示算法执行时间与输入规模n的增长关系。具体来说O(f(n))表示算法的执行时间或者空间在最坏情况下的增加率。
例如，一个算法的时间复杂度为 O(n^2)，表示在最坏情况下，算法的执行时间与输入规模 n 的平方成正比。另一个算法的时间复杂度为 O(n log n)，表示在最坏情况下，算法的执行时间与输入规模 n 的对数与 n 的乘积成正比。

## 35. 请简述 HTML5 中新增的语义化标签及其作用(HTML)
```
  语义化标签是为了让开发人员更好的阅读标签的作用，例如ul，li等
```

## 36. 解释 CSS 盒模型，包括 content、padding、border 和 margin 四个部分的作用(CSS)
```
  content 是内容盒子
  padding 是内边距
  border 是边框线宽
  margin 是外边距
  整个盒模型分为怪异盒子和标准盒子，标准盒子的宽度包含padding和border，怪异盒子的宽度仅包含content
```

## 37. 简述 Flex 布局和 Grid 布局，并说明两者之间的区别(CSS)
```
  flex 布局是一维弹性布局，设置flex权重后，flex盒子内的元素会根据剩余宽度自行布局，也可以通过flex-direction更改纵轴或者竖轴布局
  Grid布局为二维网格布局，可以分为行和列，通过grid-template-columns和grid-template-rows属性进行设置，设置每一个元素的比例，来分布盒子。
  flex布局的优势在一维状态下比较明显，简单易用，灵活度高，可以响应布局，缺点是不适用二维布局，存在兼容问题。
  Grid布局的优点是支持二维排列，虽然可以支持响应式布局，但是需要通过media queries实现。缺点是规则多，可读性不佳
```

## 38. 如何实现 CSS 动画？请列举一些 CSS 属性并说明其作用 (CSS)
```
  Css动画我们可以通过animation实现，一般情况下我们需要对元素设置keyframe，以此规定动画在指定帧的行为
```

## 39. 移动端适配有哪些方案？请列举并说明各自的优缺点(CSS)
``` 
  媒体查询：通过 CSS3 的媒体查询技术，根据不同的屏幕尺寸和设备类型，动态地改变页面样式。
  优点：能够根据不同设备的屏幕尺寸和像素密度进行适配，开发成本相对较低。
  缺点：对于屏幕尺寸变化较大的设备，布局可能会失真。

  rem 布局：通过设置根元素的字体大小，根据屏幕尺寸动态计算出各个元素的大小，从而实现适配。
  优点：适配效果比较稳定，适合多种屏幕尺寸和分辨率的设备。
  缺点：需要在不同设备的屏幕尺寸和像素密度下进行调试，开发成本相对较高。

  flexbox 布局：通过 CSS3 的 flexbox 布局，实现自适应布局。
  优点：能够根据不同设备的屏幕尺寸和像素密度进行适配，开发成本相对较低。
  缺点：对于某些老旧设备的浏览器支持不好。

  viewport 布局：通过设置 viewport 的属性，改变设备的默认缩放比例，实现适配。
  优点：能够适应不同尺寸的设备，实现自适应布局。
  缺点：需要针对不同的设备进行调整，不够灵活。
```

## 40. 解释 JavaScript 中的“传参是按值传递还是按引用传递”，并举例说明 (JS)

```
  按值传递还是按引用船体需要根据数据类型进行分析。基本数据类型，例如数字，字符串是按值传递的，即传递的是值的副本，修改值不会影响原始变量。而对复杂变量，例如数组，对象等，是按引用传递的，修改值会影响原来的值。
```

## 41. 解释 JavaScript 中的 this 关键字，并说明其指向的具体对象 (JS)

```
  this 关键字是指向当前作用域的，如果在函数外部使用，在面向浏览器中会被指向window，而node中会指向global。
  使用apply，call，bind等可以改变函数执行时的this指向。
  在箭头函数中，this的指向是它所处的词法作用域，而不是动态绑定的，一半是父级作用域的this
```

## 42. 解释 Promise 的概念及其使用方法，并解释 Promise 中的 then 和 catch 方法 （JS）

```
  promise是一种异步编程的解决方案，它通过对异步操作的结果进行封装，使得异步操作符合同步操作的写法风格，它使用resolve和reject表示异步操作的结果。
  在promise中通过then方法接受promise返回的结果，then会接受两个参数，一个是成功的回调，一个是失败的回调，then方法返回的依旧是promise对象，可以继续使用then方法进行链式调用
  catch是promise的错误捕捉方法，promise中的任意一个then方法或者promise对象本身出错都会立即执行catch方法
```

## 43. 解释 JavaScript 中的深拷贝和浅拷贝的概念，列举常见的实现方法 （JS）

```javascript
  深拷贝是指在拷贝一个对象时，不仅拷贝对象的基本数据类型，还拷贝它的引用对象，也就是说在堆内存中新建一个数据，不管是引用类型还是基本数据类型，都会开闭新的空间，彼此不影响
  浅拷贝是指在拷贝对象时，只拷贝基本数据类型，而不拷贝引用对象，即拷贝对象的指针，而不是本身，在新的对象中修改对象会导致原始对象中的引用类型变量也发生变化。
  实现方法。

  手写递归实现深拷贝

  function deepClone(obj)(obj) {
    if(typeof(obj) !== 'object' || obj == null) {
      return obj;
    }
    let result = obj instanceof Array ? [] : {};
    for (let key in obj) {
      if(obj.hasOwnProperty(key)) {
        reuslt[key] = deepClone(obj[key]);
      }
    }
    return result;
  }

  通过JSON序列化和反序列化实现
  JSON.parse(JSON.stringify(obj))

  也可以通过lodash实现
```

## 44. 简述常见的排序算法，并给出具体实现 (Algorithms)

冒泡排序，O(n^2),比较相邻两个元素大小，然后交换位置
```javascript
  function bubbleSory(arr) {
    const len = arr.length;
    for (let i = 0; i< len - 1; i++) { 
      // 此处的 len - i表示未完成排序的列表，例如i=0时，arr的长度为4时，我们需要的第二个循环中应该是0，1，2,
      for (let j = 0; j < len - i - 1; j++) {
        if(arr[j] > arr[j+1]) {
          [arr[j], arr[j+1]] = [arr[j+1], arr[j]]
        }
      }
    }
    return arr
  }
```

快排，O(nlog(n)),找到一个对比数字，然后以此为基准，将小于基准元素的值移到左边的数组，大于基准的值移到右边，然后递归快排方法进行排序
```javascript
  function quickSort(arr) {
    if(arr.length <= 1 ){
      return arr;
    }
    const pivot = arr[0];
    const left = [];
    const right = [];
    for (let i = 1; i < arr.length; i++) {
      if(arr[i] < pivot) {
        left.push(arr[i]);
      }else {
        right.push(arr[i]);
      }
    }
    return [quicksort(left), pivot,quicksort(right)]
  }
```

## 45. 简述 React Hooks 的使用，列举一些常用的 Hook 并说明其作用
1. useState: 用于声明状态，返回一个数组，包含状态和修改状态的函数，它可以让函数组件拥有变更状态的能力
2. useEffect: 用于组件挂载，更新和卸载执行副作用，例如数据获取、DOM操作、异步请求等，可以看作是CompoentDidMount，componentDidupdate和componentWillUnmount三个生命周期的组合
3. useContext: 配合createContext使得子组件获得共享的局部或者全局状态

```javascript
import { createContext, useContext } from 'react';
const myContext = createContext();
function parentComponent () {
  const [data, ChangeData] = useState(1)
  return (
    <MyContext.Provider value={data}>
      <ChildComponent/>
    <Mycontext.Provider/>
  )
}
function ChildComponent () {
  const data = useContext(Mycontext)
  return <div>{data}</div>
}
```

4. useReducer: 类似于Redux的状态管理库，用于批量管理函数组件状态

```javascript
const initialState = {
  count: 0,
};
const reducer = (state, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return {count: state.count+1};
    case 'DECREMENT':
      return {count: state.count-1};
    default:
      throw new Error();
  }
}
const Counter = () => {
  const [state,dispatch] = useReducer(reducer, initialState);
  return (
    <>
      <div>{state.count}</div>
      <div onClick = {() => dispatch({type: 'INCREMENT'})}></div>
      <div onClick = {() => dispatch({type: 'DECREMENT'})}></div>
    </>
  )
}
```

5. useCallback: 用于缓存函数，避免函数重新渲染导致重复执行，提高性能
6. useMemo: 类似于useCallback， 用于缓存计算结果，避免重复计算导致的性能问题。 useCallback和useMemo本质上是相同的，都是为了提高react组件的性能，避免重复计算和生成函数。
在源代码中
```javascript
function useCallback(callback, deps) {
  return useMemo (() => callback,deps);
} 

function useMemo(factory, deps) {
  const hook = updateWorkInProgressHook();
  // 获取上一次的memoized 值和依赖项
  const lastResult = hook.memoizedState;
  const lastDeps = hook.memoizedStateDeps;
  const same = areHookInputsEqual(deps, lastDeps);
  // 判断依赖项是否变化
  if(same){
    hook.memoizedStateDeps = deps;
    return lastResult;
  }
  // 如果发生变化，则使用factor计算memoized值
  const nextResult = factor();
  hook.memoizedStateDeps = deps
  hook.memoizedState = nextResult;
  return nextResult;
}
```
7. useRef: 创建引用，在组件的整个生命周期内访问，并可以保存一些数据。主要作用是获取DOM和使用Ref使得子组件使用父组件的方法。

## 46. React 父子组件通讯的方式 (REACT)
父子组件通讯主要通过props和Context进行，父组件可以通过props传递数据和函数到子组件，子组件通过props获取父组件传递的数据和函数进行操作，然后再通过回调函数的方式将操作后的结果传递回父组件。
此外也可以通过react Context 来实现全局状态的管理。
> 一般情况下需要避免子组件修改父组件值的情况，避免组件不可控。此外还需要注意子组件最好抽离为无状态组件，所展示的数据均来自父级别的状态组件。

## 请简述一下 React 中常用的状态管理工具有哪些，以及它们的优缺点 (REACT STATEMENT)
1. Redux
redux是一个基于flux架构的状态管理库，它的核心概念包括store、action和reducer，通过这三个概念来管理应用的状态，redux的优点是管理复杂状态方便，可以避免组件间的状态传递问题，同时通过中间件支持异步操作，适合大型应用的状态管理。缺点是使用复杂，而且会增加代码的复杂性和耦合性。
2. MOBX
mobx是基于响应式编程的状态管理库，它提供了obsereable的装饰器，可以将普通对象转换为可观察对象，当可观察对象发生变化时，mobx会自动更新依赖的视图。通过action，可以定义状态变更，同时在状态变更时通过依赖的组件。优点是使用简单，能够快速响应，缺点是需要注意性能问题。
3. Context
context是react自带的状态管理工具，它可以使用全局或局部状态的共享， 通过createcontext和usecontext方法，可以方便的在组件间共享状态，缺点是在组件层次较深或者状态过多时，增加维护的难度。

* FLUX架构 （redux）
flux架构是基于单向数据流思想提出的架构模式，在flux架构中，数据具有单向流动型，从dispatch->store->view. 这种单向的数据流设计避免了数据的循环依赖和相互影响。
FLUX的核心概念
1. ACTION: 数据行为，一般是js对象，包含type和payload属性
2. Dispatcher: 用于将action分发注册的store，一般是单例模式，在flux架构中，只有一个全局的dispatcher，负责协调action和store的通信
3. Store：数据源，一般是单例对象，Store 接收Dispatcher分发的action，然后根据action的类型，执行相应的业务逻辑，更新状态，状态更新后，通过view渲染页面
4. View： react组件，view从store获取数据，根据数据渲染界面。
Flux架构的优点在于，数据流动的单向性保证了代码的可预测性和可维护性，使得应用程序更加健壮和可扩展。但同时也存在一些缺点，例如对于大型应用程序，Flux架构需要编写大量的代码，增加了开发的工作量

* 响应式编程 （MOBX）
响应式编程通过将数据流的变化封装成一个可观察的序列，当数据流的状态变化时，自动发出通知，从而实现对数据流的响应式处理。其核心是观察者模式和函数式编程，其中观察者模式用于实时对数据变化的订阅和通知，函数式编程则用于对数据流的处理。


## Redux 中的三个核心概念是什么？分别解释其作用和关系（REDUX）
Redux的三个核心概念是 store、action和reducer
- store 是redux保存所有state的地方，可以用过store.getState获取当前的state，通过store.dispatch(action) 分发action来更新state，通过store.subscribe(listener)来注册state变化时的回调函数
- action是一个普通的js对象，描述动作，体重需要包含一个type字段来指定事件类型，通过dispatch方法发送action，从而触发reducer更新state
- reducer是一个纯函数，接收当前的state和action，返回一个新的state，reducer 的设计需要根据应用的具体业务需求来实现，但需要满足以下特点：传入的 state 和 action 不变时，返回的新 state 也不变；不应该在 reducer 中执行任何副作用，如调用 API 或修改外部状态

action触发reducer更新state中的state，组件从store中获取state并更具state的变化更新view，流程为action->reducer->store-> view。这种架构可以有效的分离状态和业务逻辑。

## MobX 中的 @observable、@action 和 @computed 分别是什么？举例说明其使用方法和作用。（MOBX）
- obserable是mobx的核心概念，将数据转换为可观察对象，使其能够被mobx追踪和响应，在mobx中，obserable对象的值可以被直接更改，当他更改后，所有依赖该对象的观察者都会自动更新。

- action装饰器将普通函数绑定到obserable对象上，以便使用它来修改obserable对象的值。在mobx中，使用action装饰器包装修改obserable对象的操作，可以保证这些操作都是在事务中进行的，从而确保执行完毕后一次性更新所有的观察者。

- computed装饰器是用于创建计算属性，计算属性是根据obserable对象的值自动更新自己的值。

## Context API 是 React 提供的原生状态管理工具，请简述其原理和使用方法，并说明其适用场景

Context 是 React 中的一个 API，它用于在组件树中传递数据。通过使用 Context，可以将数据直接传递给所有子组件，而不必将数据逐层传递给每个子组件。在使用 Context 时，需要创建一个 Context 对象，并使用 Provider 包装要传递的数据，然后在子组件中使用 useContext 钩子来获取数据。

在 React 中，Context 可以用于实现全局状态管理，但它并不像 Redux 那样提供了一套完整的状态管理方案。相比于 Redux，Context 更加轻量级，适用于小型应用或局部状态共享的场景。同时，Context 可以和 useContext 钩子一起使用，让组件在不同层级间获取和共享状态更加方便。

## 请结合一个具体的场景，分别使用 Redux 和 MobX 实现该场景下的状态管理，并比较两种方案的异同。
请简述一下 React Context 的基本原理以及它的适用场景。
请简述一下 React Hooks 中常用的状态管理 Hook 有哪些，以及它们的作用。
请结合一个具体的场景，使用 React Hooks 实现该场景下的状态管理，并说明你为什么选择了该方案。

## 解释 React 中的高阶组件（HOC）的概念和作用，并列举一些常见的使用场景
4. 浏览器相关
- 解释浏览器缓存机制，包括强缓存和协商缓存两种方式的概念和使用方法
- 解释浏览器的事件循环机制（Event Loop），并解释宏任务和微任务的概念
- 解释跨域问题及其解决方案，包括 JSONP、CORS、代理等方式的概念和使用方法
- 解释 HTTPS 的使用和原理，包括对称加密和非对称加密两种加密方式的概念和使用方法
- 简述 Web Worker 的使用方法和作用，以及与主线程的通信方式
5. 工程化相关
- 解释 Webpack 的基本原理和使用方法，包括 Loader 和 Plugin 的概念和使用方法
- 简述 Git 的基本使用和原理，包括版本控制、分支管理等概念和使用方法
- 解释 ESLint 和 Prettier 的使用和原理，包括代码风格的检查和自动格式化的概念和使用方法
- 简述性能优化的方案，包括代码压缩、图片
6. other
- HTTP 协议的基本原理和使用场景
- - 简述 HTTP 协议的基本结构和特点，包括请求方法、状态码、请求头、响应头等内容
- - 解释 HTTP 和 HTTPS 的区别及其使用场景，列举一些常见的安全问题并给出解决方案
- - 简述 HTTP 的缓存机制，包括强缓存和协商缓存的概念和使用方法
- - 解释 HTTP 中的长连接和短连接的概念，包括 HTTP/1.x 和 HTTP/2 中的实现方式
- 前端安全问题及其解决方案
- - 解释 XSS、CSRF、DDoS 攻击的概念及其防范方法
- - 简述 CSP 的使用方法和原理，包括限制内容安全策略的概念和使用方法
- - 解释 JWT 的使用方法和原理，包括 token 的生成和验证过程
- - 解释 CORS 的概念及其使用方法，包括前后端如何配合实现跨域访问
- 前端测试方法及其框架
- - 简述前端测试的常见方法，包括单元测试、集成测试、UI 测试等概念和使用方法
- - 简述 Jest 的使用方法和原理，包括针对 React 组件的测试方法和断言库的使用
- - 解释 Cypress 的概念和使用方法，包括如何进行端到端测试和模拟用户交互的方法
- - 解释 Selenium 的使用方法和原理，包括如何进行自动化测试和测试用例的编写
Node.js 的基本使用和原理
- - 简述 Node.js 的基本原理和使用方法，包括如何搭建环境和编写服务器端代码
- - 解释 Node.js 中的模块化和包管理的概念和使用方法，包括 npm 和 yarn 的使用方法
- - 简述 Node.js 中的异步编程和事件循环的概念和使用方法，包括如何使用 Promise 和 async/await
- - 解释 Node.js 中的流和缓冲区的概念和使用方法，包括如何进行文件读写和网络通信
- 数据库的基本知识和使用
- - 简述关系型数据库和非关系型数据库的概念和区别，包括各自的使用场景和优缺点
- - 解释 SQL 的基本语法和使用方法，包括数据表的创建和查询语句的编写
- - 简述 MongoDB 的使用方法和原理，包括如何进行文档读写和数据聚合
- - 解释 Redis 的概念和使用方法，包括如何进行数据存储和缓存管理
- - 微服务的使用和原理