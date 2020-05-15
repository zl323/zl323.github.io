---
layout: post
title:  "Counting Sort"
date:   2020-05-15
tags: Sorting
mathjax: true
---

Counting Sort has a linear runtime overall. In exchange for this linear time, the algorithm will take up extra space $O(k)$. The value $k$ here is the maximum element in the input array, since we have to create an intermediate array with size of $k$. Let's take a look at the pseudocode for counting sort:

{% highlight java linenos %}
// k: max element in the array A
COUNTING_SORT(A, k):
  let C[0..k] be a new array
  let res[0..A.length] be the output array
  // initialize array C with zeros
  for i = 0 to k
    C[i] = 0
  for j = 1 to A.length
    C[A[j]]++;
  // C[i] now contains the number of element equal to i
  for i = 1 to k
    C[i] = C[i] + C[i-1]
  // C[i] now counts the number of element less than or equal to i
  for j = A.length downto 1
    res[C[A[j]]] = A[j]
    C[A[j]]--
return res
{% endhighlight %}