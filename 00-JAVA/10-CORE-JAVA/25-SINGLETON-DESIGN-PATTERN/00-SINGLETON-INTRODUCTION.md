# what is singleton class?
 Singleton Design Pattern is a creational design pattern that guarantees a class has only one instance per JVM and provides a global point of access to it.

It is commonly used to manage shared resources like:
- Logging Services
- Database Connection Pools
- Caches

	etc.
## Advantage of Singleton Class
if several classes have same requirement then it is not recommended to create separate object for every requirement.
we have to create only one object and we can re-use the same object for every similar requirement so that performance & memory utilization will be improved.

## We can make the Singleton Design Pattern by:
- Making the constructor `private` so that from outside the class, objects cannot be created.
- Creating a `private static` instance of the class.
- Providing a `public static` method to return that instance.