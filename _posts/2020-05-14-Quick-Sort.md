---
layout: post
title:  "Quick Sort"
date:   2020-05-14
tags: Sorting
mathjax: true
---

Similar to Merge Sort, Quick Sort applies method of Divide and Conquer as well. Let's take a look at the pseudo code for Quick Sort.

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