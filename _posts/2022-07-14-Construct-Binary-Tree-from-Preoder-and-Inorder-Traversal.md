---
layout: post
title: Construct Binary Tree from Preorder and Inorder Traversal
category: Data Structure and Algorithms
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/14/Construct-Binary-Tree-from-Preorder-and-Inorder-Traversal/
---

Given two integer arrays preorder and inorder where preorder is the preorder traversal of a binary tree and inorder is the inorder traversal of the same tree, construct and return the binary tree.

**Example 1** Input: preorder = [3,9,20,15,7], inorder = [9,3,15,20,7]

Output: [3,9,20,null,null,15,7]

**Example 2** Input: preorder = [-1], inorder = [-1]

Output: [-1]

**Intuition** : We know that Inorder Traversal -> Left Root Right

Preorder Traversal -> Root Left Right.

So looking at Example 1 preorder = [3,9,20,15,7], inorder = [9,3,15,20,7]

Root will be 3 and looking at the Inorder 9 will be the left child of the root(3), and 15,20,7 will be the right children of 3.
Then looking at this we can try to Recursive solution to create the remaining tree.

By that logic the right subtree will have 20 as root, 15 as the left child and 7 as the right child. and since left subtree has no value, it will give us the desired output.


**Code**
```C++:
TreeNode* constructTree(int i,int j,int &ind,vector<int> &preorder,vector<int> &inorder,unordered_map<int,int> &mp)
    {
        if(i>j)
        {
            return NULL;
        }
        int rootVal=preorder[ind];
        ind+=1;

        TreeNode *root=new TreeNode(rootVal);
        
        int in=mp[rootVal];
        root->left=constructTree(i,in-1,ind,preorder,inorder,mp);
        root->right=constructTree(in+1,j,ind,preorder,inorder,mp);
        return root;
    }
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
     
        unordered_map<int,int> mp;
        
        for(int i=0;i<inorder.size();i++)
        {
            mp[inorder[i]]=i;
        }
        int ind=0;
        return constructTree(0,preorder.size()-1,ind,preorder,inorder,mp);
        
        
    }
```

```python:
class Solution:
    def buildTree(self, preorder, inorder):
        if not preorder or not inorder:
            return None
        root = TreeNode(preorder[0])
        mid = inorder.index(preorder[0])
        root.left = self.buildTree(preorder[1:mid+1], inorder[:mid])
        root.right = self.buildTree(preorder[mid+1:], inorder[mid+1:])
        return root

```

**Time and Space Complexity** TC- O(N) and SC- O(N)