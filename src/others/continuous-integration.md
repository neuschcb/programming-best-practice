# 关于持续集成

在项目开发过程中，其实本人有考虑过利用Gitlab自带的runner功能对业务微服务进行CI/CD改造，但最后由于各方面的原因并没有真实落地。建议新项目在建立之初就考虑充分利用CI/CD服务，对所有人都方便。

其实也不需要太高深的CI/CD技术，只需要写一个Shell脚本跑通编译，部署，重启服务流程即可，但很可惜，在一个光秃秃的环境中我们实在是无法实现，希望下次在开发新项目的过程中可以好好的实践CI/CD。
