1. **What is a memory leak in Java, and how can it happen even though we have garbage collection?**
	- Memory leak in Java occurs when an application holds references to those objects which are no longer required. Since those objects are still reachable, the Garbage Collector cannot reclaim their memory. over time, Heap memory gets full and application throws `OutOfMemoryError`.
	- Garbage Collection only removes objects that are no longer reachable. It cannot determine whether a reachable object is still logically required by the application.
2. How do you detect a memory leak, and how do you fix it?
3. Have you faced a memory leak in your project? How did you identify and resolve it
4. What is the garbage collector, and how does it decide which objects to remove?
5. How can you find unused or unreachable objects in a running application?