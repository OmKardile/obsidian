		


# minimal straight to point answers

  

  
***

  

## Object Oriented Programming

  

1. **Object oriented concepts:** Abstraction, Encapsulation, Modularity, Hierarchy, Polymorphism, Persistence, Concurrency.[^1]

    - **Object-based:** Uses objects, lacks all OOP features.

    - **Object-oriented:** Supports all OOP pillars.

    - **Fully object-oriented:** Everything is an object (e.g., Smalltalk, not Java).

2. **Advantages:** Modularity, code reuse, easy maintenance, security via encapsulation; data security by restricting access using visibility modifiers.[^2][^1]

3. **Class and Object:**

    - Class: Blueprint.

    - Object: Instance.

    - Example: Class Car, Object: MyCar.

4. **Characteristics of Object:** State (fields), behavior (methods), identity (unique field/address).[^1][^2]

5. **Need of getter and setter:** To read/write private fields from outside safely.[^3][^4]

6. **Abstraction \& Encapsulation with example:**

    - Abstraction: Focus on essential features (driving a car).

    - Encapsulation: Bind data and methods (Car class with speed and drive method).

7. **Polymorphism \& Types:**

    - Many forms for same entity.

    - Compile-time (method overloading) and Runtime (method overriding).[^5][^3][^1]

8. **Method overloading:** Same method name, different parameters.

    - Rules: Change number/type of params.

    - Return type is not considered.[^4][^3]

9. **Types of hierarchy:**

    - Single, Multiple (not in Java), Multilevel, Hierarchical, Hybrid.[^6][^5]

10. **Method overloading vs overriding:**

    - Overloading: Same name, diff params (compile time).

    - Overriding: Subclass provides own implementation (runtime).[^5]

11. **Object slicing:**

    - Upcasting: Subclass object referenced by superclass, derived fields/methods lost.

12. **Down-casting:**

    - Assign superclass reference to subclass.

    - Needed for accessing subclass-specific features (after instanceof check).[^6][^5]

13. **Association, composition, aggregation:**

    - Association: "has-a"

    - Composition: Part-of (tight coupling)

    - Aggregation: Has-a (loose coupling).[^5][^6]

14. **Inheritance types:**

    - Single, multi-level, hierarchical, hybrid.

    - Multiple inheritance not allowed for classes in Java.[^6][^5]

15. **Interface, abstract class, non-abstract class:**

    - Interface: Only method signatures, no fields.

    - Abstract: Contains abstract methods, can't instantiate.

    - Non-abstract: Full implementation.

16. **Design patterns, singleton:**

    - Creational, Structural, Behavioral.

    - Singleton: Only one instance allowed; use private constructor and static getInstance method.[^7][^8]

  

***

  

## Java Programming

  

1. **Collection framework:** Provides reusable data structures; e.g., ArrayList, HashMap.[^9][^10]

2. **Functional programming:** Uses functions and immutability; in Java, use Streams and Lambda.[^11]

3. **Multithreading example:** Multiple threads run tasks; producer-consumer pattern shares data with synchronization.

4. **Create threads:**

    - implements Runnable: Pass Runnable to Thread.

    - extends Thread: Subclass Thread.

5. **Executor framework:** API for managing thread pools.

6. **start() vs run():** start() creates new thread; run() executes in current thread only.

7. **Garbage Collector:** Automatically frees memory of unreachable objects.[^12][^11]

8. **main() method overloading:** Allowed, but only main(String[] args) is entry point.[^2]

9. **Thread-safe singleton:** Use synchronized block or enum for single instance.[^8][^7]

10. **Override static method:** No, static methods cannot be overridden.[^5]

11. **Encapsulation \& Abstraction:** Encapsulation—private fields, public methods; Abstraction—car hides engine details.[^7][^8][^2]

12. **Interface method collision:** No collision; one implementation, must resolve ambiguity in class.

13. **Upcasting/Downcasting:** Upcasting—subclass to superclass (safe); Downcasting—superclass to subclass (use instanceof).[^6][^5]

14. **Default methods in interface:** Can provide default implementation since Java 8.

15. **HashSet/HashMap internals:** HashSet uses HashMap; hashCode() determines bucket, equals() checks key.[^9]

16. **Collection initial capacity:** E.g., ArrayList default is 10; exceeds, resizes.

17. **HashMap thread safety:** Not thread-safe; use ConcurrentHashMap for thread safety.

18. **StringBuilder vs StringBuffer:** StringBuilder—faster, not thread-safe; StringBuffer—thread-safe.[^11][^12]

    - String pool: Shared storage for string literals.

19. **== vs equals():**

    - == : Reference check for objects, value check for primitives.

    - equals(): Content check (should be overridden).[^13][^9]

20. **Fail-fast vs fail-safe iterator:**

    - Fail-fast: Throws error if structure changes (ArrayList).

    - Fail-safe: Works on copy, no error (ConcurrentHashMap).

21. **Lambda expression:** Short functional code; types inferred by compiler.[^11]

22. **Functional interface:** Interface with single abstract method; e.g., Runnable, Predicate.[^11]

  

---

  

<div style="text-align: center">⁂</div>

  

[^1]: WhatsApp-Image-2025-08-29-at-17.21.31_0f6b2068.jpg

  

[^2]: WhatsApp-Image-2025-08-29-at-17.21.30_74087c9e.jpg

  

[^3]: Day03_Help.pdf

  

[^4]: Day03_Images.pdf

  

[^5]: Day05_Help.pdf

  

[^6]: Day05_Images.pdf

  

[^7]: Day04_Help.pdf

  

[^8]: Day04_Images.pdf

  

[^9]: Day09_Help.pdf

  

[^10]: Collection.pdf

  

[^11]: Day08_Help.pdf

  

[^12]: Day08_Images.pdf

  

[^13]: Day06_Help.pdf