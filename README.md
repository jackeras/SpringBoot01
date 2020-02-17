# Spring Boot的学习（idea）

#### 1.SpringBoot以及微服务思想的学习

简单来说就是SpringBoot其实不是什么新的框架，它默认配置了很多框架的使用方式，就像maven整合了所有的jar包，spring boot整合了所有的框架 。

**SpringBoot：“约定大于配置”，可以通过SpringBoot来构建一个个功能独立的微服务应用单元。**

​	Spring Boot的主要优点：

- 为所有Spring开发者更快的入门
- **开箱即用**，提供各种默认配置来简化项目配置
- 内嵌式容器简化Web项目
- 没有冗余代码生成和XML配置的要求



**微服务**是一种架构风格，它要求我们在开发一个应用的时候，这个应用必须构建成一系列小服务的组合；可以通过http的方式进行互通。要说微服务架构，先得说说过去我们的单体应用架构。

所谓单体应用架构（all in one）是指，我们将一个应用的中的所有应用服务都封装在一个应用中。

所谓微服务架构，就是打破之前all in one的架构方式，把每个功能元素独立出来。把独立出来的功能元素的动态组合，需要的功能元素才去拿来组合，需要多一些时可以整合多个功能元素。所以微服务架构是对功能元素进行复制，而没有对整个应用进行复制。

![Uploading 3173282649.png…](F:\code\SpringBoot01\images\3173282649.png)

#### 2.HelloWorld

##### 1)在idea下新建一个项目

new--->project---->Spring Initializr---->next---->

![image-20200202202350146](F:\code\SpringBoot01\images\image-20200202202350146.png)

----Next---->

![image-20200202202520347](F:\code\SpringBoot01\images\image-20200202202520347.png)



![image-20200202202547942](F:\code\SpringBoot01\images\image-20200202202547942.png)



![image-20200202202646637](F:\code\SpringBoot01\images\image-20200202202646637.png)

##### 2)HelloWorld项目新建步骤

1）仅需要在项目下新建一个HelloWorld02的类

2）加上Controller、RequestMapping注解，idea中

```java
@Controller
public class HelloWolrd02 {
    @RequestMapping("/hello")
    public void HelloWorld(){
        System.out.println("heihei");
    }
}
```

**总结：相对于Spring而言，少去了导包、加配置等繁杂的步骤，十分的便捷。但是对于学习底层原理，如果没有一定spring基础可能一开始就会很懵圈。**

#### 2.原理初探

1）自动装配：

​	**spring-boot-dependencies**：核心依赖都在父工程中

启动器：说白了就是SpringBoot的启动场景

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

- 比如：spring-boot-starter-web，他就会帮我们自动导入web环境所有的依赖！
- SpringBoot回见所有的功能场景，都变成了一个个的启动器
- 我们要使用什么功能，就只需要找到对应的启动器就可以了







