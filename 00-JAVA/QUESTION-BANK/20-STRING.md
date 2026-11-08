1. **What is a String in Java?**
	- String is a predefined class in Java which is used to represent a <mark>sequence of characters</mark>. Its objects are <mark>immutable</mark>, which means once we create a String object, we cannot change its content. If we try to modify it, then instead of changing the original object, Java creates a new String object with the modified content.
2. **Why is String immutable in Java? and What are the benefits of immutability?**
	In Java, String is immutable because of two reason - 
	1. Memory Optimization
	2. Security

		1. Memory Optimization
			- Java maintains a String constant Pool to reuse String objects where multiple String reference variables point to same String object.
			- Since String is immutable means one reference cannot modify the shared object's content and affect other references. and because of this, it reduces unnecessary object creation and saves Heap memory.
		2. Security
			- Strings are commonly used for sensitive information such as database URLs, file paths and authentication-related values. Immutability prevents the existing String object's content from being modified unexpectedly.
3. **How many ways are there to create an String object?**
	There are two ways to create String objects:
	1. Using String literals
	2. Using `new` keyword
4. **What is the difference between `StringBuilder` and `StringBuffer`, and which one is faster? Why?**

| #   | `StringBuffer`                                                                                                        | `StringBuilder`                                                                                                                    |
| --- | --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| 1   | At a time only one thread is allowed to operate on `StringBuffer` object, Hence `StringBuffer` object is thread-safe. | At a time only multiple threads are allowed to operate on `StringBuilder` object, Hence `StringBuilder` object is not thread-safe. |
| 2   | Since on `StringBuffer` object, only one thread is allowed, therefore its performance is slow.                        | Since on`StringBuilder` multiple objects are allowed, therefore its performance is fast.                                           |
| 3   | Every method in `StringBuffer` is always synchronized.                                                                | Every method in `StringBuilder` is not synchronized.                                                                               |
| 4   | introduced in Java 1.0v.                                                                                              | introduced in Java 1.5v.                                                                                                           |

3. **What is the difference between `equals()` and `==`?**
	In Java, == is used to compare the <mark>references</mark> of two String objects, whereas `equals()` method is used to compare their <mark>actual content</mark>.
4. **What is String interning?**
	String interning is a memory optimization technique where Java ensures that only one copy of each string literal exists in memory. This copy is stored in the String Constant Pool (SCP) which allows the JVM to reuse it.
5. **How does interning work?**
	When a String literal like "Java" is used, JVM checks whether it is already inside SCP or not:
	- if it is there, JVM reuses the reference from the SCP.
	- If it's not, JVM creates a new String object inside SCP and returns its reference.
6. **Is String really thread-safe?**
	Yes, String is thread-safe because of immutability. Once a String object is created, we cannot change its content. If we try to modify it, then instead of changing the original object. 