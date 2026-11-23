# Deques & Guitar Synthesizer

**Course:** CS 61B, Data Structures (UC Berkeley, Fall 2022), Project 1

**Goal:** build two implementations of a double-ended queue (deque) from scratch, then use one to synthesize the sound of a plucked guitar string.

## What I did
- **LinkedListDeque:** a generic, doubly linked list with a **circular sentinel node**, so adding and removing at either end runs in constant time. I implemented `get` both iteratively and **recursively**.
- **ArrayDeque:** a generic **circular array** that wraps its front and back pointers with modular arithmetic. It **resizes** by doubling when full and halving when it drops below 25% full, so memory stays proportional to the number of items.
- Both classes implement a shared `Deque` interface and support **iterators** and `equals`, so they work with Java's for-each loops and can be compared with each other.
- **MaxArrayDeque:** extended the array deque to return its largest element under any `Comparator`.
- **Testing:** wrote **JUnit** tests covering adds and removes, empty-deque edge cases, iteration, equality, resizing, and a one-million-element stress test.
- **Guitar Hero:** used the array deque as a ring buffer to implement the **Karplus-Strong** algorithm, which fills the buffer with noise on a pluck and then repeatedly averages and decays samples to produce a realistic string tone at 44.1 kHz.

## What I learned
- How the same interface can have very different performance depending on the underlying data structure.
- Amortized analysis in practice: occasional resizes still give constant average time per operation.
- Edge-case and stress tests catch bugs that a few hand-picked examples miss.

## Skills and tools
Java, generics, interfaces and inheritance, linked lists, circular arrays, dynamic resizing, iterators, comparators, recursion, JUnit, audio signal processing basics.
