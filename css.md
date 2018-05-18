css.md
1. 介绍一下CSS的盒子模型？  
   （1）有两种:IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;  
   （2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).   

1. CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？  
    选择器  
        1.id选择器（ # myid） 
        2.类选择器（.myclassname） 
        3.标签选择器（div, h1, p） 
        4.相邻选择器（h1 + p）  
        5.子选择器（ul > li）  
        6.后代选择器（li a） 
        7.通配符选择器（ * ）  
        8.属性选择器（a[rel = "external"]）  
        9.伪类选择器（a: hover, li: nth - child）  
    可继承样式: font-size font-family color, text-indent;   
    不可继承样式: border padding margin width height;   
    优先级规则:  
        优先级就近原则，同权重情况下样式定义最近者为准;  
        载入样式以最后载入的定位为准;    
        优先级: 
           + !important >  id > class > tag   
           + important比内联优先级高,但内联比 id 要高
    CSS3伪类:  
           p:first-of-type    选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
           p:last-of-type    选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
           p:only-of-type    选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
           p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。
           p:nth-child(2)    选择属于其父元素的第二个子元素的每个 <p> 元素。
           :enabled  :disabled 控制表单控件的禁用状态。
           :checked        单选框或复选框被选中。 
1. 如何居中div? 如何居中浮动元素？  
    居中div
       ```
       div {
        width: 200px;
        margin: 0 auto;
       }
       ```
    居中浮动元素  
    ```
    .div {
        width: 500px;
        height: 300px;
        margin: -150px 0 0 -250px;
        position: relative;
        left: 50%;
        top: 50%;
    }
    ```
1. 列出display的值，说明它们的作用和区别。 
    block 块类型元素一样显示。 
    none 缺省值。行内元素类型一样显示。  
    inline-block 行内元素一样显示，但其内容像块类型元素一样显示。  
    list-item 块类型元素一样显示，并添加样式列表标记。   
1. position的取值有哪些？relative和absolute的定位原点是什么？    
    + absolute 生成绝对定位的元素，相对于static定位以外的第一个父元素进行定位。
    + fixed (老IE不支持)生成绝对定位的元素，相对于浏览器窗口进行定位。  
    + relative 生成相对定位的元素，相对于其在普通流的正常位置进行定位。  
    + static 默认值。没有定位，元素出现在正常的流中。
    + inherit 规定从父元素继承 position 属性的值。  
1. CSS3有哪些新特性？  
   + CSS3实现圆角（border-radius）;   
   + 阴影（box-shadow）;   
   + 对文字加特效（text-shadow）;  
   + 渐变（gradient）;  
   + 旋转（transform）transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转,缩放,定位,倾斜   
   + 增加了更多的CSS选择器   
   + 多背景 rgba  
   + 媒体查询  
   + 多栏布局  
1. 为什么要初始化CSS样式?   
   因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。  
1. 如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）  
    多数显示器默认频率是60Hz，即1秒刷新60次，所以理论上最小间隔为1/60＊1000ms ＝ 16.7ms  
1. display:inline-block 什么时候会显示间隙？(携程)   
    移除空格、使用margin负值、使用font-size:0、letter-spacing、word-spacing  

1. display:none和visibility:hidden的区别？
  display:none 隐藏对应的元素，在文档布局中不再给它分配空间，它各边的元素会合拢，就当他从来不存在。 
  visibility:hidden  隐藏对应的元素，但是在文档布局中仍保留原来的空间。     
1. CSS中 link 和@import 的区别是？  
    (1) link属于HTML标签，而@import是CSS提供的; 
    (2) 页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
    (3) import只在IE5以上才能识别，而link是HTML标签，无兼容问题; 
    (4) link方式的样式的权重 高于@import的权重.  
1. 介绍一下box-sizing属性？  
   box-sizing属性主要用来控制元素的盒模型的解析模式。默认值是content-box。  
   1. content-box：让元素维持W3C的标准盒模型。元素的宽度/高度由border + padding + content的宽度/高度决定，设置width/height属性指的是content部分的宽/高    
   2. border-box：让元素维持IE传统盒模型（IE6以下版本和IE6~7的怪异模式）。设置width/height属性指的是border + padding + content  
1. 
