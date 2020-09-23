# Trees

## Basic Operation and Definition

creation complexity: O(1)  
adding a node: O(1)  
deleting a tree: O(1)  
removing a node: O(height)  

complete binary tree: every level is full, except for the last one.

balanced tree: every node, the height of the two subtrees don't differ by more than 1.

## Walking The Trees

**Depth-first** we go down first, visiting the whole subtree of the child of a node before the visiting the subtree of the other child.  
**Breadth-first** we visit the nodes by level:first the root, then its children, then their children, etc.  



### Depth-first  

**Pre-order** we perform the action when we enter the node for the first time, before visiting the children.  根左右
**In-order** we perform the action when we enter the node for the second time, between visiting the left and right children. 左根右
**Post-order** we perform the action when we enter the node for the third and last time, after visiting both children.  左右根

use recursive to travel
use stack(LIFO) to keep some information(i.e. how many times we visited a node)
O(n)

### Breadth-first

need a data structure to hold the information of which nodes we need to visit in the future.
queue(FIFO) each node is only visited once.  
