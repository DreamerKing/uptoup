1.  Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?  
  （1）、<!DOCTYPE> 声明位于文档中的最前面，处于<html>标签之前。告知浏览器以何种模式来渲染文档。  
  （2）、严格模式的排版和JS运作模式是以该浏览器支持的最高标准运行。  
  （3）、在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。  
  （4）、DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现。  

1.  行内元素有哪些？块级元素有哪些？ 空元素有那些？  
首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。  
    （1）行内元素有：a b span img input select strong  
    （2）块级元素有：div ul ol li dl dt dd h1 h2 h3 h4 … p  
    （3）常见的空元素：br hr img input link meta  
         鲜为人知的是：area base col command embed keygen param source track wbr

1.  页面导入样式时，使用link和@import有什么区别？  
   （1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS,定义rel连接属性等作用;而@import是CSS提供的，只能用于加载CSS;  
   （2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;  
   （3）import是CSS2.1提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;  

1.  HTML5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML和HTML5？  
   新特性
    (1) HTML5现在已经不是SGML的子集，主要是关于图像，位置，存储，多任务等功能的增加;  
    (2) 绘画canvas;
    (3) 多媒体元素video 和 audio;   (4) 本地离线存储  
        localStorage 长期存储数据，浏览器关闭后数据不丢失；  
        sessionStorage 的数据在浏览器关闭后自动删除。  
    (5) 语意化更好的内容元素，比如 article、footer、header、nav、section  
    (6) 表单控件，calendar、date、time、email、url、search  
    (7) 新的技术webworker, websockt, Geolocation  
  移除的元素  
    (1) 纯表现的元素：basefont，big，center，font, s，strike，tt，u；  
    (2) 对可用性产生负面影响的元素：frame，frameset，noframes；  
  支持HTML5新标签：  
     IE8/IE7/IE6支持通过document.createElement方法产生的标签,可以利用这一特性让这些浏览器支持HTML5新标签, 浏览器支持新标签后，还需
     要添加标签默认的样式。当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架     
```
            <!--[if lt IE 9]>
              <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
            <![endif]-->
```
  如何区分：  
    DOCTYPE声明\新增的结构元素\功能元素  

1.  语义化的理解？
+   用正确的标签做正确的事情！  
+   html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析;  
+   在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的;
+   有利于SEO：和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息：爬虫依赖于标签来确定上下文和各个关键字的权重；
+   使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
+   去掉或者丢失样式的时候能够让页面呈现出清晰的结构
+   方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页；
+   便于团队开发和维护，语义化更具可读性，可以减少差异化。

1.  HTML5的离线储存？  
   localStorage    长期存储数据，浏览器关闭后数据不丢失；
   sessionStorage  数据在浏览器关闭后自动删除。

1.  iframe有那些缺点？  
+   iframe会阻塞主页面的Onload事件;  
+   frame和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。  
   使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
   动态给iframe添加src属性值，这样可以可以绕开以上两个问题。   

1.  HTML5的form如何关闭自动完成功能？  
   给不想要提示的 form 或下某个input 设置为 autocomplete=off。

1.  请描述一下 cookies，sessionStorage 和 localStorage 的区别？  
+   cookie在浏览器和服务器间来回传递，而sessionStorage和localStorage不会;  
+   sessionStorage和localStorage的存储空间更大；  
+   sessionStorage和localStorage有更多丰富易用的接口；
+   sessionStorage和localStorage各自独立的存储空间；

1.  如何实现浏览器内多个标签页之间的通信? (阿里)  
   调用localstorge、cookies等本地存储方式  

1.  webSocket如何兼容低浏览器？(阿里)  
    Adobe Flash Socket 、 ActiveX HTMLFile (IE) 、 基于 multipart 编码发送 XHR 、 基于长轮询的 XHR

1.  浏览器本地存储
   sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。而localStorage用于持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。

1.  web storage和cookie的区别  
   Web Storage的概念和cookie相似，区别是它是为了更大容量存储设计的。Cookie的大小是受限的，并且每次你请求一个新的页面的时候Cookie都会被发送过去，这样无形中浪费了带宽，另外cookie还需要指定作用域，不可以跨域调用。 除此之外，Web Storage拥有setItem,getItem,removeItem,clear等方法，不像cookie需要前端开发者自己封装setCookie，getCookie。但是cookie也是不可以或缺的：cookie的作用是与服务器进行交互，作为HTTP规范的一部分而存在，而WebStorage仅仅是为了在本地“存储”数据而生。浏览器的支持除了IE７及以下不支持外，其他标准浏览器都完全支持(ie及FF需在web服务器里运行)，值得一提的是IE总是办好事，例如IE7、IE6中的userData其实就是javascript本地存储的解决方案。通过简单的代码封装可以统一到所有的浏览器都支持web storage。localStorage和sessionStorage都具有相同的操作方法，例如setItem、getItem和removeItem等   

1.  cookie 和session 的区别  
   1、cookie数据存放在客户的浏览器上，session数据放在服务器上。
   2、cookie不是很安全，别人可以分析存放在本地的COOKIE并进行COOKIE欺骗考虑到安全应当使用session。  
   3、session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能，考虑到减轻服务器性能方面，应当使用COOKIE。
   4、单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。
   5、所以个人建议：将登陆信息等重要信息存放为SESSION，其他信息如果需要保留，可以放在COOKIE中。     
