---
layout: post
title: Binary Tree Level Order Traversal
category: Data Structure and Algorithms
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/13/Binary-Tree-Level-Order-Traversal/
---

Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

**Example 1** : Input: root = [3,9,20,null,null,15,7]

Output: [[3],[9,20],[15,7]].

**Example 2** : Input: root = [1]

Output: [[1]].

**Intuition** : To get the Level Order Traversal of any binary tree we first need to understand what does level means? In this question we have to print out each node of any given binary tree into a particular level. In Example 1 we can see that 3 will be at 0 index or level 1, 9 aand 20 will be the left and right child of 3 at level 2 and 9 does not have any children(because of null in the given array) so at level 3 only the children of 20 are present, i.e. 15 and 7.

So to print level order we need to have Queue data structure and try to work accordingly, now working with the given BT in example 1, we will put the root of BT, i.e 3 and then pop it out of the queue, and if the left child of the root node exist we will add it onto the queue data structure else we will add the right child, if both exist then add both nodes (9, 20). Now since we have popped out of the root, we can store it into some list data structure or inside a vector(C++), to show that our first level traversal has been completed and we can move into another level. 


**Step 2** : Now, we can keep on checking the elements present inside the queue data structure and work on it like we have worked on the root node and print the list of elements/nodes present at that level.

**Code in C++ and Python**

```C++:
    class Solution {
    public:
        vector<vector<int>> levelOrder(TreeNode* root) {
            
            vector<vector<int>> ans;
            if(root == NULL) return ans;
            queue<TreeNode*> q;
        q.push(root);
        
        //stop when all the nodes have been visited
        while(!q.empty()){
            //calculate the amount of nodes in this layer
            int s=q.size();
            //store the value of nodes in this layer
            vector<int> temp;
            //stop when all the nodes in this layer have been visited
            while(s--){
            TreeNode* n=q.front();
            q.pop();
            //store the current node first
            temp.push_back(n->val);
            //push its left child into the queue if exists
            //left child is prior to right child because the level order traversal is from left to right
            if(n->left)
                q.push(n->left);
            //push its right child into the queue if exists
            if(n->right)
                q.push(n->right);
            }
            //store the result of this layer
            ans.push_back(temp);
            temp.clear();
        }
        return ans;
        }
};

```


```Python:
        class Solution:
        def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
            if not root:
                return []
            ans = []
            q = deque()
            q.append(root)
            while q:
                curr_level = []
                for _ in range(len(q)):
                    curr_node = q.popleft()
                    curr_level.append(curr_node.val)
                    if curr_node.left:
                        q.append(curr_node.left)
                    if curr_node.right:
                        q.append(curr_node.right)
                ans.append(curr_level)
            return ans

```


**Time and Space Complexity** : TC - O(N) and SC - O(N)