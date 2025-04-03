# 📌 LinkedList in Java

The **LinkedList** class in Java is a part of the Collection framework and implements the **List** interface. Unlike an `ArrayList`, which uses a **dynamic array** to store elements, a `LinkedList` stores its elements as **nodes** in a **doubly linked list**. This provides different performance characteristics and usage scenarios compared to an `ArrayList`.

## 🔗 Structure of LinkedList
A `LinkedList` is a linear data structure where each element is stored in a separate **node**. Each node contains two parts:
- **🗃 Data**: The actual value stored in the node.
- **🔗 Pointers**: Two pointers:
  - `next` → Points to the next node.
  - `previous` → Points to the previous node.

## ⚖️ Performance Considerations
- **📌 Insertions and Deletions**: `LinkedList` is more efficient for frequent **insertions** and **deletions** in the middle of the list since it does **not** require shifting elements, unlike `ArrayList`.

- **📌 Random Access**: `LinkedList` has slower random access (`get(int index)`) compared to `ArrayList` because it **traverses the list** from the beginning to reach the desired index.

- **📌 Memory Overhead**: `LinkedList` requires more memory than `ArrayList` because each node stores **extra references** (pointers to next and previous nodes).

---
## 🖥 Code Implementation

```java
import java.util.*;

public class LinkedListExample {
    public static void main(String[] args) {
        // Creating a LinkedList of Integers
        LinkedList<Integer> linkedList = new LinkedList<>();
        linkedList.add(1); // [1]
        linkedList.add(2); // [1, 2]
        linkedList.add(3); // [1, 2, 3]
        
        // Get element at index 2 (O(n) complexity)
        System.out.println(linkedList.get(2)); // Output: 3
        
        // Adding elements at different positions
        linkedList.addLast(4);  // [1, 2, 3, 4] (O(1) operation)
        linkedList.addFirst(0); // [0, 1, 2, 3, 4] (O(1) operation)
        
        // Getting the first element (O(1))
        System.out.println(linkedList.getFirst()); // Output: 0
        
        // Printing the LinkedList
        System.out.println(linkedList); // Output: [0, 1, 2, 3, 4]

        // Removing even numbers using removeIf
        linkedList.removeIf(x -> x % 2 == 0);
        System.out.println(linkedList); // Output: [1, 3]

        // Creating a LinkedList of Strings
        LinkedList<String> animals = new LinkedList<>(Arrays.asList("Cat", "Dog", "Elephant"));

        // Creating another LinkedList containing elements to be removed
        LinkedList<String> animalsToRemove = new LinkedList<>(Arrays.asList("Dog", "Lion"));

        // Removing matching elements
        animals.removeAll(animalsToRemove);
        System.out.println(animals); // Output: [Cat, Elephant]
    }
}
```

---
## 📖 Explanation of Operations

### 🟢 Adding Elements
- `linkedList.add(1); linkedList.add(2); linkedList.add(3);`
  - Adds elements **1, 2, 3** to the LinkedList.
  - The **add()** method appends elements to the **end** of the list.

### 🔍 Getting an Element
- `linkedList.get(2);`
  - Retrieves the element at **index 2**.
  - Since `LinkedList` doesn't support direct indexing like arrays, it **traverses the list** from the start (O(n) complexity).

### 🔼 Adding Elements at Specific Positions
- `linkedList.addLast(4);`
  - Appends **4** at the **end** of the LinkedList (O(1) operation).
- `linkedList.addFirst(0);`
  - Inserts **0** at the **beginning** of the LinkedList (O(1) operation).

### 🔽 Retrieving the First Element
- `linkedList.getFirst();`
  - Returns the **first** element of the LinkedList (O(1) operation).

### 📝 Removing Elements Based on Condition
- `linkedList.removeIf(x -> x % 2 == 0);`
  - Removes all **even** numbers from the LinkedList.
  - Uses a **lambda expression** to filter elements dynamically.

### 🐾 Removing Elements from Another Collection
- `animals.removeAll(animalsToRemove);`
  - Removes all occurrences of the elements present in `animalsToRemove` from `animals`.
  - The final `animals` list contains only `Cat` and `Elephant` because `Dog` was removed, and `Lion` was not in the list.

---
## 🎯 Summary
- **`LinkedList` is ideal for frequent insertions and deletions.**
- **Slower random access (`get(int index)`) compared to `ArrayList`.**
- **Higher memory usage due to node pointers.**

This was a detailed explanation of **LinkedList** in Java. 🚀 Stay tuned for more! 🎯
