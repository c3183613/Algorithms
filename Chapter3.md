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
## Linked Lists
Provides constant time in worst case for accessing, inserting and deleting.
`top()` - returns the most recently added element  
### Adjacency list representation  
|   Node|   Connected to nodes...|
| ---   |   ---     |
|   1   |   3,4,5   |
2 | 4,5
3 | 1,5
4 | 1,2
5 | 1,2,3
