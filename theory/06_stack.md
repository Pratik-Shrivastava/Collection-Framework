## Stack in Java

Since **Stack** extends `Vector`, it is **synchronized**, making it **thread-safe**.

### 📌 Key Characteristics

- **LIFO Structure**: Stack follows the **Last-In-First-Out (LIFO)** principle, where the last element added is the first one to be removed.
- **Inheritance**: Stack is a subclass of `Vector`, meaning it inherits all the features of a **dynamic array** but is constrained by the stack's LIFO nature.

---

## 🖥 Stack Implementation

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        // Creating a stack
        Stack<Integer> stack = new Stack<>();
        
        // Pushing elements onto the stack
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);
        
        // Printing the stack
        System.out.println("Stack: " + stack);
        
        // Popping the top element (removing last added element)
        Integer removedElement = stack.pop();
        System.out.println("Removed Element: " + removedElement);
        System.out.println("Stack after pop: " + stack);
        
        // Peeking (viewing the top element without removing it)
        Integer peek = stack.peek();
        System.out.println("Top Element: " + peek);
        
        // Checking if stack is empty
        System.out.println("Is Stack Empty? " + stack.isEmpty());
        
        // Checking the size of the stack
        System.out.println("Stack Size: " + stack.size());
    }
}
```

---

## 🔄 Using LinkedList as a Stack

```java
import java.util.LinkedList;

public class LinkedListStackExample {
    public static void main(String[] args) {
        // Creating a LinkedList to use as a stack
        LinkedList<Integer> linkedList = new LinkedList<>();
        
        // Pushing elements (adding at the end)
        linkedList.addLast(1);
        linkedList.addLast(2);
        linkedList.addLast(3);
        
        // Peeking (viewing the last element without removing it)
        System.out.println("Top Element: " + linkedList.getLast());
        
        // Popping (removing last element)
        linkedList.removeLast();
        System.out.println("Stack after pop: " + linkedList);
        
        // Getting the size of the stack
        System.out.println("Stack Size: " + linkedList.size());
    }
}
```

This demonstrates how `Stack` and `LinkedList` can both be used for **stack operations**, but `LinkedList` offers **more flexibility** and is part of the **Deque** interface. 🚀