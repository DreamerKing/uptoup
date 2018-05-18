1. 行内元素有哪些？块级元素有哪些？ 空元素有那些？
首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。
    （1）行内元素有：a b span img input select strong
    （2）块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p
    （3）常见的空元素：
         <br> <hr> <img> <input> <link> <meta>
        鲜为人知的是：
         <area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>

2. 页面导入样式时，使用link和@import有什么区别？
   （1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS,定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;
   （2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
   （3）import是CSS2.1提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;

3. HTML5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML和HTML5？
    (1) HTML5现在已经不是SGML的子集，主要是关于图像，位置，存储，多任务等功能的增加。
    (2) 绘画 canvas
    (3) 多媒体元素video 和 audio
    (4) 本地离线存储 
        localStorage 长期存储数据，浏览器关闭后数据不丢失；
        sessionStorage 的数据在浏览器关闭后自动删除
    (5) 语意化更好的内容元素，比如 article、footer、header、nav、section
    (6) 表单控件，calendar、date、time、email、url、search
    (7) 新的技术webworker, websockt, Geolocation

移除的元素
    (1) 纯表现的元素：basefont，big，center，font, s，strike，tt，u；
    (2) 对可用性产生负面影响的元素：frame，frameset，noframes；

支持HTML5新标签：
    IE8/IE7/IE6支持通过document.createElement方法产生的标签,可以利用这一特性让这些浏览器支持HTML5新标签, 浏览器支持新标签后，还需要添加标签默认的样式。
    当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架
        <!--[if lt IE 9]>
        <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
        <![endif]-->
如何区分： 
    DOCTYPE声明\新增的结构元素\功能元素

4. 语义化的理解？
  + 用正确的标签做正确的事情！
  + html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
  + 在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的。
  + 搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于 SEO。
  + 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。 

5. HTML5的离线储存？
   localStorage    长期存储数据，浏览器关闭后数据不丢失；
   sessionStorage  数据在浏览器关闭后自动删除。

6. iframe有那些缺点？
   *iframe会阻塞主页面的Onload事件；
   *iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
   使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
   动态给iframe添加src属性值，这样可以可以绕开以上两个问题。  

7. HTML5的form如何关闭自动完成功能？
   给不想要提示的 form 或下某个input 设置为 autocomplete=off。

8. 请描述一下 cookies，sessionStorage 和 localStorage 的区别？
   cookie在浏览器和服务器间来回传递。 sessionStorage和localStorage不会
   sessionStorage和localStorage的存储空间更大；
   sessionStorage和localStorage有更多丰富易用的接口；
   sessionStorage和localStorage各自独立的存储空间；

9. 如何实现浏览器内多个标签页之间的通信? (阿里)
   调用localstorge、cookies等本地存储方式

10. webSocket如何兼容低浏览器？(阿里)
    Adobe Flash Socket 、 ActiveX HTMLFile (IE) 、 基于 multipart 编码发送 XHR 、 基于长轮询的 XHR   