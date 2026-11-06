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
