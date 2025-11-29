# Singly Linked List Simulation Project

## 📌 Project Objective

To visually demonstrate how a **Singly Linked List** works internally by simulating:
- Node creation with memory addresses
- Pointer updates and manipulation
- Insertion operations (beginning, middle, end)
- Deletion operations (beginning, middle, end)
- Traversal with memory visualization
- Search with step-by-step comparison

This simulation reveals the **actual internal behavior** of Linked Lists, not just output.

---

## 🚀 Features

### Interactive Web-Based GUI
- **Visual node representation** with simulated memory addresses
- **Real-time animations** showing pointer updates
- **Step-by-step operation logging** with detailed explanations
- **Interactive controls** for all operations
- **Modern, beautiful UI** with dark theme and smooth transitions

### C++ CLI Implementation
- **Menu-driven interface** for easy operation
- **Detailed console output** showing internal working
- **Memory address visualization** using actual pointers
- **Step-by-step explanations** for each operation
- **Comprehensive comments** explaining the logic

---

## 📂 Project Structure

```
LinkedList-Simulation/
├── index.html              # Web-based GUI (main page)
├── styles.css              # Styling with modern design
├── script.js               # JavaScript logic and animations
├── main.cpp                # C++ implementation
├── README.md               # This file
├── memory_diagrams.txt     # ASCII diagrams of operations
└── outputs_screenshots/    # Screenshots of execution
```

---

## 🎯 Operations Demonstrated

### 1. **Insert at Beginning** - O(1)
```
Before:  head → [2000|10|NULL]
After:   head → [1500|20|→2000] → [2000|10|NULL]
```

### 2. **Insert at End** - O(n)
```
Traverse to last node, then:
temp→next = newNode
```

### 3. **Insert at Position** - O(n)
```
Traverse to position-1, then:
newNode→next = temp→next
temp→next = newNode
```

### 4. **Delete First** - O(1)
```
temp = head
head = head→next
free(temp)
```

### 5. **Delete Last** - O(n)
```
Traverse to second-to-last node, then:
free(temp→next)
temp→next = NULL
```

### 6. **Delete at Position** - O(n)
```
Traverse to position-1, then:
temp→next = temp→next→next
free(nodeToDelete)
```

### 7. **Search** - O(n)
```
Traverse and compare each node's data
```

### 8. **Traverse** - O(n)
```
Visit each node and display:
[Address | Data | Next]
```

---

## 💻 How to Run

### Web-Based GUI Version
1. Open `index.html` in any modern web browser
2. Use the control panel to perform operations
3. Watch the visual animations and operation logs

### C++ CLI Version
1. **Compile:**
   ```bash
   g++ main.cpp -o linkedlist
   ```

2. **Run:**
   ```bash
   ./linkedlist
   ```
   (On Windows: `linkedlist.exe`)

3. **Use the menu** to select operations

---

## 📊 Time Complexity Analysis

| Operation | Time Complexity | Space Complexity |
|-----------|----------------|------------------|
| Insert at Beginning | O(1) | O(1) |
| Insert at End | O(n) | O(1) |
| Insert at Position | O(n) | O(1) |
| Delete First | O(1) | O(1) |
| Delete Last | O(n) | O(1) |
| Delete at Position | O(n) | O(1) |
| Search | O(n) | O(1) |
| Traverse | O(n) | O(1) |

**Note:** n = number of nodes in the list

---

## 🎨 Sample Output (C++ Version)

```
╔════════════════════════════════════════════════════════════╗
║   SINGLY LINKED LIST - INTERNAL WORKING SIMULATION        ║
║   Demonstrates memory addresses and pointer operations    ║
╚════════════════════════════════════════════════════════════╝

┌────────────────────────────────────────────────────────┐
│                    MAIN MENU                           │
├────────────────────────────────────────────────────────┤
│  1. Insert at Beginning                                │
│  2. Insert at End                                      │
│  3. Insert at Position                                 │
│  4. Delete First Node                                  │
│  5. Delete Last Node                                   │
│  6. Delete at Position                                 │
│  7. Search for Value                                   │
│  8. Traverse List                                      │
│  9. Display List (Simple)                              │
│  0. Exit                                               │
└────────────────────────────────────────────────────────┘

Current Size: 0

Enter your choice: 1
Enter value to insert: 20

======================================================================
OPERATION: Insert at Beginning (Value: 20)
======================================================================

[Step 1] Creating new node...
New Node Details:
  Address: 0x7ffd5c8e4a20
  Data: 20
  Next: 0

[Step 2] List is empty.
  Setting head = newNode (0x7ffd5c8e4a20)

✓ Insert at beginning completed!
  New size: 1
  New head: 0x7ffd5c8e4a20
```

---

## 🔍 Internal Working Explanation

### 1. **Dynamic Memory Allocation**
- Nodes are created in **heap memory** using `new` (C++) or `new Node()` (JavaScript)
- Each node has a unique memory address
- Memory is freed using `delete` when nodes are removed

### 2. **Pointer Linking Logic**
```
Insert at Beginning:
1. Create newNode
2. newNode→next = head
3. head = newNode

Delete First:
1. temp = head
2. head = head→next
3. free(temp)
```

### 3. **Traversal Logic**
```cpp
temp = head
while (temp != NULL) {
    // Process temp
    temp = temp→next
}
```

### 4. **Memory Management**
- Proper deallocation prevents **memory leaks**
- Updating pointers before deletion prevents **dangling pointers**
- NULL checks prevent **segmentation faults**

---

## 📈 Flowchart

```
START
  ↓
Display Menu
  ↓
Get User Choice
  ↓
┌─────────────────────────────────────┐
│ Choice?                             │
├─────────────────────────────────────┤
│ Insert → Create Node → Update       │
│          Pointers → Display         │
│                                     │
│ Delete → Find Node → Update         │
│          Pointers → Free Memory     │
│                                     │
│ Search → Traverse → Compare →       │
│          Return Position            │
│                                     │
│ Traverse → Visit Each Node →        │
│            Display Details          │
│                                     │
│ Exit → Clean Up → END               │
└─────────────────────────────────────┘
```

---

## 🎓 Learning Outcomes

After using this simulation, you will understand:
1. How linked lists store data in non-contiguous memory
2. How pointers connect nodes together
3. Why some operations are O(1) and others are O(n)
4. The importance of proper memory management
5. How to implement linked list operations from scratch

---

## 🌟 Advantages of Linked Lists

- **Dynamic size** - grows and shrinks as needed
- **Efficient insertion/deletion** at beginning - O(1)
- **No memory waste** - allocates exactly what's needed
- **Easy to implement** stacks and queues

## ⚠️ Disadvantages

- **No random access** - must traverse from head
- **Extra memory** for storing pointers
- **Cache unfriendly** - nodes scattered in memory

---

## 📝 Author

**[Your Name]**  
**Date:** [Current Date]  
**Course:** Data Structures and Algorithms

---

## 📄 License

This project is created for educational purposes.

---

## 🙏 Acknowledgments

- Inspired by the need to visualize data structure internals
- Built with modern web technologies and C++
- Designed for clarity and educational value
