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

Quick Sort applies ***Divide and Conquer*** technique into the algorithm:
- ***Divide*** : Define a pivot *q*, the array is split into left array A[ *left*, *q-1* ] and right array A[ *q+1*, *right* ]
- ***Conquer*** : Recursively sort subproblem with left and right arrays.
- ***Combine*** : Since Quick Sort is an in-place algorithm, Combine operation is not necessary. Array itself is already ordered.

Now let's discuss a bit why the ***PARTITION*** method plays an important role in Quick Sort, as the performance of Quick Sort heavily depends on how we choose the pivot. What is the reason?

Assuming that each time we pick the last element as pivot:
- Best case: If everytime the chosen pivot happens to be the median of elements in the array, then the array can be perfectly split in half. We call this case the split is balanced. The overall runtime will be the same as Merge Sort, which is $O(nlogn)$.
- Worse cases: If everytime the chosen pivot happens to be the minimum or maximum. In other words, the two subarrays will have size of 0 and n-1, respectively. The recursive expression becomes the following: 
\\[
T(n) = T(n-1) + T(0) + O(n) = T(n-1) + O(n)
\\]
And we know that this will result in runtime of $O(n^2)$. This is also because of the chosen pivot is extremely unbalanced.

How about splitting the sizes of two subarrays into ratio 9:1? Does it change the overall runtime of Quick Sort? Let's take a look at the figure below.

<figure>
    <img src="https://zl323.github.io/assets/postImg/quickSort1.png" alt="useful image" height="100%" width="100%">
    <figcaption>Credit. Introduction to Algorithm by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein</figcaption>
</figure>

As we can see above, each level still takes $O(n)$ due to method of ***PARTITION***. However, the height of tree depends on the deepest branch, which is $O(log_{\frac{10}{9}}n)$. Therefore, overall the runtime will still be $O(nlog_{\frac{10}{9}}n)$ = $O(nlogn)$ since we can apply Change of Base Formula. In fact, whatever the ratio of size of two subarrays is, as long as the ratio is constant, the runtime will always become $O(nlogn)$.

***Think: So is there anyway that we can pick the pivot each time so that the size of two subarrays are as balanced as possible?***
<details>
<summary>answer</summary>

</details>

Quick Sort is ***UNSTABLE***.