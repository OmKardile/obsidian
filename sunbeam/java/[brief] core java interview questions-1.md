

***

  
## Java Programming Concepts

  

### 1. What is a Collection Framework? Explain 2 classes in Java Collections.

  

A **Collection Framework** in Java is a unified architecture for representing and manipulating collections, allowing efficient management of groups of objects in memory. It includes interfaces like List, Set, and Map, along with classes such as ArrayList, LinkedList, HashSet, HashMap, etc. Its main purpose is to manage data/objects in RAM efficiently. Introduced in Java 1.2, type-safety using generics was added in Java 5.0.[^1]

  

#### Examples:

  

- **ArrayList**: Implements the List interface. It is a dynamic array that can grow and shrink. It allows random access, and is not synchronized (thus not thread-safe).

- **HashSet**: Implements the Set interface. Stores unique elements, and uses hashing for storage. It allows fast lookups and does not maintain any order.[^2][^1]

  

***

  

### 2. What is Functional Programming? Explain Stream Programming with examples.

  

**Functional Programming** prefers computation as the evaluation of mathematical functions and avoids changing-state or mutable data. In Java, Streams API (since Java 8) enables functional-style operations on collections, allowing operations like `map`, `filter`, `reduce`, etc..[^1]

  

#### Example:

  

```java

List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

int sum = numbers.stream()

                 .filter(n -> n%2 == 0)

                 .mapToInt(n -> n)

                 .sum(); // Result: 6 (2+4)

```

  

Here, `filter` and `mapToInt` are functional operations applied on the stream.

  

***

  

### 3. Explain Multithreading using examples. Producer-Consumer standard example.

  

**Multithreading** refers to concurrent execution of two or more threads. A common example is the Producer-Consumer problem, where producer threads add data to a buffer and consumer threads remove data. (See Day06_Help/Java Buzzwords).[^3]

  

***

  

### 4. How to create new threads? Explain "implements Runnable" vs "extends Thread".

  

You can create threads in Java by either:

  

- Implementing the `Runnable` interface, and passing it to a `Thread` object.

- Extending the `Thread` class.

  

**Implements Runnable** is preferred for better design and separation of task from thread management.[^3]

  

***

  

### 5. What is Executor Framework?

  

The **Executor Framework** in Java provides a high-level API to manage pool of threads, making concurrent programming simpler. It separates thread management from the actual task to be performed, using classes such as `ExecutorService` and `Executors`.

  

***

  

### 7. What is the use of Garbage Collector in Java language?

  

The **Garbage Collector** automatically manages memory by releasing unreachable objects, preventing memory leaks. In Java, you can request garbage collection using `System.gc()` or `Runtime.getRuntime().gc()`. GC is of two types:[^4]

  

- **Minor GC**: Cleans young generation objects.

- **Major GC**: Cleans all generations, but is slower.

  

***

  

### 9. How to create thread-safe Singleton pattern?

  

Use a private static instance, a private constructor, and a public static getter method. For thread safety, initialize the instance inside a synchronized block.[^5]

  

```java

class Singleton {

    private static Singleton instance;

    private Singleton() {}

    public static synchronized Singleton getInstance() {

        if(instance == null) instance = new Singleton();

        return instance;

    }

}

```

  
  

***

  

### 10. Can you override static method?

  

**No**, static methods belong to the class, not to the instance, and are hidden, not overridden.

  

***

  

### 11. Basic OOP Principle: Encapsulation, Abstraction with examples.

  

- **Encapsulation**: Bundling data (fields) and code (methods) together, restricting access using access modifiers. Example: Private fields with public getter/setter methods.

- **Abstraction**: Focusing on essential features, hiding implementation details. Example: Abstract class or interface to represent "Shape" with a `draw()` method, leaving specific shapes to define implementation.[^6][^3]

  

***

  

### 13. What is Upcasting and Downcasting in Java? Where is it used?

  

- **Upcasting**: Assigning sub-class reference to a super-class variable. It happens implicitly and is safe.

- **Downcasting**: Assigning super-class reference to a sub-class variable, requires explicit casting, and may throw ClassCastException if type does not match.

  

Example:

  

```java

Person p = new Employee(); // Upcasting

Employee e = (Employee)p; // Downcasting

```

  

Used in polymorphism and runtime type resolution.[^6]

  

***

  

### 14. Explain default methods in interfaces.

  

Added in Java 8, default methods allow interfaces to provide method implementations, enabling new methods without breaking existing implementation.[^3]

  

***

  

### 18. Difference between StringBuilder and StringBuffer. Why String immutable? What is a String pool?

  

- **StringBuilder**: Not thread-safe, better performance in single-thread scenario.

- **StringBuffer**: Thread-safe, slower due to synchronization.

- **String is immutable**: When a String is modified, a new object is created. This guarantees thread safety and allows strings to be stored in the String pool.

- **String pool**: A pool of unique string literals stored in JVM heap to optimize memory usage.[^7][^4]

  

***

  

### 19. What is the difference between == and equals() in Java?

  

- **==** checks reference equality (if two references point to the same object).

- **equals()** checks value/content equality (the actual data inside the objects).[^3]

  

Example:

  

```java

String a = "Hello";

String b = new String("Hello");

System.out.println(a == b); // false

System.out.println(a.equals(b)); // true

```

  
  

***

  

### 20. What is a fail-fast and fail-safe iterator? Explain with code.

  

- **Fail-fast Iterator**: Throws `ConcurrentModificationException` if the collection is structurally modified during iteration (e.g., ArrayList, HashSet).

- **Fail-safe Iterator**: Works on a copy of the collection, so does not throw exceptions on modification (e.g., CopyOnWriteArrayList).[^1]

  

Example of fail-fast:

  

```java

List<Integer> list = new ArrayList<>();

Iterator<Integer> itr = list.iterator();

list.add(1); // Structural modification

itr.next();  // Throws ConcurrentModificationException

```

  
  

***

  

### 21. What is lambda expression in Java? How are lambda argument and return types determined?

  

Lambda expressions introduce concise syntax for declaring anonymous functions. Argument and return types are inferred by the compiler based on the context (usually the functional interface being implemented).[^4]

  

Example:

  

```java

// Runnable functional interface

Runnable r = () -> System.out.println("Hello");

```

  
  

***

  

### 22. What is a functional interface? Which functional interfaces are predefined and where are they used?

  

A **functional interface** is an interface with a single abstract method (SAM). Predefined examples in `java.util.function` include `Predicate`, `Function`, `Consumer`, and `Supplier`, commonly used in Stream APIs.[^4]

  

***

  

## Object Oriented Programming Concepts

  

### 1. What are object oriented concepts? Difference between object-based, object-oriented, fully object-oriented?

  

- **Object Oriented Concepts**: Abstraction, Encapsulation, Inheritance, Polymorphism.

- **Object-based**: Supports objects, but not inheritance or polymorphism (e.g. JavaScript).

- **Object-oriented**: Supports all OOP pillars (e.g. C++).

- **Fully object-oriented**: Everything is an object (e.g. Smalltalk, Java in context of its core classes).[^8][^3]

  

***

  

### 3. What is class and object? Give real-life example.

  

- **Class**: Blueprint. E.g., `Car` class.

- **Object**: Instance. E.g., `myCar = new Car()`.[^9][^10]

  

***

  

### 5. Need of getter and setter functions in class?

  

Getters retrieve field values, setters update them. They provide controlled access to class fields, ensuring encapsulation.

  

***

  

### 6. Abstraction and Encapsulation with real-life example?

  

- **Abstraction**: ATM machine, only exposes essential operations like deposit/withdraw, hides internal mechanics.

- **Encapsulation**: Class `Account` with private balance and public methods to manage balance.[^3]

  

***

  

### 7. What is polymorphism? Types and examples.

  

- **Compile-time (method overloading)**: Multiple methods with same name, different parameters.

- **Runtime (method overriding)**: Same method signature in subclass, implemented differently.

  

***

  

### 8. What is method overloading/overriding and rules for overriding?

  

- **Overloading**: Same method name, different parameters (compile-time).

- **Overriding**: Same signature in subclass. Rules include same/wider access, same signature, covariant return type, and exception list as subset of superclass method.[^6]

  

***

  

### 12. What is down-casting and when is it required? Explain with code.

  

Down-casting converts a superclass reference to a subclass reference. Used when you need subclass specific features, after type checking using `instanceof`.[^6]

  

```java

Person p = new Employee();

if(p instanceof Employee) {

    Employee e = (Employee)p;

    e.displaySalary();

}

```

  
  

***

  

### 13. Association, composition, aggregation explained with examples.

  

- **Association**: "has-a" relation; e.g., Employee has a Date of Joining.

- **Composition**: Strong ownership (part-of); e.g., Heart is part of Human.

- **Aggregation**: Weak ownership (can exist independently); e.g., Car has Driver.[^11][^6]

  

***

  

### 14. Types of inheritance, example, and problems with multiple inheritance.

  

Single, Multilevel, Hierarchical, Hybrid. Java doesn't support multiple class inheritance to avoid ambiguity, but supports multiple interface inheritance.[^6]

  

***

  

### 16. Types of design pattern – Explain Singleton design pattern.

  

- **Singleton design pattern** ensures that only one instance of a class exists throughout application life. Achieved by private constructor, static instance, and public static getter method.[^5]

  

***

  

This guide covers all key topics using structured explanations and examples, strictly using text from the provided PDFs and notes. Let me know which question or topic you want detailed code or further expansion on!

<span style="display:none">[^12][^13][^14][^15][^16][^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41]</span>

  

<div style="text-align: center">⁂</div>

  

[^1]: Day09_Help.pdf

  

[^2]: Collection.pdf

  

[^3]: Day06_Help.pdf

  

[^4]: Day08_Help.pdf

  

[^5]: Day04_Help.pdf

  

[^6]: Day05_Help.pdf

  

[^7]: Day08_Images.pdf

  

[^8]: Day01_Images.pdf

  

[^9]: Day02_Images.pdf

  

[^10]: Day02_Help.pdf

  

[^11]: Day05_Images.pdf

  

[^12]: Day09_Images.pdf

  

[^13]: Day09_Help.pdf

  

[^14]: Collection.pdf

  

[^15]: Day08_Images.pdf

  

[^16]: Day08_Help.pdf

  

[^17]: Day07_Help.pdf

  

[^18]: Day07_Images.pdf

  

[^19]: Day06_Help.pdf

  

[^20]: Day06_Images.pdf

  

[^21]: Day05_Help.pdf

  

[^22]: Day04_Images.pdf

  

[^23]: Day03_Help.pdf

  

[^24]: Day03_Images.pdf

  

[^25]: Day02_Images.pdf

  

[^26]: Day02_Help.pdf

  

[^27]: Day01_Help.pdf

  

[^28]: WhatsApp-Image-2025-08-29-at-17.21.29_9c427da4.jpg

  

[^29]: WhatsApp-Image-2025-08-29-at-17.21.30_f3ad8e57.jpg

  

[^30]: https://www.perplexity.ai/search/use-provided-pdfs-web-internet-22ZakkBlRhOEP1NkQ.5_oQ

  

[^31]: Day04_Images.pdf

  

[^32]: Day07_Help.pdf

  

[^33]: Day01_Help.pdf

  

[^34]: Day01_Images.pdf

  

[^35]: Day06_Images.pdf

  

[^36]: Day07_Images.pdf

  

[^37]: Day09_Images.pdf

  

[^38]: Day04_Help.pdf

  

[^39]: Day03_Help.pdf

  

[^40]: Day05_Images.pdf

  

[^41]: Day03_Images.pdf