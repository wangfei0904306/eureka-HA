# 搭建高可用的Eureka注册中心
---
## 分支说明
- dev_use_hosts是常用的配置hosts启动方式
- dev_no_hosts是不配置hosts的启动方式
## 使用说明
- 下载项目并启动Eureka1Application，Eureka2Application，Eureka3Application和ExampleServiceApplication
- 依次查看http://127.0.0.1:8761/ ，http://127.0.0.1:8762/ ，http://127.0.0.1:8763/
- 每个注册中心的available-replicas都出现两个服务，说明搭建成功。




