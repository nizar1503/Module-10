# Queue-Remove Two String Values from the Rear End in Python 🧵

This Python program demonstrates how to manage a list of strings and remove the last two elements (i.e., from the rear of the list).

## 🎯 Aim

To write a Python program to:
- Accept `n` string values from the user
- Remove the last two values (rear end of the list)
- Display the updated list

## 🧠 Algorithm

1. Create an empty list `q`.
2. Read an integer `n` from the user (number of strings).
3. Loop `n` times:
   - Read a string input.
   - Append it to the list `q`.
4. Remove the last element using `pop()`.
5. Remove the next last element using `pop()` again.
6. Display the updated list.

##  Program:
# 🎯 AIM: List string handling — remove last two elements and display
````
q = []
n = int(input("Enter the number of strings: "))
print("Enter the strings:")
for _ in range(n):
    s = input()
    q.append(s)
if len(q) >= 2:
    q.pop()
    q.pop()
elif len(q) == 1:
    q.pop()
print("Updated list after removing last two elements:", q)
````

### Output:
```
Enter the number of strings: 4
Enter the strings:
apple
banana
cherry
date
Updated list after removing last two elements: ['apple', 'banana']
```
## Result:
Hence removed last two elements and displayed.
