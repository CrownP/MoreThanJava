![img](https://img-blog.csdnimg.cn/20201127081319721.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3llcmVueXVhbl9wa3U=,size_16,color_FFFFFF,t_70#pic_center)

一、注解

1.注册到spring容器 
@Configuration @Bean @Component @Controller @Service @Repository 

2.包扫描注解  @ComponentScan
Value()：指定包路径  
includeFilters()、excludeFilters()：指定扫描规则，包含或排除。需要传入@Filter注解数组。@Filter的属性Type是一个枚举，有 FilterType.ANNOTATION：按照注解进行包含或者排除。ASSIGNABLE_TYPE：按照给定的类型。ASPECTJ：按照ASPECTJ表达式。REGEX：按照正则表达式。CUSTOM：按照自定义规则

3.设置Bean作用域 @Scope

- sigleton 默认单例，spring启动时将组件进行实例化并加载到容器中去。
- prototype：多实例。容器启动时不实例化，而是每次从容器获取组件对象时进行实例化。
- request：每次请求都会创建一个新的实例对象，但是同一次请求只会创建一次。要用在Web环境中
- session：在同一个session范围内，创建一个新的实例对象，用在Web环境中
- applicaiton：全局Web应用级别的作用域。不管应用程序中有多少个Spring容器，与应用程序同名的Bean只有一个。

4.懒加载 @Lazy
单例Bean默认在容器启动时进行加载，通过@Lazy注解可实现延时加载，即在调用获取该Bean对象时才进行初始化，@Lazy只针对单例Bean有效。

5.@Conditional注解

- Spring支持按照条件向IOC容器中注册bean，满足条件的bean就会被注册到IOC容器中，不满足条件的bean就不会被注册到IOC容器中。
- 阅读源码，可知：1.注解可用在类、方法上；2.接收Condition类型或其子类类型的Class对象数组；3.Conditon是一个接口。所以，我们使用@Conditional注解时，需要写一个类来实现Condition接口，它会匹配@Conditional所符合的方法

6.@Import 三种用法主要包含

- 直接填写class数组的方式，加载到容器中去
- ImportSelector接口的方式，即批量导入，这是重点
- ImportBeanDefinitionRegistrar接口方式，即手工注册bean到容器中