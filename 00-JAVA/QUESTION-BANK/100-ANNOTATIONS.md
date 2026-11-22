1. <mark>@Configuration</mark>
	
	**@Configuration** is a class level annotation which is used to tell the Spring IoC Container that this class is source of bean definition.

1. <mark>@Bean</mark>
	
	**@Bean** is a method-level annotation which is used to tell the Spring IoC Container to manage the object which is returned by that method.
2. <mark>@Component</mark>

	**@Component** is a class-level annotation which is used to tell the Spring IoC Container that register its object as a bean and detect the class during component scan.
3. <mark>@ComponentScan (basePackages = "com.flipkart")</mark>

	**@ComponentScan (basePackages = "com.flipkart")** is a class-level annotation which is used to tell the Spring IoC Container that scan the mentioned package and its subpackages for the class which is annotated with `@Component` and register their objects as a bean.
4. <mark>@Qualifier</mark>
	
	**@Qualifier** is a field-level, parameter-level or method-level annotation which is used to tell the Spring IoC Container that which specific bean should be injected when we have multiple beans of the same type.
5. <mark>@Primary</mark>
	
	**@Primary** is a class-level or method-level annotation which is used to tell the Spring IoC Container that which bean should be given preference by default for dependency injection when we have multiple beans of the same type.
5. @Autowired