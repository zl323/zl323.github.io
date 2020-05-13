---
layout: post
title:  "Selection Sort"
date:   2020-05-12
tags: Sorting
mathjax: true
---

PseudoCode Algorithm for Selection Sort

{% highlight java linenos %}
for i = 0 to n-2
  minIdx = i;
  for j = i+1 to n-1
    if(arr[j] < arr[i]) minIdx = j;
  swap(arr, minIdx, i);
{% endhighlight %}
Above is the pseudocode.

Selection Sort has a time complexity of $$O(n^2)$$. Since Selection Sort is an in-place operation, the space complexity is $O(1)$.