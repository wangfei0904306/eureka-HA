# 搭建高可用的Eureka注册中心
---
## 分支说明
- **dev_use_hosts是常用的配置hosts启动方式**:使用hosts区分hostname   
- **dev_no_hosts是不配置hosts的启动方式**:使用当前机器IP地址、17.0.0.1和localhost区分hostname 
## 使用说明
- 下载项目并启动Eureka1Application，Eureka2Application，Eureka3Application和ExampleServiceApplication
- 依次查看http://127.0.0.1:8761/ ，http://127.0.0.1:8762/ ，http://127.0.0.1:8763/
- 每个注册中心的available-replicas都出现两个服务，说明搭建成功。
## 项目中配置说明
项目中Eureka配置非常简单，如果是分别部署在三台机器上，只须按如下配置每个Eureka并修改defaultZone的server2IP和server3IP为相应的机器地址即可。如果部署在单台机器上（一般都不会这样做），参考no_hosts分支即可。
```
spring:
  application:
    name: eureka

server:
  port: 8761

eureka:
  instance:
    hostname: ${spring.cloud.client.ipAddress}
    prefer-ip-address: true
  client:
    serviceUrl:
      defaultZone: http://server2IP:8761/eureka/,http://server3IP:8761/eureka/
```

[更为详细的说明](http://blog.csdn.net/wangfei0904306/article/details/79056083)

