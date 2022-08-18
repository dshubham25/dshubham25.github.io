---
layout: post
title: Domino Piling
category: Data Structure and Algorithms
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/08/18/Domino-Piling/
---
Codeforces 50A

You are given a rectangular board of M × N squares. Also you are given an unlimited number of standard domino pieces of 2 × 1 squares. You are allowed to rotate the pieces. You are asked to place as many dominoes as possible on the board so as to meet the following conditions:

1. Each domino completely covers two squares.

2. No two dominoes overlap.

3. Each domino lies entirely inside the board. It is allowed to touch the edges of the board.

Find the maximum number of dominoes, which can be placed under these restrictions.

Input
In a single line you are given two integers M and N — board sizes in squares (1 ≤ M ≤ N ≤ 16).

Output
Output one number — the maximal number of dominoes, which can be placed.

Examples
**Input**

2 4

**Output**

4

**Input**
3 3

**Output**

4


**Intuition**

The basic idea is to floor the row and column value
(N*M)/2

```C++:
#include<bits/stdc++.h>
using namespace std;
int main(){
    ios_base::sync_with_stdio(false);
    cin.tie(0);
    int m, n;
    cin >> M >> N;
    cout << (m+n == 2 ? 0 : (m*n) / 2) << endl;
}


```

```Python:
m, n = map(int, input.split())
if m == 1 or n == 1:
    return 0
else:
    return int(m*n) // 2

```
