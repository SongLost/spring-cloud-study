
-----------------

<h2 align="center">:heart::heart::heart:如果觉得我的文章或者代码对您有帮助,可以请我喝杯咖啡哦:heart::heart::heart:</h2>
<div  align="center">    
  <img src="https://raw.githubusercontent.com/timebusker/timebusker.github.io/master/mine/wxpay.png?raw=true" width = "200" height = "200" alt="WXPAY" align=center />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/timebusker/timebusker.github.io/master/mine/alipay.png?raw=true" width = "200" height = "200" alt="ALIPAY" align=center />
</div>  
<h2 align="center">:smile::smile::smile:您的支持将鼓励我继续创作...谢谢!:smile::smile::smile:</h2>

-----------------

- ### 关于微服务架构
   + “微服务 ”一词源于 Martin Fowler 的名为 Microservices 的博文， 可以在他的官方博客
     上找到：[Microservices](http://mar巨nfowler.com/articles/microservices.html)。
   + 简单地说， 微服务是系统架构上的一种设计风格， 它的主旨是将一个原本独立的系统
     拆分成多个小型服务，这些小型服务都在各自独立的进程中运行，服务之间通过基于HTTP
     的RESTful API进行通信协作。 被拆分成的每一个小型服务都围绕着系统中的某一项或一
     些耦合度较高的业务功能进行构建， 并且每个服务都维护着自身的数据存储、 业务开发、
     自动化测试案例以及独立部署机制。 由于有了轻量级的通信协作基础， 所以这些微服务
     可以使用不同的语言来编写。
   + **微服务架构就是将一个完整的应用从数据存储开始垂直拆分成多个不同的服务，每个服务都能独立部署、独立维护、独立扩展，服务与服务间通过轻量级的通信机制（REST API或者RPC）互相调用。**

- ### 单体架构
   + 在传统的企业系统架构中，针对一个复杂的业务需求通常使用对象或业务类型来构建一
     个单体项目。在项目中将需求分为三个主要部分：**数据库、服务端处理、前端展现**。在业务
     发展初期，由于所有的业务逻辑在一个应用中，开发、测试、部署都还比较容易且方便。但
     是，随着企业的发展，系统为了应对不同的业务需求会不断为该单体项目增加不同的业务模
     块；同时随着移动端设备的进步，前端展现模块已经不仅仅局限于Web的形式，这对于系统后
     端向前端的支持需要更多的接口模块。单体应用由于面对的业务需求更为宽泛，不断扩大的需
     求会使得单体应用变得越来越腕肿。单体应用的问题就逐渐凸显出来，由于单体系统部署在一
     个进程内，往往我们修改了一个很小的功能，为了部署上线会影响其他功能的运行。并且，单体
     应用中的这些功能模块的使用场景、并发量、消耗的资源类型都各有不同，对于资源的利用又互
     相影响，这样使得我们对各个业务模块的系统容量很难给出较为准确的评估。所以，单体系统在
     初期虽然可以非常方便地进行开发和使用， 但是随着系统的发展，维护成本会变得越来越大，
     且难以控制。
   + 为了解决单体系统变得庞大脯肿之后产生的难以维护的问题，微服务架构诞生了并被我们将
     系统中的不同功能模块拆分成多个不同的服务，这些服务都能够独立部署和扩展。由于每个服务
     都运行在自己的进程内，在部署上有稳固的边界，这样每个服务的更新都不会影响其他服务的运行。
     同时，由于是独立部署的，我们可以更准确地为每个服务评估性能容量，通过配合服务间的协作流
     程也可以更容易地发现系统的瓶颈位置，以及给出较为准确的系统级性能容量评估。

- ### 架构演进
  ![image](https://github.com/timebusker/spring-cloud-study/raw/master/static/0/架构演进.png?raw=true)  

- ### 实施微服务
  + #### 单体应用的缺点：
     - 复杂性逐渐变高
     - 技术债务逐渐上升
     - 部署速度逐渐变慢
     - 阻碍技术创新
     - 无法按需伸缩
  + #### 微服应用的特性：
     - 服务组件化，每个微服务可独立运行在自己的进程里
     - 一系列独立运行的微服务共同构建起了整个系统
     - 每个服务为独立的业务开发，一个微服务一般完成某个特定的功能（订单管理、用户管理等）
     - 微服务之间通过一些轻量级的通信机制进行通信（REST API或者RPC）
  + #### 微服应用的优点：
     - 易于开发和维护
     - 启动较快
     - 局部修改容易部署
     - 技术栈不受限
     - 按需伸缩
     - DevOps
  + #### 微服面临的挑战：
     - 运维要求较高（应用进程大量增加，运维难度大）
     - 分布式的复杂性（需要关注网络延迟、分布式事务、异步消息等）
     - 接口调整成本高（业务逻辑上的依赖并不会消除， 只是从单体应用中的代码依赖变为了服务间的通信依赖）

- ### 从单体应用到微服务
  + #### [为什么选择Spring Cloud](http://blog.didispace.com/microservice-framework/)
     - SpringCloud的出现，可以说是对微服务架构的巨大支持和强有力的技术后盾。它不像
       Dubbo（服务治理）、Disconf(分布式配置管理)、Elastic-Job（批量任务）、Zipkin（服务跟踪）等框架那样， 
       只是解决微服务中的某一个问题， 而是一个解决微服务架构实施的综合性解决框架，它整合了诸多被广泛实践和
       证明过的框架作为实施的基础部件，又在该体系基础上创建了一些非常优秀的边缘组件。

  + #### 微服务设计原则
     - 单一职责原则
     - 服务自治原则
     - 轻量级通信原则
     - 接口明确原则
  + #### 垂直拆分单体应用
     - 在架构师对于一个大型系统架构的设计与实施的过程中，面对环境、资源、团队等各种因素的影响，
       几乎不会出现完全相同的架构设计。 对于微服务架构而言更是如此， 由于并没有一个标准或正式的定义， 
       每位架构师都根据自身理解与实际情况来进行设计， 并在发展的过程中不断演化与完善。
     - 服务拆分可以实施横向或者纵向两种拆分方式，甚至可以将应用进行横向和纵向的拆分，按照不同的业务域进行拆分，
       形成独立的业务领域微服务集群；同时把一个业务功能里的不同模块或者组件进行拆分。例如把公共组件拆分成独立的原子服务，
       下沉到底层，形成相对独立的原子服务层。这样一纵一横，就可以实现业务的服务化拆分。
     - 按照不同的业务域进行拆分，例如订单、商品、权限、用户等，形成独立的业务领域微服务集群。
       ![image](https://github.com/timebusker/spring-cloud-study/raw/master/static/0/服务垂直拆分转型.png?raw=true)

- ### Spring Cloud简介
   + Spring Cloud是 一个基千Spring Boot实现的微服务架构开发 工具。 它为微服务架构中
     涉及的 配置管理、 服务治理、 断路器、 智能路由、 微代理、 控制总线、 全局锁、 决策竞选、
     分布式会话和集群状态管理等操作提供了 一种简单的开发方式。
   + Spring Cloud包含了多个子项目（针对分布式系统中涉及的多个不同开源产品，还可能会新增）， 如下所述：
     - **Spring Cloud Config**：配置管理工具， 支持使用Git存储 配置内容， 可以使用它实现应用配置的外部化存储，
       并支持客户端配置信息刷新、加密／解密配置内容等。
     - **Spring Cloud Netflix**： 核心组件，对多个Netflix OSS开源套件进行整合
         * ***Eureka***：服务治理组件，包含服务注册中心、服务注册与发现机制的实现
         * ***Hystrix***：容错管理组件，实现断路器模式，帮助服务依赖中出现的延迟和为故障提供强大的容错能力。
         * ***Ribbon***:客户端负载均衡的服务调用组件
         * ***Feign***:基于 Ribbon 和 Hystrix 的声明式服务调用组件
         * ***Zuul***:网关组件，提供智能路由、访问过滤等功能
         * ***Archaius***:外部化配置组件
     - **Spring Cloud Bus**：事件、消息总线，用于传播集群中的状态变化或事件，以触发后续的处理，比如用来动态刷新配置等
     - **Spring Cloud Cluster**：针对 ZooKeeper、Redis、Hazelcast、Consul 的选举算法和通用状态模式的实现
     - **Spring Cloud Cloudfoundry**：与 Pivotal Cloudfoundry 的整合支持
     - **Spring Cloud Consul**：服务发现与配置管理工具
     - **Spring Cloud Stream**：通过 Redis、Rabbit、Kafka 实现的消费微服务，可以通过简单的声明式模型来发送和接收消息。
     - **Spring Cloud AWS**：用千简化整合 Amazon Web Service 的组件
     - **Spring Cloud Security**：安全工具包，提供在 Zuul 代理中对 OAuth2.0 客户端请求的中继器。
     - **Spring Cloud Sleuth**：Spring Cloud 应用的分布式跟踪实现， 可以完美整合 Zipkin
     - **Spring Cloud ZooKeeper**：基于 ZooKeeper 的服务发现与配置管理组件
     - **Spring Cloud Starters**：Spring Cloud 的基础组件，它是基于 Spring Boot 风格项目的基础依赖模块。
     - **Spring Cloud CLI**：用于在Groovy中快速创建 Spring Cloud 应用的 Spring Boot CLI 插件

- ### 项目开发环境
  - JDK1.8
  - Maven 3.3.9
  - Eclipse
  - undertow
  - slf4j + logback
  - spring boot 1.5.3.RELEASE
  - spring cloud Dalston.SR1

- ### 相关文章
   - [**Spring Cloud 参数配置**](https://github.com/timebusker/spring-cloud-study/tree/master/static/Article/spring-cloud参数配置.md)
   - [**Eureka Server的高可用**](https://github.com/timebusker/spring-cloud-study/tree/master/static/Article/Eureka-Server高可用.md)

#### 模块列表
----
#### [spring-cloud-study-1-1..........................................入门实践](https://github.com/timebusker/spring-cloud-study/tree/master/spring-cloud-study-1-1/)


#### [spring-cloud-study-2-1..........................................分布式配置中心](https://github.com/timebusker/spring-cloud-study/tree/master/spring-cloud-study-2-1/)

#### [spring-cloud-study-3-1..........................................消息总线](https://github.com/timebusker/spring-cloud-study/tree/master/spring-cloud-study-3-1/)

#### [spring-cloud-study-4-1..........................................服务网关](https://github.com/timebusker/spring-cloud-study/tree/master/spring-cloud-study-4-1/)

----
