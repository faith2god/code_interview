---
title: 102-binary-tree-level-order-traversal
tags: 在河之洲,算法,小书匠
grammar_cjkRuby: true
---


# problem
[102-binary-tree-level-order-traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/#/description)
# solution
用两个队列
```cpp
    vector<vector<int>> levelOrder(TreeNode* root) {
        queue<TreeNode *> q1;
        vector<vector<int>> result;
        if (root == NULL)
            return result;
        q1.push(root);
        while (!q1.empty())
        {
            queue<TreeNode *> q2;
            vector<int> ret;
            while (!q1.empty())
            {
                TreeNode * cur = q1.front();
                ret.push_back(cur->val);
                q1.pop();
                if (cur->left)
                    q2.push(cur->left);
                if (cur->right)
                    q2.push(cur->right);
            }
            result.push_back(ret);
            q1 = q2;
        }
        return result;
    }

```

只用一个队列
    vector<vector<int>> levelOrder(TreeNode* root) {
        queue<TreeNode *> q1;
        vector<vector<int>> result;
        if (root == NULL)
            return result;
        q1.push(root);
        int qsize = 1;
        while (!q1.empty())
        {
            vector<int> ret;
            for (int i = 0; i < qsize; i++)
            {
                TreeNode * cur = q1.front();
                ret.push_back(cur->val);
                q1.pop();
                if (cur->left)
                    q1.push(cur->left);
                if (cur->right)
                    q1.push(cur->right);
            }
            qsize = q1.size();
            result.push_back(ret);
        }
        return result;
    }