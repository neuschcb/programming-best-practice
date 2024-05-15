# 微服务设计

做微服务设计一方面是为分布式做准备，另一方面也是对于异构的项目来说必须经理的设计。本项目中使用了springboot，scala（spark），python作为项目语言，且在实践过程中发现springdata jpa和springdata neo4j存在冲突，需要分开，故必须对项目的微服务进行设计。

本项目中微服务间交互使用http协议，使用openfeign封装好的方式实现请求，该方案无需对编码人员增加太多的负担，编码人员只需要完成http接口的编写即可进行rpc，这是非常好的rpc方案。当然，涉及到多语言（Java，Go，Rust等混合）同时使用的时后，也可以去寻找其他普适性的框架，如grpc等，但就本项目而言，并不需要grpc来提升性能，相比Spark实时计算造成的耗时，json解析的耗时实在是不算什么了。