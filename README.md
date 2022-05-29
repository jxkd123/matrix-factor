# matrix-factor

https://github.com/google-research/google-research/tree/master/tabnet

一个完整的多因子量化项目, 包括：串起数据、因子筛选&合成、回测等诸多细节，成为下一步更实战的量化投资做准备。
https://github.com/piginzoo/mfm_learner/blob/169537b84c2add70bd4ef52e997bfea7f48b685e/example

MultiFactorModel

https://github.com/MingkaiLee/MultiFactorModel

数据预处理及因子计算 ：从规模、估值、成长、盈利、技术等维度筛选出十几个具有长期稳定选股能力的因子，进行缺失值、去极值、标准化、市值和行业中性化处理。
收益预测模型 ：我们最后要优化的目标函数中的预期收益通过因子IR加权法计算获得，各因子权重值为各因子在滚动时间内平均IR值在所有因子在滚动时间内平均IR值之和中的占比，因子在滚动时间内平均IR值越大，说明该因子在选股时作用越大，权重也越大，反之亦然。

https://github.com/algo21-221040012/Assignment1/blob/master/factor.csv

ICRank IR

1.什么是IC/IR？

IC：信息系数（Information Coefficient，简称 IC），代表因子预测股票收益的能力。IC的计算方法是：计算全部股票在调仓周期期初排名和调仓周期期末收益排名的线性相关度（Correlation）。IC越大的因子，选股能力就越强。

IR：信息比率（Information Ratio,简称IR）= IC的多周期均值/IC的标准方差，代表因子获取稳定Alpha的能力。整个回测时段由多个调仓周期组成，每一个周期都会计算出一个不同的IC值，IR等于多个调仓周期的IC均值除以这些IC的标准方差。所以IR兼顾了因子的选股能力（由IC代表）和因子选股能力的稳定性（由IC的标准方差的倒数代表）。

IC最大值为1，表示该因子选股100%准确，对应的是排名分最高的股票，选出来的股票在下个调仓周期中，涨幅最大；相反，如果IC值为-1，则代表排名分最高的股票，在下个调仓周期中，跌幅最大，是一个完全反向的指标。

实际上，反向的指标也是非常有意义的。最无用的IC值是0或者接近0的值，这代表该因子对于股票没有任何的预测能力。当IC的绝对值大于0.05时，因子的选股能力较强，当IR大于0.5时因子稳定获取超额收益能力较强。

2.如何获取因子的IC/IR

