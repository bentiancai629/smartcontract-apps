# MEV 是在为谁工作

最近的机器人越来越难赚钱了，回头算下来有一半以上的利润都送给了矿工，感觉很郁闷。

## MEV 是什么

MEV，全称 Maximum Extractable Value，翻译过来是“最大可提取价值”。一开始我还以为这是指从区块链上提取最大的价值，现在想来，这实际上是指从科学家身上提取最大的价值。

## MEV 来源

MEV 来源于链上的 DEFI 生态提供的价值偏差。比如 ETH 链上有 Uniswap v2 和 Uniswap v3，如果代币在 Uniswap v2 和 Uniswap v3 上的价格不一样，那么科学家就有机会两者之间套利。套利的收益除了给矿工交一部分作为 GAS 费用之外，剩下的就是科学家的利润。这听起来是不错的生意，但实际上远没有这么简单。

## MEV 提取流程

在 MEV 提取过程中，科学家会计算利润和套利路径，并把执行逻辑都写成合约代码，使用机器人来完成调用。这时如果没有人发现并执行同一套利路径，那么只需要向矿工缴纳正常的 GAS 费用；如果有别人发现并执行同一套利路径，那么就必须支付比别人更高的 GAS 以确保自己的交易优先完成。

由于区块链上的交易都是公开的，利润稍大的套利路径都能被筛选并研究出来，从而导致激烈的 GAS 竞争。而区块链上的 GAS 竞价都是公开的，因此给矿工的 GAS 往往能在一个块的时间内翻上好几倍。最终如果没有人退出，往往需要将全部的利润都给矿工，直到有一方结束内耗。

## MEV 优化

由于在交易排序的过程中矿工有着绝对的权力，因此科学家是处于弱势地位的。曾经有个名叫 EDEN 的项目试图使用代币质押替代 GAS 竞争来进行交易排序，但最后失败了，因为矿工总能从两个规则之中挑选对自己最有利的执行。目前起更大作用的是 FlashBot，它通过让科学家发送不公开的交易来完成不透明 GAS 竞价，显著降低了链上 GAS 竞争的激烈程度。但这依旧算不上一个最终的解决办法，希望后来人能给出一个更加公平、可用的交易排序方案。