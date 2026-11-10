# Multithreading Interview Questions (3 YOE Backend Developer)

## 1. Threading basics
1. **What is a thread in Java?**
	 - Within a process, <mark>a smallest unit of execution</mark> is called a **Thread**.
	 - Within a process, Threads share process's memory space and system resources.
	 - In Java, every program has at least one Thread: the **`main` thread**.
2. **What is the difference between a process, a thread?**

| #   | `Process`                                                                                  | `Thread`                                                                                  |
| --- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| 1   | A program under execution is called a **Process**.                                         | Within a process, a smallest unit of execution is called a **Thread**.                    |
| 2   | A Process has its own memory space and system resources.                                   | Within a process, Threads share process's memory space and system resources.              |
| 3   | Process can communicate with each other which is called IPC (Inter-Process Communication). | Threads can easily communicate to each other because they share a process's memory space. |
| 4   | Generally, crashing of one process can not crash to another processes.                     | Crashing of one thread may affect an entire proccess.                                     |

3. **What is the difference between multitasking and multithreading?**

	
| #   | multitasking                                                                                                                                              | multithreading                                                                                                                                                      |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Executing several tasks simultaneously where each task is a separate independent program (process), is called multitasking.                               | Executing several tasks simultaneously where each task is a separate independent part of the same program, is called multithreading.                                |
| 2   | **Example-** While typing a Java program in editor, we can listen audio songs from same system and at the same time we can download a file from internet. | **Example:** While using an e-commerce application, one thread can handle order processing, another can process payments, and another can send email notifications. |
| 3   | Multitasking is best suitable at **OS-Level**.                                                                                                            | Multithreading is best suitable at **Programmatic-Level**.                                                                                                          |


4. **What is context switching, and why is it expensive?**
	- Context switching is a mechanism in which the CPU switches its execution from one process or one thread to another.
	- Basically, when the CPU switches from one process to another, the operating system saves the current state of the running process, Then it loads the saved state of another process and resumes its execution.
	- Context switching is expensive because whenever the CPU switches from one process or thread to another, it has to save the current execution state and load the next execution state. During this time, the CPU is not performing actual application work.
5. **What is the difference between concurrency and parallelism?**
	Concurrency is where multiple tasks are executing during overlapping periods of time where they use single CPU core one after another.
	Whereas Parallelism means multiple tasks are executing at the same time by using multiple CPU cores.
	Example: 
	- Concurrency can be achieve by Threads and ExecutorService Framework.
	- Parallelism can be achieve by by `parallelStream()` or a ForkJoinPool.
6. **What are the advantages and disadvantages of multithreading?**
	<mark>Advantage:</mark>
	- Better CPU Utilization
	- Improved Performance
	- Resource Sharing
	- Faster Context Switching
	<mark>Disadvantage:</mark>
	- Race Condition
	- Deadlock
	- Synchronization Overhead
	- Difficulty in Debugging
7. **What is the main thread in Java?**
	When we run a java application, JVM creates and starts a main thread which is responsible for executing `main()` method.
	- It is the starting point of execution in a standard Java application.
	- We can create additional threads from the main thread.
8. **What happens when main thread finishes while other threads are still running?**
	If the main thread finishes its execution while other threads are still running, the JVM does not terminate immediately. It waits for all remaining threads to complete their execution except Daemon Thread.
9. **What is a daemon thread? Give a use case and explain what happens to it when all user threads finish.**
	- The Threads which are executing in the background are called **Daemon Threads**. Example: Garbage Collector etc.
	- The main objective of Daemon Thread is **to provide support for non-Daemon Threads** (main-Thread).
	- When all user threads finish their execution, the JVM can shut down even if daemon threads are still running.
10. **What is thread priority? Is it reliable across platforms?**
	- Every thread in Java has some priority, it may be default priority which is generated by JVM (or) a customized priority which is provided by a programmer.
	- The valid range of thread-priority is **1-10**.
		- 1 is **Min Priority**
		- 5 is **Normal Priority**
		- 10 is **Max Priority**.
	- The thread which is having highest priority will get the chance first.
	- If two threads having same priority then we can't expect the exact execution order. it depends on Thread-Scheduler.
	- The default priority only for the **main** thread is 5. but for all remaining threads, the default priority will be inheriting from parent to child.

## 2. Creating and running threads

11. **How do you create your own thread?**
	We can define a Thread in the following two ways:
	1. By extending `Thread` class
	2. By implementing `Runnable` interface
	![define-a-thread](define-a-thread.drawio.svg)

12. **Which is better for creating a thread: extending `Thread` or implementing `Runnable`?**
	We can define a Thread in the following two ways:
	1. By extending `Thread` class
	2. By implementing `Runnable` interface
	Among the two ways of defining a thread, the `implements Runnable` approach is recommended.

	In the first appraoch, our class always extend `Thread` class, so there is no chance of extending any other class. Hence, we are missing **inheritance benefit**.

	But in the second appraoch, while implementing `Runnable` interface, we can extend any other class. Hence, we won't miss any inheritance benefit.

	> Because of above reason `implements Runnable` interface approach is **recommended** than extending `Thread` class.
13. **What is the difference between `Runnable` and `Callable`?**


| #   | `Runnable`                                                             | `Callable`                                                                        |
| --- | ---------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| 1   | `Runnable` is a functional interface available in `java.lang` package. | `Callable` is a functional interface available in `java.util.concurrent` package. |
| 2   | It contains an abstract method `run()`.                                | It contains an abstract method `call()`.                                          |
| 3   | The `run()` method has a `void` return type.                           | The `call()` method returns a value of type `V`.                                  |
| 4   | It cannot return a result directly.                                    | It can return a result.                                                           |
| 5   | It cannot declare checked exceptions.                                  | It can declare checked exceptions.                                                |
| 6   | It can be executed using the `Thread` class or `ExecutorService`.      | It is generally executed using `ExecutorService`.                                 |


14. **Why don't we call `run()` directly when we want multithreading?**

	We don't call the `run()` method directly because it behaves like a normal method call and executes in the current thread. 

	If we want to achieve multithreading, we should call the `start()` method  which creates a new thread of execution and this thread will call `run()` method internally.

15. **Why can't we call `start()` twice on a thread, and which exception is thrown?**

	We cannot call the `start()` method twice on the same thread because a thread can be started only once during its lifecycle. 

	Once we start a thread, it goes into its Thread lifecycle. and once it terminates, we can not start the same thread again. and if we try to start it again, we will get `IllegalThreadStateException`.
16. **Can you create a thread using a lambda expression? Why does that work?**

	Yes, we can create a thread using a lambda expression because the `Runnable` interface is a functional interface. It contains only one abstract method, which is `run()`.

	Lambda Expression is responsible to give the implementation of that abstract method. and in this way, we don't need to implement the `Runnable` interface explicitly by creating a class.
17. **What is the difference between `start()` and `run()` in terms of the call stack?**

	When we call the `start()` method, JVM creates a new thread with its own separate stack which will be responsible to call `run()` method in its own stack.

	Whereas, when we call `run()` method directly then it behaves like a normal method call and will execute in the current thread stack.
## 3. Thread life cycle and control

17. **Explain the thread life cycle and what causes each state transition.**

	Java has six thread states: NEW, RUNNABLE, BLOCKED, WAITING, TIMED_WAITING and TERMINATED.

	NEW ➜ RUNNABLE ➜ BLOCKED ➜ RUNNABLE ➜ ... ➜ TERMINATED
	
	NEW ➜ RUNNABLE ➜ WAITING / TIMED_WAITING ➜ RUNNABLE ➜ ... ➜ TERMINATED

	Initially, when we create a thread object, it enters the NEW state. When we call the start() method, it moves to the RUNNABLE state, where it is ready for execution or currently executing.

	- If a thread tries to enter a synchronized block but the required lock is held by another thread, it enters the BLOCKED state.
	- If a thread waits for another thread to perform some action, it enters the WAITING state. If it waits for a specified amount of time, it enters the TIMED_WAITING state.
	- Finally, when the run() method completes its execution or terminates due to an uncaught exception, the thread enters the TERMINATED state.
18. **What is the difference between the `BLOCKED`, `WAITING` and `TIMED_WAITING` states?**


| #   | `BLOCKED`                                                                                                                                                                                                                                                                                                        | `WAITING`                                                                                                                                                                                                                                                        | `TIMED_WAITING`                                                                                                                                                                              |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Whenever multiple threads are trying to execute a synchronized instance method on the same object then JVM decides which thread is allowed for execution. Whichever thread is getting scheduled to execute that synchronized method will acquire that Object Lock, while other threads will be in Blocked State. | in inter-thread communication, when a Thread which is expecting updation is responsible to call wait() method on that required object then, immediately the Thread will enter into WAITING state in indefinite time. common methods are: `wait()`, `join()` etc. | When a thread waits for a specified amount of time then it will go into `TIMED_WAITING`. Common Methods are: - `Thread.sleep(milliseconds)`, `wait(milliseconds)`, `join(milliseconds)` etc. |

19. **What does `join()` do? When would you use it?**
	
	The `join()` method in Java is used when one thread wants to wait for another thread to complete its execution.
	
	**Example:** 
	
	Suppose we have two threads
		- Thread A: Generates a report.
		- Thread B: Sends an email containing that report.
		
	Report must be prepare before sending that email then Thread B has to wait for Thread A to complete its execution and we can achieve this by using `join()`.
		
19. **What is the difference between `sleep()` and `wait()`?**

| #   | `sleep()`                                                                                                                                      | `wait()`                                                 |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| 1   | `sleep()` is a static method of `Thread` class                                                                                                 | `wait()` is an instance method of `Object` class.        |
| 2   | `sleep()` method is used to pause the execution of the current thread for a specific time.                                                     | `wait()` method is used for inter-thread communication.  |
| 3   | when `sleep()` method pause the execution of the current thread for a specific time, it does not release the monitor lock held by that thread. | `wait()` method releases the monitor lock of the object. |

20. **What does `yield()` do, and how does it differ from `sleep()`?**
21. **How do you stop a thread safely? Why are `stop()` and `suspend()` deprecated?**
22. **How does thread interruption work? What does `interrupt()` do when a thread is sleeping or waiting?**
23. **Why does `Thread.sleep()` require a try-catch block or a `throws` clause?**
24. **What is an uncaught exception handler for a thread? What happens when a thread throws an unhandled exception?**

## 4. Synchronization and locks

26. What is synchronization, and why do we need it?
27. What is a race condition, and which situations can cause one?
28. What is a critical section?
29. What is the difference between a synchronized method and a synchronized block? Which would you prefer and why?
30. What is an object lock (monitor), what is its purpose, and who acquires it?
31. What is a class-level lock, and why do we need it?
32. What is the difference between an object lock and a class lock? Can two threads run a static synchronized method and an instance synchronized method at the same time?
33. What is reentrancy? Is `synchronized` reentrant?
34. If a thread holds a lock and calls another synchronized method on the same object, what happens?
35. Can a constructor be synchronized? Can a variable be synchronized?
36. Is a `synchronized` block on a `String` literal or an `Integer` safe? Why or why not?
37. What is the difference between a synchronized collection and a concurrent collection?

## 5. The Java Memory Model, `volatile` and atomicity

38. What is the Java Memory Model?
39. What does the `volatile` keyword do? What problem does it solve?
40. What is the difference between `volatile` and `synchronized`?
41. Does `volatile` make `count++` thread-safe? Why or why not?
42. What is the happens-before relationship?
43. What are visibility, atomicity and ordering issues in multithreading?
44. What is instruction reordering, and how do `volatile` and `synchronized` prevent problems from it?
45. What is double-checked locking in a Singleton, and why is `volatile` required?
46. What are atomic classes (`AtomicInteger`, `AtomicReference`)? How do they work internally (CAS)?
47. What is Compare-And-Swap, and what is the ABA problem?
48. What is the difference between `AtomicInteger` and a synchronized counter? When would you use each?
49. What is `LongAdder`, and when is it better than `AtomicLong`?

## 6. Inter-thread communication

50. What is inter-thread communication?
51. Why are `wait()`, `notify()` and `notifyAll()` defined in `Object` and not in `Thread`?
52. Why must `wait()` and `notify()` be called from a synchronized context? What happens if they aren't?
53. What is the difference between `notify()` and `notifyAll()`? When can `notify()` cause problems?
54. What are spurious wakeups, and why should `wait()` be called inside a loop?
55. Does `wait()` release the lock? Does `sleep()` release it?
56. How would you implement the producer-consumer problem using `wait()` and `notify()`?
57. How would you implement producer-consumer using a `BlockingQueue`? Which approach do you prefer in production?
58. Where did you use the producer-consumer pattern in your project?

## 7. Deadlock, livelock and starvation

59. What is a deadlock? What are the four conditions required for it?
60. Write a program that creates a deadlock.
61. How do you detect a deadlock in a running application (thread dump, `jstack`, `ThreadMXBean`)?
62. How do you prevent or avoid deadlocks (lock ordering, `tryLock` with timeout)?
63. What is a livelock?
64. What is thread starvation, and what causes it?
65. How do you read a thread dump? What would you look for in a production hang?

## 8. Executor framework and thread pools

66. What is `ExecutorService` in Java, and why is it preferred over creating threads manually?
67. What are the different types of thread pools (`newFixedThreadPool`, `newCachedThreadPool`, `newSingleThreadExecutor`, `newScheduledThreadPool`)?
68. What is the difference between `execute()` and `submit()`?
69. What are the core parameters of `ThreadPoolExecutor` (core size, max size, queue, keep-alive, rejection policy)?
70. In what order does a `ThreadPoolExecutor` create threads and queue tasks?
71. What are the rejection policies, and which one would you choose?
72. What are the problems with `newFixedThreadPool` and `newCachedThreadPool` in production (unbounded queue, unbounded threads)?
73. How do you size a thread pool for CPU-bound and I/O-bound tasks?
74. What is the difference between `shutdown()` and `shutdownNow()`? What is `awaitTermination()`?
75. What is `ScheduledExecutorService`? How does `scheduleAtFixedRate` differ from `scheduleWithFixedDelay`?
76. What is `ForkJoinPool`, and what is work stealing?
77. What happens if a task submitted to an executor throws an exception?

## 9. Future and CompletableFuture

78. What is a `Future`? What are its limitations?
79. What is the difference between `Future.get()` blocking and a timeout version?
80. What is `CompletableFuture`, and how does it improve on `Future`?
81. What is the difference between `thenApply`, `thenCompose` and `thenCombine`?
82. How do you run several service calls in parallel and combine the results (`allOf`, `anyOf`)? Use an example like fetching order, payment and inventory data.
83. How do you handle exceptions in a `CompletableFuture` chain (`exceptionally`, `handle`)?
84. Which thread pool does `CompletableFuture.supplyAsync()` use by default? Why might you pass your own executor?

## 10. Locks API and synchronizers

85. What is the difference between `synchronized` and `ReentrantLock`?
86. What are `tryLock()`, `lockInterruptibly()` and fair locks in `ReentrantLock`?
87. What is a `Condition`, and how does it relate to `wait()`/`notify()`?
88. What is `ReadWriteLock`, and when would it help?
89. What is `StampedLock`, and what is optimistic reading?
90. What is a `CountDownLatch`? Give a use case such as service startup checks.
91. What is the difference between `CountDownLatch` and `CyclicBarrier`?
92. What is a `Semaphore`? How would you use one to limit concurrent access to an external payment gateway?
93. What are `Phaser` and `Exchanger`?

## 11. ThreadLocal and concurrent collections

94. What is `ThreadLocal`, and where is it used (user context, `SimpleDateFormat`, transaction context)?
95. Can `ThreadLocal` cause a memory leak in a thread pool? How do you prevent it?
96. What is the difference between `HashMap`, `Hashtable`, `Collections.synchronizedMap` and `ConcurrentHashMap`?
97. How does `ConcurrentHashMap` achieve thread safety in Java 8?
98. What is `CopyOnWriteArrayList`, and when is it a good choice?
99. What are `BlockingQueue` implementations, and how do they differ (`ArrayBlockingQueue`, `LinkedBlockingQueue`, `PriorityBlockingQueue`, `SynchronousQueue`)?
100. What is the difference between `ConcurrentLinkedQueue` and `LinkedBlockingQueue`?

## 12. Modern concurrency

101. What are virtual threads in Java 21, and what problem do they solve?
102. How do virtual threads differ from platform threads? When would they not help?
103. What is structured concurrency?
104. What is the difference between parallel streams and an executor? When can `parallelStream()` hurt performance?

## 13. Scenarios and coding

105. Two threads increment a shared counter 1000 times each, and the result is less than 2000. Why, and how would you fix it?
106. How would you make a Singleton class thread-safe? Compare eager, synchronized method, double-checked locking, and the holder class approach.
107. Write a program to print odd and even numbers using two threads in sequence.
108. Write a program to print numbers 1 to 10 using three threads in round-robin order.
109. Implement a thread-safe bounded buffer or blocking queue.
110. Implement a simple rate limiter, or limit an `OrderService` to N concurrent requests.
111. How would you process 10,000 orders in parallel and wait for all to finish?
112. Your production service slows down under load and CPU is at 100%. How do you investigate thread-related causes?
113. Your application's thread pool is exhausted and requests are timing out. How do you diagnose and fix it?
114. How do you ensure thread safety in a Spring Boot application (singleton beans, shared state, request-scoped data)?
115. Where did you use multithreading, executors or `CompletableFuture` in your project?