- [HTTP缓存协议实战 - vivo互联网技术 - 博客园 (cnblogs.com)](https://www.cnblogs.com/vivotech/p/15899226.html)
  Http缓存一般分为两种：**私有缓存**；**共享缓存**（常见的是CDN）
  私有缓存：缓存被存储在设备本地或独立的账户体系下，仅供当前用户使用，可以用来降低服务器压力，提供用户体验，甚至实现离线浏览。
  共享缓存：在代理服务器或者其他中间服务器中进行二次缓存的数据，一般常见的是CDN，这种缓存可以被多个用户访问，用来减少流量和延迟。

对于一次网络数据交互，本地缓存和共享缓存可以同时存在，HTTP协议中规定了如何进行控制这些缓存的使用和更新。在HTTP中，控制缓存有两张字段：**Pragma**和**cache-control**。
Pragma:在HTTP/1.0中定义的字段，支持现有的所有浏览器。
cache-control HTTP/1.1 
Pragma的优先级大于cache-control

- [SpringCloud微服务实战——搭建企业级开发框架（二）：环境准备 - 全栈程序猿 - 博客园 (cnblogs.com)](https://www.cnblogs.com/FullStackProgrammer/p/15449014.html)
- JVM 垃圾回收机制
  JAVA最大的特点是实现自动内存管理（自动分配对象，自动垃圾回收）
  一、垃圾回收相关算法
  垃圾回收主要有两个阶段：标记阶段、清除阶段
  标记阶段：该阶段主要为了判断对象是否存活
         对象存活：有指针指向对象（对象还有可用的价值）
         对象销毁：没有指针指向对象（对象没有可用的价值）
  1、引用计数算法
        对每一个对象内部保存一个整数引用属性，记录对象被引用的次数情况。当对象被任何一个变量引用，次数就+1，当引用失效，次数-1，当次数为0，表示该对象可以被回收。
         优点：实现简单，判断效率高，回收没有延迟性。
         缺点：
  - 需要给对象增加额外的空间开销。
  - 无法处理循环引用（致命的缺点，导致Java没有使用该算法）

[note:]循环引用确实是导致内存泄露，但由于Java不采用该算法，该例子就不能作为Java内存泄漏露的举例。
![img](https://img2022.cnblogs.com/blog/2597186/202202/2597186-20220216205926532-626214637.png)

- 但是python采用了该算法，看它如何解决这个缺点

  - 手动解除引用，在合适的时候，程序员自己手动处理回收
  - 使用弱引用，weakref是python专门提供用来解决循环引用的

  2、可达性分析算法（根搜索算法，追踪性算法）

  - 它是从GCRoots开始，从上到下根据引用判断是否能链接到目标对象。可以达到目标对象，就不是垃圾；达不到的对象就是垃圾，等待回收
  - 相对于引用计数算法，执行效率没有那么高。但是主要可以解决循环引用的问题。

