---
layout: post
title:  "Selection Sort"
date:   2020-05-12
tags: Sorting
---

PseudoCode Algorithm for Selection Sort
{% highlight java %}
for i = 0 to n-2
  minIdx = i;
  for j = i+1 to n-1
    if(arr[j] < arr[i]) minIdx = j;
  swap(arr, minIdx, i);
{% endhighlight %}