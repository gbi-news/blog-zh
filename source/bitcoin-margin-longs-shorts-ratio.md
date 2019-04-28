---
title: 比特币保证金多空率（BMLS）
date: 2019-04-28 16:23:57
tags: ["GBI", "BMLS"]
---

今天我们上线了一个新的指数：**比特币保证金多空率（BMLS）**

BMLS 是一个[龙门资本](http://www.longmen.fund/)设计，由 GBI 团队实现的微观指数。

该指数的计算方法为：

```latex,autorun
BMLS = 
  \frac{ Bitfinex\ 比特币保证金看多总额}{ Bitfinex\ 比特币保证金看空总额} 
  \times 100
```

该指数受到比特币借贷看空和借贷看多需求的影响。它可以作为市场情绪指标，当指标低于 100％ 表示看跌情绪，反之为看多情绪。

访问 [GBI.news](https://gbi.news/) 查看该指数。

