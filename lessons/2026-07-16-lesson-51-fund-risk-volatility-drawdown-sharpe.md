# 第五十一课：基金风险指标、波动率、最大回撤与 Sharpe Ratio 入门

## 基本信息

- 日期：2026-07-16
- 数据截至：2026-07-16 16:12（Asia/Shanghai）。基金风险披露采用 SEC《Mutual Funds and ETFs: A Guide for Investors》；SPY 采用 State Street 页面显示的 2026-07-16 基金信息、2026-07-15 NAV/市场价格、2026-07-14 持仓和行业权重、2026-06-30 业绩；利率背景采用 U.S. Treasury Daily Treasury Par Yield Curve Rates 2026-07-15。
- 主题：为什么基金表现不能只看收益率；如何用波动率、最大回撤、Sharpe Ratio、Beta、集中度和流动性理解基金风险。
- 学习目标：理解 Volatility、Standard Deviation、Maximum Drawdown、Sharpe Ratio、Risk-free Rate、Excess Return、Beta、Downside Risk、Liquidity Risk 和 Concentration Risk；学会做基金风险检查页。
- 相关资产：ETF、指数基金、主动基金、SPY、S&P 500、美国国债收益率、风险调整收益。
- 核心来源：
  - SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
  - State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课学会了问“基金跑赢谁”。今天继续问：

> 如果两个基金都赚了 10%，它们的风险一样吗？

不一样。一个基金可能一路平稳涨到 10%，另一个可能先跌 30% 再反弹到 10%。最终收益相同，但持有过程、心理压力、追加资金风险和卖在低点的概率完全不同。

### 参考的教材式概念顺序

1. Return：收益率，结果数字。
2. Volatility：波动率，收益上下摆动的幅度。
3. Standard Deviation：标准差，衡量波动的常用统计指标。
4. Drawdown：回撤，从阶段高点跌到低点的幅度。
5. Maximum Drawdown：最大回撤，观察期内最深的一次下跌。
6. Risk-free Rate：无风险利率，常用短期美国国债收益率作为近似背景。
7. Excess Return：超额于无风险利率的回报。
8. Sharpe Ratio：夏普比率，用单位波动换来的超额回报。
9. Beta：相对市场的敏感度。
10. Downside Risk：下行风险，更关心亏损或低于目标回报的波动。
11. Liquidity Risk：流动性风险，想卖时能不能以合理价格卖出。
12. Concentration Risk：集中度风险，少数公司、行业或因子控制组合表现。

### 核心概念

最小风险框架可以写成：

```text
基金评价 = 回报 + 回报路径 + 风险来源

回报路径：
- 波动率：上下摆动大不大
- 最大回撤：最难受时跌了多少
- 恢复时间：跌下去以后多久回到前高

风险调整：
- Excess Return = 基金回报 - 无风险利率
- Sharpe Ratio = Excess Return / Volatility

风险来源：
- 市场风险
- 行业集中
- 个股集中
- 利率和汇率
- 流动性
- 费用和税务
```

Sharpe Ratio 不是神奇评分。它只是把“多赚多少”除以“波动多大”。如果数据窗口、收益频率、无风险利率或波动结构不同，Sharpe 的可比性会变差。初学者应把它当作提问工具，不当作投资结论。

### 用自己的话解释

风险不是“会不会跌”这么简单，而是“跌的时候你能不能承受、为什么跌、跌了以后是否还能按计划持有”。最大回撤像一段旅程中最深的坑，波动率像路面颠簸程度，Sharpe Ratio 像问“每承受一单位颠簸，换来了多少额外收益”。

### 常见误区

- 误区一：收益高就代表风险低。可能只是承担了更高风险。
- 误区二：波动率低就一定安全。低波动资产也可能有信用、流动性或估值风险。
- 误区三：最大回撤只影响心理。回撤会影响再平衡、保证金、现金需求和卖出时点。
- 误区四：Sharpe Ratio 越高越一定好。它依赖历史数据和统计假设，不能覆盖尾部风险。
- 误区五：持仓数量多就没有集中度风险。第 48 课已经看到，SPY 持有很多股票，但仍有大型科技和信息技术权重。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC《Mutual Funds and ETFs: A Guide for Investors》提示，基金和 ETF 不由 FDIC 或其他政府机构担保，投资者可能亏钱；过去业绩不是未来表现的可靠指标，但可以帮助评估基金历史波动；基金和 ETF 都有会降低回报的成本。SEC 还提醒投资者先判断自己的财务目标和风险承受能力，并说明一般来说潜在回报越高，亏损风险也越高。

State Street SPY 页面在风险披露中说明，ETF 可以随适用指数上下波动；ETF shares may trade at prices above or below NAV；在市场压力时期，ETF 可能出现显著折价；股票也会因个别公司情况、经济条件、利率、通胀、信用、流动性和地缘政治事件而波动。

SPY 的 2026-07-14 持仓和行业权重显示，NVIDIA 权重 7.91%、Apple 7.13%、Microsoft 4.41%；Information Technology 行业权重 37.50%。这说明一个大型宽基 ETF 也要看集中度风险：不是只有单一股票才有集中度。

U.S. Treasury Daily Treasury Par Yield Curve Rates 显示，2026-07-15 的 3-month rate 为 3.83%，10-year rate 为 4.55%，30-year rate 为 5.08%。短端利率可作为风险调整收益的背景之一，但它不是个人账户的保证收益，也不等于所有人的真实机会成本。

### 为什么重要

第 50 课问“是否跑赢基准”。第 51 课问“为了跑赢，承受了什么路径”。这两个问题必须一起看：

```text
基金 A：
年化回报 10%，最大回撤 -12%，波动率 14%

基金 B：
年化回报 10%，最大回撤 -45%，波动率 30%

结果一样，路径不同。
如果投资者在最大回撤时承受不住，最终收益就不再属于他。
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| 基金/ETF 可亏钱 | 不受 FDIC 或其他政府机构担保，投资者可能亏钱 | SEC guide | 风险底线 |
| 过去业绩 | 过去业绩不是未来表现的可靠指标，但可帮助评估波动 | SEC guide | 业绩边界 |
| SPY NAV | 754.68 美元 | State Street, as of 2026-07-15 | 净值口径 |
| SPY closing price | 754.81 美元 | State Street, as of 2026-07-15 | 市场价格口径 |
| SPY premium/discount | 0.01% | State Street, as of 2026-07-15 | 折溢价风险 |
| SPY 30-day median bid/ask spread | 0.00% | State Street, as of 2026-07-15 | 流动性观察 |
| SPY top holding | NVIDIA 7.91% | State Street, as of 2026-07-14 | 集中度 |
| SPY IT sector weight | 37.50% | State Street, as of 2026-07-14 | 行业暴露 |
| U.S. 3-month Treasury rate | 3.83% | U.S. Treasury, 2026-07-15 | 风险调整背景 |
| U.S. 10-year Treasury rate | 4.55% | U.S. Treasury, 2026-07-15 | 利率环境 |

### 这些现实事件如何连接理论

用 SPY 的公开数据可以搭一个入门风险检查：

```text
基金：SPY
数据截至：2026-07-15 / 2026-07-14

净值和交易：
- NAV：754.68
- Closing Price：754.81
- Premium/Discount：0.01%
- 30-day median bid/ask spread：0.00%

集中度：
- NVIDIA：7.91%
- Apple：7.13%
- Microsoft：4.41%
- Information Technology：37.50%

风险解释：
- 交易成本指标很低，不代表市场风险低。
- 持仓数量很多，不代表没有少数公司和行业暴露。
- 历史回报好，不代表未来不会出现大回撤。
```

再把利率放进来：

```text
假设某基金一年回报 10%
同日 3-month Treasury rate 约 3.83%
粗略 Excess Return = 10% - 3.83% = 6.17%

如果基金年化波动率是 20%
粗略 Sharpe Ratio = 6.17% / 20% = 0.31

这只是教学算式：
- 未核验该基金真实波动率
- 未考虑税务、费用、分红和持有期
- 不能作为买卖建议
```

### 至少一个真实市场机制案例

真实机制是“回撤后的恢复难度”。

```text
从 100 跌到 80：
回撤 = -20%

从 80 回到 100：
需要上涨 25%
```

跌 20% 以后，不是涨 20% 就回本，而是要涨 25%。这就是为什么最大回撤比单日涨跌更重要。回撤越深，需要的恢复涨幅越高，投资者越容易在压力中改变计划。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 基金披露、基金招募说明书、ETF 二级市场交易、基金风险披露、国债收益率曲线、市场压力和流动性。
- 已确认事实：SEC 明确提示基金和 ETF 可亏钱、过去业绩不能保证未来；SPY 风险和持仓来自 State Street；利率来自 U.S. Treasury。
- 市场可能如何传导：利率上升会提高无风险收益背景并影响估值；地缘政治、通胀和信用环境会影响股票和 ETF 波动；少数大权重公司会放大指数型基金的集中度。
- 仍需核验或观察：基金真实历史波动率、最大回撤、Beta、下行波动、持仓变化、行业权重变化、折溢价和压力市场成交质量。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Volatility | 波动率 | 收益上下摆动的幅度 | 衡量路径颠簸 |
| Standard Deviation | 标准差 | 统计波动的常用指标 | 许多风险指标的基础 |
| Drawdown | 回撤 | 从高点跌下来的幅度 | 衡量痛苦路径 |
| Maximum Drawdown | 最大回撤 | 观察期内最深下跌 | 检验能否承受 |
| Risk-free Rate | 无风险利率 | 常用短期国债收益率近似 | 计算超额回报背景 |
| Excess Return | 超额回报 | 回报减无风险利率 | 看承担风险后多赚多少 |
| Sharpe Ratio | 夏普比率 | 超额回报除以波动率 | 粗略看风险调整收益 |
| Beta | 贝塔 | 对市场涨跌的敏感度 | 判断市场暴露 |
| Downside Risk | 下行风险 | 更关注亏损方向的波动 | 比总波动更贴近亏损体验 |
| Liquidity Risk | 流动性风险 | 想卖时价格和成交不理想 | 压力市场更重要 |
| Concentration Risk | 集中度风险 | 少数持仓或行业占比过高 | 宽基基金也可能有 |
| Recovery Return | 恢复涨幅 | 下跌后回本需要的涨幅 | 回撤越深越难恢复 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和利率、第 47 课组合暴露、第 49 课 ETF 折溢价、第 50 课基金表现归因。
- 本课哪些内容会在后续课程继续使用：资产配置、再平衡、风险预算、核心/卫星组合、基金筛选。
- 如果看不懂本课，可以先回到：第 1 课收益与风险、第 3 课金融产品地图、第 46 课投资备忘录。

## 案例拆解

- 案例对象：SPY 的集中度、交易口径和风险披露。
- 已确认事实：
  - SPY 2026-07-15 NAV 为 754.68 美元，closing price 为 754.81 美元，premium/discount 为 0.01%。
  - SPY 2026-07-14 前三大持仓为 NVIDIA 7.91%、Apple 7.13%、Microsoft 4.41%。
  - SPY 2026-07-14 Information Technology 权重为 37.50%。
  - SEC 提示基金和 ETF 可亏钱，过去业绩不是未来表现的可靠指标。
  - U.S. Treasury 2026-07-15 3-month rate 为 3.83%，10-year rate 为 4.55%。
- 来源日期和链接：见本课“来源”。
- 分析推理：SPY 的折溢价和买卖价差指标显示其交易层面流动性较强，但持仓和行业权重说明仍有市场风险、科技行业集中和少数大公司暴露。
- 后续验证指标：最大回撤、年化波动率、Beta、下行波动、行业权重、前十大持仓、折溢价、bid/ask spread、利率曲线变化。

## 一个可复制的基金风险检查页

```text
基金名称：
数据截至：
基准：

收益：
- NAV return：
- Market price return：
- Benchmark return：
- Active return：

路径风险：
- Volatility / Standard deviation：
- Maximum drawdown：
- Recovery time：
- Downside risk：

风险调整：
- Risk-free rate：
- Excess return：
- Sharpe ratio：
- Beta：

结构风险：
- Top holdings：
- Sector concentration：
- Liquidity / bid-ask spread：
- Premium / discount：
- Expense ratio：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：把基金观察表从“收益率排名”升级为“收益、回撤、波动、集中度、流动性”。
- 对持仓或基金选择的启发：如果个人收入和投资都依赖科技行业，那么信息技术权重高的基金会放大同一风险来源。
- 对工作、收入、消费或风险管理的启发：风险承受能力不是口号，要和现金储备、收入稳定性、负债和心理承受路径连接起来。

## 结论边界

- 可以确定：基金和 ETF 可亏钱；过去业绩不能保证未来；风险需要同时看波动、回撤、集中度、流动性和利率背景。
- 不能确定：本课不能预测 SPY 或任何基金未来回撤、波动率或 Sharpe Ratio，也不能证明某一风险指标单独足够。
- 需要继续观察：基金最新风险披露、持仓集中、行业权重、利率、折溢价、买卖价差和压力市场表现。
- 不构成投资建议的原因：本课只解释基金风险指标和阅读框架，不建议买入、卖出、持有或配置任何基金。

## 练习题

1. 一个基金从 100 跌到 70，再回到 100。最大回撤是多少？从 70 回到 100 需要上涨多少？
2. 为什么两个年化回报相同的基金，最大回撤不同，会带来完全不同的持有体验？
3. 用 SPY 的 2026-07-14 持仓数据，写出两个集中度风险来源。
4. 如果某基金年回报 9%、短期国债利率 4%、年化波动率 20%，粗略 Sharpe Ratio 是多少？这个计算有什么局限？
5. 选一个基金，写一页风险检查：volatility、maximum drawdown、top holdings、sector weight、bid/ask spread 和 premium/discount。

## 学习交接

- 本课已经完成：把第 50 课的基金表现归因推进到收益路径、风险调整收益和基金风险检查。
- 本课最重要的一句话：基金收益属于结果，波动、回撤、集中度和流动性决定你能不能真的拿到这个结果。
- 需要复习的关键词：Volatility、Standard Deviation、Maximum Drawdown、Sharpe Ratio、Risk-free Rate、Excess Return、Beta、Downside Risk、Liquidity Risk、Concentration Risk。
- 还不稳定、下次要回看的地方：如何把单个基金风险指标放进完整组合，决定核心仓位、卫星仓位和再平衡规则。
- 适合下次打开仓库先读的文件：`lessons/2026-07-16-lesson-51-fund-risk-volatility-drawdown-sharpe.md`

## 下节课安排

- 建议主题：第五十二课：基金组合构建、核心/卫星配置与再平衡入门。
- 学习目标：理解单个基金好坏不等于组合合理，学会用 asset allocation、core-satellite、risk budget、rebalancing band、correlation 和 liquidity reserve 组织基金组合。
- 建议案例：使用 SPY、QQQ、一个等权指数或债券基金作教学对照，但必须重新核验基金官网、费用率、持仓、相关性、利率背景和风险披露。
- 必须解释的关键词：Asset Allocation、Core-Satellite、Risk Budget、Rebalancing、Rebalancing Band、Correlation、Diversification、Liquidity Reserve、Position Sizing。
- 下节课开始前需要联网核验的数据：基金官网的最新持仓、行业权重、费用率、表现、风险披露；Treasury 最新收益率曲线；如涉及债券基金，还要核验 duration、credit quality、yield 和 SEC yield。

## 来源

- SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
- State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
