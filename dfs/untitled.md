# Untitled

###  题目

![](../.gitbook/assets/tu-pian%20%286%29.png)

### 分析

* 输入：二叉树
* 输出：最小深度
* 解题思路：深搜

      初始化最小深度为一个较大的值，每次遇到叶子节点（左右子树都为NULL），判断是否小于最小深度，成立的话，则更新最小深度。

### 代码

```c
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int minDepth(TreeNode* root) {
        if(!root)
            return 0;
        else{
            int min=999999;
            getMinDepth(root,1,min);
            return min;
        }
            
    }
    void getMinDepth(TreeNode *root,int depth,int &min){
        if(!root->left&&!root->right){
            if(depth<min)
                min=depth;
        }
        else{
            if(root->left)
                getMinDepth(root->left,depth+1,min);
            if(root->right)
                getMinDepth(root->right,depth+1,min);
        }
    }
};
```

