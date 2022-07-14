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

**Approach for C++**
- Create a map to store the inorder indexes.
- Call the function constructTree with all 7 parameters as shown above.
- In the recursive function, first check the base case, if (preStart,>preEnd || inStart> inEnd) then return NULL.
- Construct a node (say root) with the root value( first element of preorder). 
- Find the index of the root, say elem from the hashmap.
- Find the number of elements ( say nElem) in the left subtree  = elem – inStart
- Call recursively for the left subtree with correct values (shown in the above table) and store the answer received in root->left.
- Call recursively for the right subtree with correct values (shown in the above table) and store the answer received in root->right.
- Return root


**Code**
```C++:
TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder){
    map<int, int> inMap;
    for(int i =0; i < inorder.size(); i++){
        inMap[inorder[i]] = i;
    }
    TreeNode* root = buildTree(preorder, 0, preorder.size()-1, inorder, 0, inorder.size()-1, inMap);

    return root;
}
TreeNode* buildTree(vector<int>& preorder, int preStart, int preEnd, vector<int>& inorder, int inStart, int inEnd, map<int, int> inMap){
    if(preStart > preEnd || inStart > inEnd) return NULL;
    TreeNode* root = new TreeNode(preorder[preStart]);

    int inRoot = inMap(root->val);
    int numLeft = inRoot - inStart;
    root->left = buildTree(preorder, preStart+1, preStart + numsLeft, inorder, inStart, inRoot-1, inMap);
    root->right = buildTree(preorder, preStart+numsLeft+1, preEnd, inorder, inRoot+1, inEnd, inMap);

    return root;
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