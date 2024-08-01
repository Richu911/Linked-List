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
To use the linked list, simply include the LinkedList.h header file in your C++ program and create an instance of the LinkedList class.
```
  #ifndef richu_LinkedList_H
#define richu_LinkedList_H

#include <iostream>
#include <stdexcept>

class LinkedList
    {
        private:
        
            typedef struct Node
                {
                    int value;
                    Node*next;
                }*nodePtr;

            Node*head;
            Node*curr;
            Node*temp;
            Node*delPtr;

        public:

            int count = 1;

            LinkedList()
                {
                    head = NULL;
                    curr = NULL;
                    temp = NULL;
                }
            
            void addFirst(int addValue)
                {
                    nodePtr node = new Node;
                    Node*n = node;
                    n -> value = addValue;
                    n -> next = NULL;

                    if(head != NULL)
                        {
                            count += 1;

                            curr = head;

                            while(curr -> next != NULL)
                                {
                                    curr = curr -> next;
                                }

                            curr -> next = n;
                        }
                    else
                        head = n;
                }

            void addLast(int addValue)
                {
                    nodePtr node = new Node;
                    Node*n = node;

                    if(head != NULL)
                        {
                            count += 1;

                            n -> value = addValue;

                            curr = head;
                            head = n;
                            n -> next = curr;
                        }
                    else
                        head = n;

                }

            void removeLast()
                {
                    if(head != NULL)
                        {   
                            count -= 1;

                            curr = head;

                            while(curr -> next != NULL)
                                {
                                    curr = curr -> next;
                                }
                            
                            delPtr = curr;
                            delete delPtr;
                        }
                        // O(n)
                        else
                            std::cout << "\nlist is empty\n";
                }

            void removeFirst()
                {

                    if(head != NULL)
                        {
                            count -= 1;

                            delPtr = head;
                            head = head -> next;
                            
                            delete delPtr;
                        }
                    // O(n)
                    else
                        std::cout << "\nlist is empty\n";
                }

            void indexOf(int item)
                {
                    int index = 0;
                    curr = head;

                    while(curr != NULL && curr -> value != item)
                        {
                            curr = curr -> next;
                            index += 1;
                        }
                    
                    if(curr == NULL)
                        std::cout << "\nvalue does not exist in linked list" << "\n";
                    else
                        std::cout << "\nvalue " << item << " is at index " << index << "\n";

                }

            void print()
                {
                    curr = head;

                    std::cout << "\n[";

                    if(head != NULL)
                        {
                            while(curr -> next != NULL)
                                {
                                    std::cout << curr -> value << ", ";
                                    curr = curr -> next;
                                }

                            std::cout << curr -> value;
                        }
                    
                    std::cout << "]\n";
                    // O(n)
                }

            void length()
                {
                    /* int count = 0;
                        curr = head;
                        
                        while(curr != NULL)
                            {
                                curr = curr -> next;
                                count += 1;
                            }

                        std::cout << "length is " << count << "\n";
                        O(n) */

                    std::cout << "\nlength is " << count << "\n";
                    // O(1)

                }

            void reverseList()
                {
                    if(head != NULL)
                        {
                            curr = head;
                            temp = curr;
                            head = head -> next;
                            curr -> next = NULL;
                            curr = head;

                            while(head -> next != NULL)
                                {
                                    head = head -> next;
                                    curr -> next = temp;
                                    temp = curr;
                                    curr = head;
                                }
                            
                            head -> next = temp;
                            // O(n)
                        }
                }

            int KthNodeFromEnd(int K)
                {
                    if(head != NULL)
                        {
                            if(K > 0)
                                {
                                    curr = head;
                                    temp = curr;

                                    for(int i = 0; i < K - 1; i++)
                                        {
                                            curr = curr -> next;
                                            if(curr == NULL)
                                                throw new std::invalid_argument("invalid argument");
                                        }

                                    while(curr -> next != NULL)
                                        {
                                            curr = curr -> next;
                                            temp = temp -> next;
                                        }
                                    std::cout << "\nKth value from end is " << temp -> value << "\n";
                                    return temp -> value;
                                }
                        }
                    return -1;
                }

    };

#endif // richu_LinkedList_H
```
