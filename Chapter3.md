# Data Structures
## Notes
Abstract data type (ADT)    - data together with functions that operate on the
data. Type is "abstract" when how data represented/how the functions implemented
are not specified, only the behaviour is specified.
### Stack
First in, last out.  
`init()`    - Initialize stack with no items.
`empty()`   - Boolean return value which is true when the stack has no elements.
`push(push)`    - Put on top of stack
Returns false otherwise.  
`pop()`     - Removes last element added to the stack.  
`top()`     - Return most recent element added to stack.
Note that the way these functions are implemented are not specified. One such
way is to use an array or vector.
### Queues
First in, first out
`init()`    - Initialize queue with no items.
`empty()`   - Like the stack  
`enqueue(item)` - Add element to the rear
`dequeue()` - Remove least recently added element
`front()`   - Returns least recent element added but does not remove it
## Exercises
1S.
```
`---` separates each push/pop
push/pop: -3 -- empty -- 38 -- 38,88 -- 38, 88, 70 -- 38, 88
```  
2. How do abstract data types relate to classes, which are major componoent of
object oriented programming languages?  
Classes may be abstract when there is common funcionality between related
classes. It may be beneficial to extract the commonalities in to a parent class
which may then be derived or "inherited" from.

4. Write a version of *push* that checks for a full array. If the array is full,
the function simply returns false. If the array is not full, the behaviour is
the same as the original *push*, except that the function also returns true.
Assume that SIZE specifies the size of the array.
```"c++"
boolean stack::push(T element)
{
    if(num_elements_in_stack == SIZE)
        return false;
    array[num_elements_in_stack+1] = element;
    num_elements_in_stack++;
    return true;
}
```

5. Write a version of *push* that checks for a full array. If the array is
full, the function creates a new array twice the size of the old array and
copies old elements in to the new array. If the array is not full, the behaviour
is the same as the original *push*, except that the function also returns true.
Assume that SIZE specifies the size of the array.
```"c++"
void stack::push(T element)
{
    if(num_elements_in_stack == SIZE)
    {
        T[] new_array = new T[SIZE*2];
        SIZE = SIZE * 2;
        // copy over data in old array to new array
        for(int i=1; i<=num_elements_in_stack; i++)
        {
            new_array[i] = array[i];
        }
        array = new_array
    }
    array[num_elements_in_stack+1] = element;
    num_elements_in_stack++;
}
```
## Linked lists
Provides constant time in worst case for accessing, inserting and deleting.
`top()` - returns the most recently added element  
### Adjacency list representation  
**Need to insert an image here**
|   Node|   Connected to nodes...   |
|   --- |   ---                     |
|   1   |   3,4,5                   |
|   2   |   4,5                     |
|   3   |   1,5                     |
|   4   |   1,2                     |
|   5   |   1,2,3                   |

## Binary trees
### Tree traversals
Loose rule: The prefix of 'order' e.g. *pre*-order refers to when the root
should be visited. After noting that, move from left to right when dealing with
nodes and their children. Recursion may be necessary if tree is more than 2
levels deep.
**Pre-order**   - root, left child(ren), right child(ren)
**Post-order**  - left child(ren), right child(ren), root
**In-order**    - root, left child(ren), right child(ren)
## Binary search tree
Data: nodes that may be compared with >, <, or ==
Place as left child of root if element being added is less than or equal to
root.
Place as right child of root if element being added is more than or equal to
root.
## Priority queue, heaps, and heapsort
Insert item in to data structure with a priority (integer) and allows us to
delete the item in the priority queue with the highest priority. e.g. priority
queues may be used in an operating system when dealing with processes. Processes
which have been completed (highest priority) will be removed from the priority
queue.  
### Binary heap
A heap is a binary tree where each level (except for the lowest level) is full.  
**Binary minheap**  - Value of the node is lesser or equal to that of its
children
**Binary maxheap**  - Value of the node is great or equal to that of its
children, must have the ability to:  
- return the largest value
- delete a value and maintain max-heap format
- insert an abitrary value and maintain max-heap format
*Weakly sorted*     - values along a path to terminal node are in non-increasing
order. Values along the same level are in no particular order.  
A max-heap may be used to implement a priority queue as the highest priority
will always be at the root of the tree. Parent of a node (assuming the node is
not the root mode) is floor(`i`/2) where `i` is the `i`th node (root node is 1).
The left child of a node is `2*i`, and the right child is `2*i+1`
#### Deleting from a heap
When deleting the root node, the node which is bottom-most and right-most is
swapped with the deleted node. This node may be found as the last element in the
array. If this swap violates the max-heap format, swap the value with the
largest child until max-heap format is restored (*heapify*).  
Note: amt_of_nodes refers to the number of nodes in the subtree `array`
**Heapify psuedo**
O(lg(`amount_of_nodes`)) where `amount_of_nodes` is the amount of nodes in the
subtree.
```"c++"
void siftdown(int[] array, int heapify_node, int amt_of_nodes)
{
    T temp_value = v[heapify_node];
    // check for entire subtree
    while(2*heapify_node <= amt_of_nodes)
    {
        int child = 2*i;
        // if there is a right child and it's bigger than the left child,
        // move child
        if(child < amt_of_nodes && v[child + 1] > v[child])
            child = child + 1;
        // move child up if appropriate
        if(v[child] > temp_value)
            v[heapify_node] = v[child]
        else
            break;  // end while loop
        heapify_node = child;
    }
    // insert original v[heapify_node] in correct spot
    v[heapify_node] = temp;
}
```
**Delete psuedo**
O(h)
```"c++"
void heap_delete(int[] heap_array, int amt_of_nodes)
{
    // move root node to end
    v[1] = v[n]
    n = n - 1
    heapify(heap_array, 1, n); // 1 removes the root
}
```
#### Inserting to a heap
Adds to the leftmost possible branch while maintaining max-heap format. While
the newly added value is larger than its parent, swap with the parent
```"c++"
void heap_insert(int[] heap_array, int insert_value, int amt_of_nodes)
{
    heap_array[amt_of_nodes+1] = insert_value;
    current_node = amt_of_nodes = amt_of_nodes + 1;
    parent = (int) (current_node/2)
    while(parent > 1 && heap_array[current_node] > heap_array[parent])
    {
        heap_array[current_node] = heap_array[parent]
        current_node = parent
        parent = (int) (current_node/2)
    }
    heap_array[current_node] = insert_value;
}
```
#### Heapify
Turn every subtree in to a max-heap
```"c++"
heapify(int[] heap_array, int amt_of_nodes)
{
    // n/2 index of the parent of last node
    for(int i = amt_of_nodes; i>1; i--)
    {
        siftdown(heap_array, i, amt_of_nodes)
    }
}
```
### Indirect heap
**Key**: Array which holds the data. Is not modified unless the values of the
heap are to be modified.
**Into**: Value is the index in the heap structure where key[i] is found.
**Out of**: Value is the index in key where value of node is to be found in heap
structure. In a heap of size `n`, `outof[1]` holds the index of
key[index_of_biggest_value] where `index_of_biggest_value` is the index of the
biggest value in `key` and `outof[n]` holds the index of the smallest value in
`key`
### Heap sort
Create a max-heap. Swap first and last node and reduce heap size by 1 by
reducing the heap array counter. Repeat this step until heap is of size 1. Array
is now sorted.
