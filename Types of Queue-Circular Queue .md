# 🔄 Types of Queue-Circular Queue in Python

This project demonstrates the implementation of a **Circular Queue** in Python. The queue accepts 3 user values, performs enqueue and dequeue operations, and displays the removed values.

---

## 🎯 Aim

To develop a Python program that implements a Circular Queue:
- Accepts 3 values from the user
- Removes the 3 values from the queue
- Displays the removed values

---

## 🧠 Algorithm

1. **Initialize** a circular queue of fixed size (e.g., 5).
2. **Define the following functions**:
   - `enqueue()`: Inserts an element into the queue.
   - `dequeue()`: Removes an element from the queue.
   - `display()`: Shows the queue contents.
3. Accept 3 values from the user using the `enqueue()` method.
4. Remove 3 values using the `dequeue()` method.
5. Print the removed values.

---

## 💻 Program:
```
class CircularQueue:
    def __init__(self, size=5):
        self.size = size
        self.queue = [None] * size
        self.front = -1
        self.rear = -1
    
    def is_full(self):
        return (self.rear + 1) % self.size == self.front
    
    def is_empty(self):
        return self.front == -1
    
    def enqueue(self, data):
        if self.is_full():
            print("Queue is full. Cannot enqueue", data)
            return False
        if self.is_empty():
            self.front = 0
        self.rear = (self.rear + 1) % self.size
        self.queue[self.rear] = data
        return True
    
    def dequeue(self):
        if self.is_empty():
            print("Queue is empty. Cannot dequeue.")
            return None
        data = self.queue[self.front]
        if self.front == self.rear:
            self.front = -1
            self.rear = -1
        else:
            self.front = (self.front + 1) % self.size
        return data
    
    def display(self):
        if self.is_empty():
            print("Queue is empty.")
            return []
        elements = []
        i = self.front
        while True:
            elements.append(self.queue[i])
            if i == self.rear:
                break
            i = (i + 1) % self.size
        return elements

cq = CircularQueue()
print("Enter 3 values to enqueue:")
for _ in range(3):
    val = input("Value: ")
    cq.enqueue(val)

print("\nRemoving 3 values from the queue:")
removed_values = []
for _ in range(3):
    removed = cq.dequeue()
    if removed is not None:
        removed_values.append(removed)

print("Removed values:", removed_values)

```
### Output:
```
Enter 3 values to enqueue:
Value: 10
Value: 20
Value: 30

Removing 3 values from the queue:
Removed values: ['10', '20', '30']
```
## Result:
Hence implementation of a Circular Queue id done.
