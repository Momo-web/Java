# SSM

![image-20230223214239503](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232142553.png)



![image-20230223214511598](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232145640.png)



![image-20230223214709478](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232147544.png)



![image-20230223214751176](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232147251.png)



![image-20230223214856760](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232148788.png)

## 1.Spring

### 1.1课程介绍

![image-20230223215045899](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232150939.png)



![image-20230223215325814](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232153868.png)



![image-20230223215445484](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232154539.png)



![image-20230223215552635](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232155696.png)



### 1.2 初识Spring

![image-20230223215648206](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232156249.png)



![image-20230223220104534](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232201592.png)



![image-20230223220514073](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232205141.png)



![image-20230223220818272](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232208335.png)



![image-20230223221036396](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232210439.png)



### 1.3 Spring系统架构 

![image-20230223221141434](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232211494.png)



![image-20230223221246461](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232212543.png)



![image-20230223221858154](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232218220.png)



![image-20230223222019965](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232220046.png)



### 1.4 核心概念

![image-20230223222126936](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232221977.png)



![image-20230223222646465](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232226534.png)



![image-20230223224357370](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232243532.png)



![image-20230223224508045](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232245115.png)

### 1.5 Ioc入门

![image-20230223224745783](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232247836.png)

![image-20230223224944992](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232249044.png)



![image-20230224140338609](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241403677.png)



![image-20230224140356458](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241403526.png)



![image-20230224140431585](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241404667.png)



![image-20230224140515181](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241405254.png)

![image-20230224140602347](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241406384.png)





```xml
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>5.2.10.RELEASE</version>
    </dependency>
```



![image-20230224134441464](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241344537.png)



![image-20230224134554870](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241345929.png)



![image-20230224134725072](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241347095.png)







### 1.6 DI入门

![image-20230224140849620](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241408672.png)

![image-20230224141739544](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241417607.png)

![image-20230224141749488](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241417554.png)

![image-20230224141911077](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241419156.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <!--1.导入spring的坐标spring-context，对应版本是5.2.10.RELEASE-->

    <!--2.配置bean-->
<!--    bean标签配置
    id属性表示给bean起名字
    class属性表示给bean定义类型-->
    <bean id="bookDao" class="com.itheima.dao.impl.BookDaoImpl"/>

    <bean id="bookService" class="com.itheima.service.impl.BookServiceImpl">
        <!--7.配置service与dao的关系-->
        <!--property标签表示配置当前bean的属性
        name属性表示配置哪一个具体的属性
        ref属性表示参照哪一个bean-->
        <property name="bookDao" ref="bookDao"/>
    </bean>
    
</beans>
```



### 1.7 bean基础配置

![image-20230224142150282](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241421346.png)



![image-20230224142246072](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241422141.png)



![image-20230224143042844](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241430920.png)



![image-20230224144357148](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241443196.png)



```java
        //3.获取ioc容器
        ApplicationContext act = new ClassPathXmlApplicationContext("applicationContext.xml");
        
        BookService bookService = (BookService) act.getBean("bookService");
        BookService bookService2 = (BookService) act.getBean("bookService");
        System.out.println(bookService);
        System.out.println(bookService2);
//        com.itheima.service.impl.BookServiceImpl@25bbe1b6
//        com.itheima.service.impl.BookServiceImpl@25bbe1b6

        //地址一样，容器创建bean默认是单例，想要非单例需要通过配置完成，如下
        //scope="prototype"

//        com.itheima.service.impl.BookServiceImpl@59494225
//        com.itheima.service.impl.BookServiceImpl@6e1567f1
```



![image-20230224144701538](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241447586.png)



### 1.8 bean实例化

![image-20230224144901179](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241449241.png)



![image-20230224150603425](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241506499.png)





![image-20230224150757436](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241507535.png)



![image-20230224150727758](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241507817.png)





![image-20230224153640555](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241536620.png)

![image-20230224153751187](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241537234.png)





![image-20230224155220189](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241552274.png)





![image-20230224155948489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241559550.png)



![image-20230224160056140](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302241600186.png)



### 1.9 bean生命周期

![image-20230224202627312](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242026374.png)

![image-20230224205925600](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242059673.png)



![image-20230224205951489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242059565.png)

![image-20230224210238815](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242102861.png)

![image-20230224210314186](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242103249.png)



![image-20230224210347850](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242103912.png)



### 1.10 依赖注入方式

#### A. setter注入

![image-20230224220144866](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242201054.png)



![image-20230224210832132](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242108200.png)



![image-20230224210857954](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242108026.png)

![image-20230224213704158](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242137192.png)

![image-20230224213347192](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242133268.png)



![image-20230224213530989](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242135058.png)



![image-20230224213520020](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242135115.png)

 

#### B. 构造器注入

![image-20230224221123181](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242211256.png)



![image-20230224221136765](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242211842.png)

![image-20230224221207939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242212015.png)

![image-20230224221619929](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242216009.png)



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

<!--标准书写
    <bean id="bookDao" class="com.momo.dao.impl.BookDaoImpl">
        <constructor-arg name="databaseName" value="mysql"/>
        <constructor-arg name="connectionNum" value="666"/>
    </bean>

    <bean id="userDao" class="com.momo.dao.impl.UserDaoImpl"/>

    <bean id="bookService" class="com.momo.service.impl.BookServiceImpl">
        <constructor-arg name="bookDao" ref="bookDao"/>
        <constructor-arg name="userDao" ref="userDao"/>
    </bean>-->

<!--解决形参名称的问题，与形参不耦合
    <bean id="bookDao" class="com.momo.dao.impl.BookDaoImpl">
        <constructor-arg type="java.lang.String" value="mysql"/>
        <constructor-arg type="int" value="666"/>
    </bean>

    <bean id="userDao" class="com.momo.dao.impl.UserDaoImpl"/>

    <bean id="bookService" class="com.momo.service.impl.BookServiceImpl">
        <constructor-arg name="bookDao" ref="bookDao"/>
        <constructor-arg name="userDao" ref="userDao"/>
    </bean>-->

    <!--解决参数类型重复问题，使用参数位置解决参数匹配-->
    <bean id="bookDao" class="com.momo.dao.impl.BookDaoImpl">
        <constructor-arg index="0" value="mysql"/>
        <constructor-arg index="1" value="666"/>
    </bean>

    <bean id="userDao" class="com.momo.dao.impl.UserDaoImpl"/>

    <bean id="bookService" class="com.momo.service.impl.BookServiceImpl">
        <constructor-arg name="bookDao" ref="bookDao"/>
        <constructor-arg name="userDao" ref="userDao"/>
    </bean>
</beans>
```





### 1.11 依赖自动装配

![image-20230224222010944](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242220998.png)

![image-20230224223955615](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242239670.png)

![image-20230224224154713](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242241776.png)

![image-20230224224233286](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242242403.png)





### 1.12 集合注入

![image-20230224224414040](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242244089.png)





![image-20230224230138716](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242301772.png)

![image-20230224230151163](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242301216.png)

![image-20230224230205619](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242302667.png)

![image-20230224230215913](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242302967.png)

![image-20230224230228113](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242302166.png)

```java
package com.momo.dao.impl;

import com.momo.dao.BookDao;

import java.util.*;

/**
 * @author momo~
 * @version 1.0
 */
public class BookDaoImpl implements BookDao {

    private int[] array;

    private List<String> list;

    private Set<String> set;

    private Map<String,String> map;

    private Properties properties;

    public void setArray(int[] array) {
        this.array = array;
    }

    public void setList(List<String> list) {
        this.list = list;
    }

    public void setSet(Set<String> set) {
        this.set = set;
    }

    public void setMap(Map<String, String> map) {
        this.map = map;
    }

    public void setProperties(Properties properties) {
        this.properties = properties;
    }

    @Override
    public void save() {
        System.out.println("遍历数组：" + Arrays.toString(array));

        System.out.println("遍历List" + list);

        System.out.println("遍历Set" + set);

        System.out.println("遍历Map" + map);

        System.out.println("遍历Properties" + properties);
    }
}

```





```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="bookDao" class="com.momo.dao.impl.BookDaoImpl">
        <property name="array">
            <array>
                <value>100</value>
                <value>200</value>
                <value>300</value>
            </array>
        </property>
        <property name="list">
            <list>
                <value>itcast</value>
                <value>itheima</value>
                <value>boxuegu</value>
            </list>
        </property>
        <property name="set">
            <set>
                <value>itcast</value>
                <value>itheima</value>
                <value>boxuegu</value>
            </set>
        </property>
        <property name="map">
            <map>
                <entry key="country" value="china"/>
                <entry key="province" value="henan"/>
                <entry key="city" value="kaifeng"/>
            </map>
        </property>
        <property name="properties">
            <props>
                <prop key="country">china</prop>
                <prop key="province">henan</prop>
                <prop key="city">kaifeng</prop>
            </props>
        </property>
    </bean>
</beans>
```

![image-20230224230353656](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302242303720.png)





### 1.13 数据源对象管理

![image-20230225101523624](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251015691.png)

![image-20230225104316766](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251043857.png)



```xml
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>

    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>5.2.10.RELEASE</version>
    </dependency>

    <dependency>
      <groupId>com.alibaba</groupId>
      <artifactId>druid</artifactId>
      <version>1.2.16</version>
    </dependency>

    <!-- https://mvnrepository.com/artifact/c3p0/c3p0 -->
    <dependency>
      <groupId>c3p0</groupId>
      <artifactId>c3p0</artifactId>
      <version>0.9.1.2</version>
    </dependency>

    <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>8.0.32</version>
    </dependency>

  </dependencies>
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">


    <!--管理DruidDataSource对象-->
    <bean  class="com.alibaba.druid.pool.DruidDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/spring_db"/>
        <property name="username" value="root"/>
        <property name="password" value="root"/>
    </bean>

    <bean id="dataSource" class="com.mchange.v2.c3p0.ComboPooledDataSource">
        <property name="driverClass" value="com.mysql.jdbc.Driver"/>
        <property name="jdbcUrl" value="jdbc:mysql://localhost:3306/spring_db"/>
        <property name="user" value="root"/>
        <property name="password" value="root"/>
        <property name="maxPoolSize" value="1000"/>
    </bean>
</beans>
```



### 1.14 Spring加载properties文件

![image-20230225110415036](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251104130.png)



![image-20230225111039808](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251110902.png)

![image-20230225111224027](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251112071.png)



```properties
jdbc.driver=com.mysql.cj.jdbc.Driver
jdbc.url=jdbc:mysql://127.0.0.1:3306/spring_db
jdbc.username=root
jdbc.password=root
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="
            http://www.springframework.org/schema/beans
            http://www.springframework.org/schema/beans/spring-beans.xsd
            http://www.springframework.org/schema/context
            http://www.springframework.org/schema/context/spring-context.xsd
            ">

    <!--开启context命名空间-->
    <!--加载properties配置文件-->
    <context:property-placeholder location="classpath*:*.properties" system-properties-mode="NEVER"/>

    <!--使用属性占位符${}读取properties文件中的属性-->
    <bean  class="com.alibaba.druid.pool.DruidDataSource">
        <property name="driverClassName" value="${jdbc.driver}"/>
        <property name="url" value="${jdbc.url}"/>
        <property name="username" value="${jdbc.username}"/>
        <property name="password" value="${jdbc.password}"/>
    </bean>

    <bean id="bookDao" class="com.momo.dao.impl.BookDaoImpl">
        <property name="name" value="${jdbc.driver}"/>
    </bean>

</beans>
```



### 1.15 容器

![image-20230225134053113](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251340193.png)



![image-20230225135456235](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251354306.png)



![image-20230225135518842](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251355900.png)



```java
package com.momo;

import com.momo.dao.BookDao;
import org.springframework.context.support.ClassPathXmlApplicationContext;
import org.springframework.context.support.FileSystemXmlApplicationContext;

/**
 * @author momo~
 * @version 1.0
 */
public class App {
    public static void main(String[] args) {

        //1.加载类路径下的配置文件
        ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("applicationContext.xml");

        //2.从文件系统下加载配置文件
        //FileSystemXmlApplicationContext ctx = new FileSystemXmlApplicationContext("D:\\Users\\mo\\Desktop\\Java\\SSM\\code\\spring_10_container\\src\\main\\resources\\applicationContext.xml");

        //1.获取bean第一种方式
        //BookDao bookDao = (BookDao) ctx.getBean("bookDao");
        //2.获取bean第二种方式
        //BookDao bookDao = ctx.getBean("bookDao",BookDao.class);
        //3.获取bean第三种方式
        BookDao bookDao = ctx.getBean(BookDao.class);
        
        bookDao.save();

        //2.
    }
}

```



![image-20230225140713660](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251407759.png)

![image-20230225140756131](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251407192.png)



![image-20230225140854738](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251408796.png)



### 1.16 核心容器总结

![image-20230225141049461](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251410536.png)



![image-20230225141100411](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251411499.png)

![image-20230225141323340](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251413446.png)



### 1.17 注解开发

![image-20230225141608519](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251416575.png)



![image-20230225143456459](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251434541.png)

![image-20230225143543983](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251435054.png)

### 1.18  纯注解开发模式

![image-20230225145659029](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251456120.png)



![image-20230225145859134](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251458230.png)



![image-20230225145944922](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251459992.png)



![image-20230225150106587](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251501660.png)



```java
//@Component("bookDao")
@Repository("bookDao")
public class BookDaoImpl implements BookDao {
    @Override
    public void save() {
        System.out.println("bookDao save...");
    }
}
```



```java
//@Component
@Service
public class BookServiceImpl implements BookService {
    private BookDao bookDao;

    public void setBookDao(BookDao bookDao) {
        this.bookDao = bookDao;
    }

    @Override
    public void save() {
        System.out.println("bookService save...");
        bookDao.save();
    }
}
```



```java
@Configuration
@ComponentScan("com.momo")
public class SpringConfig {
}
```



```java
public class AppForAnnotation {
    public static void main(String[] args) {
        ApplicationContext ctx = new AnnotationConfigApplicationContext(SpringConfig.class);

        BookDao bookDao = (BookDao) ctx.getBean("bookDao");
        System.out.println(bookDao);

        BookService bookService = ctx.getBean(BookService.class);
        System.out.println(bookService);
    }
}
```



### 1.19 bean管理

![image-20230225150507977](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251505031.png)

![image-20230225155701161](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251557220.png)



![image-20230225155727860](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251557939.png)



![image-20230225155748997](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251557052.png)

```java
package com.momo.dao.impl;

import com.momo.dao.BookDao;
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Repository;

import javax.annotation.PostConstruct;
import javax.annotation.PreDestroy;

/**
 * @author momo~
 * @version 1.0
 */
@Repository
//@Scope("prototype")
@Scope("singleton")
public class BookDaoImpl implements BookDao {
    @Override
    public void save() {
        System.out.println("bookDao save...");
    }

    @PostConstruct
    public void init() {
        System.out.println("init...");
    }

    @PreDestroy
    public void destroy() {
        System.out.println("destroy...");
    }
}

```



![image-20230225155828877](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251558942.png)





### 1.20 注解开发依赖注入

![image-20230225160000874](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251600924.png)

![image-20230225163311791](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251633886.png)



![image-20230225163350263](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251633331.png)



![image-20230225163601184](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251636246.png)



![image-20230225164224509](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251642589.png)

![image-20230225164417225](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251644291.png)



### 1.21 第三方bean管理

![image-20230225164610999](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302251646060.png)



![image-20230225212020156](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252120231.png)

![image-20230225212058363](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252120446.png)



![image-20230225212120292](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252121376.png)





![image-20230225212919333](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252129428.png)



![image-20230225212933852](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252129924.png)

![image-20230225212959476](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252129545.png)



### 1.22 注解开发总结

![image-20230225213058114](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252130175.png)

![image-20230225213541682](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252135779.png)



### 1.23 Spring整合MyBatis



![image-20230226113836292](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261138399.png)



![image-20230225214649789](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252146908.png)



![image-20230225214904103](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302252149215.png)





![image-20230226113138867](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261131986.png)



![image-20230226113226761](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261132852.png)



![image-20230226113247819](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261132891.png)



### 1.24 Spring整合JUnit

![image-20230226115736889](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261157976.png)



![image-20230226115748964](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302261157026.png)



### 1.25 AOP

#### **关于动态代理**

![image-20230226223607854](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262236021.png)



![image-20230226224608342](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262246509.png)



![image-20230226224509916](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262245027.png)





![image-20230226230919489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262309653.png)



![image-20230226231911483](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262319644.png)



![image-20230226233358088](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302262333182.png)



![image-20230227095138232](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302270951359.png)



#### 1.AOP简介

![image-20230301102618252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011026327.png)



![image-20230301103122811](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011031930.png)



![image-20230301103502542](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011035627.png)

![image-20230301103516640](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011035710.png)



#### 2. AOP入门案例

![image-20230301103704514](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011037574.png)

![image-20230301110039015](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011100085.png)

##### **1.导入坐标**

![image-20230301110130635](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011101741.png)



##### 2.制作连接点

![image-20230301110225006](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011102145.png)



##### 3.通知与通知类、切入点、切面

![image-20230301110442381](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011104504.png)



##### 4.spring注解类

![image-20230301110624316](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011106391.png)



##### 5.结果

![image-20230301110710509](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011107597.png)



![image-20230301110016586](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011100667.png)



![image-20230301110757721](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011107801.png)



![image-20230301110812084](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011108143.png)

![image-20230301110828756](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011108819.png)

![image-20230301110924117](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011109199.png)

![image-20230301110947910](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011109987.png)

![image-20230301110959965](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011110037.png)

#### 3.AOP工作流程

![image-20230301132622058](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011326133.png)



![image-20230301132559913](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011325975.png)

![image-20230301132657939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011326000.png)



#### 4.AOP切入点表达式

![image-20230301132824117](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011328177.png)



![image-20230301133020948](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011330042.png)



![image-20230301133214943](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011332029.png)



![image-20230301133621454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011336548.png)

![image-20230301135227184](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011352275.png)

![image-20230301135332611](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011353717.png)



#### 5.AOP通知类型

![image-20230301142529935](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011425007.png)



![image-20230301142552722](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011425793.png)

![image-20230301142609197](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011426282.png)

![image-20230301142619191](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011426267.png)



![image-20230301142836362](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011428462.png)



![image-20230301142847182](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011428256.png)

![image-20230301142859951](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011429028.png)

```java
package com.momo.aop;

import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.annotation.*;
import org.springframework.stereotype.Component;

/**
 * @author momo~
 * @version 1.0
 */
@Component
@Aspect
public class MyAdvice {
    @Pointcut("execution(void com.momo.dao.BookDao.update())")
    private void pt(){}

    @Pointcut("execution(int com.momo.dao.BookDao.select())")
    private void pt2(){}

    //@Before("pt()")
    public void before(){
        System.out.println("before advice...");
    }

    //@After("pt()")
    public void after(){
        System.out.println("after advice...");
    }

    //@Around("pt()")
    public Object around(ProceedingJoinPoint pjp) throws Throwable {
        System.out.println("around before advice...");
        //表示对原始操作的调用
        Object proceed = pjp.proceed();
        System.out.println("around after advice...");
        return proceed;
    }

    @Around("pt2()")
    public Object aroundSelect(ProceedingJoinPoint pjp) throws Throwable {
        System.out.println("around before advice...");
        //表示对原始操作的调用
        Integer proceed = (Integer) pjp.proceed();
        System.out.println("around after advice...");
        return proceed + 566;
    }

    //@AfterReturning("pt2()")
    public void afterReturning(){
        System.out.println("afterReturning advice...");
    }

    //@AfterThrowing("pt2()")
    public void afterThrowing(){
        System.out.println("afterThrowing advice...");
    }
}

```



#### 6.案例：测试业务层接口万次执行效率

![image-20230301143426021](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303011434100.png)

![image-20230302101739072](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021017173.png)

![image-20230302101754005](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021017097.png)



![image-20230302101851234](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021018285.png)



```java
package com.momo.aop;

import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.Signature;
import org.aspectj.lang.annotation.Around;
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Pointcut;
import org.springframework.stereotype.Component;

/**
 * @author momo~
 * @version 1.0
 */
@Component
@Aspect
public class ProjectAdvice {

    //匹配业务层所有方法
    @Pointcut("execution(* com.momo.service.*Service.*(..))")
    private void servicePt(){}

    @Around("ProjectAdvice.servicePt()")
    public void runSpeed(ProceedingJoinPoint proceedingJoinPoint) throws Throwable {

        Signature signature = proceedingJoinPoint.getSignature();
        String declaringTypeName = signature.getDeclaringTypeName();
        String name = signature.getName();


        long start = System.currentTimeMillis();
        for (int i = 0; i < 10000; i++) {
            proceedingJoinPoint.proceed();
        }
        long end = System.currentTimeMillis();
        System.out.println("万次执行：" + declaringTypeName + name + "--->" + (end-start) + "ms");
    }
}

```

![image-20230302101955917](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021019961.png)



#### 7.AOP通知获取数据

![image-20230302102119283](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021021346.png)

![image-20230302102250953](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021022016.png)

![image-20230302141357002](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021413120.png)



![image-20230302141426139](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021414233.png)

#### 8.案例：百度网盘密码数据兼容处理

![image-20230302141732990](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021417090.png)

![image-20230302144403035](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021444137.png)

```java
package com.momo.aop;

import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.annotation.Around;
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Pointcut;
import org.springframework.stereotype.Component;

/**
 * @author momo~
 * @version 1.0
 */
@Component
@Aspect
public class DataAdvice {
    @Pointcut("execution(boolean com.momo.service.*.*(..))")
    private void servicePt(){
    }

    @Around("DataAdvice.servicePt()")
    public Object trimStr(ProceedingJoinPoint pjp) throws Throwable {
        Object[] args = pjp.getArgs();
        for (int i = 0; i < args.length; i++) {
            //判断参数是不是字符串
            if (args[i].getClass().equals(String.class)){
                args[i] = args[i].toString().trim();
            }
        }
        Object ret = pjp.proceed(args);
        return ret;

    }
}
```



![image-20230302144642783](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021446853.png)

![image-20230302144843251](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021448334.png)



![image-20230302145159952](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021452023.png)

### 1.26 Spring事务

![image-20230302145409185](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021454250.png)



![image-20230302145612106](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303021456181.png)

![image-20230302221645445](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022216551.png)



![image-20230302222625353](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022226445.png)



![image-20230302222714179](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022227262.png)



![image-20230302222737777](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022227858.png)

### 1.27 Spring事务角色

![image-20230302222851632](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022228696.png)

![image-20230302223203746](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022232847.png)



![image-20230302223406221](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022234279.png)



### 1.28 Spring事务属性

![image-20230302223505033](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022235112.png)



![image-20230302230804844](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022308933.png)





![image-20230302231215447](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022312549.png)



![image-20230302231325672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022313759.png)



![image-20230302231349745](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022313828.png)



![image-20230302231730881](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303022317945.png)





## 2.SpringMVC

### 1.1 SpringMVC简介

![image-20230303100333146](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031003227.png)



![image-20230303100525439](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031005504.png)



![image-20230303100724786](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031007858.png)



![image-20230303100842393](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031008493.png)



![image-20230303100921417](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031009473.png)



### 1.2 SpringMVC入门案例

![image-20230303101029360](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031010441.png)

![image-20230303101356143](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031013213.png)

![image-20230303101443316](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031014372.png)

![image-20230303101557692](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031015787.png)



![image-20230303103826621](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031038691.png)

![image-20230303103841875](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031038937.png)

![image-20230303103855651](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031038713.png)

![image-20230303104059707](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031040768.png)

![image-20230303104134358](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031041445.png)

![image-20230303104149938](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031041014.png)

![image-20230303104210644](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031042712.png)

![image-20230303104230775](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031042831.png)



###  1.3 入门案例工作流程

![image-20230303122527535](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031225701.png)



### 1.4 bean加载控制

![image-20230303122908683](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031229752.png)

![image-20230303122955495](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031229558.png)

![image-20230303125347173](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031253267.png)



![image-20230303125517336](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031255411.png)



![image-20230303130038130](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031300215.png)

### 1.5 Postman

![image-20230303130229289](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031302352.png)

![image-20230303131436918](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031314994.png)

### 2.1 请求映射路径

![image-20230303131616021](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031316074.png)

![image-20230303133327162](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031333226.png)



![image-20230303133347782](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031333842.png)

![image-20230303134227039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031342175.png)



### 2.2 传参

![image-20230303140822522](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031408616.png)



![image-20230303140848846](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031408923.png)



![image-20230303142126121](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031421200.png)

![image-20230303142138341](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031421427.png)



### 2.3 五种类型参数传递

![image-20230303142302464](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031423539.png)



![image-20230303144729589](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031447670.png)



![image-20230303144749821](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031447893.png)



![image-20230303144810864](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031448942.png)



![image-20230303144820917](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031448992.png)



![image-20230303144836748](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031448825.png)



### 2.4 json数据传递参数

![image-20230303150816124](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031508176.png)



![image-20230303150828481](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031508542.png)



![image-20230303150839659](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031508716.png)



![image-20230303150853907](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031508979.png)



![image-20230303150907573](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031509644.png)

![image-20230303150935145](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031509216.png)

![image-20230303150948113](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031509190.png)



![image-20230303151006089](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031510169.png)





![image-20230303151128985](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031511046.png)



![image-20230303151152305](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031511362.png)

```java
package com.momo.controller;

import com.momo.domain.User;
import org.springframework.format.annotation.DateTimeFormat;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.ResponseBody;

import java.util.Arrays;
import java.util.Date;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
@Controller
public class UserController {
    @RequestMapping("/commonParam")
    @ResponseBody
    public String commonParam(String name,int age){
        System.out.println("普通参数传递 name ==>" + name);
        System.out.println("普通参数传递 age ==>" + age);
        return "{'module':'common param'}";
    }

    //普通参数：请求参数名与形参名不同时，使用@RequestParam注解关联请求参数名称与形参名称之间的关系
    @RequestMapping("/commonParamDifferentName")
    @ResponseBody
    public String commonParamDifferentName(@RequestParam("name") String userName , int age){
        System.out.println("普通参数传递 userName ==> "+userName);
        System.out.println("普通参数传递 age ==> "+age);
        return "{'module':'common param different name'}";
    }

    //POJO参数：请求参数与形参对象中的属性对应即可完成参数传递
    @RequestMapping("/pojoParam")
    @ResponseBody
    public String pojoParam(User user){
        System.out.println("pojo参数传递 user ==> "+user);
        return "{'module':'pojo param'}";
    }

    //嵌套POJO参数：嵌套属性按照层次结构设定名称即可完成参数传递
    @RequestMapping("/pojoContainPojoParam")
    @ResponseBody
    public String pojoContainPojoParam(User user){
        System.out.println("pojo嵌套pojo参数传递 user ==> "+user);
        return "{'module':'pojo contain pojo param'}";
    }

    //数组参数：同名请求参数可以直接映射到对应名称的形参数组对象中
    @RequestMapping("/arrayParam")
    @ResponseBody
    public String arrayParam(String[] likes){
        System.out.println("数组参数传递 likes ==> "+ Arrays.toString(likes));
        return "{'module':'array param'}";
    }

    //集合参数：同名请求参数可以使用@RequestParam注解映射到对应名称的集合对象中作为数据
    @RequestMapping("/listParam")
    @ResponseBody
    public String listParam(@RequestParam List<String> likes){
        System.out.println("集合参数传递 likes ==> "+ likes);
        return "{'module':'list param'}";
    }


    //集合参数：json格式
    //1.开启json数据格式的自动转换，在配置类中开启@EnableWebMvc
    //2.使用@RequestBody注解将外部传递的json数组数据映射到形参的集合对象中作为数据
    @RequestMapping("/listParamForJson")
    @ResponseBody
    public String listParamForJson(@RequestBody List<String> likes){
        System.out.println("list common(json)参数传递 list ==> "+likes);
        return "{'module':'list common for json param'}";
    }

    //POJO参数：json格式
    //1.开启json数据格式的自动转换，在配置类中开启@EnableWebMvc
    //2.使用@RequestBody注解将外部传递的json数据映射到形参的实体类对象中，要求属性名称一一对应
    @RequestMapping("/pojoParamForJson")
    @ResponseBody
    public String pojoParamForJson(@RequestBody User user){
        System.out.println("pojo(json)参数传递 user ==> "+user);
        return "{'module':'pojo for json param'}";
    }

    //集合参数：json格式
    //1.开启json数据格式的自动转换，在配置类中开启@EnableWebMvc
    //2.使用@RequestBody注解将外部传递的json数组数据映射到形参的保存实体类对象的集合对象中，要求属性名称一一对应
    @RequestMapping("/listPojoParamForJson")
    @ResponseBody
    public String listPojoParamForJson(@RequestBody List<User> list){
        System.out.println("list pojo(json)参数传递 list ==> "+list);
        return "{'module':'list pojo for json param'}";
    }

    //日期参数
    //使用@DateTimeFormat注解设置日期类型数据格式，默认格式yyyy/MM/dd
    @RequestMapping("/dataParam")
    @ResponseBody
    public String dataParam(Date date,
                            @DateTimeFormat(pattern="yyyy-MM-dd") Date date1,
                            @DateTimeFormat(pattern="yyyy/MM/dd HH:mm:ss") Date date2){
        System.out.println("参数传递 date ==> "+date);
        System.out.println("参数传递 date1(yyyy-MM-dd) ==> "+date1);
        System.out.println("参数传递 date2(yyyy/MM/dd HH:mm:ss) ==> "+date2);
        return "{'module':'data param'}";
    }
}

```



### 2.5 日期型参数传递

![image-20230303194909646](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031949692.png)

![image-20230303195659016](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031956102.png)



![image-20230303195725227](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031957301.png)



![image-20230303195936524](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303031959597.png)

```java
    //日期参数
    //使用@DateTimeFormat注解设置日期类型数据格式，默认格式yyyy/MM/dd
    @RequestMapping("/dataParam")
    @ResponseBody
    public String dataParam(Date date,
                            @DateTimeFormat(pattern="yyyy-MM-dd") Date date1,
                            @DateTimeFormat(pattern="yyyy/MM/dd HH:mm:ss") Date date2){
        System.out.println("参数传递 date ==> "+date);
        System.out.println("参数传递 date1(yyyy-MM-dd) ==> "+date1);
        System.out.println("参数传递 date2(yyyy/MM/dd HH:mm:ss) ==> "+date2);
        return "{'module':'data param'}";
    }
}

```



### 2.6 响应

![image-20230303200209784](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032002828.png)

![image-20230303202734837](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032027894.png)

![image-20230303202745750](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032027813.png)

![image-20230303202818201](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032028264.png)

![image-20230303202831761](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032028834.png)



![image-20230303202842739](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032028809.png)

![image-20230303202925977](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032029050.png)

![image-20230303203009207](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032030289.png)

![image-20230303203241522](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032032583.png)

```java
package com.momo.controller;

import com.momo.domain.User;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

import java.util.ArrayList;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
@Controller
public class UserConteoller {

    //响应页面/跳转页面
    //返回值为String类型，设置返回值为页面名称，即可实现页面跳转
    @RequestMapping("/toJumpPage")
    public String toJumpPage(){
        System.out.println("跳转页面");
        return "page.jsp";
    }

    //响应文本数据
    //返回值为String类型，设置返回值为任意字符串信息，即可实现返回指定字符串信息，需要依赖@ResponseBody注解
    @RequestMapping("/toText")
    @ResponseBody
    public String toText(){
        System.out.println("返回纯文本数据");
        return "response text";
    }

    //响应POJO对象
    //返回值为实体类对象，设置返回值为实体类类型，即可实现返回对应对象的json数据，需要依赖@ResponseBody注解和@EnableWebMvc注解
    @RequestMapping("/toJsonPOJO")
    @ResponseBody
    public User toJsonPOJO(){
        System.out.println("返回json对象数据");
        User user = new User();
        user.setName("itcast");
        user.setAge(15);
        return user;
    }

    //响应POJO集合对象
    //返回值为集合对象，设置返回值为集合类型，即可实现返回对应集合的json数组数据，需要依赖@ResponseBody注解和@EnableWebMvc注解
    @RequestMapping("/toJsonList")
    @ResponseBody
    public List<User> toJsonList(){
        System.out.println("返回json集合数据");
        User user1 = new User();
        user1.setName("传智播客");
        user1.setAge(15);

        User user2 = new User();
        user2.setName("黑马程序员");
        user2.setAge(12);

        List<User> userList = new ArrayList<User>();
        userList.add(user1);
        userList.add(user2);

        return userList;
    }
}

```



### 3.1 REST风格

![image-20230303203538737](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032035799.png)



![image-20230303203900213](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032039288.png)



![image-20230303204636173](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032046260.png)



### 3.2 RESTful入门案例

![image-20230303212856872](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032128972.png)



![image-20230303213005017](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032130087.png)

![image-20230303213029910](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032130992.png)



![image-20230303213042785](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032130865.png)

![image-20230303213206941](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032132022.png)

![image-20230303213228341](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032132397.png)

```java
package com.momo.controller;

import com.momo.domain.User;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.*;

/**
 * @author momo~
 * @version 1.0
 */
@Controller
public class UserController {
    @RequestMapping(value = "/users",method = RequestMethod.POST)
    @ResponseBody
    public String save(){
        System.out.println("user save ..." );
        return "{'module':'user save'}";
    }

    @RequestMapping(value = "/users/{id}",method = RequestMethod.DELETE)
    @ResponseBody
    public String delete(@PathVariable Integer id){
        System.out.println("user delete ..." + id);
        return "{'module':'user delete'}";
    }

    @RequestMapping(value = "/users",method = RequestMethod.PUT)
    @ResponseBody
    public String update(@RequestBody User user){
        System.out.println("user update ..." + user);
        return "{'module':'user update'}";
    }

    @RequestMapping(value = "/users/{id}",method = RequestMethod.GET)
    @ResponseBody
    public String getById(@PathVariable Integer id){
        System.out.println("user getById ..." + id);
        return "{'module':'user getById'}";
    }

    @RequestMapping(value = "/users",method = RequestMethod.GET)
    @ResponseBody
    public String getAll(){
        System.out.println("user getAll ...");
        return "{'module':'user getAll'}";
    }
}

```





### 3.3 RESTful快速开发

![image-20230303213418158](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032134242.png)

![image-20230303215629704](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032156782.png)

![image-20230303215646695](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032156774.png)



![image-20230303215757748](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032157815.png)

```java
package com.momo.controller;

import com.momo.domain.Book;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.*;

import javax.jws.soap.SOAPBinding;

/**
 * @author momo~
 * @version 1.0
 */
//@Controller
//@ResponseBody
@RestController
@RequestMapping("/books")
public class BookController {

    //@RequestMapping(method = RequestMethod.POST)
    @PostMapping
    public String save(@RequestBody Book book){
        System.out.println("book save ..." + book);
        return "{'module':'book save'}";
    }

    //@RequestMapping(value = "/{id}",method = RequestMethod.DELETE)
    @DeleteMapping("/{id}")
    public String delete(@PathVariable Integer id){
        System.out.println("book delete ..." + id);
        return "'module':'book delete'";
    }
    //@RequestMapping(method = RequestMethod.PUT)
    @PutMapping
    public String update(@RequestBody Book book){
        System.out.println("book update" + book);
        return "'module':'book update'";
    }
    //@RequestMapping(value = "/{id}",method = RequestMethod.GET)
    @GetMapping("/{id}")
    public String getById(@PathVariable Integer id){
        System.out.println("book getById ..." + id);
        return "'module':'book getById'";
    }
    //@RequestMapping(method = RequestMethod.GET)
    @GetMapping
    public String getAll(){
        System.out.println("book getAll ...");
        return "'module':'book getAll'";
    }
}

```



### 3.4 REST案例—基于RESTful页面数据交互

![image-20230303231234263](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032312387.png)



![image-20230303231249820](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032312921.png)

![image-20230303231321366](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032313449.png)



![image-20230303231339832](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303032313912.png)



### 4.1 SSM整合

![image-20230304101928544](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041019625.png)





![image-20230304102010004](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041020072.png)



![image-20230304142846140](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041428227.png)



![image-20230304142227572](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041422670.png)



![image-20230304142237921](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041422015.png)

![image-20230304142251876](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041422949.png)



![image-20230304142304910](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041423012.png)



![image-20230304142332491](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041423565.png)



![image-20230304142347466](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041423572.png)



![image-20230304142400046](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041424116.png)



![image-20230304142411549](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041424634.png)



![image-20230304142429201](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041424290.png)



![image-20230304142455191](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041424277.png)



![image-20230304142511696](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041425773.png)



![image-20230304142541748](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041425810.png)

![image-20230304142557509](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041425575.png)

![image-20230304142637005](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041426076.png)



![image-20230304142648401](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041426475.png)



![image-20230304142704027](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041427089.png)

### 4.2 表现层数据封装

![image-20230304143625407](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041436488.png)



![image-20230304143550722](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041435803.png)



![image-20230304143847303](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041438380.png)





![image-20230304150233427](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041502518.png)



![image-20230304150321136](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041503215.png)



![image-20230304150348669](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041503725.png)



### 4.3 异常处理器

![image-20230304150542259](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041505333.png)



![image-20230304150913363](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041509437.png)

![image-20230304150924161](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041509226.png)

![image-20230304151001097](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041510163.png)



![image-20230304151141671](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041511737.png)

![image-20230304151243357](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041512426.png)

![image-20230304152116842](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041521917.png)

![image-20230304152130517](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041521603.png)



![image-20230304152200489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041522556.png)

### 4.4 项目异常处理

![image-20230304152444477](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041524553.png)



![image-20230304152610847](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041526931.png)



![image-20230304152711873](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041527941.png)



![image-20230304153004466](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041530545.png)



![image-20230304162145929](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041621014.png)



![image-20230304162204857](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041622940.png)



![image-20230304162214366](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041622443.png)

![image-20230304162229656](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041622735.png)



![image-20230304162309680](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041623769.png)



![image-20230304162343705](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041623776.png)



![image-20230304162401251](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041624316.png)

### 4.5 SSM标配开发 

#### 前后台协议联调——数据展示

![image-20230304163704122](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041637220.png)



![image-20230304163747588](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041637713.png)



![image-20230304163938389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041639473.png)



#### 前后台协议联调——数添加数据

![image-20230304164636919](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041646970.png)



![image-20230304164852464](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041648547.png)



![image-20230304170606282](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303041706491.png)



#### 前后台协议联调——数添加数据

![image-20230304211946935](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042119987.png)

![image-20230304212339305](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042123524.png)



#### 前后台协议联调——数添加数据

![image-20230304214349532](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042143577.png)



![image-20230304214437689](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042144881.png)



![image-20230304214514439](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042145517.png)

![image-20230304214602250](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042146314.png)







### 5.1 拦截器

![image-20230304214643323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042146382.png)



![image-20230304215116005](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042151105.png)



![image-20230304215542111](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042155205.png)



![image-20230304215912670](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042159732.png)



![image-20230304215924743](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042159804.png)



### 5.2拦截器入门案例

![image-20230304224901929](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042249028.png)



![image-20230304224916239](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042249313.png)

![image-20230304224935972](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042249049.png)



![image-20230304230236421](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042302514.png)



![image-20230304230402050](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042304128.png)



![image-20230304230417620](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042304699.png)

### 5.3 拦截器参数

![image-20230304231405003](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042314085.png)



![image-20230304231425328](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042314407.png)

![image-20230304231442403](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042314475.png)

![image-20230304231453018](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042314083.png)

### 5.4 拦截器链配置

![image-20230304232014501](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042320693.png)



![image-20230304232309162](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042323264.png)



![image-20230304232411461](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042324537.png)

![image-20230304232552128](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303042325194.png)



## 3. maven高级 

![image-20230305101554365](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051015466.png)

### 1.分模块开发与设计

![image-20230305101806256](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051018354.png)



![image-20230305101942326](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051019416.png)



![image-20230305102042119](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051020213.png)



![image-20230305111925995](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051119098.png)



![image-20230305111945577](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051119651.png)





![image-20230305112018351](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051120424.png)



![image-20230305112317302](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051123352.png)



![image-20230305112440039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051124141.png)





![image-20230305112113213](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051121269.png)





### 2.依赖管理

![image-20230305123947357](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051239421.png)



![image-20230305124022302](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051240386.png)





![image-20230305124559121](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051245200.png)



![image-20230305124328670](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051243742.png)



![image-20230305125316278](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051253362.png)



![image-20230305125934396](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051259473.png)

![image-20230305125948246](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051259332.png)



![image-20230305130031212](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051300270.png)



### <span style="color:red">3.聚合与继承</span>

![image-20230305130437305](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051304395.png)



![image-20230305131016198](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051310279.png)



![image-20230305131029489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051310560.png)



![image-20230305131048979](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051310034.png)



![image-20230305131307883](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051313988.png)



![image-20230305131402118](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051314185.png)

![image-20230305133137374](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051331450.png)



![image-20230305133149633](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051331702.png)



![image-20230305133202375](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051332441.png)



![image-20230305133214748](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051332818.png)



![image-20230305133228104](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051332184.png)



![image-20230305133300819](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051333885.png)



### <span style="color:red">4.属性管理</span>

![image-20230305133642703](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051336792.png)



![image-20230305134609825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051346888.png)

![image-20230305134626858](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051346919.png)



![image-20230305140734456](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051407526.png)

![image-20230305140746997](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051407059.png)

![image-20230305140801133](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051408207.png)

![image-20230305140813951](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051408018.png)



![image-20230305140844331](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051408379.png)

![image-20230305140856289](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051408348.png)





![image-20230305141331800](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051413883.png)



![image-20230305141454920](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051414998.png)





### 5.多环境配置与应用

![image-20230305141550825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051415877.png)



![image-20230305141714720](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051417800.png)



![image-20230305142725240](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051427328.png)



![image-20230305142757240](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051427295.png)



![image-20230305142951034](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051429087.png)



![image-20230305144133533](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051441614.png)



![image-20230305144151989](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051441065.png)





### 6.私服

![image-20230305144300836](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051443888.png)



![image-20230305144549391](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051445467.png)



![image-20230305144638740](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051446803.png)

![image-20230305145341214](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051453293.png)

![](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051551310.png)



![image-20230305155106542](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303051551609.png)



![image-20230305201619758](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052016823.png)



**私服仓库分类**

![image-20230305205234456](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052052537.png)



![image-20230305205251323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052052388.png)



**本地仓库访问私服配置**

![image-20230305205936278](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052059368.png)

![image-20230305211732824](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052117862.png)



![image-20230305211715362](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052117412.png)



![image-20230305212438252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052124368.png)



![image-20230305220524984](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052205071.png)



![image-20230305220545834](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052205906.png)



![image-20230305220601007](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052206093.png)



![image-20230305220650063](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052206150.png)



![image-20230305220718979](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052207038.png)



## 4.SpringBoot

![image-20230305220959320](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052209385.png)



![image-20230305221016472](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052210536.png)

#### 1.SpringBoot简介

![image-20230305221034876](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052210933.png)



![image-20230305221202909](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052212972.png)



**SpringBoot工程入门案例**



![image-20230305221224389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052212476.png)



![image-20230305221335543](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052213632.png)



![image-20230305225229368](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052252571.png)



![image-20230305225441377](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052254469.png)



![image-20230305225509332](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052255402.png)





![image-20230305225551337](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052255408.png)



![image-20230305225601505](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052256625.png)



![image-20230305225709392](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052257488.png)



![image-20230305225721562](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052257635.png)

![image-20230305225853836](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052258919.png)



**SpringBoot工程官网创建方式**

![image-20230305230249050](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052302119.png)



![image-20230305230337766](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052303836.png)



**SpringBoot项目快速启动**

![image-20230305230833945](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052308030.png)



![image-20230305231147407](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052311457.png)

![image-20230305231158124](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052311183.png)

![image-20230305231213349](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052312410.png)





**SpringBoot起步依赖**

![image-20230305231613555](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052316628.png)



![image-20230305232645323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052326422.png)



![image-20230305232837930](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052328007.png)

![image-20230305232941129](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052329217.png)



![image-20230305233011445](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052330519.png)

![image-20230305233513816](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052335912.png)





![image-20230305233631942](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303052336001.png)





#### 2.基础配置

![image-20230306102557742](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061025805.png)



##### 2.1 配置文件格式(.perperties/.yml/.yaml）三种格式

![image-20230306102628944](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061026003.png)

![image-20230306102643203](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061026285.png)

![image-20230306103734265](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061037362.png)

![image-20230306104024626](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061040688.png)



![image-20230306104044127](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061040180.png)



![image-20230306104136878](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061041938.png)





##### 2.2 yaml格式

![image-20230306104618644](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061046735.png)



![image-20230306105027719](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061050794.png)

![image-20230306105158052](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061051124.png)



![image-20230306105212366](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061052427.png)



##### 2.3 yaml数据读取方式（3种）

![image-20230306111238593](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061112686.png)



![image-20230306111519399](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061115510.png)



![image-20230306111635407](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061116498.png)



![image-20230306111706382](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061117442.png)

![image-20230306111721744](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061117818.png)



##### 2.4 多环境开发配置

![image-20230306123737398](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061237493.png)



![image-20230306125712330](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061257410.png)



![image-20230306125746325](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061257394.png)

![image-20230306125824758](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061258840.png)



![image-20230306125835368](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061258433.png)







![image-20230306125627900](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061256019.png)



##### 2.5 多环境命令行启动

![image-20230306131130856](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061311921.png)



![image-20230306131358719](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061313807.png)





##### 2.6 多环境开发控制

![image-20230306132816945](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061328019.png)



![image-20230306132839367](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061328450.png)



![image-20230306132906539](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061329622.png)



![image-20230306132955825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061329899.png)



![image-20230306133007916](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061330997.png)



![image-20230306133025332](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061330392.png)



##### 2.7 配置文件分类

![image-20230306133129057](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061331132.png)



![image-20230306133148298](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061331364.png)



#### 3.整合第三方技术

![image-20230306134440299](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061344358.png)



##### 3.1 整合JUnit



![image-20230306134547121](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061345209.png)



![image-20230306135654625](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061356701.png)



![image-20230306135710093](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061357171.png)





##### 3.2整合 MyBatis

![image-20230306140033290](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061400348.png)

![image-20230306140100372](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061401434.png)



![image-20230306140125778](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061401860.png)



![image-20230306140139326](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061401417.png)



![image-20230306142336075](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061423171.png)



![image-20230306142348982](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061423057.png)



![image-20230306142359813](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061423890.png)



![image-20230306142426856](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061424919.png)

![image-20230306142452721](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061424778.png)



##### 3.3 整合ssm

![image-20230306145751882](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061457964.png)

![image-20230306145759828](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061457890.png)



![image-20230306150112047](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061501124.png)



![image-20230306150147884](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061501948.png)



![image-20230306150202290](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061502348.png)



![image-20230306150216144](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061502229.png)



![image-20230306145816677](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061458745.png)

## 5.MyBatisPlus

![image-20230306145922618](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061459685.png)



![image-20230306150231827](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061502880.png)



#### 5.1 MyBatisPlus简介

![image-20230306150331416](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061503471.png)

![image-20230306150541803](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303061505872.png)

![image-20230306211603392](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062116501.png)



![image-20230306211627087](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062116169.png)



![image-20230306211656047](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062116137.png)



![image-20230306211714512](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062117594.png)



![image-20230306211738494](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062117596.png)



![image-20230306211840466](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062118542.png)



![image-20230306211853580](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062118664.png)

**MyBatisPlus概述**

![image-20230306212238069](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062122125.png)



![image-20230306212359550](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062123612.png)



#### 5.2 标准数据层开发

![image-20230306212613585](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062126655.png)

![image-20230306212649207](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062126320.png)



![image-20230306214315720](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062143801.png)

![image-20230306214356712](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062143791.png)

![image-20230306214432816](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062144888.png)



**分页功能**

![image-20230306214508357](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062145449.png)



![image-20230306220004209](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062200297.png)



![image-20230306220031272](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062200353.png)



![image-20230306220042255](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062200325.png)

![image-20230306220102831](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062201901.png)



![image-20230306220122912](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062201981.png)



#### 5.3 DQL编程控制

![image-20230306220206210](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062202275.png)



![image-20230306220304345](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062203449.png)



![image-20230306222409509](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062224597.png)



![image-20230306222440617](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062224705.png)



![image-20230306222530127](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062225194.png)



![image-20230306223740230](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062237308.png)

![image-20230306223801358](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062238449.png)



![image-20230306223823839](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303062238910.png)



![image-20230307104427716](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071044835.png)



**查询条件设置**

![image-20230307105831494](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071058595.png)



![image-20230307105844096](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071058179.png)

![image-20230307105927432](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071059500.png)

https://baomidou.com/pages/10c804/#abstractwrapper



![image-20230307110140939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071101030.png)



![image-20230307110227260](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071102338.png)

**问题一**

![image-20230307110359238](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071103318.png)

![image-20230307110434394](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071104482.png)

![image-20230307110858186](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071108262.png)





**问题二**

![image-20230307110714039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071107127.png)



![image-20230307110736655](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071107740.png)

![image-20230307111052096](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071110173.png)



**问题三**

![image-20230307111412731](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071114822.png)

![image-20230307111432672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071114754.png)



**问题四**

![image-20230307111535152](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071115236.png)

![image-20230307111601507](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071116591.png)

![image-20230307111618327](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071116399.png)



![image-20230307112220052](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071122114.png)



![image-20230307112229712](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071122785.png)



#### 5.4 DML编程控制

![image-20230307112339267](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071123323.png)

![image-20230307135303700](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071353773.png)



![image-20230307135509973](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071355060.png)



![image-20230307140622429](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071406523.png)



![image-20230307140940516](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071409620.png)



![image-20230307140953376](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071409444.png)



![image-20230307141001176](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071410247.png)



**多记录操作**

![image-20230307141057706](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071410770.png)



![image-20230307141725414](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071417486.png)



**逻辑删除**

![image-20230307143601185](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071436257.png)

![image-20230307143624878](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071436944.png)



![image-20230307143703430](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071437544.png)



![image-20230307143723292](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071437353.png)



**乐观锁**

![image-20230307143921344](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071439419.png)

![image-20230307145317775](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071453854.png)



![image-20230307145326286](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071453357.png)



![image-20230307145334970](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071453048.png)

![image-20230307145346886](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071453986.png)



![image-20230307145520526](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071455597.png)

**代码生成器**

![image-20230307151320399](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071513540.png)



![image-20230307151513675](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071515784.png)



![image-20230307151636812](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071516870.png)

![image-20230307153603250](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071536333.png)



![image-20230307153616632](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071536697.png)



![image-20230307153628472](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071536550.png)



![image-20230307153638968](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071536036.png)



![image-20230307153649069](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071536145.png)



![image-20230307153712206](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202303071537270.png)



















































































