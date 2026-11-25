1. **What is the Front Controller design pattern? How is it implemented in Spring MVC?**

	- Front Controller is a design pattern which is implemented by `DispatcherServlet`. 
	- It acts as the entry point of Spring MVC web application.
	- The `DispatcherServlet` class, with the help of `HandlerMapping`, knows that for all particular actions (means client requests) which controller class or method should be called.
	- In our application, we need to configure the Front Controller so that all the requests must hit the **Front Controller class first**.

2. **What is `DispatcherServlet`, and why is it called the Front Controller?**

	- `DispatcherServlet` is a Servlet which is provided by the Spring MVC Framework.
	- `DispatcherServlet` is used to receive the incoming HTTP requests and delegates the responsibilities to `HandlerMapping`, `HandlerAdapter`, and `ViewResolver`.
	- `DispatcherServlet` is called as Front Controller because whenever a request comes from the client side, `DispatcherServlet` is the class which faces the HTTP request first. it delegates the responsibilities to `HandlerMapping`, `HandlerAdapter`, and `ViewResolver` and find the exact controller class or method for processing.

3. **Explain the complete request-processing flow in Spring MVC.**

	(or)

	**When a client sends an HTTP request, how does Spring MVC identify which Controller class and method should handle that request?**

	(or)
	
	**Suppose your application has multiple Controller classes. How does Spring MVC decide which Controller should receive a particular request?**
	
	Answer →
	
	In Spring MVC, the complete request-processing flow has 8 steps:
	1. Client sends an HTTP request.
	2. Tomcat server receives the request and forward it to`DispatcherServlet`.
	3. `doDispatch()` method which is written `DispatcherServlet` has invoked. it delegates the responsibility to `HandlerMapping` to identify the exact Controller class and handler method based on the incoming request.
	4. `HandlerMapping` is an interface. `DispatcherServlet` communicates with `HandlerMapping` implementations by calling their `getHandler(request)` method which identify the exact controller class and handler method which will handle the incoming request.
	5. `HandlerMapping` returns **`HandlerExecutionChain`**. it contains three things:
		1. The controller method.
		2. The process of executing that handler.
		3. A sequence of applicable interceptors.
	6. The `DispatcherServlet` with the help of `HandlerAdapter`, invokes the selected Controller method and process the request based the written logic and return the result. During this process, `preHandle()` and `postHandle()` interceptor methods are executed.
		1. 
	7. Depending on the Controller's return type, Spring MVC either uses
		1. `ViewResolver` to resolve the view (or )
		2. `HttpMessageConverter` to convert the returned object into a response format such as JSON.
	8. The server sends the appropriate HTTP response back to the client.

4. **What is the role of** `web.xml` **in a traditional Spring MVC application?**

	- `web.xml` is a deployment descriptor file used in Java web applications to configure the web application and its components.
	- In Spring MVC application, it is used for three purposes:
		1. To configure the Front Controller (`DispatcherServlet`).
		2. To define the URL mapping for the `DispatcherServlet`.
		3. To configure the other web application components such as filters and listeners.

5. **How do you configure `DispatcherServlet` in `web.xml`?**

	In web.xml we can configure `DispatcherServlet` using the `<servlet> and <servlet-mapping>`.
	- `<servlet>` is used to register the `DispatcherServlet` with the Servlet container.
	- `<servlet-name>` is used to define a name for the Servlet.
	- `<servlet-class>` is used to specify the fully qualified class name of the Servlet.
	- `<servlet-mapping>` is used to map the registered Servlet to a particular URL pattern.
	- `<url-pattern>` is used to tell the front controller that which incoming requests should be handled by the `DispatcherServlet`. if we are using **/**, it means all the requests after **/** will be considered.

6. **What happens if we do not configure the `DispatcherServlet` mapping correctly?**

	If we don't configure the `DispatcherServlet` mapping correctly in `web.xml` then incoming requests may not reach the `DispatcherServlet`, and as a result `DispatcherServlet` will not be able to find the exact Controller method and the client will be get HTTP error response such as *404 Not Found*

7. **Can DispatcherServlet directly invoke a Controller method without using HandlerAdapter?**

	No.

8. 