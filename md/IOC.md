IOC(Inversion of Control, 控制反转)是一种软件设计原则，用于管理应用程序中各个组件之间的依赖关系。

后端系统中，会有很多对象：

- Controller：接受 http 请求，调用 Service，返回响应。
- Service：实现业务逻辑。
- Repository：实现对数据库的增删改查。

此外，还有数据库链接对象 DataSource，配置对象 Config 等等。

在应用初始化的时候，需要先理清依赖之间关系，创建所有对象并组合起来。这是后端系统的一个痛点问题，解决这个痛点的就是 IOC 控制反转。

什么是 IOC：在 class 上声明依赖了什么，然后让工具去分析声明的依赖，根据先后顺序自动把对象创建好，然后组装起来。这就是 IOC 的实现思路。

1. Service 可以被注入也可以注入到别的对象；
2. Controller 只需要被注入