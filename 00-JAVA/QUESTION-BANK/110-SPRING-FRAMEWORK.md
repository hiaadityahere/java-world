1. **What is a Web Application?**
	- Application which is available over internet for customer use.
	- Example of Web applications - Zerodha, Zoho, WhatsApp, IRCTC, Amazon, Flipkart, Rapido, Ola, Draw.io, YouTube, LinkedIn etc.
2. **Define what is a standalone application?**
	
	A **Standalone Application** is an application that can run independently without depending on another application or external application server to execute its core functionality.

	**Example:** A java application running on console.
3. **What is Spring Framework?**
	- Spring Framework is open Source __Enterprise Web Application Development__ framework which will help us to develop an application.
	- Spring Framework is Light Weight, means we add only only those dependencies which our project needs.
4. **Why Spring Framework is considered as a light weight framework?**
	- Spring Framework is considered lightweight because it supports
		- POJO-based development
		- Dependency Injection through IoC container
		- Modular Architecture
		We use only the required modules and dependencies which our project needs and doesn't include entire framework.
5. **Which port does Apache Tomcat use by default for HTTP connections?**

	8080
6. **What is IoC, IoC Container and Bean in Spring Framework?**

	When we are developing a Java application using Spring Framework then, instead of creating, managing, and nullifying objects by our application, we have handed over this responsibility to Spring, This concept is called as <mark>IoC (Inversion of Control)</mark>.

	The part of Spring Framework which is responsible for Object Lifecycle Management is called as <mark>IoC Container</mark>.  IoC Container reads the configuration by using XML (or) Java config (or) annotations, it creates the objects, inject the necessary dependencies and manages their complete lifecycle.
	and those objects which lifecycle is managed by this IoC Container is called as <mark>Beans</mark>.
7. **What are different types of IoC Container in Spring Framework?**

	In Spring Framework, there are two types of IoC Container:
	1. **BeanFactory**
	2. **ApplicationContext**
8. **What is BeanFactory in Spring Framework?**
	- BeanFactory is one of the types of Spring IoC Container. 
	- It is the <mark>root interface of the Spring IoC Container</mark> which is responsible for providing basic bean management and dependency injection functionality.
	- It is the most basic container which gives only basic features.
	- `BeanFactory` uses <mark>lazy loading</mark>.
	- Because of its limited features, `BeanFactory` is rarely used directly in real applications.
9. **What is ApplicationContext in Spring Framework?**
	- `ApplicationContext` is one of the types of Spring IoC Container. 
	- It is a sub-interface of `BeanFactory` which has all the features of `BeanFactory` and it also contains the advanced enterprise-level features like- event publishing, internationalization (messages), resource loading etc.
	- `ApplicationContext` uses eager loading.
	- The implementations of `ApplicationContext` is:
		1. `ClassPathXmlApplicationContext` (**XML-Based**)
		2. `FileSystemXmlApplicationContext` (**XML-Based**)
		3. `AnnotationConfigApplicationContext` (**Java-Based** & **Annotation-Based**)
10. **What is lazy loading and eager loading in Spring IoC Container?**

	**(or)**
	
	**When does Spring create the beans, at startup or when we ask for them?**

	**(or)**

	**What is the difference between how BeanFactory and ApplicationContext load beans?**

	Lazy Loading and Eager Loading are the ways to tell the Spring IoC Container that when to create a bean.

	<mark>Lazy Loading</mark>
	- In Lazy Loading, the IoC Container creates the bean only when it is requested for the first time, for example - by calling `getBean()`. 
	- `BeanFactory` uses lazy loading.
	
		<mark>Advantage</mark>
		- Application startup is faster.
		- Memory saving.
		
		<mark>Disadvantage</mark>
		- Configuration problems are found later, at runtime, when the bean is first requested.

	<mark>Eager Loading</mark>
	- In Eager Loading, the IoC Container immediately creates the bean when the container starts. It does not wait for someone to ask for the beans. 
	- `ApplicationContext` uses eager loading for singleton beans by default.
	
		<mark>Advantage</mark>
		-  Configuration problems (a wrong bean name, a missing dependency) are found at startup and not at runtime.
		
		<mark>Disadvantage</mark>
		- Application startup is slower.
		- Memory consumption is higher (because all singleton beans are created even if some of them are never used).
11. **In how many ways can we configure beans in Spring?**

	There are three ways to configure a bean in Spring:
	1. XML Based
	2. Java Config
	3. Annotation Based