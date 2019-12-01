# Spring Cloud 微服务入门教程

## 适宜人群

- 具备Java基础，对Spring Cloud有一定兴趣,又懒得看书或者官方文档的
- 了解Spring，Spring MVC， Spring Boot，Maven
- 会使用git，因为代码的例子会存放在github和码云上
- 对于已经了解Spring Cloud组件的朋友，可以直接绕道看Spring文档

## 前言

与微服务架构的概念想对应的是单体架构应用。以一个电商系统为例。电商系统包含客户子系统，经销商子系统，商品子系统，订单子系统等。单体应用把所有的子系统集合在一个\*.jar,\*.war,\*.ear中进行发布。而微服务架构允许我们单独发布每一个子系统。

### 微服务的优劣

微服务最大的特性：以增加系统整体复杂度为代价，提高系统弹性。

#### 优点

- 每个应用的单独发布使得微服务更容易进行水平扩展。例如电商系统的业务在进行大量会员注册的时候需要增加客户子系统的实例数量以支撑更多的注册请求。那么微服务架构的系统可以只水平扩充客户子系统的服务数量。而单体应用只能选择扩充整个服务的实例数量。
- 更小的代码量让开发人员在更短的时间内熟悉子系统的业务逻辑。
- 更小的代码量，意味着每个系统只需要更短的启动时间。我曾经面对过一个启动需要10-15分钟的电商系统。而我仅仅是修改了客户管理系统中的一小块代码。
- 还有一个很屌(丝)的优点是：阿里云服务器1核cpu,2GB内存，40GB SSD,年费为609元，而2核cpu，4GB内存, 60GB SSD的价格是1872元。硬件资源提升1倍，价格提升3倍。

#### 缺点

- 增加开发人员的学习成本。
- 因为单体应用的拆分导致系统内的调用变成了系统间的调用，增加了整个系统的复杂度。典型的不适应在于，以前几个sql的join能解决的问题变成了几个子系统之间的调用。以前用事务包裹起来就能简单实现的失败回滚变成了要自己想办法的事情。

以上优缺点存储个人臆想结果，没有查阅任何资料，如果读者作为面试答案回答，导致丢失工作，笔者概不负责。

## 范围

Spring Cloud核心组件。

- Actuator
- Config-server
- Eureka
- Hystrix
- Zuul
- Security
- Stream
- Sleuth & Zipkin