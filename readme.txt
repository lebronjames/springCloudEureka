注册中心Eureka, 系统版本：SpringBoot：1.3.5.RELEASE ，SpringCloud：Brixton.RELEASE
1) pom.xml引入
spring-cloud-starter-eureka-server
2) Application主类增加@EnableEurekaServer注解，启动一个服务注册中心提供给其他应用进行对话
3) 修改系统启动参数（可选）
server:
  port: 1111
eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
    serviceUrl:
      defaultZone: http://localhost:${server.port}/eureka/