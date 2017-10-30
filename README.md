# awesome-lgb

[官方调参指南](http://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html)

[官方参数列表](http://lightgbm.readthedocs.io/en/latest/Parameters.html)

### LightGBM的亮点(很多人比较关注两个点儿，自己对系统优化也非常感兴趣)：

1.基于Histogram的决策树算法

2.带深度限制的leaf-wise的树生长策略

(ps: 为了简化码字量，统一用lgb指代LightGBM)

### 问题

1.似乎在xgb和lgb中，都没有提供针对多分类的平衡方案(只有二分类)？

### 参数理解

1. lgb的树生长算法是leaf-wise，当需要调节模型(树)复杂度时，以num\_leaves为主，max\_depth为辅。

2. 解决二分类问题的不平衡参数：‘is\_unbalance’=True。该参数将不平衡问题解决放入模型构建过程中，解放劳动力。不过对lgb如何解决不平衡问题仍然保持好奇？

scale\_pos\_weight=1.0，weight of positive class in binary classification task.

3. bagging思想的融入。bagging\_fraction和bagging\_freq同时设置，feature\_fraction。从fraction的字面意思来理解，应该是通过sampling增加多样性，避免overfitting。

4. min\_data\_in\_leaf

5. min\_sum\_hessian\_in\_leaf  
 

