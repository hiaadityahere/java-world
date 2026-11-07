1. **Can you explain the JVM memory model? What lives in the heap, the stack and Metaspace?**
	When we run a Java program, JVM bifurcate its runtime memory area into 5 section - 
	1. Stack
	2. Heap
	3. Metaspace
	4. PC Register
	5. Native Method Stack
	
		1. **Stack**
			- Each java thread has its own Stack memory which is not shared between threads.
			- Whenever a method is invoked, JVM creates a stack frame inside that thread's Stack memory. 
			- Each Stack Frame contains a Local Variable Array, Operand Stack and method execution-related information.
			- The local variable array stores - primitive data types, object reference and array reference. 
			- once the method execution completes, its Stack Frame is popped from the stack (LIFO — Last In, First Out).
			- If Stack memory gets exhausted, JVM throws StackOverflowError.
		2. **Heap**
			- Heap is a shared runtime memory area where JVM stores actual objects and arrays. stack memory is responsible to store only references but Heap is the area where actual objects stores.
			- Heap also includes the actual array object (array reference -> stack, actual object -> Heap) similarly String reference -> stack and actual object inside Heap
			- Heap memory is managed by the Garbage Collector which clean the objects which is unreachable.
		3. **Metaspace**
			- Metaspace stores class level information such as
				- class names and their structures
				- field names, types and modifiers
				- method names, signatures and modifiers
				- Runtime Constant Pool
				- Class hierarchy (inheritance and interfaces)
			- Metaspace uses Native Memory rather than Java Heap memory.
			- Metaspace introduced in Java 8, replacing PermGen (Permanent Generation).
		4. PC Register (Program Counter Register)
			- Each Java thread has its own PC Register.
			- PC Register stores the next address of the JVM instruction to be executed.
		5. Native Method Stack
			- The Native Method Stack supports the execution of native methods.
			- Native methods are methods which are implemented in some other language that Java.

2. **Which Java versions have you worked with, and which features did you actually use in your project?**
	- I have primarily worked with Java 17 to develop and run my Maven-based projects. 

	- I have also used Java 8 features such as the Stream API and Optional. Stream API helped me for operations like filtering, mapping and processing collections.

3. **What is the difference between static and non-static members in Java?**
	
| #   | Static Members                                                          | Non-Static Members                                                                |
| --- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| 1   | Static members are declared using the `static` keyword.                 | Non-static members are declared without the `static` keyword.                     |
| 2   | Static members belong to class and they can be called using class name. | Non-static members belong to objects and they can be accessed using object names. |
| 3   | Static members allocate memory only once when the class is loaded.      | Non-static members allocate memory each time an object is created.                |
| 4   | Scope of Static members are class level.                                | Scope of Non-Static members are limited to object-level.                          |
| 5   | Static methods cannot access instance members directly.                 | Non-Static methods can access both instance and static members.                   |

4. **What is a static initialization block, and when would you use one?**
5. **Why can’t a static method be overridden in Java?**
	- Static method cannot be overridden in Java because static methods belong to the class, not to individual objects.
	- Method overriding is based on runtime polymorphism, where JVM decides which method to execute based on the actual object type.
	- Since static methods are associated with the class, they are resolved at compile time based on the reference class. This is called static binding (early binding).
	- If a child class writes a static method with the same signature as its parent class, it is called Method Hiding, not Method Overriding.
6. Can a static method be overloaded?
	- Yes, static methods can be overloaded because method overloading depends on the method signature.
	- Method overloading is based on compile-time polymorphism, where the compiler decides which method should be called based on the arguments passed during the method call.
	- and the `static` keyword does not restrict method overloading.
7. Can a static method access a non-static method directly?
8. What are wrapper classes, and why does Java need them? How do autoboxing and unboxing work?
9. What are the different ways to create an object in Java?

| #   | Approach      | Example                                    |
| --- | ------------- | ------------------------------------------ |
| 1   | `new` keyword | `Employee e = new Employee(101, "Alpha");` |
|     |               |                                            |
