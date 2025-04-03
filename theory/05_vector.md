# 📜 Vector in Java

A **Vector** in Java is a part of the `java.util` package and is one of the legacy
classes in Java that implements the **List** interface.  
It was introduced in **JDK 1.0** before the collection framework and is **synchronized**, making it **thread-safe**.
Now it is a part of the **collection framework**.

However, due to its **synchronization overhead**, it's generally recommended
to use other modern alternatives like **ArrayList** in single-threaded scenarios.  
Despite this, **Vector** is still useful in certain situations, particularly in **multi-threaded environments** where thread safety is a concern.

---

## 🔑 Key Features of Vector

- **Dynamic Array**: Like `ArrayList`, `Vector` is a **dynamic array** that grows automatically when more elements are added than its current capacity.

- **Synchronized**: All the methods in `Vector` are **synchronized**, which makes it **thread-safe**. However, this can introduce **performance overhead** in single-threaded environments.
- **Legacy Class**: `Vector` was part of Java's **original release** and is considered a **legacy class**. It's recommended to use `ArrayList` in single-threaded environments.
- **Resizing Mechanism**: When the current **capacity** of the `Vector` is exceeded, it **doubles** its size by default (or increases by a specific capacity increment if provided).
- **Random Access**: Similar to `ArrayList`, `Vector` allows **random access** to elements, making it **efficient for retrieval**.

---

## 🏗 Constructors of Vector

### 1️⃣ Default Constructor
```java
Vector<Integer> vector1 = new Vector<>(); // Creates a vector with an initial capacity of 10
```

### 2️⃣ Constructor with Initial Capacity
```java
Vector<String> vector2 = new Vector<>(20); // Creates a vector with an initial capacity of 20
```

### 3️⃣ Constructor with Initial Capacity and Capacity Increment
```java
Vector<Double> vector3 = new Vector<>(10, 5); // Increases capacity by 5 when needed
```

### 4️⃣ Constructor with Collection
```java
List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
Vector<Integer> vector4 = new Vector<>(list); // Initializes vector with elements from list
```

---

## 🛠 Methods in Vector

### 1️⃣ Adding Elements
```java
Vector<Integer> numbers = new Vector<>();
numbers.add(10); // Adds element at the end
numbers.add(20);
numbers.add(30);
numbers.add(1, 15); // Inserts 15 at index 1
System.out.println(numbers); // Output: [10, 15, 20, 30]
```

### 2️⃣ Retrieving Elements
```java
int element = numbers.get(2); // Gets the element at index 2
System.out.println(element); // Output: 20
```

### 3️⃣ Modifying Elements
```java
numbers.set(2, 25); // Replaces the element at index 2
System.out.println(numbers); // Output: [10, 15, 25, 30]
```

### 4️⃣ Removing Elements
```java
numbers.remove(1); // Removes element at index 1
numbers.remove(Integer.valueOf(25)); // Removes the element with value 25
System.out.println(numbers); // Output: [10, 30]
```

### 5️⃣ Checking Size and Emptiness
```java
System.out.println(numbers.size()); // Output: 2
System.out.println(numbers.isEmpty()); // Output: false
```

### 6️⃣ Checking for an Element
```java
System.out.println(numbers.contains(10)); // Output: true
System.out.println(numbers.contains(50)); // Output: false
```

### 7️⃣ Clearing the Vector
```java
numbers.clear(); // Removes all elements from the vector
System.out.println(numbers); // Output: []
```

---

## 🏛 Internal Implementation of Vector

- Internally, `Vector` **uses an array** to store its elements.
- The **size of this array grows** as needed when more elements are added.
- The **default behavior** is to **double the size** of the array when it runs out of space.
- This **resizing operation** is costly, as it requires copying old elements to a new, larger array.

---

## 🔄 Synchronization and Performance

- Since **Vector methods are synchronized**, only **one thread can access** the vector at a time.
- This makes `Vector` **thread-safe**, but it introduces **performance overhead** in single-threaded environments due to **locking and unlocking costs**.
- In modern Java applications, **`ArrayList`** is generally **preferred over `Vector`** when synchronization isn't required.
- For **thread-safe collections**, alternatives like **`CopyOnWriteArrayList`** or **`ConcurrentHashMap`** from `java.util.concurrent` are recommended.

---

## 📌 Summary

✔ `Vector` is a **legacy synchronized** collection class that implements the `List` interface.  
✔ It behaves like a **dynamic array** and grows as needed.  
✔ It provides **thread safety** but at a **performance cost** in single-threaded environments.  
✔ In modern applications, **`ArrayList`** or **concurrent alternatives** like `CopyOnWriteArrayList` are preferred unless **thread safety** is required.  

---

🚀 **That's everything you need to know about `Vector` in Java!** 🎯
