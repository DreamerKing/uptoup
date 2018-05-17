1. NodeJS的优缺点
+ 事件驱动 
+ 不用担心多线程，锁，并行计算的问题
+ V8引擎速度非常快
+ 前后端通用，全栈开发速度快

- 版本更新速度快，容易出现版本兼容性问题
- 对不同链接不支持进程和线程操作

2. 什么是错误优先的回调函数？
 错误优先的回调函数用于同时返回错误和数据。其中第一个参数返回错误，并验证它是否出错，其他参数作为返回数据。

3. 如何避免回调地狱？
 + 模块化：将回调函数转为独立的函数
 + 使用流程控制库 如co, async等
 + 使用Promise对象
 + 使用async/await

4. 什么是Promise?
 Promise可以帮助我们更好的处理异步操作。

5. 用什么工具可以保证一致的代码风格？为什么要这样做？
便于团队协作，一致的代码风格，可以让团队成员快速修改代码，而不用每次去适应新的风格。提高开发和Bug修复效率。
常用的工具有 
  +  Editor Config 
  + ESLint 
  + JSHint 
  + JSLint 
  + JSCS 
  + JS Standard

6. 什么是stub?
  stub是用于模拟一个组件或者模块的函数或者程序，主要用于模块行为，比如测试时，stub可以为函数调用返回模拟结果。

7. 什么是测试金字塔？
测试金字塔反应了需要编写的单元测试，集成测试和端到端测试的比例。

8. 如何利用Node监听80端口？
在类Unix系统一般不建议监听80端口，因为需要超级管理员权限。如过一定要监听，可以加一层反向代理(如nginx)来实现。  

9. 什么是事件循环？
 Node采用单线的处理机制，而Node在底层则是借助libuv来作为抽象封装层，从而屏蔽了不同操作系统的差异。

 10. 运算错误和程序员错误的区别
  运算错误并不是bug，而是与系统相关的问题，而程序员错误就是所谓的bug。

11. 使用npm有啥好处？
安装和管理项目依赖方便，并且能够指明依赖的具体版本。可以通过package.json文件来管理项目信息，配置脚本以及指明具体的依赖版本。

ES6
let, const, class, extends, super, arrow functions, template string, destructuring, default, rest arguments

什么是同构？
一套代码既可以在服务端运行又可以在客户端运行，这就是同构应用。简而言之, 就是服务端直出和客户端渲染的组合, 能够充分结合两者的优势，并有效避免两者的不足。

为什么同构？
性能: 通过Node直出, 将传统的三次串行http请求简化成一次http请求，降低首屏渲染时间
SEO: 服务端渲染对搜索引擎的爬取有着天然的优势
兼容性: 部分展示类页面能够有效规避客户端兼容性问题，比如白屏。

如何保证你的HTTP cookies安全不受XSS攻击
在set-cookieHTTP头部加上这几个信息：
HttpOnly-这个属性用来防止跨站脚本攻击，它不允许cookie被JavaScript代码获取。
secure-这个属性告诉浏览器只有在HTTPS连接时才发送cookie
像这样：Set-Cookit: sid=<cookit-value>; HttpOnly

ES6
1. 变量声明const和let (块级作用域，无变量提升)
2. 模板字符串`` ${}  str.includes() str.repeat() str.startWith() str.endsWith() 
3. 函数默认参数 箭头函数 剩余参数
4. 对象增强 键值对简写 对象浅复制Object.assign() 
5. 数据访问 对象和数组的解构 
6. 展开运算符 `...`
7. import 和 export  as  default(有且仅有一个)
8. Promise
9. Generators `*` `yield`




ES7
1. 求幂运算符`**`
2. Array.prototype.includes() 查看数组是否包含指定元素
3. 函数作用域中严格模式的变更

includes() > indexOf() 
```
['a', 'b', 'c'].includes('a')  //true
['a', 'b', 'c'].includes('e')  //false
['a', 'b', 'c', 'e'].includes('b',2) // false
[1, NaN, 2, 3].indexOf(NaN) // -1
[1, NaN, 2, 3].includes(NaN) // true
[1, +0, 3, 4].includes(-0) //true
[1, +0, 3, 4].indexOf(-0) //1
```

```
3**2 // 9
Math.pow(3,2) //9
```
 

ES8
async/await
Generator {value: value, done: true} function* yield
异步函数变体
+ 函数声明： async function foo(){}
+ 函数表达式： const foo=async function(){}
+ 对象的方式： let obj={ async foo(){} }
+ 箭头函数： const foo=async ()=>{}
+ 生成器模式: function* foo() { yield value }

Object.entries()
```
Object.entries({one:1, two:2}) // [['one',1],['two',2]]
Object.entries([1,2]) //[['0',1],['1',1]]
Object.entries({[Symbol()]:1, two: 2}) // [['two',2]]
Object.entries({3: 'a', 4: 'b', 1: 'c'}) // [['1','c'],['3','b'],['4', 'a']]
```

```
let obj = { one:1, two:2};
for(let [k,v] of Object.entries(obj)) {
    console.log(`${k}: ${v}`);
}
```
Object.values() 返回顺序与Object.entries() 保持一致
```
Object.values({one: 1, two: 2}) // [1, 2]
Object.values({3:'a', 4: 'b', 1: 'c', 2: 'a'}) // ['c', 'a', 'a', 'b']
```

字符串填充: padStart和padEnd 第一个参数字符串目标长度，第二个参数填充字段，可选，默认空格,
如果字符串长度大于目标长度，则原样显示，小于才使用填充字段填充。
```
"Vue".padStart(10)  // '       Vue'
"React".padEnd(10, '_*') // 'React_*_*_'
```

Object.getOwnPropertyDescriptors()
该方法会返回目标对象中所有属性的属性描述符，该属性必须是对象自己定义的，不能是从原型链继承来的。
```
let obj = {
    id: 1,
    name: "test",
    get gender() {
        console.log('gender')
    },
    set grade(g) {
        console.log(g)
    }
}

Object.getOwnPropertyDescripors(obj);
Object.getOwnPropertyDescripor(obj, 'id');
```
返回描述符有数据描述符和存取器描述符，返回结果中可能含有的键有：configurable、enumerable、value、writable、get、set

Object().assign()方法只能拷贝一个属性的值，而不会拷贝它背后的复制方法和取值方法。 Object.getOwnPropertyDescriptors()主要是为了解决 Object.assign()无法正确拷贝 get属性和 set属性的问题。

```
let obj = {
    id: 1,
    name: 'test',
    get gender() {
        console.log('gender')
    }
}
 Object.assign(obj);
```

```
let obj = {
    id: 1,
    name: 'test',
    get gender() {
        console.log('gender')
    }
};
let obj1 = {};
Object.defineProperties(obj1, Object.getOwnPropertyDescriptors(obj))
Object.getOwnPropertyDescriptors(obj1);

```

函数参数列表与调用中的尾部逗号
```
let foo = function(a,b,c,) {
    console.log(a,b,c);
    console.log(arguments);
}
foo(1,2,3,);
```

