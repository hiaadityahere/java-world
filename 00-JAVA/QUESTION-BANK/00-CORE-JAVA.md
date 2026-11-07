1. Can you explain the JVM memory model? What lives in the heap, the stack and Metaspace?
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
2. Which Java versions have you worked with, and which features did you actually use in your project?
3. What is the difference between static and non-static members in Java?
4. What is a static initialization block, and when would you use one?
5. Why can’t a static method be overridden in Java?
6. What are wrapper classes, and why does Java need them? How do autoboxing and unboxing work?
7. What are the different ways to create an object in Java?