# Data Structures
## Notes
Abstract data type (ADT)    - data together with functions that operate on the
data. Type is "abstract" when how data represented/how the functions implemented
are not specified, only the behaviour is specified.
### Stack
First in, last out.  
`push()`    - Put on top of stack
`empty()`   - Boolean return value which is true when the stack has no elements.
Returns false otherwise.  
`pop()`     - Removes last element added to the stack.  
`top()`     - Return most recent element added to stack.
### Queues
First in, first out
## Exercises
1S.
```
push/pop: -3 -- empty -- 38 -- 38,88 -- 38, 88, 70 -- 38, 88
```  
2. How do abstract data types relate to classes, which are major componoent of
object oriented programming languages?  
Classes may be abstract when there is common funcionality between related
classes. It may be beneficial to extract the commonalities in to a parent class
which may then be derived or "inherited" from.
