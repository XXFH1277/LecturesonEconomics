# 第六十九课：自动赎回票据读表入门：观察日、票息障碍、赎回条件与最坏情景

## 基本信息

- 日期：2026-07-26
- 数据截至：2026-07-26（Asia/Shanghai）。BofA Finance LLC 结构化票据案例采用 SEC EDGAR 2026-06-22 final pricing supplement；Federal Reserve H.15 最新发布日为 2026-07-24、数据截至 2026-07-23；SEC、Investor.gov 和 FINRA 页面采用当前可访问版本。
- 主题：为什么自动赎回票据里的“年化票息”必须和观察日、票息障碍、赎回条件、阈值和最坏情景一起读。
- 学习目标：理解 autocallable note、observation date、contingent coupon、coupon barrier、call value、threshold value、principal at risk、estimated value、underwriting discount、no listing 和 secondary market liquidity。
- 相关资产：BofA Finance/BAC 担保票据、AMD common stock、S&P 500、短端美债利率、结构化票据、ELN。
- 核心来源：
  - SEC EDGAR, BofA Finance LLC, Contingent Income Auto-Callable Yield Notes Linked to the Common Stock of Advanced Micro Devices, Inc., Pricing Supplement, 2026-06-22: https://www.sec.gov/Archives/edgar/data/70858/000191870426017575/form424b2.htm
  - SEC Investor.gov, Investor Bulletin: Structured Notes, 2015-01-12: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
  - FINRA, Understanding Structured Notes With Principal Protection, 2023-04-12: https://www.finra.org/investors/insights/structured-notes-principal-protection
  - FINRA Regulatory Notice 12-03, Heightened Supervision of Complex Products, 2012-01-17: https://www.finra.org/rules-guidance/notices/12-03
  - SEC/FINRA press release, SEC, FINRA Warn Retail Investors About Investing in Structured Notes with Principal Protection, 2011-06-02: https://www.sec.gov/news/press/2011/2011-118.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-24: https://www.federalreserve.gov/releases/h15/
  - S&P Dow Jones Indices, S&P 500 official index page, data as of 2026-07-23: https://www.spglobal.com/spdji/en/indices/equity/sp-500/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

今天从一个很容易出错的句子开始：

> 票据写着 26.50% per annum contingent coupon，是不是一年就能赚 26.50%？

不是。这里至少有三个限制：

```text
contingent：票息是有条件的，不是固定利息。
per annum：年化口径，不等于已经赚到。
autocallable：达到赎回条件后，票据可能提前结束，后面的票息不再发生。
```

自动赎回票据的读表方式不是“看最高票息”，而是画一棵条件树：

```text
每个观察日：
标的是否高于票息障碍？
标的是否高于自动赎回线？
如果触发赎回，是否还有后续付款？
如果一直未赎回，到期是否跌破阈值？
```

### 参考的教材式概念顺序

1. Autocallable Note：自动赎回票据，达到条件时提前结束。
2. Observation Date：观察日，用来检测标的价格是否满足票息或赎回条件。
3. Contingent Coupon：有条件票息，只有满足条件才支付。
4. Coupon Barrier：票息障碍，标的价格不低于这条线时才可能付票息。
5. Call Value：赎回触发值，标的达到这条线时可能自动赎回。
6. Call Observation Date：赎回观察日，专门判断是否触发自动赎回。
7. Threshold Value：本金风险阈值，到期跌破后可能开始按标的跌幅亏本金。
8. Principal at Risk：本金有风险，票据不保证返还全部本金。
9. Starting Value：初始价格，计算障碍、阈值和赎回线的基准。
10. Ending Value：最终价格，通常在估值日确定。
11. Estimated Value：估计价值，发行人估算的票据价值。
12. Underwriting Discount：承销折扣，销售和发行成本的一部分。
13. No Listing：不上市交易，通常没有交易所流动性。
14. Worst-Performing：最差表现标的，多标的票据中以表现最差的资产决定结果。
15. Memory Coupon：记忆票息，部分票据会在未来满足条件时补付之前未付票息，本课案例不采用它，但后续读表要识别。

### 核心概念

自动赎回票据有两个最关键的开关：

```text
票息开关：
观察日标的价格 >= coupon barrier
-> 当期可能支付 contingent coupon

赎回开关：
赎回观察日标的价格 >= call value
-> 票据提前结束
-> 投资者拿回约定赎回金额
-> 后续票息机会停止
```

它还有一个最关键的下行门槛：

```text
到期时标的价格 < threshold value
-> 本金保护条件失败
-> 投资者可能按标的下跌承担损失
```

所以“高票息”不是独立结论。它必须和三个问题一起看：

```text
票息多久才可能拿到？
标的跌到哪里就没有票息？
标的跌到哪里开始亏本金？
```

### 用自己的话解释

假设一张票据每月看一次标的股票价格：

```text
如果股票还在 60% 障碍线上方：
支付本月票息。

如果到了赎回观察日，股票回到初始价或更高：
提前赎回，票据结束。

如果到期时股票低于 50% 阈值：
开始亏本金，亏损可能非常大。
```

这不是存款利息，而是用一组条件把收益和亏损重新分配。投资者拿到较高的条件票息，是因为接受了股票下跌、本金受损、发行人信用、流动性和提前赎回的组合风险。

### 常见误区

- 误区一：年化票息等于实际收益。年化只是把当期票息换算成年口径，不代表条件一定满足，也不代表产品会持有满一年。
- 误区二：只要没有跌破 coupon barrier 就安全。coupon barrier 只决定票息，threshold value 才决定到期本金风险的关键门槛。
- 误区三：自动赎回是额外好处。自动赎回可能让投资者提前拿回钱，但也停止后续高票息机会，并带来再投资风险。
- 误区四：单只股票挂钩票据只要看发行人。还要看标的股票波动、公司事件、行业估值和除权调整。
- 误区五：二级市场卖出和卖 ETF 一样。很多票据不在交易所上市，发行人或关联方也未必持续做市。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC EDGAR 上 BofA Finance LLC 2026-06-22 final pricing supplement 显示，该产品是 Contingent Income Auto-Callable Yield Notes，挂钩 Advanced Micro Devices, Inc. common stock，发行人为 BofA Finance LLC，担保人为 Bank of America Corporation。票据本金规模为 200,000 美元，定价日为 2026-06-22，发行日为 2026-06-25，到期日为 2028-12-28，若未提前赎回，期限约 2.5 年。

该文件显示，票据的 contingent coupon rate 为 26.50% per annum，即每月 2.2084%，条件是观察日 AMD 的 Observation Value 不低于 Starting Value 的 60.00%。Starting Value 为 551.63 美元，coupon barrier 为 330.98 美元，threshold value 为 275.82 美元，call value 为 551.63 美元，即初始值的 100.00%。

自动赎回从 2026-12-22 call observation date 开始。如果在任何赎回观察日，AMD 的 Observation Value 不低于 call value，票据将自动赎回，投资者每 1,000 美元本金收到 1,000 美元加当期 contingent coupon，之后不再付款。若到期前未自动赎回，且 ending value 低于 threshold value，赎回金额会低于 50% 本金，极端情况下可能亏掉全部本金。

同一文件还显示，公开发行价为每 1,000 美元本金 1,000 美元；初始 estimated value 为每 1,000 美元本金 949.40 美元；underwriting discount 最高为每 1,000 美元本金 28.75 美元；票据不在任何证券交易所上市；文件封面还提示该票据不是 FDIC insured、不是银行存款式 guarantee，且 may lose value。这里要区分：BAC 对票据付款作公司担保，不等于银行存款保险或无风险保证。

Federal Reserve H.15 2026-07-24 release 显示，截至 2026-07-23，effective federal funds rate 为 3.63%，4-week Treasury bill secondary market rate 为 3.73%，3-month Treasury bill secondary market rate 为 3.81%，10-year Treasury constant maturity 为 4.71%。这些数字说明现金和美债有自己的市场收益背景。若一个结构化票据展示远高于短端利率的条件票息，读者应先问“哪些风险被打包进来了”，而不是把它当作现金利率替代品。

SEC Investor.gov 和 FINRA 材料都提醒，结构化票据可能非常复杂，支付结构、流动性、发行人信用和费用都可能让普通投资者难以准确评估风险。FINRA Regulatory Notice 12-03 也把带有复杂衍生品特征的结构化票据列为可能需要更高监督的复杂产品。

### 为什么重要

BofA AMD 案例把自动赎回票据的关键误读集中在一页：

```text
26.50% per annum
-> 看起来很高

60% coupon barrier
-> 票息并不保证

100% call value
-> 标的回到初始价或更高时，票据可能提前结束

50% threshold value
-> 到期跌破阈值后，本金可能大幅亏损

estimated value 949.40 vs public offering price 1000
-> 初始经济价值和购买价格不同
```

初学者要学会把这些数字放在一张表里，而不是只复制最高的票息数字。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| 发行人 / 担保人 | BofA Finance LLC / Bank of America Corporation | SEC EDGAR, 2026-06-22 | 信用风险 |
| 票据规模 | 200,000 美元 | SEC EDGAR, 2026-06-22 | 产品规模 |
| 定价日 / 发行日 / 到期日 | 2026-06-22 / 2026-06-25 / 2028-12-28 | SEC EDGAR, 2026-06-22 | 时间线 |
| 挂钩标的 | AMD common stock | SEC EDGAR, 2026-06-22 | 参考资产 |
| Starting Value | 551.63 美元 | SEC EDGAR, 2026-06-22 | 计算基准 |
| Contingent coupon rate | 26.50% per annum，2.2084% per month | SEC EDGAR, 2026-06-22 | 年化票息口径 |
| Coupon barrier | 330.98 美元，60% of Starting Value | SEC EDGAR, 2026-06-22 | 票息条件 |
| Call value | 551.63 美元，100% of Starting Value | SEC EDGAR, 2026-06-22 | 自动赎回条件 |
| Threshold value | 275.82 美元，50% of Starting Value | SEC EDGAR, 2026-06-22 | 本金风险阈值 |
| Estimated value | 949.40 美元 per 1,000 principal | SEC EDGAR, 2026-06-22 | 初始价值差异 |
| Underwriting discount | 最高 28.75 美元 per 1,000 principal | SEC EDGAR, 2026-06-22 | 销售成本 |
| 交易所上市 | 不在任何证券交易所上市 | SEC EDGAR, 2026-06-22 | 流动性风险 |
| EFFR / 4-week T-Bill / 3-month T-Bill | 3.63% / 3.73% / 3.81% | Fed H.15, 2026-07-23 | 现金收益背景 |

### 这些现实事件如何连接理论

第一条链：条件票息。

```text
标的价格在观察日高于 coupon barrier
-> 支付当期 contingent coupon
-> 若低于 barrier，当期可能没有票息
-> 年化票息不等于保证收益
```

第二条链：自动赎回。

```text
标的价格在 call observation date 高于 call value
-> 票据自动赎回
-> 投资者收到本金加当期票息
-> 之后不再享有后续票息
-> 需要重新投资，面对再投资风险
```

第三条链：到期本金风险。

```text
未自动赎回
-> 到期看 ending value
-> ending value >= threshold value：通常返还本金
-> ending value < threshold value：本金按标的下跌暴露亏损
```

第四条链：发行价和估计价值。

```text
投资者按 public offering price 买入
-> 文件披露 initial estimated value
-> 估计价值低于发行价
-> 差额反映销售、结构、对冲和发行人经济条款
-> 到期前二级市场报价可能低于本金
```

### 至少一个真实市场机制案例

案例：BofA Finance AMD 自动赎回票据的情景树。

把每 1,000 美元本金想成一张条件合同：

```text
每月观察日：
AMD >= 330.98 美元
-> 支付 22.084 美元 contingent coupon

AMD < 330.98 美元
-> 当期不支付 contingent coupon

从 2026-12-22 开始的赎回观察日：
AMD >= 551.63 美元
-> 自动赎回，支付 1,000 美元本金 + 当期票息，票据结束

如果一直没有自动赎回，到了 2028-12-22 估值日：
AMD >= 275.82 美元
-> 到期返还 1,000 美元本金，是否有最终票息还要看是否 >= 330.98 美元

AMD < 275.82 美元
-> 赎回金额低于 50% 本金，极端情况下可能为零
```

这棵树解释了为什么 26.50% 不能单独读。这个数字只是在满足条件时的年化票息口径，不包括未付票息、提前赎回、标的下跌、发行人信用和二级市场折价。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC EDGAR 注册证券披露、FINRA 复杂产品监督、经纪商销售和适当性、发行人与担保人信用、非交易所上市产品的流动性安排。
- 已确认事实：BofA AMD 案例是 SEC EDGAR 上的 final pricing supplement；文件披露发行人、担保人、票息条件、自动赎回条件、阈值、估计价值、承销折扣和不上市交易；SEC/FINRA 长期提醒结构化票据可能复杂、昂贵、流动性差且不等同于无风险产品。
- 市场可能如何传导：标的波动率越高，条件票息可能越高，但本金风险和触发风险也更明显；短端利率影响发行人融资和投资者替代收益；信用利差会影响票据二级市场价值。
- 仍需核验或观察：AMD 最新官方价格和公司事件、BofA/BAC 信用状况、每个观察日价格、是否触发票息或赎回、税务处理、二级市场报价和投资者实际成交价。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Autocallable Note | 自动赎回票据 | 达到条件后提前结束的票据 | 决定期限和票息机会 |
| Observation Date | 观察日 | 检查标的价格的日期 | 票息和赎回开关 |
| Contingent Coupon | 有条件票息 | 条件满足才支付的票息 | 不是固定利息 |
| Coupon Barrier | 票息障碍 | 支付票息所需的最低标的水平 | 决定现金流是否发生 |
| Call Value | 赎回触发值 | 达到后自动赎回的标的水平 | 结束后续收益机会 |
| Threshold Value | 阈值 | 到期本金风险的关键线 | 跌破后可能大亏 |
| Principal at Risk | 本金有风险 | 可能亏掉部分或全部本金 | 不能当存款 |
| Starting Value | 初始值 | 条款计算的基准价格 | 所有百分比的起点 |
| Ending Value | 最终值 | 到期估值日价格 | 决定最终付款 |
| Estimated Value | 估计价值 | 发行人估算的票据价值 | 常低于发行价 |
| Underwriting Discount | 承销折扣 | 销售和承销成本 | 影响投资者经济条件 |
| No Listing | 不上市交易 | 没有交易所买卖渠道 | 流动性风险 |
| Worst-Performing | 最差表现标的 | 多资产中表现最差者决定结果 | 多标的票据风险更高 |
| Memory Coupon | 记忆票息 | 后续满足条件时可能补付之前未付票息 | 必须看是否存在和条件 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券信用风险，第 64 课期权入门，第 67 课期权收益型 ETF 读表，第 68 课结构化票据与 ELN。
- 本课哪些内容会在后续课程继续使用：最差表现标的、单股挂钩、分散化错觉、复杂产品销售规则、适当性、税务和行为金融中的高票息诱惑。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图和第 8 课衍生工具入门，先理解“债务关系”和“未来条件付款”。

## 案例拆解

- 案例对象：BofA Finance LLC 2026-06-22 AMD contingent income auto-callable yield notes。
- 已确认事实：
  - 发行人为 BofA Finance LLC，担保人为 Bank of America Corporation。
  - 挂钩标的是 AMD common stock，Starting Value 为 551.63 美元。
  - contingent coupon rate 为 26.50% per annum，月度票息为每 1,000 美元本金 22.084 美元。
  - coupon barrier 为 Starting Value 的 60%，即 330.98 美元。
  - call value 为 Starting Value 的 100%，即 551.63 美元，自动赎回从 2026-12-22 开始。
  - threshold value 为 Starting Value 的 50%，即 275.82 美元。
  - initial estimated value 为每 1,000 美元本金 949.40 美元，低于 1,000 美元 public offering price。
  - 票据不在任何证券交易所上市，且不是 FDIC insured、不是银行存款式 guarantee，仍然 may lose value；这不取消 BAC 作为公司担保人的信用风险分析。
- 来源日期和链接：见本课“来源”。
- 分析推理：该票据用单只股票波动风险、本金风险、自动赎回和发行人信用，换取条件票息。它不是现金工具，也不是 AMD 股票的简单替代。
- 后续验证指标：每个 observation date 的 AMD 收盘价、是否满足 coupon barrier、是否触发 call value、到期是否高于 threshold value、发行人信用利差、二级市场报价和税务文件。

## 一页自动赎回票据读表顺序

```text
第一步：身份
- Issuer：
- Guarantor：
- Principal amount：
- 是否 FDIC insured：
- 是否 bank guaranteed：

第二步：时间线
- Pricing date：
- Issue date：
- First observation date：
- First call observation date：
- Valuation date：
- Maturity date：

第三步：标的
- Reference asset：
- Starting value：
- 是否看价格回报还是总回报：
- 是否享有股息：

第四步：票息
- Coupon rate：
- Monthly/quarterly coupon：
- Coupon barrier：
- 是否 contingent：
- 是否 memory：

第五步：赎回
- Call value：
- Call observation dates：
- Early redemption amount：
- 赎回后是否还有付款：

第六步：到期亏损
- Threshold value：
- Barrier value：
- Principal at risk：
- 最坏情景是否可能亏 100%：

第七步：价格和退出
- Public offering price：
- Estimated value：
- Underwriting discount：
- 是否上市：
- 发行人是否承诺做市：
```

## 个人情境连接

- 对关注清单的启发：把“年化票息”字段改成“条件票息”，旁边必须放 coupon barrier、call value、threshold value、observation date 和 issuer。
- 对持仓或基金选择的启发：如果一只基金或账户中有 ELN/结构化票据，不能只看现金分配，要穿透到参考资产和发行人信用。
- 对工作、收入、消费或风险管理的启发：自动赎回票据很适合训练“条件概率”思维。任何看起来高的收入，都要先问触发条件、失败条件和退出价格。

## 结论边界

- 可以确定：自动赎回票据的票息通常有条件；coupon barrier、call value、threshold value 和 observation date 共同决定现金流；发行价、估计价值、承销折扣和不上市交易都必须读；本金可能亏损。
- 不能确定：本课不能预测 AMD、BofA/BAC 信用、任何票据观察日结果、自动赎回概率、二级市场价格或税后收益。
- 需要继续观察：每个观察日标的价格、发行人信用利差、最终付款事件、二级市场报价、税务披露和同类票据新发行条款。
- 不构成投资建议的原因：本课只解释结构化票据读表和风险边界，不建议买入、卖出或持有任何票据、股票、ETF、基金、债券或衍生品。

## 练习题

1. 为什么 26.50% per annum contingent coupon 不能理解成确定年收益？
2. coupon barrier 和 threshold value 分别控制什么？
3. 自动赎回触发后，为什么投资者可能面临再投资风险？
4. 如果一张票据的 public offering price 是 1,000 美元，但 estimated value 是 949.40 美元，你会在读表中提出哪三个问题？
5. 选一份自动赎回票据 424B2 文件，画出“票息、自动赎回、到期返本、到期亏损”四条路径。

## 学习交接

- 本课已经完成：把自动赎回票据从“高票息”拆成 observation date、contingent coupon、coupon barrier、call value、threshold value、estimated value、underwriting discount 和 no listing。
- 本课最重要的一句话：自动赎回票据的收益不是一个数字，而是一组日期、价格线和信用承诺共同组成的条件树。
- 需要复习的关键词：Autocallable Note、Observation Date、Contingent Coupon、Coupon Barrier、Call Value、Threshold Value、Principal at Risk、Estimated Value、Underwriting Discount、No Listing、Secondary Market Liquidity、Worst-Performing、Memory Coupon。
- 还不稳定、下次要回看的地方：多标的票据为什么常常由 worst-performing asset 决定结果，以及为什么“篮子里资产更多”不一定代表风险更分散。
- 适合下次打开仓库先读的文件：`lessons/2026-07-26-lesson-69-autocallable-notes-barrier-coupon-liquidity-risk.md`

## 下节课安排

- 建议主题：第七十课：多标的结构化票据与最差表现风险入门：篮子、相关性、单股事件与分散化错觉。
- 学习目标：理解 worst-performing、basket note、correlation、single-stock event risk、knock-in、memory coupon、non-call period、decrement index 和 issuer call risk。
- 建议案例：使用 SEC EDGAR 上 least-performing 或 worst-performing multi-underlying auto-callable notes，结合 S&P 500、Nasdaq-100、Russell 2000 或单股案例，解释为什么多标的结构可能由最弱一环决定现金流和本金结果。
- 必须解释的关键词：Worst-Performing、Basket Note、Correlation、Single-Stock Event Risk、Knock-In、Memory Coupon、Non-Call Period、Decrement Index、Issuer Call Risk、Scenario Tree。
- 下节课开始前需要联网核验的数据：至少一份最新多标的 auto-callable final pricing supplement、SEC/FINRA 复杂产品材料、相关指数官方页面、标的股票官方/交易所价格背景、Fed H.15 最新利率和发行人信用披露。

## 来源

- SEC EDGAR, BofA Finance LLC, Contingent Income Auto-Callable Yield Notes Linked to Advanced Micro Devices, Inc.: https://www.sec.gov/Archives/edgar/data/70858/000191870426017575/form424b2.htm
- SEC Investor.gov, Investor Bulletin: Structured Notes: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
- FINRA, Understanding Structured Notes With Principal Protection: https://www.finra.org/investors/insights/structured-notes-principal-protection
- FINRA Regulatory Notice 12-03, Heightened Supervision of Complex Products: https://www.finra.org/rules-guidance/notices/12-03
- SEC/FINRA press release, SEC, FINRA Warn Retail Investors About Investing in Structured Notes with Principal Protection: https://www.sec.gov/news/press/2011/2011-118.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- S&P Dow Jones Indices, S&P 500 official index page: https://www.spglobal.com/spdji/en/indices/equity/sp-500/
