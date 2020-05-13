---
layout: post
title:  "Merge Sort"
date:   2020-05-13
tags: Sorting
mathjax: true
---
The image below shows how the merge sort operates at each level. 
<img src="https://zl323.github.io/assets/postImg/mergeSort1.png" alt="useful image" height="70%" width="70%">

At each level of the tree, the size of input is split into half. The size of input will continue splitting until the size of input becomes 1. This splitting process will occur in $O(logn)$ times.

At each level of the tree, MERGE operation will be performed. The MERGE operation will have cost of $O(n)$ since we need to compare each element from the left and right half, and put them into a single array. Here is the pseudocode for MERGE_SORT recursive method.