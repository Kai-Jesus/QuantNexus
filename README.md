# QuantNexus
基于图的神经网络（如 FcGAGA）来建立更复杂的因果模型： 将 ETH 和 PENDLE 作为两个时间序列节点，建立因果图（Causal Graph）。 通过门控注意力机制（Gated Attention），让模型自适应地学习 ETH 价格变化对 PENDLE 的影响权重。   边缘级任务 边缘级推理的一个例子是图像场景理解。将其表述为边缘级分类：给定表示图像中对象的节点，希望预测这些节点中的哪些共享边缘或该边缘的值是多少。如果想发现实体之间的联系，可以认为图是完全连通的，并根据它们的预测值修剪边缘以得到稀疏图。


神经网络
ETH/USDT
PENDLE/USDT

Granger Causality（历史数据预测未来是有局限的，所以主要的研究方向是让神经网络学习到币和币中间的关系变化来预测一个很短期的迟滞窗口。因为这个是一个数据规律肯定可以被预测出来的）

N-beats
FcGAGA（Granger-Gated Attention Graph Aggregator）是一种专为时间序列预测任务设计的深度学习模型，结合了Granger因果关系、图神经网络（GNN）和注意力机制（Attention），旨在高效地提取时间序列中的关键特征，并增强多变量时间序列数据中的因果推理能力。


ETH/USDT 与 PENDLE/USDT 的因果关系
在交易市场中，不同加密货币之间通常存在复杂的因果关系（Granger Causality），特别是当一种资产（如 ETH）对另一种资产（如 PENDLE）具有价格影响时，我们可以通过数据分析来验证其因果性。
ETH 价格对 PENDLE 价格的影响
PENDLE 作为 DeFi（去中心化金融）生态的一部分，与 ETH 具有较强的联动性，其价格波动可能受到 ETH 价格趋势的直接或间接影响：
（1）趋势传导效应
ETH 是 PENDLE 主要流动性对
PENDLE 主要在以太坊生态中运行，其交易对（PENDLE/USDT）的大部分流动性可能来源于 ETH/USDT，因此 ETH 的价格变动会影响整个 DeFi 生态的资金流动和市场情绪。
ETH 上涨（资金流入）推动 PENDLE
当 ETH 价格上涨时，市场投资者的风险偏好增强，DeFi 生态通常会随之受益，导致 PENDLE 价格也可能跟随上涨。
ETH 下跌（市场恐慌）抛售 PENDLE
反之，当 ETH 价格暴跌时，整个市场可能进入避险模式，导致 PENDLE 等山寨币的抛售压力增加，价格同步下跌。
（2）反转幅度与趋势影响
ETH 价格的反转点（局部底部/顶部）可能是 PENDLE 的提前或滞后信号
若 ETH 价格出现剧烈反转（例如大幅上涨后突然回调），市场资金可能会转向其他 DeFi 资产，导致 PENDLE 价格短期受影响。
若 ETH 价格持续单边趋势，则 PENDLE 可能会同步放大波动率。
ETH 作为市场风向标
PENDLE 相较于 ETH 市值更小，因此波动性更高。当 ETH 突破关键支撑/阻力位，市场情绪会迅速蔓延到 PENDLE，可能导致 PENDLE 价格放大 ETH 走势的幅度。
为了验证 ETH 价格变动是否真正影响 PENDLE，Granger 因果检验（Granger Causality Test）来量化这种关系：
使用Vector AutoRegression (VAR) 模型，设定 ETH 价格的滞后项（Lags）。
计算 Granger 因果关系 p-value：
如果 p-value 显著小于 0.05，可以认为 ETH 价格对 PENDLE 价格具有因果影响。

![image](https://github.com/user-attachments/assets/c529a20c-2db2-4f1a-ada0-f3c294c89990)

基于 GNN（图神经网络）的因果建模
由于传统的 Granger 因果检验仅限于线性因果关系，利用**基于图的神经网络（如 FcGAGA）**来建立更复杂的因果模型：
将 ETH 和 PENDLE 作为两个时间序列节点，建立因果图（Causal Graph）。
通过门控注意力机制（Gated Attention），让模型自适应地学习 ETH 价格变化对 PENDLE 的影响权重。
结合 Transformer 或 LSTM 进行预测，提高捕捉非线性关系的能力。

边缘级任务
边缘级推理的一个例子是图像场景理解。除了识别图像中的对象之外，深度学习模型还可用于预测它们之间的关系。将其表述为边缘级分类：给定表示图像中对象的节点，希望预测这些节点中的哪些共享边缘或该边缘的值是多少。如果想发现实体之间的联系，可以认为图是完全连通的，并根据它们的预测值修剪边缘以得到稀疏图。



