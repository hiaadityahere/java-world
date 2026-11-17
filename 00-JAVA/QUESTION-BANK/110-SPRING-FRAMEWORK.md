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