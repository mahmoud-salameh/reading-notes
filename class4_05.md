# Linked Lists

## What is a Linked List

__**A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.**__

__**There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.**__

## Terminology:
* Linked List - A data structure that contains nodes that links/points to the next node in the list.
* Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
* Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
* Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
* Next - Each node contains a property called Next. This property contains the reference to the next node.
* Head - The Head is a reference of type Node to the first node in a linked list.

## What does it look like

![link](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList1.PNG)

## Traversal

__**When traversing through a linked list, the Current variable will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end**__

Traversal Example :

    ALGORITHM Includes (value)
    // INPUT <-- integer value
    // OUTPUT <-- boolean

    Current <-- Head

    WHILE Current is not NULL
    IF Current.Value is equal to value
      return TRUE

    Current <-- Current.Next

    return FALSE

What exactly is happening:

1. We are first creating Current at the Head to guarantee we are starting from the beginning. (Remember that Head is always the first node in a Linked List)
2. We create a while loop. This loop will only run if the node that Current is pointing to is not null. This also means we can guarantee that we are still looking at a Node while the loop is running.
3. Once we are in the while loop, we are checking if the value of the current node is equal to the value we are looking for. Given the logic, if that condition is true, then we have found the value we were looking for, so we return true.
4. If the Current node does not contain the value we are looking for, we then must move Current to the next node that is being referenced. Again, because the condition of this while loop is to only run if we are still at a node, we can safely traverse to the next node without fear of getting a NullReferenceException.

__**Traversal Big O**__

__**The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.**__

## Adding a Node

__**Order of operations is extremely important when it comes to working with a Linked List. What I mean by this is you must be careful that all references to each link/node is properly assigned.**__

1. Here are the required steps to add a new node with an O(1) efficiency.
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList2.PNG)

2. newNode.Next by default is set to null. We want to set newNode.Next property to the same location that the Head node is pointing towards. Because Head is just a reference type, we will be assigning it to the same allocation in memory as the node it is pointing too. In this case, it’s Node1.
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList3.PNG)

### Print Out Nodes

Printing out all of the nodes in a Linked List is very similar to what we did in the Includes() method. This is because we are leveraging our Current node and a while loop to traverse through the existing linked list.
__Here is the pseudo code for a method to print out all the nodes in a linked list:__

    ALGORITHM Print()
    // INPUT <-- None
    // OUTPUT <-- string to console

    Current <-- Head

     WHILE Current is not equal to NULL
     OUTPUT <-- "{Current.Value} --> "
    Current <-- Current.Next

     OUTPUT <-- "NULL"

__**Much like in Includes, we are creating a while loop to check and make sure we are not at the end of a linked list. Right before the while loop restarts, we move Current to equal the next node in the list.**__

