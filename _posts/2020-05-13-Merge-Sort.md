---
layout: post
title:  "Merge Sort"
date:   2020-05-13
tags: Sorting
mathjax: true
---
The image below shows how the merge sort operates at each level. 
<img src="https://zl323.github.io/assets/postImg/mergeSort1.png" alt="useful image" height="50%" width="50%">

At each level of the tree, the size of input is split into half. The size of input will continue splitting until the size of input becomes 1. This splitting process will occur in $O(log_n)$ times.