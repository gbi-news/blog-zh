---
title: GBI 2019，区块链指数，一个全新的开始。
tags: ["区块链", "GBI"]
date: 2018-12-31 00:09:01
---

大家新年好。这是 GBI.news 团队的第一篇博客，也宣告 GBI 指数（[gbi.news](https://gbi.news)）将迎来最大一次的调整。

GBI 指数已经运行了两年，从2017 年 1 月 1 日的 1000 点到最高 22480 点，到现在的 4400 点左右，宏观的反映了两年来区块链资产市场的趋势，经过两年的试运行后，这次进行的调整，有可能是最后一次的调整，我们把进入指数的品种和权重计算方式，交给市场，尽可能不再进行人工干预，主要的调整如下：

1. 指数成分品种调整为 10个，市值排名前 10 的品种自动成为指数成分，每 24 小时修正一次。
2. 成分品种在排名靠前的 10 大交易平台的交易量为计算成分的权重比例。

目前 GBI 使用市值为 Coinmarketcap 的数据，未来会以更准确、公平、有效为目标，建设新的数据源。

## 指数规则

指数最终的品种按照市值进行权重加权计算。因此，指数的结构存在两个核心选择，一是选择哪些品种；二是选择哪些交易所的价格。

原则上，我们应该选择最能表现市场的品种，即市值最高的前 N 个币种。前 N 市值品种在指数中的权重占比取决于品种的交易量占比。交易量则根据品种在全球交易市场中，选取较大的前 M 个交易所来确定。

GBI 方案细则如下：

1. 从市场中，找到市值 Top N 的币种，市值为 

```latex,autorun
A_{i} (i < N)
```

2. 从市场中，找到 Top N 币种的 Top M 交易所，分别其交易量为  

```latex,autorun
V_{i,j}  (i < N, j < M)
```

3. 计算每个币的权重，前十市值品种在指数中的权重占比取决于品种的交易量占比。用 `V_{n}` 表示前 N 名品种在过去 24 小时的交易量（V 表示 Volume），交易量选取该币种所在的前十名交易所的交易量之和。

4. 其中， 的计算方法为：

```latex,autorun
V\_{n} = \sum_{j=1}^{M}{V_{n,j}}
```

5. 因此，第 n 名品种的权重计算公式为：

```latex,autorun
   W\_{n} = \frac{V_{n}}{\sum_{i=1}^{N}{V_{i}}}
```

6. 最后，GBI 的计算公式为：

```latex,autorun
GBI = \frac{\sum_{i=1}^{N}{A_{i} \times W_{i}}}{A_{0}} \times \alpha \times 1000, (N=10)
```
   
其中，常量 `α` 用于确保计算权重更新时，指数的连续性。

## 操纵防范

指数的客观性是指数价值所在，但也需要预防指数被不适当的操纵的可能，管理团队会根据指数计算原则对构成指数的市场因素不断观察，对于构成对指数的客观性有破坏性的因素，将采取适当方式进行调整。所有人工干预的规则会事先制定，并且确保在工具的操作过程中公正、公开。

人工干预工具包括：

- **交易所观察池**：流量计算在交易所观察池中进行，符合计算要求的交易所才会参与指数计算。
- **预观察期**：新交易所需经过 3 个月的预观察期后，才能进入观察池，纳入观察范围。
- **交易量清洗**：挖矿交易、无手续费交易等非正常交易产生的交易量将不会被计算在内。
- **终止观察**：如果发现交易所存在严重人为因素影响市场的行为，将该交易所移除观察池。

GBI.news 经过本次调整后，将成为无需每年人工修正成分的更加真实反映市场趋势的指标，2019年，除了区块链行业指数，还将开放更多功能。