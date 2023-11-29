# RBO
关于cbo的概括性介绍参考[Rule-based Query Optimization | Querify Labs](https://www.querifylabs.com/blog/rule-based-query-optimization)，重点在于引入**Rule**，即pattern和对应的transformation。

# Optimizer in Calcite
- [Apache Calcite 优化器详解（二） | Matt's Blog (matt33.com)](https://matt33.com/2019/03/17/apache-calcite-planner/)中给出了相关例子和Calcite优化器设计结构。
- [Calcite 启发式 Planner (HepPlanner) - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/61661909)给出了一个HepProgram的life cycle
- [深入理解 Calcite HepPlanner 优化器原理 - 端小强的博客 (strongduanmu.com)](https://strongduanmu.com/blog/deep-understand-of-calcite-hep-planner/)中对于代码逐行解释，可惜图裂了，而且感觉解释想chatgpt搞的

`RelOptRuleOperand`用于匹配的过程，operands匹配后才会执行transformation。此外，rule还有一个matches方法用来承担自己的side condition（其他条件约束）。