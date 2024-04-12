## Stock Price Forecasting by a Deep Convolutional Generative Adversarial Network

> **Autoregressive integrated moving average**
>
> 

> **Long short-term memory**
>
> 

> Deep Convolutional Generative Adversarial Network
>
> 

> Financial Times Stock Exchange Milano Indice di Borsa
>
> 米兰股票指数

> Generative adversarial network
>
> 

大概是这几个步骤：
1. 使用 TimeSeriesSplit 这是sklearn库的一个工具，主要是用于时间序列数据的交叉验证，按时间顺序分割数据集为训练集和测试集 对数据进行抽样，分离出train/test data 
2. 使用Gradient Boosting Regression训练一个回归预测模型，RMSE作为loss function
Gradient Boosting Regression训练模型的过程，要计算rmse来计算损失，特征筛选的过程也要做一下，特征太多的话要用pca降维
3. 从模型中获取feature importance列表，把importance极低的特征删除或者使用多项式等方法融合
4. 机器学习模型的性能可能不够，试下其他的模型，像是线性回归，逻辑回归决策树这些，这些模型相对计算见到那并且易于解释
5. 假如特征维度过大，考虑特征进行适当的PCA降维，以提升模型训练速度
6. 将“原始数据输入→用于训练特征组输出”这一过程封装成函数，以供后续的实时预测使用