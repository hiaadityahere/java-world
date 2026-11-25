1. What is the Front Controller design pattern? How is it implemented in Spring MVC?

	- Front Controller is a design pattern which is implemented by `DispatcherServlet`. The `DispatcherServlet` class, with the help of `HandlerMapping`, knows that for all particular actions (means client requests) which controller class or method should be called.
	- It acts as the entry point of Spring MVC web application.
	- In our application, we need to configure the Front Controller so that all the requests must hit Front Controller class first.
2. aa