---
layout: post
title:  "Binary Tree & Binary Search Tree"
date:   2020-05-22
tags: BinaryTree BST Tree
mathjax: true
---

A ***binary tree*** is a tree such that every vertex has degree at most 2. Usually we consider the tree to be rooted at some ***root*** node. We define current node is the ***Parent*** node, the parent node has two ***Child*** nodes, ***Left*** and ***Right*** children nodes. Here is the data structure of a binary tree node:

{% highlight java linenos %}
class TreeNode{
    int value;      // data value of the node
    TreeNode left;  // a reference to left child, could be null
    TreeNode right; // a reference to right child, could be null
}
{% endhighlight %}

From the data structure, we can tell that it is similar to LinkedList. Actually the data structure ***LinkedList is a special case of tree***.

Some other definitions and terms:
- A binary tree may be empty, containing no nodes.
- **Internal node**: any node that has at least one non-empty child.
- **Leaf node**: any node that has two empty children.
- For a given node A, any node on a path from A up to the root is an ***ancestor*** of A.
- The ***depth*** of a node A in a tree is the length of path from the **ROOT** of the tree to **A**.
- The ***height*** of a tree is the depth of the deepest node(leaf node).
- The ***size*** of a binary tree is the number of nodes in it(including root).