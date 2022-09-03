---
title: "Leetcode 124 Maximum Path Sum"
date: 2022-09-04T01:07:09+08:00
tags: ["leetcode"]
---

[題目連結](https://leetcode.com/problems/binary-tree-maximum-path-sum/)

給定一棵樹上的兩個節點可以得到唯一的路徑，要找到路徑上節點總和最大的值

先把路徑其中一個端點限制在根節點上，考慮這個根節點走出去的最大總和路徑，我暫且叫它「假最大總和」，如果算出來是負的就把它當作 0。對每個節點我們可以遞迴算這個值。

注意到原本題目問的路徑沒有限制其中一個端點一定要是根節點，因此我們要對每個節點另外算一個東西：當前節點的值，加上左子樹的假最大總和，再加上右子樹的假最大總和。這算出來就會是以這個節點為最高點的最大總和路徑。我們對每個節點算好這個東西以後取最大值即可。

以下是程式碼：

```cpp
class Solution
{
private:
    int dfs(TreeNode *root, int &ret)
    {
        int left = root->left ? dfs(root->left, ret) : 0;
        int right = root->right ? dfs(root->right, ret) : 0;
        ret = max(ret, left + right + root->val);
        return max(0, root->val + max(left, right));
    }
public:
    int maxPathSum(TreeNode *root)
    {
        int ret = INT_MIN;
        dfs(root, ret);
        return ret;
    }
};
```
