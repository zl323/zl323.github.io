---
layout: post
title:  "Binary Tree"
date:   2020-05-22
tags: BinaryTree Tree
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

Full Binary Tree vs. Complete Binary Tree vs. Balanced Binary Tree
- Full Binary Tree: A binary tree is ***FULL*** if every node is either a leaf node or else it is an internal node with two non-empty children. e.g. Huffman Coding Tree.
- Complete Binary Tree: A binary tree is ***COMPLETE*** in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible. e.g. max/min heap. You can find  [heap](/_posts/2020-05-16-Heap-Sort.md) article here. Noted that ***A complete tree must be a balanced tree***.
- Balanced Binary Tree: A binary tree is considered ***BALANCED*** in which the depth of the left and right subtrees of every node differ by 1 or less.

<details>
<summary>Can you draw them?</summary>
<p>
</p>
</details>

Binary Tree Traversal(recursively)
- Preorder: root, left, right
- Inorder: left, root, right
- Postorder: left, right, root

Here are the pseudocode for 3 different binary tree traversals:

{% highlight java linenos %}
preOrder(root):
  if root is empty: return;

  print(root.val);
  preOrder(root.left);
  preOrder(root.right);

inOrder(root):
  if root is empty: return;

  inOrder(root.left);
  print(root.val);
  inOrder(root.right);

postOrder(root):
  if root is empty: return;
  
  postOrder(root.left);
  postOrder(root.right);
  print(root.val);
{% endhighlight %}

Expression Tree

A Expression Tree is used to represent a mathematical expression. ***Internal nodes*** of the expression tree are operators in the expression, with subtrees being the sub-expressions that are its operand. All ***leaf nodes*** are operands.
 
Here is an example of Expression Tree:

<figure>
    <img src="https://zl323.github.io/assets/postImg/expressionTree.jpg" alt="useful image" height="50%" width="50%">
    <figcaption>Expression Tree</figcaption>
</figure>

> By applying inOrder, preOrder, postOrder, we can have
> 
> Infix Expression: (a+(b$\times$c))+(d$\times$(e+f))
> 
> Postfix Expression: abc*+def+*+
>
> Prefix Expression: ++a$\times$bc$\times$d+ef

Pseudocode for constructing Expression Tree:

We consider a postfix expression as an input for constructing an expression tree.

{% highlight java linenos %}
CONSTRUCT_EXPRESSION_TREE(postfix)
  initialize a stack
  for i = 0 to postfix.length
    if(postfix[i] is an operand)
      Create a node and push it onto a stack
    else: // if it is an operator
      Pop two nodes T1, T2 from the stack and form a tree with the operator as root, T1 and T2 as left and right child
      Push the tree onto the stack
  return stack.pop()
{% endhighlight %}

A small summary on how to solve binary tree problems.

<figure>
    <img src="https://zl323.github.io/assets/postImg/二叉树的解法.jpg" alt="useful image" height="80%" width="80%">
    <figcaption>Expression Tree</figcaption>
</figure>