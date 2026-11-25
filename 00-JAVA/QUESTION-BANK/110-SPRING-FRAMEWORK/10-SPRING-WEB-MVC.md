1. What is the Front Controller design pattern? How is it implemented in Spring MVC?

	- Front Controller is a design pattern which is implemented by `DispatcherServlet`. 
	- It acts as the entry point of Spring MVC web application.
	- The `DispatcherServlet` class, with the help of `HandlerMapping`, knows that for all particular actions (means client requests) which controller class or method should be called.
	- In our application, we need to configure the Front Controller so that all the requests must hit Front Controller class first.
2. **What is `DispatcherServlet`, and why is it called the Front Controller?**

	- `DispatcherServlet` is a Servlet which is provided by the Spring MVC Framework.
	- `DispatcherServlet` is used to receive the incoming HTTP requests and delegates the responsibilities to `HandlerMapping`, `HandlerAdapter`, and `ViewResolver`.
	- `DispatcherServlet` is called the Front Controller because 
3. 