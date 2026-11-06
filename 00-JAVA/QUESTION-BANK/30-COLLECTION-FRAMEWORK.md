# Framework basics
1. Explain the Collection Framework hierarchy. How do `Collection`, `List`, `Set`, `Queue`, `Deque` and `Map` relate to each other?
2. What are the benefits of the Collection Framework over plain arrays?
3. Why isn’t `Map` part of the `Collection` interface?
4. What is the difference between `Collection` and `Collections`?
5. What is the difference between `Iterable`, `Iterator` and `Collection`?
6. What are generics in collections, and what is type erasure?
7. Which collections have you used in your project, and why did you choose them?
# `List`
8. What is an ArrayList, and how does it work internally? How does it grow when it is full?
9. What is the default capacity of an ArrayList, and what is its growth factor?
10. What do `ensureCapacity()` and `trimToSize()` do?
11. What is the difference between ArrayList and LinkedList, and when would you choose each?
12. What is the time complexity of adding and removing elements in a LinkedList at the beginning, middle and end?
13. What is the difference between ArrayList and Vector?
14. What is the difference between CopyOnWriteArrayList and ArrayList?
15. How do you remove duplicates from a List while preserving order?
16. What is the difference between `Arrays.asList()`, `List.of()` and `new ArrayList<>(...)`? Which are fixed-size or immutable?
# `Set`
17. What is the difference between a List and a Set? Explain in detail.
18. How does HashSet work internally?
19. What is the difference between HashSet, LinkedHashSet and TreeSet?
20. How does LinkedHashSet work internally?
21. What is the difference between LinkedHashSet and LinkedList?
22. What happens when you add a duplicate element to a Set?
23. How does TreeSet maintain order, and which data structure does it use internally?
24. Which of HashSet, LinkedHashSet and TreeSet allow a null element?
25. What happens if you add a user-defined object to a TreeSet without implementing `Comparable`?
26. You have an `Employee` class with `empId` and `empName`. If you insert two `Employee` objects into a TreeSet, what happens, and how do you fix it?
# `Map`
27. How does the `get()` method of a HashMap work?
28. How does a HashMap work internally?
29. How is the bucket index calculated from the hash code?
30. Why is a HashMap’s capacity always a power of two?
31. What are the initial capacity and load factor of a HashMap? What is rehashing, and how does resizing work?
32. What is a hash collision, and how does HashMap handle it?
33. What happens when two keys have the same `hashCode()` but are not equal?
34. What is a Red-Black Tree, and why does HashMap use it?
35. How does treeification work in HashMap? When does untreeification happen?
36. How many entries can a HashMap hold, and what limits that?
37. Why should HashMap keys be immutable? What can go wrong with a mutable key?
38. Can a HashMap have a null key or null values? What about Hashtable, TreeMap and ConcurrentHashMap?
39. What is the difference between HashMap and Hashtable?
40. What is the difference between HashMap and HashSet?
41. What is a LinkedHashMap, and how does it differ from a HashMap?
42. What is the difference between HashMap, LinkedHashMap and TreeMap?
43. What is the difference between TreeSet and TreeMap?
44. What is a `WeakHashMap`, and when would you use it?
45. What is an `IdentityHashMap`?
46. What is an `EnumMap`, and why is it faster than a HashMap for enum keys?
47. What is the best way to iterate over a Map?
48. How do you sort a Map by key and by value?
49. Explain `computeIfAbsent`, `merge`, `getOrDefault` and `putIfAbsent`.
50. Where did you use Map in your project?
# `Queue`, `Deque`, `Stack`
51. What is the difference between `Queue` and `Deque`?
52. What is the difference between `offer`/`add`, `poll`/`remove` and `peek`/`element`?
53. What is a PriorityQueue, and how does it order elements internally (binary heap)?
54. How do you implement a max-heap using a PriorityQueue?
55. Why is `Stack` discouraged, and what should you use instead (`ArrayDeque`)?
56. What is a `BlockingQueue`? What is the difference between `ArrayBlockingQueue` and `LinkedBlockingQueue`?
# Iterators: fail-fast and fail-safe
57. What is a `ConcurrentModificationException`, and when is it thrown?
58. What is the difference between fail-fast and fail-safe iterators?
59. Can you give examples of fail-fast and fail-safe collection classes and explain how each works?
60. What happens if you modify a collection while iterating over it?
61. How does `modCount` help detect concurrent modification?
62. How do you safely remove elements while iterating (`Iterator.remove()`, `removeIf`)?
63. What is the difference between `iterator.remove()` and `list.remove()`?
64. What is the difference between `Iterator` and `ListIterator`?
65. Why is there a `ListIterator` but no `SetIterator` or `MapIterator`?
66. What is the difference between `Enumeration` and `Iterator`?
67. What is the difference between `Iterator` and `Spliterator`?
# Sorting and comparison
68. What is the difference between `Comparable` and `Comparator`? When would you use `compareTo()` and when `compare()`?
69. What is the difference between `equals()` and `compareTo()`/`compare()`?
70. How do you sort a list of custom objects by multiple fields (`Comparator.comparing().thenComparing()`)?
71. What happens if `compareTo()` is inconsistent with `equals()` in a TreeSet or TreeMap?
72. What is the difference between `Collections.sort()` and `Arrays.sort()`, and which algorithm do they use?
73. Where did you use `Comparable` and `Comparator` in your project?
# `equals()` and `hashCode()`
74. What is the difference between `equals()` and `hashCode()`?
75. Why do we need to override both `equals()` and `hashCode()`?
76. If you override only `hashCode()` and not `equals()`, what happens when the object is used as a HashMap key?
77. If you override only `equals()` and not `hashCode()`, what happens?
78. What role does `equals()` play in hashing-based collections?
79. What is the contract between `equals()` and `hashCode()`?
# Concurrent and thread-safe collections
80. What is the difference between HashMap and ConcurrentHashMap?
81. How does ConcurrentHashMap achieve thread safety? How did it change between Java 7 (segments) and Java 8 (CAS and synchronized bins)?
82. When would you choose ConcurrentHashMap over a synchronized HashMap, and when does it stop helping?
83. What race conditions can occur when multiple threads use a HashMap? What could happen during resizing?
84. What is the difference between a synchronized collection (`Collections.synchronizedMap`) and a concurrent collection (`ConcurrentHashMap`)?
85. How do you make a collection thread-safe?
86. Where did you use ConcurrentHashMap in your project?
87. Where did you use the producer-consumer pattern in your project?
# Immutability and modern Java
