1. 说说你对闭包的理解  
    使用闭包主要是为了设计私有的方法和变量。闭包的优点是可以避免全局变量的污染，缺点是闭包会常驻内存，会增大内存使用量，使用不当很容易造成内存泄露。  
    闭包有三个特性:
    1. 函数嵌套函数  
    2. 函数内部可以引用外部的参数和变量  
    3. 参数和变量不会被垃圾回收机制回收  

1. 请你谈谈Cookie的弊端  
   cookie虽然在持久保存客户端数据提供了方便，分担了服务器存储的负担，但还是有很多局限性的。  
   每个特定的域名下最多生成cookie个数有限制
   IE和Opera 会清理近期最少使用的cookie，Firefox会随机清理cookie。  
   cookie的最大大约为4096字节，为了兼容性，一般不能超过4095字节。  
   优点:   
    1. 通过良好的编程，控制保存在cookie中的session对象的大小。
    2. 通过加密和安全传输技术（SSL），减少cookie被破解的可能性。
    3. 只在cookie中存放不敏感数据，即使被盗也不会有重大损失。
    4. 制cookie的生命期，使之不会永远有效。偷盗者很可能拿到一个过期的cookie。  
   缺点：  
    1. `Cookie`数量和长度的限制。每个domain最多只能有20条cookie，每个cookie长度不能超过4KB，否则会被截掉。  
    2. 安全性问题。如果cookie被人拦截了，那人就可以取得所有的session信息。即使加密也与事无补，因为拦截者并不需要知道cookie的意义，他只要原样转发cookie就可以达到目的了。  
    3. 有些状态不可能保存在客户端。例如，为了防止重复提交表单，我们需要在服务器端保存一个计数器。如果我们把这个计数器保存在客户端，那么它起不到任何作用。 
1. XML和JSON的区别？  
    (1).数据体积方面。JSON相对于XML来讲，数据的体积小，传递的速度更快些。
    (2).数据交互方面。JSON与JavaScript的交互更加方便，更容易解析处理，更好的数据交互。
    (3).数据描述方面。JSON对数据的描述性比XML较差。
    (4).传输速度方面。JSON的速度要远远快于XML。

