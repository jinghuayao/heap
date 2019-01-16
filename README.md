### Priority Heap

Priority Heap can be represented by a list or complete binary tree. The list respresentation is a level order traversal of the complete tree representation. We shall only discuss min heap as max heap can be obtained from min heap by using the opposite numbers of the comparison values in the min heap.

A heap is a complete binary tree for which every parent node has a value less than or equal to any of its children. If we count elements from 0, the requirement is that heap[k] <= heap[2*k + 1] and heap[k] <= heap[2*k + 2] for all 0 <= k < len(heap)//2.
