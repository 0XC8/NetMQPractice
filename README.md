# NetMQPractice
NetMQ经验代码实例。

根据项目经验，一般应用于`Clients-Server`架构的多端软件开发的模式，当前实例项目记录自己的项目最佳实践经验，还封装了后端接收到消息后的仿MVC路由执行机制。（项目经验有限，还有NetMQ的更多功能可能还未使用过，待以后实际使用了再增加）

## NetMQ 简介
NetMQ是轻量级消息通信库ZeroMQ的100%纯C#实现。

NetMQ使用一些传统上专用消息中间件产品提供的功能扩展了标准`socket`，NetMQ的sockets提供了 对异步消息队列的抽象、多路消息模式、消息过滤（订阅）、无缝访问多种通信协议等功能。  本质上是`socket`的封装，组件本身不带数据持久化的，不同于ActiveMQ/RabbitMQ等；优点：**性能高，轻量级，无依赖**。

**文档：**
- [官网：GitHub项目地址](https://github.com/zeromq/netmq)
- [NetMQ 文档（精简实用）](https://netmq.readthedocs.io/en/latest/)
- [ZeroMQ 详细文档（超长内容）](http://zguide.zeromq.org/page:all)

## 实例演示范围
- 客户端`Request-Response 阻塞式` 向服务器端一对一请求数据；
- 客户端`Router-Dealer 非阻塞式` 向服务端请求数据，或者服务端向客户端一对一推送数据；
- 服务端`Publish–subscribe 广播模式` 向所有客户端广播发布消息；
- 客户端登陆服务端授权方式；
- 服务端采用仿MVC的`Controler`模式编写代码，处理客户端到服务端请求数据的命令路由场景。
