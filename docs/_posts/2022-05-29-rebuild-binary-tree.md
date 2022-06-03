---
layout: post
title: "Rebuild Binary Tree"
date:  2022-05-29 10:11:53 +0800
categories: Leetcode
---

这是《剑指Offer》的第七题 -- “重建二叉树”的做题思路。

题目：
> 输入某二叉树的前序遍历和中序遍历的结果，请重建该二叉树。假设输入的前序遍历和
中序遍历结果都不含重复的数字。

思路：

前序遍历的顺序为“根 -> 左 -> 右”，所以前序遍历序列的第一个节点一定是根节点。又
因为中序遍历的顺序为“左 -> 根 -> 右”，左子树和右子树是被根节点分开的。现在
我们有了根节点，所以只要遍历中序遍历序列，并找到根节点的位置，那么它前面的元素
就是左子树的元素，它后面的元素就是右子树的元素。接下来，我们可以分别对左、右子树
用这个策略**递归**完成整个二叉树的建造。

这是我在 Leetcode 的[提交记录](https://leetcode.cn/problems/zhong-jian-er-cha-shu-lcof/submissions/)。

以上。