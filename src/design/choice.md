# 选型

项目的选型其实非常简单，只要遵循如下的原则：

- 除了项目核心功能的实现外，所有的选型全部选择成熟的开源项目
- 选择文档完善，用的人较多的开源项目
- 如果你不确定该项目是否可用，那就先选择它，但注意要在其上再封装一层，方便随时替换
- 重要的部分选择重量级的项目，不太重要的部分选择轻量的项目
- 选择简单易用好理解的开源项目

在本组新的项目选型的方面，推荐大家使用如下的框架（这也是我们实践过比较方便的脚手架）：

- Java后端开发：集成式的框架建议使用ruoyi（新项目一般使用ruoyi的Vue版本），如果需要一些其他比较奇怪的数据库的话（比如NoSQL和图数据库）建议使用SpringData，RPC框架如果主要是在Springboot框架下开发的话建议使用dubbo，如果需要在其他语言或框架下做开发的话可以使用openfeign去连接（HTTP协议，开发较为简单）或者grpc（现在Springboot的grpc支持非常不错了），消息队列如果对性能要求不是很高的情况下，使用ActiveMQ内置的队列可能会更方便部署，如果需要多语言支持的话，Kafka，RabbitMQ可能更好一些。
  ___注：其实现阶段Dubbo的生态也非常不错了，异构开发其实也可以考虑dubbo，不过没在其他语言中用过dubbo，所以具体怎么样笔者也不知道___
- python后端开发：python后端目前没有用到过比较集成的框架，毕竟目前python在组内是使用都是做微服务的，这部分使用Sanic这种框架可能比Django更方便，性能也不差很多，消息队列的话如果是python微服务内部使用的话推荐使用[RQ框架](https://python-rq.org/)，这个更方便一些，和组内长时任务的需求也比较相符合。
- 前端开发：前端肯定是Vue体系了，如果使用ruoyi就参考ruoyi的开发流程操作就好，图表这边，图结构推荐使用AntV G6，其他图标推荐使用EChart
- 网关层：网关这边没什么好说的，OpenResty莽就完事了，如果需要成品的框架的话可能Kong是一个不错的选择。市面上也有一些Java的网关，不过没用过，不好评价。据说Cloudflare那边计划把他们开源的Rust库扩写成一个网关（主要是反向代理和缓存方面的，对权限方面可能不那么完善）如果在开启新项目的时候碰巧他们已经production ready了可以调研调研尝试一下。