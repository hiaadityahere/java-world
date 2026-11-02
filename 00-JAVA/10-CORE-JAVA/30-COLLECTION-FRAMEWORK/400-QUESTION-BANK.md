# Q1 What is Fail Fast?
In Java, Iterators are used to iterate over the collection objects. While iterating, if we are trying to do some structural modification (adding or removing elements) on a collection object, then immediately we will get `ConcurrentModificationException`. 
This scenario is called as Fail-Fast.
# Q2 How Fail Fast Iterator works ?
- To know whether the collection is structurally modified or not, fail-fast iterators use an internal variable called __modCount__ which increments each time when a collection is modified.
- When an iterator is created, it uses one another variable - called `expectedModCount`, which stores the current value of `modCount`. 
- Whenever the iterator performs certain operation, such as- `next()`,  it compares `expectedModCount` with `modCount`.
- If both values differ, it throws `ConcurrentModificationException`.
**Example of Fail-Fast Collections:**
- `ArrayList`
- `LinkedList`
- `HashSet`
- `LinkedHashSet`
- `TreeSet`
- `HashMap`
- `LinkedHashMap`
- `TreeMap`
- `Vector`
- `Stack`
- `PriorityQueue`
# Q3 What is Fail Safe ?
Fail-safe iterators are safe and don't throw any Exception if we modify the structure of a collection object while iterating over it. These Fail-Safe iterators.
# Q4 How Fail Safe Iterator works ?
Fail Safe iterators make a copy of the internal collection object and iterates over the copied collection. so if any structural modification happens then it affect on the copied collection (which is called as Snapshot), **not original collection**. 
**Example of Fail Safe Collection** - `ConcurrentHashMap`, `CopyOnWriteArrayList`
Since Fail Safe creates a copy, therefore it takes some extra memory.

# Q5 What is the contract between equals() and hashCode() method and what is the impact of these method in hashing based collection?