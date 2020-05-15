---
layout: post
title:  "Quick Sort"
date:   2020-05-14
tags: Sorting
mathjax: true
---

Similar to Merge Sort, Quick Sort applies method of Divide and Conquer as well. Let's first take a look at the pseudo code for Quick Sort.

{% highlight java linenos %}
// recursive method
// A: input; left: left index; right: right index
QUICK_SORT(A, left, right):
  // base case: left >= right, return
  if(left < right)
    pivot = PARTITION(A, left, right)   // get pivot index
    QUICK_SORT(A, left, pivot-1)        // QUICK_SORT left part
    QUICK_SORT(A, pivot+1, right)       // QUICK_SORT right part
{% endhighlight %}

The key of this algorithm is the ***PARTITION*** method.

{% highlight java linenos %}
PARTITION(A, left, right):
  // choose right index as the pivot index by default
  pivot = A[right]
  l = left
  r = right - 1
  // left and right pointers move towards center
  while l <= r
    if(A[l] < pivot) l++
    else if(A[r] >= pivot) r--
    else swap(A, l++, r--)
  // swap pivot value with the left pointer
  swap(A, right, l);
  return l
{% endhighlight %}

Merge Sort applies ***Divide and Conquer*** technique into the algorithm:
- ***Divide*** : Define a pivot *q*, the array is split into left array A[*left*, *q-1*] and right array A[*q+1*, *right*]
- ***Conquer*** : Recursively sort subproblem with left and right arrays.
- ***Combine*** : Since Quick Sort is an in-place algorithm, Combine operation is not necessary. Array itself is already ordered.

Now let's discuss a bit why the ***PARTITION*** method plays an important role in Quick Sort. The performance of Quick Sort depends on how we choose the pivot. What is the reason?

- Best case: If every time the chosen pivot happens to be the median of elements in the array, then the array can be perfectly split in half. We call this case the split is balanced. The overall runtime will be the same as Merge Sort, which is $O(nlogn)$.
- Worse cases: 1. Array is already sorted.
               2. Every time