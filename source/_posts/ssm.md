---
title: SSM框架集成基础（一）配置文件
date: 2018.1.27
tags: [SSM]
categories: SSM
---

1. 配置文件
   web.xml web应用程序的核心文件,web应用程序运行时，会首先读取web.xml文件,依据上面的代码完成初始化的配置
   application.xml web应用程序的应用配置文件,通常作为主配置文件写在web.xml中,当读取web.xml时也会读取application.xml 文件
   spring-mvc.xml 配置springmvc相关的配置文件
   spring-mybatis.xml 配置spring与mybatis集成的相关配置文件
2. 文件作用
3. 代码编写
3.1 首先我们需要在web.xml配置好spring核心,也就是DispatcherServlet

```java
<servlet>
   <servlet-name>dispatcher</servlet-name>
   <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
   <init-param>
     <param-name>contextConfigLocation</param-name>
     <param-value>classpath:spring-mvc.xml</param-value>
   </init-param>
   <load-on-startup>1</load-on-startup>
 </servlet>

 <servlet-mapping>
   <servlet-name>dispatcher</servlet-name>
   <url-pattern>/</url-pattern>
 </servlet-mapping>

```

3.2 web.xml注册加载application.xml文件

```java
<context-param>
  <param-name>contextConfigLocation</param-name>
  <param-value>classpath:application.xml</param-value>
</context-param>
```

3.3 application.xml 注册加载相关mybatis集成文件

```java

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="classpath:spring-mybatis.xml"/>

</beans>
```

3.4 spring-mvc.xml 加载相关springmvc的

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:mvc="http://www.springframework.org/schema/mvc"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mav="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">

    <!-- 注解的支持，可以将请求参数绑定到控制器参数-->
    <mvc:annotation-driven/>

    <!--注解扫描-->
    <context:component-scan base-package="org.aibo.*"/>

    <!--静态资源处理，mapping：匹配URL，location：静态资源在WebApp中的位置-->
    <mvc:resources mapping="/css/**" location="/css/"/>
    <mvc:resources mapping="/images/**" location="/images/"/>
    <mvc:resources mapping="/js/**" location="/js/"/>
    <mvc:resources mapping="/video/**" location="/video/"/>
    <mvc:resources mapping="/fonts/**" location="/fonts/"/>
    <mav:resources mapping="/bootstrap/**" location="/bootstrap/"/>
    <mvc:resources mapping="/layui/**" location="/layui/"/>

    <!-- 注解的映射器 -->
    <bean class="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping"/>

    <!-- 注解的适配器 -->
    <bean class="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter"/>

    <!-- 视图解析器 -->
    <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="contentType" value="text/html"/>
        <property name="prefix" value="/"/>
        <property name="suffix" value=".jsp"/>
    </bean>
</beans>

```


4. 总结
web.xml 配置springmvc框架的核心DispatcherServlet
application.xml 配置应用文件可以写在不同配置文件中然后导入,这样可以减少代码量,层次更加清楚
spring-mvc.xml 配置springmvc相关,主要是完成1.注解扫描配置２.视图解析配置3.适配器和控制器的配置4.静态资源映射配置
spring-mybatis.xml 配置mybatis相关,主要是完成1.数据源配置2.注解扫描包配置３.事务管理配置.
5. 未完代续......
