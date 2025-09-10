#  Singly Linked List : Find the Middle Node of a Singly Linked List Using Recursion

This Python program demonstrates how to find the middle node of a singly linked list using recursion. The program calculates the middle element by utilizing two pointers, with one pointer moving one step at a time (slow) and the other moving two steps at a time (fast). When the fast pointer reaches the end of the list, the slow pointer will be at the middle node.

##  Aim

To write a Python program that:
- Creates a singly linked list.
- Uses recursion to find the middle node of the list.
- In case of an even number of nodes, it returns the second middle element.

##  Algorithm

1. **Node Class**: 
   - Define a `Node` class to represent each node in the singly linked list. Each node has two attributes: `data` and `next`.
   
2. **LinkedList Class**:
   - Define a `LinkedList` class that manages the linked list with methods to:
     - `append(data)`: Add a new node to the end of the list.
     - `get_middle_recursive(slow, fast)`: A recursive helper function to find the middle node using two pointers (slow and fast).
     - `find_middle()`: A method to call the recursive function and return the middle node's data.

3. **Input**:
   - First, the program reads an integer `n`, representing the number of elements in the linked list.
   - Then, it reads `n` space-separated integers to form the linked list.

4. **Recursive Middle Finding**:
   - The `get_middle_recursive` method uses two pointers to traverse the list:
     - The `slow` pointer moves one step at a time.
     - The `fast` pointer moves two steps at a time.
   - When the `fast` pointer reaches the end, the `slow` pointer will be at the middle node.

5. **Output**:
   - The program prints the middle element. If the list has an even number of nodes, it returns the second middle element.

---

##  Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        
class LinkedList:
    def __init__(self):
        self.head = None
        
    def traverse_list(self):
        if self.head is None:
            print("List has no element")
            return
        else:
            n = self.head
            while n is not None:
                print(n.data , " ")
                n = n.next
    
    def insert_at_start(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head= new_node
        
    def insert_at_end(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            return
        n = self.head
        while n.next is not None:
            n= n.next
        n.next = new_node
        
    def insert_at_position (self, position, data):
        if position == 1:
            new_node = Node(data)
            new_node.next = self.head
            self.head = new_node
        i = 1
        n = self.head
        while i < position-1 and n is not None:
            n = n.next
            i = i+1
        if n is None:
            print("Index out of bound")
        else: 
            new_node = Node(data)
            new_node.next = n.next
            n.next = new_node
        

new_linked_list = LinkedList()
new_linked_list.insert_at_end(25)
new_linked_list.insert_at_end(35)
new_linked_list.insert_at_end(45)
print("After inserting elements at the end")
new_linked_list.traverse_list()

new_linked_list.insert_at_start(15)
print("After inserting elements at the beginning")
new_linked_list.traverse_list()

new_linked_list.insert_at_position(2,40)
print("Inserting elements at the specific position")
new_linked_list.traverse_list()

```

## Sample Input & Output
<img width="869" height="473" alt="image" src="https://github.com/user-attachments/assets/3e9a0d1b-7610-4618-a4c8-fb3937cd3274" />

## Result
The Program was executed successfully


