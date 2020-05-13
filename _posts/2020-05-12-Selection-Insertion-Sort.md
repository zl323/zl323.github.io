---
layout: post
title:  "Selection/Insertion Sort"
date:   2020-05-12
tags: Sorting
mathjax: true
---

PseudoCode Algorithm for Selection Sort

{% highlight java linenos %}
SELECTION_SORT(A):
for i = 0 to n-2
  minIdx = i;
  for j = i+1 to n-1
    if(A[j] < A[i]) minIdx = j;
  swap(A, minIdx, i);
{% endhighlight %}
Above is the pseudocode.

Selection Sort has a time complexity of $O(n^2)$. Since Selection Sort is an ***in-place*** operation, the space complexity is $O(1)$.

PseudoCode Algorithm for Insertion Sort
{% highlight java linenos %}
INSERTION_SORT(A):
for i = 1 to n-1
  key = A[i]
  i = j-1
  while i>0 and A[i]>key
    A[i+1] = A[i] // shift right
    i--
  A[i+1] = key    // swap
{% endhighlight %}

Insertion Sort has two cases to consider:
- Best Case: If the array is sorted in ASCENDING order, then the time complexity is $O(n)$.
- Worst Case: If the array is sorted in DESCENDING order, then the time complexity is $O(n^2)$.

Since Insertion Sort is an ***in-place*** operation, the space complexity is $O(1)$.