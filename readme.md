# log4j笔记

# 疑问：

1. lo4j的jar有两种：

   ```xml
   <!-- https://mvnrepository.com/artifact/log4j/log4j -->
   <dependency>
       <groupId>log4j</groupId>
       <artifactId>log4j</artifactId>
       <version>1.2.17</version>
   </dependency>
   
   ```

   ```xml
   <!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core -->
   <dependency>
       <groupId>org.apache.logging.log4j</groupId>
       <artifactId>log4j-core</artifactId>
       <version>2.12.1</version>
   </dependency>
   
   ```

   问题来了，到底用哪种？两种有什么区别？

   解决：用slf4j、log4j结合用

2. log4j、slf4j的区别

   1. log4j

      ```java
      private static final Logger log=Logger.getLogger(this.class);
      ```

   2. slf4j

      ```java
      private static final Logger log=LoggerFactory.getLogger(this.class);
      ```

      问题来了，Logger声明是不是一样？

# 1、log4j能做什么

## 1、可以控制日志的输入地

这些地点包括：

1. 本地文件。
2. 控制台。
3. GUI组件。
4. 套接口服务器。
5. NT的事件记录器。

## 2、控制日志的输出格式

1. 按照时间显示日志，存放日志。

# 2、log4j关键点

1. 目的地：appender
2. 布局：layout
3. 控制单元：logger（有点难懂）
4. 级别：level

3、log4j日志级别

debug<info<warn<error<fatal<off

log.debug();

log.info();

... ... 

log4j.rootlogger=debug，表示把debug以及高于debug级别的日志都打印出来.

# 3、多个控制单元

级别由logger精确度最高的确定，比如精确到包的，而输出看各自的。

上述对properties有用，而xml可以更精确。

# 4、log4j.xml/log4j.properties

log4j.xml优先级别高于properties，log4j.xml能控制的粒度更高

log4j.xl比较重要的：

1. filter
2. activity=false（只有自己决定，其他的logger控制单元没有用）
3. log4je（eclipse log4j插件）