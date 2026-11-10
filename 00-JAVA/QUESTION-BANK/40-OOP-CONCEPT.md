1. What is OOP, and why do we need it?
2. What are the main advantages of OOP?
3. What are the four pillars of OOP in Java?
4. what is the difference between class and object?

	
| #   | Class                                                                                                              | Object                                                                                                                                                                            |
| --- | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | A Class is a **blueprint** / **template** for creating objects. <br>or we can say- Class is definition of objects. | An Object is an instance of a class that represents a real-world entity with **Properties (Variables)** and **Behaviors (Methods)**.                                              |
| 2   | A class can be created by using `class` keyword followed by **ClassName** written in Pascal Case.                  | In general, an Object can be created by using `new` keyword.                                                                                                                      |
| 3   | There is only one way to define a class, i.e., `class Employee {}`                                                 | There are multiple ways to create an object, such as- `new` Keyword, `clone()`, deserialization, Copy Constructor, Using Reflection, Using Factor Methods, Using String literals. |
| 4   | A class can exist without an object.                                                                               | An object can't exist without a class.                                                                                                                                            |
| 5   | A class does not allocate memory when it is created.                                                               | An object allocates memory when it is created.                                                                                                                                    |
| 6   | Class metadata is stored in Metaspace.                                                                             | An object are stored inside heap memeory.                                                                                                                                         |
| 7   | A ClassLoader is responsible for load a class into JVM.                                                            | A JVM is responsible to allocate memory for objects inside                                                                                                                        |


5. Can you give a real-world example of encapsulation?
6. What is the difference between abstraction and encapsulation?
7. What is the difference between method overloading and method overriding?
8. What is the purpose of method overloading?
9. What is dynamic method dispatch?
10. What is an abstract class?
11. What are the advantages and disadvantages of inheritance?
12. What are the is-a and has-a relationships?
13. Why is it advisable to prefer has-a (composition) over is-a (inheritance)?
14. What is the difference between a `final` method and a `private` method?
# Interface
1. What changes were made to interfaces from Java 7 to Java 9?
2. Why were default and static methods added to interfaces?
3. Why were private methods introduced in interfaces in Java 9?
4. Why do we use private methods in general?
5. Is it possible to have a concrete method in an interface?
6. What is the diamond problem in Java, and how does Java handle it?
7. Abstract classes and interfaces seem to do similar work. What is the difference, and when would you use each?
8. What is a functional interface? Can you give examples of existing ones?
9. What is the difference between a functional interface and a marker interface?
10. What is a marker interface?
11. A marker interface has no methods. How does it work internally?
12. Can you write a custom marker interface?