1. What is the Front Controller design pattern? How is it implemented in Spring MVC?

	- Front Controller is a design pattern which is implemented by `DispatcherServlet`. 
	- It acts as the entry point of Spring MVC web application.
	- The `DispatcherServlet` class, with the help of `HandlerMapping`, knows that for all particular actions (means client requests) which controller class or method should be called.
	- In our application, we need to configure the Front Controller so that all the requests must hit the **Front Controller class first**.

2. **What is `DispatcherServlet`, and why is it called the Front Controller?**

	- `DispatcherServlet` is a Servlet which is provided by the Spring MVC Framework.
	- `DispatcherServlet` is used to receive the incoming HTTP requests and delegates the responsibilities to `HandlerMapping`, `HandlerAdapter`, and `ViewResolver`.
	- `DispatcherServlet` is called as Front Controller because whenever a request comes from the client side, `DispatcherServlet` is the class which faces the HTTP request first. it delegates the responsibilities to `HandlerMapping`, `HandlerAdapter`, and `ViewResolver` and find the exact controller class or method for processing.

3. **Explain the complete request-processing flow in Spring MVC.**

	In Spring MVC, the complete request-processing flow has 8 steps:
	1. Client sends an HTTP request.
	2. Tomcat server receives the request and forward it to`DispatcherServlet`.
	3. The `DispatcherServlet` delegates the responsibilty 
4. 