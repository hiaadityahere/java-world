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
3. How many ways are there to create an String object?
	There are two ways to create String objects:
	1. Using String literals
	2. Using `new` keyword
4. What is the difference between `StringBuilder` and `StringBuffer`, and which one is faster? Why?
5. What is the difference between `equals()` and `==`?
	In Java, == is used to compare the <mark>references</mark> of two String objects, whereas `equals()` method is used to compare their <mark>actual content</mark>.
6. What is String interning?
	
7. How does interning work?
8. Is String really thread-safe?