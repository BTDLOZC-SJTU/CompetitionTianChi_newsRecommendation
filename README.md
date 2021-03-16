# CompetitionTianChi_newsRecommendation
天池大赛——新闻推荐场景下的用户行为预测挑战赛，SOLO赛，B榜排名5/5338

# 解决方案
### 召回方案
使用热度召回、改进itemCF、抽样Swing和item2vec进行多路召回，结合faiss库计算相似文章尝试解决冷启动问题，采用bayes-optimization选取最优超参数，最终每个用户召回50篇候选文章。
### 排序方案
构建用户行为和文章自身特征，根据召回结果按照1:5划分正负样本转化为CTR预估问题，采用lightGBM进行5折交叉验证，根据输出概率得到文章得分，最终HR@5达到0.27，HR@50达到0.49。
