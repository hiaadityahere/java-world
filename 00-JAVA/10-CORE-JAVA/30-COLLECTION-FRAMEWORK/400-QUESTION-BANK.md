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
