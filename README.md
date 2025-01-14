# Linked List

## Overview
This is a C++ implementation of a singly linked list data structure. The linked list is a dynamic collection of nodes, where each node contains a value and a pointer to the next node in the list.

## Features
* Insertion and deletion of nodes at the beginning, end, and at specific positions in the list
* Searching for nodes by value
* Traversal of the list in forward direction
* Reversing the list
* Finding the length of the list
* Finding the Kth node from the end

## Usage
To use the linked list, simply include the `richu_LinkedList.h` header file in your C++ program and create an instance of the `LinkedList` class.
```
#include "LinkedList.h"

int main() {
    LinkedList<int> mylist;

    // Insert nodes at the end of the list
    mylist.insert(1);
    mylist.insert(2);
    mylist.insert(3);

    // print the list
    mylist.print();

    // delete the first node
    mylist.removeFirst();

    //print the list again
    mylist.print();

    return 0;
}
```
Here is a link to download the header file: https://downgit.github.io/#/home?url=https://github.com/Richu911/Linked-List/blob/main/richu_LinkedList.h

## API
### Member Functions
* `addFirst()`: Inserts a new node with the given value at the beginning of the list
* `addLast()`: Inserts a new node with the given value at the end of the list
* `removeFirst()`: Deletes the node at the beginning of the list, i.e., the head of the list
* `removeLast()`: Deletes the node at the end of the list
* `removeFirst()`: Deletes the node at the beginning of the list
* `indexOf()`: prints and returns the value at the given index. If value is not found returns -1.
* `print()`: prints the Linked list in square brackets
* `length()`: prints and returns the length of the list
* `reverseList()`: reverses the list
* `KthNodeFromEnd()`: prints and returns Kth node from end

## Building and Testing
To build and test the LinkedList class, use the following commands:
```
g++ -o richu_LinkedList.exe richu_LinkedList.h
richu_LinkedList.h
```
This will compile the LinkedList class and run a simple test program.

## License
This code is released under the MIT License. See the LICENSE file for details.

## Acknowledgements
This Linked list is a modification of the linked list implementation on Paul Programming youtube channel.
