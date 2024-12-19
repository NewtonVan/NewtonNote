* [ClickHouse 中最重要的表引擎：MergeTree 的深度原理解析 - 古明地盆 - 博客园 (cnblogs.com)](https://www.cnblogs.com/traditional/p/15218743.html)
	* 如何分区，如何借助稀疏索引快速查找，利用skip idx剪枝
	* 如何Merge不同区间，对应id如何更新
	* 压缩，但是压缩这里说的不是很好
* [ClickHouse及其MergeTree引擎 | Random walk to my blog (liangyaopei.github.io)](https://liangyaopei.github.io/2021/01/09/clickhouse-essentials/)
	* 很好的图例讲解
* [干货高能！ClickHouse性能优化，看这一篇就够了 - Michael的笔记本 (junxworks.cn)](https://blog.junxworks.cn/articles/2024/05/11/1715396614044.html#toc_h3_14)
	* 优化概述：Merge Tree，激进的剪枝