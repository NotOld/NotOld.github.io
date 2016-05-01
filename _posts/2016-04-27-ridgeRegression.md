---
layout: post
title: "岭回归（Ridge regression）学习"
description: "POD方法确实又叫做主成分分析方法（Principal Component Analysis;PCA），以前我接触到了PCA方法，两者的数学本质（SVD）是一模一样的，都是对协方差矩阵进行分析，得到最大的Variance的信息（方向，幅值），但是应用的对象还是有些不同，这里主要是讲讲这些不同..."
category: '学习'
---

# 岭回归（Ridge regression）学习
根据coursera上面的课程为依据。

1. 初衷： 就是为了解决Overfitting的问题，对传统的最小二乘的方法中的系数约束下？

3. 效果展示
<img src="http://i4.piimg.com/323c574d1239190c.jpg">
示例性质，原始列化的流场，分别是五个时刻的测量值。
<img src="http://i4.piimg.com/8eaf7865e0ac7b41.jpg">
这是五个列化的流场基

### 结论
1. POD 就是PCA，也就是SVD，当然中间存在的推导过程网上很多，就不再累赘的叙述。
2. POD 的基有两个特点。a)越靠前，这个基capture的能量越多，这个性质可以用到数据降维操作中；b)越靠前，这个基就越光滑，这个结论和FFT的结论类似，该结论可以用到数据光滑操作上面，同时也可以应用到去噪去坏点等问题中。
3. 原始的POD有几个问题。a)随着时间推演，流动模态在发生变化，用恒定的基去描述虽然可以达到整体最优，但是还不能随着时间自适应的去调整基的选择。b)原始的POD和PCA都是需要完整数据的参与，gappy POD的出现也就是为了解决数据存在残缺的情况。c）PCA/POD解决的都是线性空间的问题，对于问题本身是非线性的可能存在不足

## 致谢
[1]. [Kernel PCA 原理和演示](http://zhanxw.com/blog/2011/02/kernel-pca-%E5%8E%9F%E7%90%86%E5%92%8C%E6%BC%94%E7%A4%BA/)
[2]: [主成分分析PCA](http://www.cnblogs.com/zhangchaoyang/articles/2222048.html)
[3]: [主成分分析 PCA算法](http://blog.sina.com.cn/s/blog_59d470310100j7f1.html)




