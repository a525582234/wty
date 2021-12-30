---
title: SpringBoot+MyBatisPlus 实现多数据源动态切换
date: 2021-12-30T16:32:06+09:00
description: SpringBoot+MyBatisPlus 实现多数据源动态切换
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 🤖
tags:
- springBoot
- MyBatisPlus
categories:
- Java ##series:-Themes Guide
image: /images/feature1/flowchart.png
---

本文主要介绍MybatisPlus中的组件Dynamic实现动态数据源切换；

1. Pom配置文件

   ```xml
    <dependencies>
   
           <dependency>
               <groupId>com.baomidou</groupId>
               <artifactId>dynamic-datasource-spring-boot-starter</artifactId>
               <version>3.3.2</version>
           </dependency>
   
           <!--Mysql驱动 -->
           <dependency>
               <groupId>mysql</groupId>
               <artifactId>mysql-connector-java</artifactId>
           </dependency>
           <!--Druid连接池 -->
           <dependency>
               <groupId>com.alibaba</groupId>
               <artifactId>druid-spring-boot-starter</artifactId>
               <version>1.2.8</version>
           </dependency>
           <!--Mybatis Plus -->
           <dependency>
               <groupId>com.baomidou</groupId>
               <artifactId>mybatis-plus-boot-starter</artifactId>
               <version>3.3.2</version>
           </dependency>
   
           <dependency>
               <groupId>org.springframework.boot</groupId>
               <artifactId>spring-boot-starter-web</artifactId>
           </dependency>
   
           <dependency>
               <groupId>org.projectlombok</groupId>
               <artifactId>lombok</artifactId>
               <optional>true</optional>
           </dependency>
           <dependency>
               <groupId>org.springframework.boot</groupId>
               <artifactId>spring-boot-starter-test</artifactId>
               <scope>test</scope>
               <exclusions>
                   <exclusion>
                       <groupId>org.junit.vintage</groupId>
                       <artifactId>junit-vintage-engine</artifactId>
                   </exclusion>
               </exclusions>
           </dependency>
       </dependencies>
   ```

   

2. Yaml文件配置

   ```yaml
   server:
       port: 8080
   spring:
       application:
           name: demo_one
   
       autoconfigure:
           #自动化配置 例外处理
           exclude: com.alibaba.druid.spring.boot.autoconfigure.DruidDataSourceAutoConfigure
       datasource:
           type: com.alibaba.druid.pool.DruidDataSource
           dynamic:
               primary: mysql #默认数据源
               datasource:
                   mysql1:
                       url: jdbc:mysql://mysqlIP:3306/test?useUnicode=true&characterEncoding=UTF-8&autoReconnect=true&useSSL=false&serverTimezone=GMT%2B8
                       username: root
                       password: 123456
                       driver-class-name: com.mysql.cj.jdbc.Driver
                   mysql2:
                       url: jdbc:mysql://mysqlIP:3306/test?useUnicode=true&characterEncoding=UTF-8&autoReconnect=true&useSSL=false&serverTimezone=GMT%2B8
                       username: root
                       password: 123456
                       driver-class-name: com.mysql.cj.jdbc.Driver
   #	如果是oracel 也是一样的
   #                oracle:
   #                    url: jdbc:oracle:thin:@127.0.0.1:1521:xe
   #                    username: system
   #                    password: 123123
   #                    driver-class-name: oracle.jdbc.OracleDriver
               druid:
                   max-active: 50
                   max-wait: 10000
                   min-idle: 3
                   initial-size: 5
   
   mybatis-plus:
       #  mapper-locations:复杂的操作可能需要自己写SQL，SQL可以写到xml文件中，这里指定和Dao对应的xml文件，此时我们需要在resources中创建一个mapper目录
       mapper-locations: mapper/*.xml
       #  type-aliases-package:指定JavaBean的别名包，和MyBatis用法一样
       type-aliases-package: com.*.entity
       configuration:
           #    map-underscore-to-camel-case:开启驼峰功能，数据库表列名如果有_，可以自动按驼峰命名规则转换
           map-underscore-to-camel-case: true
           #    log-impl:日志开启，方便测试
           log-impl: org.apache.ibatis.logging.stdout.StdOutImpl
   ```

   

3. 动态数据切换

   1. 直接使用注解指定数据源，具体使用例子如下：

      ```java
      package com.wty.demo_one.mapper;
      
      import com.baomidou.dynamic.datasource.annotation.DS;
      import com.baomidou.mybatisplus.core.mapper.BaseMapper;
      import com.wty.demo_one.entity.User;
      import org.apache.ibatis.annotations.Mapper;
      
      @Mapper
      @DS("mysql2")//可以使用在类上
      public interface UserMapper extends BaseMapper<User> {
          @DS("mysql1")//也可以使用在方法上
          User selectOne(Long userId);
      }
      ```

      