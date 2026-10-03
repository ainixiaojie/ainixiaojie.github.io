---
title: Backtracking
index_img: /img/index_img/index_img2.jpg
banner_img: /img/post_banner.jpg
date: 2023-07-28 20:08:35
categories: 算法
tags: Backtracking algorithm
---

# 回溯算法（Backtracking algorithm）

通过迭代的方式在解空间中寻找符合条件的解
寻找符合条件的组合，排列

解空间，要清楚的构造自己的解空间
树的形状，去搜索解

终止条件与剪枝函数
剪枝函数：在递归寻找符合条件的解的过程中，遇到中间过程就不符合条件的，就终止当前，不在继续往下寻找，直接返回
终止条件：寻找的解，形式上符合结果的形式了，是不是最终的解，还需要多加一重判断。终止条件就是解形式符合结果就行。

剪枝函数放置在哪里呢？
放在for循环里面更好还是在终止条件里面更好？

放在循环里面可以更快的终止不符合条件的解
但是放在终止条件，有清晰明了的结构

所以自己判断。在处理节点这里处理

```
vector<vector<int>> res;
vector<int> tem;

void backtracking(参数) {
    if (终止条件) {
        存放结果;
        return;
    }

    for (选择：本层集合中元素（树中节点孩子的数量就是集合的大小）) {
        处理节点;
        backtracking(路径，选择列表); // 递归
        回溯，撤销处理结果
    }
}
```

