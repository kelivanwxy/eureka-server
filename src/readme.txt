一、勾选spring cloud discovery、选择Eureka Server
二、启动类添加注解@EnableEurekaServer
三、启动项目，访问当前端口即可访问Eureka页面
四、解决控制台报错问题，服务端自身也实现客户端功能，需要自己注册自己，代码如下
    eureka:
      client:
        service-url:
          defaultZone: http://localhost:8080/eureka/
五、添加项目名称，修改端口号为8761，隐藏自身注册
    spring:
      application:
        name: eureka-server

    server:
      port: 8761

    eureka:
      client:
        service-url:
          defaultZone: http://localhost:8761/eureka/
        register-with-eureka: false
六、$ git push -u origin master
    上面命令将本地的master分支推送到origin主机，同时指定origin为默认主机，
    后面就可以不加任何参数使用git push了