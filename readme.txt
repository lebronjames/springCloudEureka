注册中心Eureka, 系统版本：SpringBoot：1.3.5.RELEASE ，SpringCloud：Brixton.RELEASE
1) pom.xml引入
spring-cloud-starter-eureka-server
2) Application主类增加@EnableEurekaServer注解，启动一个服务注册中心提供给其他应用进行对话
3) 修改系统启动参数（可选）
server:
  port: 1111
eureka:
  instance:
    hostname: peer1
  client:
  #是否注册自身到eureka服务器
    register-with-eureka: true
  #是否从eureka服务器获取注册信息
    fetch-registry: true
    serviceUrl:
      defaultZone: http://peer2:1112/eureka/
      
Eureka Server的同步遵循着一个非常简单的原则：只要有一条边将节点连接，就可以进行信息传播与同步
http://10.5.2.241:1111/