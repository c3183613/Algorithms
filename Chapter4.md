# Searching
Searching on unsorted lists often degenerates to a brute-force search until we
find our desired result. When searching in a sorted this, we can find our *key*
much quicker.
## Notes
### Binary search
If the binary tree has an odd amount of element; when split, the second half
will have one more element. Assuming that the list is in a non-increasing
order... the following function will return the index of `key` if it is found,
or -1 otherwise.
`[0, 1, ... i, j, ..., n]`
```"c++"
int binarySearch(int[] list, int i, int j, int key)
{
    while(i<=j)
    {
        k = (i+k)/2;
        if(key == list[k])
            return k;   // found key
        else if(key > list[k])
            i = k+1;    // search second half
        else
            j = k-1;    // search first half
    }
    return -1;          // if reach this line, key not found
}
```
### Depth first search
Must have some way of keep track if each node has been visited. Depth first
search is recursive in nature. Select a starting node, mark as visited. Select
an adjacent node to visit, if it has been marked as visited, select another
adjacent node to visit. If no more adjacent nodes can be visited by this node,
return and allow parent nodes to marking and visiting their child nodes.
```
dfs_recursive(adj_list, start)
{

}
```
### Breadth first search
Use boolean vector or hash map to mark nodes as visited. Also use a queue used
to keep track of which node is to be explored next.  
At root, mark all child nodes in vector/mash map as visited & add to queue for
methodical traversing. Next node in the queue is used to perform the same
operation.
