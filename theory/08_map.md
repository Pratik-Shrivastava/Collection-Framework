# 🛤️ Java Map

## 📌 Introduction
A `Map` in Java is a **key-value pair** data structure that **does not allow duplicate keys**.  
Each key maps to **at most one value**, making it similar to a **dictionary**.

> 🚨 Unlike other collection classes, `Map` does **not** extend the `Collection` interface.

---

## 🔑 Key Characteristics of the Map Interface
✔ **Key-Value Pairs**: Each entry consists of a **unique key** and a **corresponding value**.  
✔ **Unique Keys**: No two entries can have the same **key**.  
✔ **One Value per Key**: Each key **maps to only one value**.  
✔ **Ordering**:
   - 🗂️ `LinkedHashMap` maintains **insertion order**.
   - 🌲 `TreeMap` maintains **natural order**.
   - 🎮 `HashMap` does **not** maintain any order.

---

## 🔥 Key Characteristics of HashMap
✔ **Unordered**: Elements are **not stored in any particular order**.  
✔ **Allows `null` Keys & Values**: One `null` key and multiple `null` values are allowed.  
✔ **Not Thread-Safe**: Needs **external synchronization** for multi-threaded use.  
✔ **Performance**: `O(1)` for `get()` and `put()` (on average, with a good hash function).

---

## 🚀 Example Code
```java
HashMap<Integer, String> map = new HashMap<>();
map.put(31, "Shubham");
map.put(11, "Akshit");
map.put(2, "Mehul");
System.out.println(map);

String student = map.get(31);
System.out.println(student);

String s = map.get(69);
System.out.println(s);

System.out.println(map.containsValue("Shubham"));
for (int i : map.keySet()) {
    System.out.println(map.get(i));
}
Set<Map.Entry<Integer, String>> entries = map.entrySet();
```

### 📌 Explanation
- **`map.put(key, value)`** → Adds key-value pairs.
- **`map.get(key)`** → Retrieves the value of the given key.
- **`map.containsValue(value)`** → Checks if a value exists.
- **`map.keySet()`** → Returns all keys.
- **`map.entrySet()`** → Returns all key-value pairs.

---

## 🏰️ Basic Components of HashMap
✔ **Key** → The unique identifier used to retrieve values.  
✔ **Value** → The data stored in the map.  
✔ **Bucket** → Storage location for key-value pairs.  
✔ **Hash Function** → Converts a key into an index for storage.

### 🎯 Properties of a Hash Function
- ✅ **Deterministic** → Same input gives the same output.  
- ✅ **Fixed Output Size** → Consistent size regardless of input.  
- ✅ **Efficient** → Fast computation.  

---

## 🏡 How Data is Stored in HashMap
### 📊 Steps:
1⃣ The **key** is hashed to generate a **hash code**.  
2⃣ The **index** is computed using:  
   ```java
   int index = hashCode % arraySize;
   ```
3⃣ The **key-value pair** is stored in the **computed index**.

```java
map.put("apple", 50);
// "apple" is hashed, index is computed, and ("apple", 50) is stored.
```

---

## 🔄 How HashMap Retrieves Data
1⃣ The **key is hashed** to generate a **hash code**.  
2⃣ The **index** is calculated.  
3⃣ The **bucket** is searched for the key-value pair.  

---

## ⚔️ Handling Collisions
When two keys generate the **same index**, Java uses:
- **Linked List** (before Java 8).
- **Balanced Tree (Red-Black Tree)** (Java 8+ for better performance).

### Example:
```java
map.put("apple", 50);
map.put("banana", 30);
map.put("orange", 80);
```
If `"apple"` and `"orange"` share the same bucket, they form a **linked list**:
```
Bucket 5: ("apple", 50) -> ("orange", 80)
```

---

## 📏 HashMap Resizing (Rehashing)
✔ **Default Size**: `16`  
✔ **Load Factor**: `0.75`  
✔ **Threshold for Resizing**: `size > capacity × load factor`  

### 🔄 Rehashing Process:
1⃣ **Capacity doubles** (from 16 → 32).  
2⃣ **All entries are rehashed** into new buckets.

---

## ⏳ Time Complexity
| Operation           | Average-Case 🏆 | Worst-Case 😨 | Explanation |
|--------------------|----------------|--------------|-------------|
| `put(key, value)` | O(1)            | O(log n)     | Inserts key-value pair. O(log n) if bucket becomes a tree. |
| `get(key)`        | O(1)            | O(log n)     | Retrieves value. O(log n) for tree-based buckets. |
| `remove(key)`     | O(1)            | O(log n)     | Removes key-value pair. |
| `containsKey()`   | O(1)            | O(log n)     | Checks if a key exists. |
| `containsValue()` | O(n)            | O(n)         | Checks if a value exists. |
| `size()`          | O(1)            | O(1)         | Returns the number of elements. |

---

## 🍏 Example: Storing Fruit Quantities
| 🍎 Fruit  | 📦 Quantity |
|---------|------------|
| Apple   | 50        |
| Banana  | 30        |
| Orange  | 80        |
| Grape   | 20        |

```java
HashMap<String, Integer> fruitMap = new HashMap<>();
fruitMap.put("Apple", 50);
fruitMap.put("Banana", 30);
fruitMap.put("Orange", 80);
fruitMap.put("Grape", 20);
```

---

## 🎡 Summary
✔ `HashMap` provides **O(1) access time** on average.  
✔ **Handles collisions** using **linked lists** or **red-black trees** (Java 8+).  
✔ **Not thread-safe** → Use `ConcurrentHashMap` for multi-threading.  
✔ **Uses hashing** for efficient storage.  

---

🚀 **Now you understand HashMap in Java like a pro!** 🏆🎯
