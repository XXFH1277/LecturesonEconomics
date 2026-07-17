# 第五十五课：T-Bill 阶梯、拍卖口径与再投资风险入门

## 基本信息

- 日期：2026-07-17
- 数据截至：2026-07-17 21:50（Asia/Shanghai）。T-Bill 已完成拍卖数据来自 U.S. Treasury FiscalData API，过滤 `security_type=Bill` 且 `auction_date <= 2026-07-17`；短端市场背景采用 Federal Reserve H.15 2026-07-16 发布、截至 2026-07-15 的数据；T-Bill 机制采用 TreasuryDirect 官方说明。
- 主题：T-Bill 为什么折价发行；如何读 auction date、issue date、maturity date、discount rate、investment rate、price per 100 和 bid-to-cover；如何用 T-Bill ladder 管理短期现金。
- 学习目标：理解 T-Bill 的现金流、拍卖口径、价格公式、阶梯安排和再投资风险；能把官方拍卖结果转成一页现金管理笔记。
- 相关资产：美国国库券、短端利率、现金管理、货币市场基金、短债 ETF。
- 核心来源：
  - TreasuryDirect, Treasury Bills: https://www.treasurydirect.gov/marketable-securities/treasury-bills/
  - TreasuryDirect, Understanding Pricing and Interest Rates: https://www.treasurydirect.gov/marketable-securities/understanding-pricing/
  - U.S. Treasury FiscalData API, Auctions Query: https://api.fiscaldata.treasury.gov/services/api/fiscal_service/v1/accounting/od/auctions_query
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-16: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - iShares SGOV product page: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课把现金管理分成银行存款、货币市场基金、T-Bill 和短债 ETF。今天只盯住 T-Bill：

> T-Bill 没有票息，为什么还会有收益？

答案是：T-Bill 通常折价买入，到期按面值收回。买入价和面值之间的差额，就是利息。

### 参考的教材式概念顺序

1. Face Value：面值，到期时财政部支付的金额。
2. Discount：折价，用低于面值的价格买入。
3. Price per 100：每 100 美元面值的成交价格。
4. Auction Date：拍卖日，市场出价确定结果的日期。
5. Issue Date：发行日，证券正式交割并开始计息的日期。
6. Maturity Date：到期日，财政部支付面值的日期。
7. Discount Rate：贴现率，用 360 天和面值口径表达折价程度。
8. Investment Rate：投资利率，更接近投资者投入资金后的年化收益口径。
9. Bid-to-Cover：认购倍数，投标金额与接受金额的比例，观察拍卖需求。
10. T-Bill Ladder：国库券阶梯，把资金分散到不同到期日。
11. Rollover：滚动续投，到期后再买下一期。
12. Reinvestment Risk：再投资风险，到期续投时新利率可能变低。

### 核心概念

TreasuryDirect 对 bills 的基本描述是：

```text
T-Bill 是 1 年以内到期的短期证券
通常按折价或面值出售
到期时支付面值
利息 = 面值 - 购买价格
```

TreasuryDirect 的 T-Bill 定价公式是：

```text
Price = Face Value x (1 - (discount rate x time) / 360)
```

注意这个公式里的 discount rate 不是你最终到手的简单 APY。它是财政部传统的票据贴现报价口径，分母用 360 天，基数是面值。Investment rate 则更接近“投入多少钱、持有多少天、到期拿回多少钱”的投资收益口径。

### 用自己的话解释

T-Bill 像一张短期欠条：

```text
你今天少付一点钱买它
到期财政部按完整面值还你
差额就是你的利息
```

T-Bill ladder 像把一笔钱拆成几段到期：

```text
一部分 4 周到期
一部分 8 周到期
一部分 13 周到期
一部分 26 周到期

每隔一段时间都有钱回来
回来后可以使用，也可以续投
```

阶梯的目标不是预测利率，而是避免把所有现金都锁在同一个到期日和同一个利率点。

### 常见误区

- 误区一：discount rate 就是我的真实到手收益。它是报价口径，不等于所有平台显示的 APY 或 investment return。
- 误区二：T-Bill 到期安全，所以任何期限都适合现金管理。现金用途日期仍然第一重要。
- 误区三：阶梯就是稳赚更多。阶梯主要管理到期分布和再投资风险，不保证收益更高。
- 误区四：bid-to-cover 越高就一定值得买。它是拍卖需求指标，不是个人投资建议。
- 误区五：到期后自动续投没有风险。续投时利率可能下降，也可能遇到账户、税务或现金需求变化。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve 2026-06-17 FOMC statement 显示，FOMC 维持 federal funds target range 在 3.50% 到 3.75%。Federal Reserve H.15 2026-07-16 release 显示，2026-07-15 effective federal funds rate 为 3.63%，Treasury bills secondary market 中 4-week 为 3.64%、3-month 为 3.70%、6-month 为 3.77%、1-year 为 3.80%。

Treasury FiscalData API 中，截至当前日期 2026-07-17 已完成的最新 T-Bill 拍卖结果包括：

| Security term | Auction date | Issue date | Maturity date | High discount rate | High investment rate | Price per 100 | Bid-to-cover |
| --- | --- | --- | --- | ---: | ---: | ---: | ---: |
| 4-Week | 2026-07-16 | 2026-07-21 | 2026-08-18 | 3.660% | 3.721% | 99.715333 | 2.57 |
| 8-Week | 2026-07-16 | 2026-07-21 | 2026-09-15 | 3.650% | 3.722% | 99.432222 | 2.84 |
| 17-Week | 2026-07-15 | 2026-07-21 | 2026-11-17 | 3.745% | 3.845% | 98.762069 | 3.35 |
| 13-Week | 2026-07-13 | 2026-07-16 | 2026-10-15 | 3.760% | 3.849% | 99.049556 | 2.84 |
| 26-Week | 2026-07-13 | 2026-07-16 | 2027-01-14 | 3.860% | 3.992% | 98.048556 | 3.11 |

这里有一个容易误读的地方：2026-07-21 是 issue date，不是今天已经发行后的持有状态。当前日期是 2026-07-17，拍卖已经完成，但部分证券要到 2026-07-21 才正式交割发行。

### 为什么重要

T-Bill 拍卖表给初学者三个信息：

```text
价格：我每 100 美元面值要付多少钱
期限：钱什么时候回来
收益率：折价和投入资金之间的年化关系
需求：拍卖认购是否充足
```

用 2026-07-16 的 4-week T-Bill 举例：

```text
Face Value = 100
Discount Rate = 3.660% = 0.0366
Time = 28 days

Price = 100 x (1 - (0.0366 x 28) / 360)
Price = 100 x (1 - 0.0028467)
Price = 99.71533
```

这和 FiscalData 返回的 price per 100 = 99.715333 基本一致。也就是说，每 100 美元面值，买入价约 99.715333 美元；到期拿 100 美元，差额约 0.284667 美元。若按 1,000 美元面值理解，买入价约 997.15333 美元，到期拿 1,000 美元，差额约 2.84667 美元。

这不是“4 周赚 3.66 美元”。3.660% 是年化贴现率口径，不是每 100 美元 4 周直接赚 3.660 美元。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| FOMC target range | 3.50%-3.75% | Federal Reserve, 2026-06-17 | 政策利率背景 |
| Effective federal funds rate | 3.63% | H.15, 2026-07-15 数据 | 短端利率锚 |
| 4-week T-Bill secondary rate | 3.64% | H.15, 2026-07-15 | 市场背景 |
| 3-month T-Bill secondary rate | 3.70% | H.15, 2026-07-15 | 市场背景 |
| 6-month T-Bill secondary rate | 3.77% | H.15, 2026-07-15 | 市场背景 |
| 1-year T-Bill secondary rate | 3.80% | H.15, 2026-07-15 | 期限比较 |
| 4-week auction high investment rate | 3.721% | Treasury FiscalData, auction date 2026-07-16 | 拍卖案例 |
| 4-week price per 100 | 99.715333 | Treasury FiscalData, auction date 2026-07-16 | 手算价格 |
| 8-week auction high investment rate | 3.722% | Treasury FiscalData, auction date 2026-07-16 | 期限比较 |
| 17-week auction bid-to-cover | 3.35 | Treasury FiscalData, auction date 2026-07-15 | 需求指标 |
| SGOV 30 Day SEC Yield | 3.57% | iShares, 2026-07-15 | 短债 ETF 对照 |

### 这些现实事件如何连接理论

现金管理可以从“收益率比较”推进到“期限匹配”：

```text
H.15 短端利率：
告诉我们市场短期利率的大背景

FiscalData 拍卖结果：
告诉我们新发行 T-Bill 的价格、收益和需求

TreasuryDirect 规则：
告诉我们 T-Bill 的到期、面值、折价和购买限制

ETF / money market fund 页面：
告诉我们把 T-Bill 包进基金工具后，收益率口径和流动性规则会变
```

如果某人有 20,000 美元，6 个月内可能陆续用钱，一个入门级阶梯可以这样思考：

```text
马上可能用：银行存款或货币市场基金
4 周后可能用：4-week T-Bill
8 周后可能用：8-week T-Bill
13 周后可能用：13-week T-Bill
26 周后可能用：26-week T-Bill
```

这只是教学结构，不是配置建议。真实情况还要看税务、账户、平台、结算、最低购买金额、是否需要提前卖出、以及所在国家/地区的合规限制。

### 至少一个真实市场机制案例

2026-07-16 的 4-week T-Bill auction 是一个完整的机制案例：

```text
Auction date：2026-07-16
Issue date：2026-07-21
Maturity date：2026-08-18
High discount rate：3.660%
High investment rate：3.721%
Price per 100：99.715333
Bid-to-cover：2.57
```

这张表把“现金管理”变成可核验现金流：你知道什么时候拍卖、什么时候交割、什么时候到期、每 100 面值要付多少钱、收益率口径是什么、市场需求大概如何。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：U.S. Treasury 国债发行制度、Federal Reserve 货币政策、短端资金市场、银行与经纪账户基础设施。
- 已确认事实：TreasuryDirect 说明 T-Bill 期限从 4 周到 52 周，通常折价或按面值出售，到期支付面值；H.15 提供短端利率背景；FiscalData 提供官方拍卖结果。
- 市场可能如何传导：FOMC 政策利率影响短端利率，短端利率影响 T-Bill 拍卖收益、货币市场基金收益和短债 ETF 收入口径；财政部发行供给和市场需求影响 auction result。
- 仍需核验或观察：未来 FOMC 决策、H.15 短端利率、后续 T-Bill 拍卖 high investment rate、bid-to-cover、财政部发行规模和个人账户的结算规则。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Treasury Bill | 美国国库券 | 1 年以内到期的美国短期国债 | 现金管理核心工具 |
| Face Value | 面值 | 到期时支付的金额 | 计算利息的终点 |
| Discount | 折价 | 低于面值买入 | T-Bill 收益来源 |
| Price per 100 | 每 100 面值价格 | 买 100 美元面值要付多少钱 | 官方拍卖表核心字段 |
| Discount Rate | 贴现率 | 用面值和 360 天表达折价 | 不等于简单到手 APY |
| Investment Rate | 投资利率 | 更接近投入资金收益的年化口径 | 更适合横向比较 |
| Auction Date | 拍卖日 | 出价并确定拍卖结果的日期 | 区分交易和交割 |
| Issue Date | 发行日 | 证券正式交割日期 | 现金开始被占用 |
| Maturity Date | 到期日 | 到期收回面值的日期 | 和用钱日期匹配 |
| Bid-to-Cover | 认购倍数 | 投标量除以接受量 | 观察拍卖需求 |
| T-Bill Ladder | 国库券阶梯 | 分散到不同到期日 | 管理流动性和再投资 |
| Rollover | 滚动续投 | 到期后继续买下一期 | 会遇到新利率 |
| Reinvestment Risk | 再投资风险 | 续投时利率可能降低 | 短期工具核心风险 |
| Secondary Market | 二级市场 | 已发行证券转让市场 | 中途卖出会受价格影响 |
| Settlement | 结算 | 资金和证券正式交割 | 决定现金何时真正离开账户 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和利率、第 49 课 ETF 交易机制、第 53 课债券基金、第 54 课现金管理。
- 本课哪些内容会在后续课程继续使用：收益率曲线、货币政策传导、短端利率、应急资金分层、基金收益率口径比较。
- 如果看不懂本课，可以先回到：第 54 课，重新区分银行存款、货币市场基金、T-Bill 和短债 ETF。

## 案例拆解

- 案例对象：2026-07-16 4-week Treasury Bill auction。
- 已确认事实：
  - Auction date 为 2026-07-16。
  - Issue date 为 2026-07-21，maturity date 为 2026-08-18。
  - High discount rate 为 3.660%，high investment rate 为 3.721%。
  - Price per 100 为 99.715333。
  - Bid-to-cover ratio 为 2.57。
  - H.15 2026-07-15 的 4-week T-Bill secondary market rate 为 3.64%。
- 来源日期和链接：见本课“来源”。
- 分析推理：拍卖 high discount rate 和 H.15 secondary market rate 接近，但不是同一个口径；auction price 把折价现金流锁定到具体 issue date 和 maturity date；bid-to-cover 说明拍卖需求，但不能单独作为投资判断。
- 后续验证指标：下次 4-week / 8-week / 13-week / 26-week auction high investment rate、price per 100、bid-to-cover、H.15 短端利率、FOMC statement 和个人账户结算规则。

## 一个可复制的 T-Bill 阶梯检查页

```text
现金用途：
总金额：
最晚需要用钱日期：
是否可以接受中途卖出：

当前短端利率背景：
- Effective federal funds rate：
- 4-week T-Bill：
- 3-month T-Bill：
- 6-month T-Bill：
- 1-year T-Bill：

阶梯安排：
- 立即可用现金：
- 4-week：
- 8-week：
- 13-week：
- 26-week：

每一期记录：
- Auction date：
- Issue date：
- Maturity date：
- High discount rate：
- High investment rate：
- Price per 100：
- Bid-to-cover：
- 到期后用途：花掉 / 续投 / 转入其他现金工具

风险边界：
- 提前用钱怎么办：
- 利率下降怎么办：
- 平台结算延迟怎么办：
- 税务和账户规则如何处理：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：T-Bill 不是只记收益率，要同时记录 auction date、issue date、maturity date 和 price per 100。
- 对持仓或基金选择的启发：短债 ETF 和 T-Bill ladder 可以服务相似现金管理目标，但 ETF 更重交易便利，T-Bill 更重明确到期现金流。
- 对工作、收入、消费或风险管理的启发：应急资金可以分层，最急的钱保持高流动性，确定期限的钱才考虑具体到期日工具。

## 结论边界

- 可以确定：T-Bill 通常折价或按面值出售，到期支付面值；discount rate、investment rate 和 price per 100 是不同口径；T-Bill ladder 可以分散到期日。
- 不能确定：本课不能预测未来 T-Bill 利率、FOMC 决策、财政部拍卖需求或任何阶梯方案的最优比例。
- 需要继续观察：短端利率、FOMC、Treasury auction results、财政部发行规模、个人账户平台规则和税务处理。
- 不构成投资建议的原因：本课只解释 T-Bill 机制和现金流框架，不建议买入、卖出、续投或配置任何具体期限。

## 练习题

1. T-Bill 没有票息，收益从哪里来？用“买入价、面值、到期日”三个词解释。
2. 2026-07-16 的 4-week T-Bill price per 100 为 99.715333。若买 1,000 美元面值，到期前不提前卖出，折价差额约是多少？
3. Discount rate 和 investment rate 为什么不能混为一谈？
4. 如果 13 周后可能需要用钱，为什么不应该把所有现金都买成 26-week T-Bill？
5. 设计一个 4 档 T-Bill ladder，并写出每档到期后“花掉、续投、转入存款或货币市场基金”的规则。

## 学习交接

- 本课已经完成：把 T-Bill 从“短期国债”推进到拍卖口径、价格公式、阶梯安排和再投资风险。
- 本课最重要的一句话：T-Bill ladder 的重点不是预测利率，而是让现金按不同日期有序回到你手里。
- 需要复习的关键词：Treasury Bill、Discount Rate、Investment Rate、Price per 100、Auction Date、Issue Date、Maturity Date、Bid-to-Cover、T-Bill Ladder、Rollover、Reinvestment Risk。
- 还不稳定、下次要回看的地方：短端利率为什么会变，FOMC、SOFR、H.15、国库券供需和货币市场基金收益率之间如何传导。
- 适合下次打开仓库先读的文件：`lessons/2026-07-17-lesson-55-tbill-ladder-auction-reinvestment-risk.md`

## 下节课安排

- 建议主题：第五十六课：收益率曲线、FOMC、SOFR 与现金收益率传导入门。
- 学习目标：理解政策利率、effective federal funds rate、SOFR、T-Bill rate、money market fund yield 和短债 ETF yield 为什么会联动但不完全相同。
- 建议案例：使用 Federal Reserve H.15、FOMC statement、New York Fed SOFR 页面和一个货币市场基金/短债 ETF 页面，画出短端利率传导链。
- 必须解释的关键词：Policy Rate、Target Range、Effective Federal Funds Rate、SOFR、Treasury Bill Rate、Repo、Yield Curve、Basis、Lag、Pass-through。
- 下节课开始前需要联网核验的数据：最新 FOMC statement、H.15 short rates、New York Fed SOFR、Treasury FiscalData auction results、货币市场基金 7-day yield 和短债 ETF 30 Day SEC Yield。

## 来源

- TreasuryDirect, Treasury Bills: https://www.treasurydirect.gov/marketable-securities/treasury-bills/
- TreasuryDirect, Understanding Pricing and Interest Rates: https://www.treasurydirect.gov/marketable-securities/understanding-pricing/
- U.S. Treasury FiscalData API, Auctions Query: https://api.fiscaldata.treasury.gov/services/api/fiscal_service/v1/accounting/od/auctions_query
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- iShares SGOV product page: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
