# Ways to implement Singleton
There are multiple ways to implement Singleton in Java:
1. Eager Initialization
2. Lazy Initialization
3. Thread-safe Singleton (Double-Checked Locking)
4. Enum Singleton

## 1. Eager Initialization
The instance is created when the class is loaded.
```java
public class DatabaseConnection {

    private static final DatabaseConnection INSTANCE =
            new DatabaseConnection();

    private DatabaseConnection() {
    }

    public static DatabaseConnection getInstance() {
        return INSTANCE;
    }
}
```

Advantages:
- Simple
- Thread safe because class initialization is thread-safe in Java.

Disadvantage:
- The instance is created even if it is never used.
## 2. Lazy Initialization
The instance is created when it is requested for the first time.
```java
public class DatabaseConnection {

    private static DatabaseConnection instance;

    private DatabaseConnection() {
    }

    public static DatabaseConnection getInstance() {

        if (instance == null) {
            instance = new DatabaseConnection();
        }

        return instance;
    }
}
```

Advantage:
- The instance is created when it is requested for the first time.

Disadvantage:
- Not thread-safe because at a particular multiple threads can create multiple instances.
## 3. Thread-Safe Singleton (Double-Checked Locking)
The instance is created only once even if at a particular multiple threads access the method simultaneously.
```java
public class DatabaseConnection {

    private static volatile DatabaseConnection instance;

    private DatabaseConnection() {
    }

    public static DatabaseConnection getInstance() {

        if (instance == null) {

            synchronized (DatabaseConnection.class) {

                if (instance == null) {
                    instance = new DatabaseConnection();
                }
            }
        }

        return instance;
    }
}
```
We use `volatile` to make sure that when one thread updates a variable, other threads can see its updated value immediately.
## Enum Singleton