---
layout: post
title:  "Sorting Algorithm Summary"
date:   2020-05-19
tags: Sorting
mathjax: true
---

Here is a Table of Characteristics of Sorting Algorithm in comparison.

<style>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
</style>
| Sorting Algorithms | Worst  | Average | Stability | Space |
| ------------------ |:------:|:-------:|:---------:|------:|
| Selection Sort     |$O(n^2)$| $O(n^2)$|  unstable |$O(1)$ |
| Insertion Sort     |$O(n^2)$| $O(n^2)$|  stable   |$O(1)$ |
| Merge Sort       |$O(nlogn)$| $O(nlogn)$|  stable |$O(n)$ |
| Quick Sort       |$O(n^2)$| $O(nlogn)$| unstable  |$O(1)$ | 
| Heap Sort        |$O(nlogn)$|$O(nlogn)$| unstable |$O(1)$ |

Some Notes to Take:
- If the size of input $n \leq 50$, we choose ***Insertion Sort*** or ***Selection Sort***.
- If the input file is mostly in ascending order, we choose ***Insertion Sort***, ***Bubble Sort*** or ***Randomized QuickSort***.
- If the size of input $n$ is relatively large, we will consider the following cases:
  * If the inputs are distributed randomly, in other words, the pivots are distributed randomly, then we use ***Quick Sort***.
  * If QuickSort is not able to take the job, then we use ***Heap Sort*** as it has the same time complexity as QuickSort.
  * If the ***STABILITY*** needs to be maintained, we can use ***Insertion Sort combined with Merge Sort***. Since they are both stable algorithm, while heap sort and quick sort are unstable.