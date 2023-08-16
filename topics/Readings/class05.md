# class 05 reading: Big O and Linked Lists .
# Big O Notation: Analyzing Algorithm Efficiency

Big O notation is a tool used to assess the efficiency of algorithms or functions based on two main factors:

- *Running Time (Time Complexity):* The duration an algorithm takes to execute.
- *Memory Space (Space Complexity):* The memory resources utilized by an algorithm to store data and instructions.

## Key Points:

### Overview:
Big O is employed to determine the worst-case efficiency of an algorithm. It focuses on Running Time and Memory Space. Four key areas are considered for analysis:

1. *Input Size:* Refers to the scale of parameter values an algorithm processes. It incorporates the number of elements in arrays or lists, impacting Running Time and Memory Space.

2. *Units of Measurement:* Three time measurements are used to quantify Running Time: elapsed time in milliseconds, the number of operations executed, and the count of basic operations, which are usually the most time-consuming within inner loops. Memory Space is gauged through four sources of memory usage during runtime.

3. *Orders of Growth:* Efficiency is described using the input size 'n' and evaluating the Units of Space and Time required for that 'n'. As 'n' increases, Order of Growth demonstrates how Running Time or Memory Space escalates.

4. *Asymptotic Notations:* These notations characterize different cases of algorithm complexity. Big O (upper bound) denotes worst-case efficiency, Big Omega (lower bound) reflects the best case, and Big Theta (tight bound) represents the average or typical case.

### Worst Case, Best Case, Average Case:
These cases offer insights into algorithm behavior for different inputs: worst case for the most challenging input, best case for the easiest input, and average case for typical inputs.

In summary, Big O notation evaluates algorithm efficiency by considering both Running Time and Memory Space. It helps analyze how algorithms perform across varying input sizes, distinguishing between different types of complexity growth. While Big O is the most commonly used notation, Big Omega and Big Theta provide additional insights into best and average cases, respectively.

---

# Linked Lists

A *Linked List* is a data structure made up of *nodes* that are connected to each other. Each node contains some data and a reference to the next node in the sequence. There are two types of Linked Lists: *Singly Linked Lists* (each node points to the next node) and *Doubly Linked Lists* (each node points to both the next and previous nodes).

## Terminology:

- *Linked List:* A collection of nodes connected through references.
- *Node:* An individual item in the list, containing data and a reference to the next node.
- *Head:* The first node in the list.
- *Current:* The currently focused node when traversing the list.
- *Next:* A reference in each node pointing to the next node.
- *Singly:* Each node has a reference to the next node.
- *Doubly:* Each node has references to both the next and previous nodes.

## Traversal:
Traversal means moving through the nodes of a linked list. You can't use a loop, so you rely on the "next" reference in each node. Use a while loop to check if the current node is not null, then move to the next node until you reach the end.

## Includes:
An example of traversal is searching for a value in the linked list. You start from the Head and keep moving to the Next node until you find the value or reach the end. If you find the value, return true; otherwise, return false.

## Adding a Node:
Adding a node to the beginning of a singly linked list is efficient (O(1)). You create a new node, set its Next to the current Head, and update the Head to point to the new node.

## Adding a Node in the Middle:
Adding a node to the middle of a linked list involves traversing until you find the desired position. You adjust the references of the nodes before and after the new node to include it.

## Printing Nodes:
You can print all the nodes in a linked list by traversing through them and outputting their values. Start from the Head, move through the nodes using the Next references, and print their values until you reach the end.

## Comparison with Arrays:
Linked lists and arrays both store data, but linked lists are more dynamic in memory usage, while arrays need contiguous memory. Linked lists are great for insertion and deletion at any point, but arrays are faster for random access.
