# summary 
# 实习阶段总结 ssm框架demo

### Listener中@Autowired无法注入的问题

原因如下：在Listener监听器中无法使用Spring容器的@Resource或者@Autowired 注解的方法注入bean，因为，在web Server容器中，无论是Servlet，Filter，还是Listener都不是Spring容器管理的，因此我们都无法在这些类中直接使用Spring注解的方式来注入我们需要的对象。在这里，Servlet的整个生命周期都是由Servlet容器来处理的。如果把它硬放到Spring容器中去创建，Servlet对象是可被Spring容器建出来，但Servlet容器可能跟本就不知道这个Servlet是否存在，因为不在它自己的容器中。所以，servlet交给web server来管理，不要交给spring管理。
