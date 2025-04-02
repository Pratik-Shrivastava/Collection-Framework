# 📜 ArrayList in Java

An **ArrayList** is a resizable array implementation of the **List** interface. 
Unlike **arrays** in Java, which have a **fixed size**, an `ArrayList` can dynamically **change its size** as elements are added or removed.
This flexibility makes it a popular choice when the number of elements in a list **isn’t known in advance**.

## ⚙️ Internal Working of ArrayList

- Unlike a regular array, which has a **fixed size**, an `ArrayList` can **grow and shrink** dynamically.
- This dynamic resizing is achieved by creating a **new array** when the current array is **full** and copying the elements to the new array.
- Internally, the `ArrayList` is implemented as an **array of Object references**.
- When we create an `ArrayList`, it has an **initial capacity** (default is **10**). The **capacity** refers to the size of the internal array before needing to resize.

## 🔼 Adding Elements to an ArrayList

1️⃣ **Check Capacity**: Before adding a new element, `ArrayList` checks if there is enough space in the internal array (`elementData`).

2️⃣ **Resize if Necessary**: If the internal array is full, `ArrayList` creates a **new array** with a larger capacity (usually **1.5 times** the current size) and copies the elements.

3️⃣ **Add the Element**: The new element is stored at the **appropriate index**, and the **size** is incremented.

## 🔽 Removing Elements from an ArrayList

1️⃣ **Check Bounds**: The `ArrayList` first checks if the **index is valid**.

2️⃣ **Remove the Element**: The element is removed, and all elements **to the right** shift one position **to the left**.

3️⃣ **Reduce Size**: The **size** is decremented by **1**.

---

## 🖥️ Code Implementation

```java
import java.util.*;

public class ArrayListExample {
    public static void main(String[] args) {
        //  Creating a resizable ArrayList
        List<Integer> dynamicList = new ArrayList<>();
        dynamicList.add(1); // Adds 1 to the list → [1]
        dynamicList.set(0, 2); // Updates index 0 to 2 → [2]

        //  Creating a fixed-size list from an array
        Integer[] array = {1, 2, 3};
        List<Integer> fixedSizeList = Arrays.asList(array); // [1, 2, 3]
        fixedSizeList.set(0, 9); // Updates first element to 9 → [9, 2, 3]
        // fixedSizeList.add(4); // ❌ Throws UnsupportedOperationException

        //  Creating an immutable list (Java 9+)
        List<Integer> immutableList = List.of(1, 2, 3); // [1, 2, 3]
        // immutableList.add(4); // ❌ Throws UnsupportedOperationException
    }
}
```

---

## 🔄 ArrayList Operations

### 1️⃣ Get Operation
```java
List<Integer> numbers = new ArrayList<>(List.of(1, 2, 3, 4, 5));

// Accessing elements using index
System.out.println(numbers.get(0)); // Prints first element

// Iterating using a for loop
for (int i = 0; i < numbers.size(); i++) {
    System.out.println(numbers.get(i));
}

// Iterating using an enhanced for loop
for (int num : numbers) {
    System.out.println(num);
}
```

### 2️⃣ Modify Operation
```java
numbers.set(0, 9); // Updates first element to 9 → [9, 2, 3, 4, 5]
```

### 3️⃣ Remove Operation
```java
//  Removing an element by index
numbers.remove(1);  // Removes element at index 1 → [9, 3, 4, 5]

//  Removing an element by value
numbers.remove(Integer.valueOf(3)); // Removes 3 from the list → [9, 4, 5]
```

### 4️⃣ Element Check Operation
```java
boolean containsNine = numbers.contains(9); // ✅ Returns true as 9 is in the list
```

### 5️⃣ Converting to an Array
```java
Integer[] numArray = numbers.toArray(new Integer[0]);
//  Using 0 allows Java to determine the correct array size automatically
```

### 6️⃣ Sorting
```java
Collections.sort(numbers);     // 🔼 Sorts in ascending order
numbers.sort(null);           // 🔼 Sorts in ascending order (default)

numbers.sort((a, b) -> Integer.compare(b, a)); // 🔽 Sorts in descending order
```

---

🚀 **This was a detailed explanation of ArrayList in Java! Stay tuned for more!** 🎯