---
layout: post
title:  "Merge Sort"
date:   2020-05-13
tags: Sorting
mathjax: true
---
The image below shows how the merge sort operates at each level. 
<figure>
    <img src="https://zl323.github.io/assets/postImg/mergeSort1.png" alt="useful image" height="70%" width="70%">
    <figcaption>Credit. Introduction to Algorithm by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein</figcaption>
</figure>
At each level of the tree, the size of input is split into half. The size of input will continue splitting until the size of input becomes 1. This splitting process will occur $O(logn)$ times.

At each level of the tree, MERGE operation will be performed. The MERGE operation will have cost of $O(n)$ since we need to compare each element from the left and right half, and put them into a single array. Thus, the overall time complexity of merge sort is $O(nlogn)$.

Here is the pseudocode for MERGE_SORT recursive method.

{% highlight java linenos %}
// recursive method
// A: input; ACopy: copy of input; left: left index; right: right index
MERGE_SORT(A, ACopy, left, right):
  // base case: left >= right, return
  if(left < right)
    mid = left + (right - left)/2       // get mid index
    MERGE_SORT(A, ACopy, left, mid)     // MERGE_SORT left part
    MERGE_SORT(A, ACopy, mid+1, right)  // MERGE_SORT right part
    MERGE(A, ACopy, left, mid, right)   // MERGE two parts
{% endhighlight %}

Here is the pseudocode for MERGE method.
{% highlight java linenos %}
// ACopy consists of 2 half SORTED arrays.
// We want to overwrite the original array A
MERGE(A, ACopy, left, mid, right):
  // initialize left and right pointers
  LPtr = left           
  RPtr = mid + 1
  // compare, overwrite, and move pointers
  while LPtr < mid && RPtr < right
    if(ACopy[LPtr] < ACopy[RPtr]) 
      A[left++] = ACopy[LPtr++]
    else 
      A[left++] = ACopy[RPtr++]
  // post processing on LPtr
  while(LPtr < mid) A[left++] = ACopy[LPtr++]
  // Question, why we don't need to worry RPtr?
{% endhighlight %}

We can also analyze the runtime with the method of Master Theorem.

\\[
T(n) =
  \begin{cases}
    O(1) &\text{if } n=1\\\\\\\\
    2T(n/2)+O(n) &\text{if } n>1
  \end{cases}
\\]
With this method, we can also get the runtime of this sorting algorithm $O(nlogn)$.

Noted that the ***space complexity*** of merge sort is $O(n)$ due to using a copy of input array $ACopy$, seen in pseudocode.

Merge Sort applies ***Divide and Conquer*** technique into the algorithm:
- ***Divide***: Compute midPoint index to split the array into half. This costs constant time, $O(1)$.
- ***Conquer***: Recursively find subproblem with size of n/2 from left and right halves. This costs time. $2T(n/2)$
- ***Merge***: Merge two sorted parts into one array in ascending order. This costs linear time, $O(n)$

<details>
<summary>Detailed Implementation of Merge Sort in Java</summary>

{% highlight java linenos %}
// recursive method
// A: input; ACopy: copy of input; left: left index; right: right index
MERGE_SORT(A, ACopy, left, right):
  // base case: left >= right, return
  if(left < right)
    mid = left + (right - left)/2       // get mid index
    MERGE_SORT(A, ACopy, left, mid)     // MERGE_SORT left part
    MERGE_SORT(A, ACopy, mid+1, right)  // MERGE_SORT right part
    MERGE(A, ACopy, left, mid, right)   // MERGE two parts
{% endhighlight %}

</details>


***Think: Why do we prefer splitting into half for MERGE_SORT?***
<details>
<summary>answer</summary>

</details>