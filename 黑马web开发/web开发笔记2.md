# Node.js

**Node.js是一个开源的跨平台的==JavaScript运行环境==**，它允许开发者在服务器端运行JavaScript代码。Node.js基于Google的V8引擎，使得JavaScript代码的执行速度非常快，性能优异。它使得JavaScript可以在服务器端运行，而不仅仅局限于浏览器端的客户端脚本语言。



- 将npm安装路径配置成全局路径

​	`~/.bash_profile`: 用户主目录下的 `.bash_profile` 文件，这是一个 shell 启动文件，登录时会被执行。

- 输入命令使配置生效

​	`source ~/.bash_profile`





# Maven 

## 新建项目

https://blog.csdn.net/guorenhao/article/details/124583146

连包带类一起创建controller.HelloController：

- 包：controller

- 类：HelloController

	

> **artifact ：** 开发过程中生成的任何有价值的输出物，例如文档、代码库、可执行文件、设计图等。
>
> 例子：The build process generates several artifacts, including the application binary and deployment scripts. (构建过程生成了几个产出物，包括应用程序二进制文件和部署脚本。)



## 依赖配置注意点

1. 在maven工程的pom.xml文件中

	和视频中不一样的点：

	- 右键diagrams   bundle的UML插件    需要下载专业版本
	- 没有自动生成如下代码，需要补全

	```xml
	<properties>
	    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
	    <java.version>17</java.version>
	    <maven.compiler.source>17</maven.compiler.source>
	    <maven.compiler.target>17</maven.compiler.target>
	</properties>
	```

	

2. 配置生效需要点击 右上角m的小标



## 生命周期

1. 在同一套生命周期中，我们在执行后面的生命周期时，前面的生命周期都会执行。
	- package打包📦的jar包会放在target下，双击target，在其之前的test（同一个生命周期下）也会运行

2. install：讲打包好的jar包安装到maven的本地仓库下
3. maven界面上的小闪电可以选择跳过某个阶段
4. clean清理上个生成到target下的文件



## IDEA配置

IDEA2023的同学，请选module左侧generators下的MavenArchetype然后中间“Archetype”中下拉选择后缀为“quickstart”目即可









# Springboot

## 简介

Spring家族旗下这么多的技术，最基础、最核心的是 SpringFramework。其他的spring家族的技术，都是基于SpringFramework的，SpringFramework中提供很多实用功能，如：依赖注入、事务管理、web开发支持、数据访问、消息服务等等。

在项目中，直接基于SpringFramework进行开发，存在两个问题：配置繁琐、入门难度大。 **Spring Boot 可以帮助我们非常快速的构建应用程序、简化开发、提高效率 。**





## 基于SpringBoot进行Web开发

1. 创建项目后将java包设置成source这样可以新建java class

	

2. 标红点一下pom.xml文件

	- `@RestController`
		RESTful Web Service Controller。这个注解是用于创建 RESTful 风格的 Web 服务控制器。

		`@RestController` 是 `@Controller` 和 `@ResponseBody` 注解的组合。以下是它们的作用和组合的目的：

		- **`@Controller`**：标记一个类作为 Spring MVC 控制器。这个类的处理方法将用于处理 Web 请求。
		- **`@ResponseBody`**：注解在方法上，表示方法的返回值会被==自动转换为 JSON 或 XML 格式==，并直接写入 HTTP 响应体中，而不是返回一个视图页面。

		

	- `@RequestMapping("/hello")`

		注解在 `hello` 方法上，将其映射到一个 HTTP 请求路径。默认情况下，它映射到根路径（`/`）。

3. 自动生成的包名（删除蓝色部分）

	![image-20240616142300947](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240616142300947.png)

  	后面的依赖选择Web下的Spring Web

### 启动类

```java
@SpringBootApplication
public class SpringbootWebQuickstartApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringbootWebQuickstartApplication.class, args);
    }

}
```




### 请求

- **形参**

在Springboot的环境中，对原始的==HttpServletRequest request==进行了封装，接收参数的形式更加简单。 如果是简单参数，参数名与形参变量名相同，定义==同名的形参==即可接收参数。

~~~java
@RestController
public class RequestController {
    // http://localhost:8080/simpleParam?name=Tom&age=10
    // 第1个请求参数： name=Tom   参数名:name，参数值:Tom
    // 第2个请求参数： age=10     参数名:age , 参数值:10
    
    //springboot方式
    @RequestMapping("/simpleParam")
    public String simpleParam(String name , Integer age ){//形参名和请求参数名保持一致
        System.out.println(name+"  :  "+age);
        return "OK";
    }
}

/*不同名形参*/
@RestController
public class RequestController {
    // http://localhost:8080/simpleParam?name=Tom&age=20
    // 请求参数名：name （Postman中设置的）

    //springboot方式
    @RequestMapping("/simpleParam")
    public String simpleParam(@RequestParam("name") String username , Integer age ){
        System.out.println(username+"  :  "+age);
        return "OK";
    }
}
~~~



- **实体参数**

	**POJO** 是 "Plain Old Java Object" 的缩写，意思是 "简单旧式 Java 对象"。POJO 实体类指的是一个没有特殊要求的 Java 类，它通常用于表示数据库中的表或持久化存储中的记录。



- 集合

	`@RequestParam List<String> hobby`

	> **`@RequestParam` 的作用**
	>
	> - **绑定参数**：`@RequestParam` 注解将查询参数 `hobby` 绑定到控制器方法的 `List<String> hobby` 参数上。Spring 会自动将请求参数值（`reading`、`cooking`、`travelling`）转换为 List 类型，并注入到方法参数中。
	> - **处理多个值**：Spring 自动处理同名参数的多个值，并将它们作为列表传递给方法参数。
	> - **类型转换**：如果请求参数是其他类型（例如整数），Spring 会自动进行类型转换。
	>
	> - **`required` 属性**：指定参数是否是必需的（默认是 `true`）。如果参数是可选的，可以设置 `required = false`。

	

- JSON

	需要将Http方法设置成POST，因为JSON的数据需要放在请求体中

	其他的一般选择x-www-form-urlencoded

	在body中选择raw & JSON

	JSON数据==键名与形参对象属性名==相同，实现自动封装，定义POJO类型形参即可接收参数

	需要使用 @RequestBody 标识，将JSON对象的请求数据封装到一个实体对象



![image-20240609220218374](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240609220218374.png)





### 响应

**统一响应结果**

Result (code, msg, data)

```java
public class Result {
    private Integer code;//响应码，1 代表成功; 0 代表失败
    private String msg;  //响应码 描述字符串
    private Object data; //返回的数据
}
```



 Java 静态方法（Static Method）

> 属于类本身而不是类的实例的方法。使用 `static` 关键字进行声明，通常用于那些不依赖于实例变量和实例方法的功能。可以直接通过`类名.方法名`访问



### 案例

**需求**：获取员工数据（xml文件），完成数据处理，并在页面展示

1. 文件

  - 员工数据(emp.xml)，直接导入进来，放在 src/main/resources目录下
  - 员工实体类 Emp.java，放置于POJO包下

2. 工具类

  - 在pom.xml引入dom4j依赖，为XmlParserUtils服务

  - 已经准备好解析XML文件的工具类XmlParserUtils

    > **List<T>**:它表示返回一个包含 `T` 类型对象的列表。`List` 是一个接口，通常用来表示元素有序且可重复的集合。`T` 是一个占位符，代表某种类型。使用泛型可以使方法能够处理各种类型，而不需要指定具体的类型。

  - 直接在创建一个包 com.itheima.utils ，然后将工具类XmlParserUtils拷贝进来

    

    ```java
    // 组装数据
    //获取构造方法，加上declared说明包括私有的也能获取
    Constructor<T> constructor = targetClass.getDeclaredConstructor(String.class, Integer.class, String.class, String.class, String.class);
    constructor.setAccessible(true);
    T object = constructor.newInstance(name, Integer.parseInt(age), image, gender, job);
    
    list.add(object);
    
    ```

    **反射机制**

    https://www.bilibili.com/video/BV1ke4y1w7yn/?spm_id_from=333.337.search-card.all.click&vd_source=8a49335b38d7c23e4806c2d0a1adfb84

    反射通过==class字节码文件==，对封装类的字段（变量），方法和构造函数的信息进行编程访问。

    e.g.  idea的自动补全提示

    

    - 获取class对象的三种方式

    	> 源代码阶段（只存在于硬盘当中）
    	>
    	> 获取全类名：包名+类名（类名右键选copy reference）

    	![image-20240610142854221](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240610142854221.png)

3. 前端向后端索要数据，后端从xml里解析数据

	











3. 前端页面资源
	- 已经准备好，直接拷贝进来，放在src/main/resources下的static目录下

> 在SpringBoot项目中，静态资源默认可以存放的目录：
>
> - classpath:/static/
> - classpath:/public/
> - classpath:/resources/
> - classpath:/META-INF/resources/
>
> classpath：
>
> - 代表的是类路径，在maven的项目中，其实指的就是 src/main/resources 或者 src/main/java，但是java目录是存放java代码的，所以相关的配置文件及静态资源文档，就放在 src/main/resources下。



### 三层架构

![image-20240616232535554](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240616232535554.png)

- Controller：控制层。接收前端发送的请求，对请求进行处理，并响应数据。调用Service层来进行逻辑处理（Service层处理完后，把处理结果返回给Controller层）
- Service：业务逻辑层。Serivce层调用Dao层（逻辑处理过程中需要用到的一些数据要从Dao层获取）
- Dao：数据访问层(Data Access Object)，也称为持久层。负责数据访问操作，包括数据的增、删、改、查。操作文件中的数据（Dao拿到的数据会返回给Service层）

![](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240617071534173.png)



### IOC & DI

#### Terms

- **控制反转：** Inversion Of Control，简称IOC。对象的创建控制权由程序自身转移到外部（容器），这种思想称为控制反转。

	> 对象的创建权由程序员主动创建转移到容器(由容器创建、管理对象)。这个容器称为：IOC容器或Spring容器

- **依赖注入：** Dependency Injection，简称DI。容器为应用程序提供运行时，所依赖的资源，称之为依赖注入。

	> 程序运行时需要某个资源，此时容器就为其提供这个资源。
	>
	> 例：EmpController程序运行时需要EmpService对象，Spring容器就为其提供并注入EmpService对象

- **bean对象**

	> IOC容器中创建、管理的对象

![image-20240617072455426](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240617072455426.png)



#### 注解

要把某个对象交给IOC容器管理，需要在对应的类上加上如下注解之一：

| 注解        | 说明                                                         | 位置                                                    |
| :---------- | ------------------------------------------------------------ | ------------------------------------------------------- |
| @Controller | @Component的衍生注解                                         | 标注在控制器类上                                        |
| @Service    | @Component的衍生注解                                         | 标注在业务类上                                          |
| @Repository | @Component的衍生注解                                         | 标注在数据访问类上（由于与mybatis整合，用的少）         |
| @Component  | 声明bean的基础注解                                           | 不属于以上三类时，用此注解                              |
| @Autowired  | - 按照**类型**进行自动装配<br />- spring框架提供的注解<br /> | 在字段上使用 `@Autowired` 注解，Spring 会自动注入依赖。 |
| @Resource   | - 按照bean的名称进行注入<br />  通过name属性指定要注入的bean的名称<br />- JDK提供的注解 | 字段 (Field) 上                                         |
| @Primary    | 存在多个相同类型的Bean注入时，确定默认实现                   | 在对应 @Component上下                                   |
| @Qualifier  | 指定当前要注入的bean对象。 在@Qualifier的value属性中，指定注入的bean的名称。 | 不能单独使用，必须配合@Autowired使用                    |

> 字段指类中变量，用于存储类的属性数据











# HTTP

浏览器和服务器是按照HTTP协议进行数据通信的，规定了数据传输的格式。

HTTP协议默认端口号为80，如果将Tomcat端口号改为80，则将来访问Tomcat时，将不用输入端口号。

- 请求协议：浏览器将数据以请求格式发送到服务器

	- 包括：

		- **请求行（POST  /brand  HTTP/1.1）**

		- **请求头 (以空行结束：`\r\n` 是 HTTP 协议中用来表示行结束的字符序列（回车+换行）。)**

			> **`\n` (Line Feed, LF)**:
			>
			> - ASCII 代码为 10（十进制），表示换行。
			> - 用于 Unix 系统（如 Linux 和 macOS）中的行结束符。
			>
			> **`\r\n` (Carriage Return + Line Feed, CR+LF)**:
			>
			> - 由两个字符组成：
			> 	- `\r` (Carriage Return, CR)：ASCII 代码为 13（十进制），表示回车。
			> 	- `\n` (Line Feed, LF)：ASCII 代码为 10（十进制），表示换行。
			> - 用于 Windows 系统中的行结束符。

		- **请求体（payload）**

- 响应协议：服务器将数据以响应格式返回给浏览器

	- 包括：**响应行(HTTP/1.1  200  OK)** 、**响应头(以空行结束)** 、**响应体（response）** 



字符序列（CharSequence）是一个**接口**，可以是字符串（String）或其他实现了 CharSequence 接口的类（如 StringBuilder、StringBuffer 等）

- `String` 是不可变类，一旦创建就不能被修改。每次对字符串进行操作（如连接、替换等），都会创建一个新的字符串对象。
- `StringBuilder` 是可变类，可以动态地修改其内部的字符序列。这样可以避免创建大量临时对象，提高了字符串操作的效率。



**UTF-8**

1-4个字节

3 字节的编码格式是：1110xxxx 10xxxxxx 10xxxxxx，其中 "x" 表示该字节的有效数据位。

> - 第一个字节的高位位数（1 的个数）表示了该字符使用多少个字节来编码。例如，以 110xxxxx、1110xxxx 和 11110xxx 开头的字节分别表示 2 字节、3 字节和 4 字节编码的字符。
>
> - 后续字节的前两位固定为 10，用于表示这是一个后续字节。





# Web服务器

==Web服务器==是一个==应用程序(软件)==，对HTTP协议的操作进行封装，使得程序员不必直接对协议进行操作(不用程序员自己写代码去解析http协议规则)，让Web开发更加便捷。主要功能是"提供网上信息浏览服务"。



![image-20240609184358147](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240609184358147.png)



> Java SE：标准版
> Java ME：小型版
> Java EE：企业版



> Nginx：严格来说，它不是web服务器而是一个反向代理服务器
>
> 不使用代理：服务器<-->浏览器直接交互，直接知道对方的IP地址。
>
> 什么是（正向）代理？
>
> - 正向：国内访问google，我（客户端）知道目的地，但服务器不知道请求的发起
>
> - 反向：你以为你访问的是google，实际只是google的一个代理。
>
> 	Why？主要是集群、负载均衡，将请求（动态）均匀的分配到不同的Web服务器   PS：通常配合Keepalived使用，避免nginx单点崩溃



## Tomcat

将项目放置到 webapps 目录下，即部署完成

基于Springboot开发的web应用程序，内置了tomcat服务器，当启动类运行时，会自动启动内嵌的tomcat服务器。



# BS架构

![image-20240609200737034](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240609200737034.png)

![image-20240609200905693](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240609200905693.png)





# Mybatis

https://mybatis.org/mybatis-3/zh_CN/index.html

MyBatis是一款优秀的 **持久层** **框架**，用于简化JDBC的开发。

以前我们是在**图形化客户端工具**中（Datagrip）编写SQL查询代码，发送给数据库执行，数据库执行后返回操作结果,图形化工具会把数据库执行的查询结果，使用表格的形式展现出来

现在使用**Mybatis**操作数据库，就是在Mybatis中编写SQL查询代码，发送给数据库执行，数据库执行后返回结果





# route

es6 react => nextjs

![image-20240618180054986](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240618180054986.png)

react nextjs react-query zustand/redux
