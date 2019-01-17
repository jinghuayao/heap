### Priority Heap

Priority Heap can be represented by list or complete binary tree. The list respresentation is a level order traversal of the complete tree representation. We shall only discuss min heap as max heap can be obtained from min heap by using the opposite numbers of the comparison values in the min heap.

A heap is a complete binary tree for which every parent node has a value less than or equal to any of its children. If we count elements from 0, the requirement is that heap[k] <= heap[2*k + 1] and heap[k] <= heap[2*k + 2] for all 0 <= k < len(heap)//2.

The implementation we use is that in Python3 (see the heapq module https://docs.python.org/3/library/heapq.html#heapq.heapify).

1. Create a heap: (1) use an empty list: h = list(); (2) heapify a populated list: heapq.heapify(h) here h is an non-empty list. heapify
transform h into a heap, in-place, in linear time. 

2. heapq.heappush(h, item): push the item into h, maintaining the heap invariance.

3. heapq.heappop(h): pop and return the smallest item from h if h is not empty, i.e., h[0] in the current implementation, and maintain the heap invariance, otherwise, raise the error type: IndexError.

4. heapq.heappushpop(h, item): first push item into the heap, and then pop and return the smallest element from the heap.

5. heapq.heapreplace(h, item): first pop and return the smallest element from the heap, and then push the item into the heap. In action, it is equivalent to heapq.pop(h) + heapq.push(h, item), but is faster the combination.

Three general purpose functions:

1. heapq.merge(*iterables, key=None, reverse=False): merge multiple sorted inputs into a single sorted output, and return an iterator over the sorted values.

2. heapq.nlargest(n, iterable, key=None): return a list with the n largest elements from the dataset defined by iterable according to the one-variable function key.

3. heapq.nsmallest(n, iterable, key=None): return a list with the n smallest elements from the dataset defined by iterable.

If the number of requested elements n is small, heapq.nlargest() and heapq.nsmallest() perform efficiently. If n is large, using sorted() and slicing is more efficient; In the extreme case n == 1, use max() or min(). 
