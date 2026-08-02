# 第七十二课：结构化产品发行人信用与二级市场估值入门：信用利差、估计价值、做市报价与退出成本

## 基本信息

- 日期：2026-08-02
- 数据截至：2026-08-02（Asia/Shanghai）。结构化票据案例采用 SEC EDGAR 已核验的 2026 年 424B2 定价补充文件；Federal Reserve H.15 采用 2026-07-31 发布、数据截至 2026-07-30；FINRA 和 SEC 投资者教育材料采用当前可访问版本。
- 主题：为什么结构化票据的“1,000 美元发行价”不等于“1,000 美元随时可卖回”，以及为什么先看发行人信用和估计价值。
- 学习目标：理解 issuer credit risk、guarantor、senior unsecured debt、estimated value、issue price、underwriting fee、proceeds to issuer、secondary market bid、market making、bid-ask spread、credit spread、liquidity discount 和 conflict of interest。
- 相关资产：Jefferies Financial Group Inc. 三指数 worst-performing 自动赎回票据、JPMorgan Chase Financial Company LLC 三指数 least-performing callable contingent interest notes、Citigroup Global Markets Holdings Inc. 复杂指数挂钩自动赎回票据、短端美债利率。
- 核心来源：
  - SEC EDGAR, Jefferies Financial Group Inc., Senior Autocallable Contingent Coupon Barrier Notes due July 15, 2032, Pricing Supplement dated 2026-07-10: https://www.sec.gov/Archives/edgar/data/96223/000114036126028453/ef20077971_424b2.htm
  - SEC EDGAR, JPMorgan Chase Financial Company LLC, Callable Contingent Interest Notes linked to the least performing of NDX, RTY and SPX due May 5, 2028, Pricing Supplement dated 2026-06-02: https://www.sec.gov/Archives/edgar/data/19617/000191870426015650/form424b2.htm
  - SEC EDGAR, Citigroup Global Markets Holdings Inc., Autocallable Contingent Coupon Equity Linked Securities linked to S&P 500 Futures 40% Intraday Edge Volatility TCA 6% Decrement Index due May 1, 2031, Pricing Supplement dated 2026-04-27: https://www.sec.gov/Archives/edgar/data/831001/000095010326006435/dp245915_424b2-us26e0020d.htm
  - SEC EDGAR, Jefferies Financial Group Inc. Form 10-Q for quarter ended 2026-05-31: https://www.sec.gov/Archives/edgar/data/96223/000009622326000025/jef-20260531.htm
  - SEC EDGAR, JPMorgan Chase & Co. Form 10-Q for quarter ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/19617/000162828026029344/0001628280-26-029344-index.htm
  - SEC Investor.gov, Investor Bulletin: Structured Notes, 2015-01-12: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
  - FINRA Regulatory Notice 12-03, Heightened Supervision of Complex Products, 2012-01-17: https://www.finra.org/rules-guidance/notices/12-03
  - FINRA, Understanding Structured Notes With Principal Protection, 2023-04-12: https://www.finra.org/investors/insights/structured-notes-principal-protection
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-31: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

先从一个很直观的问题开始：

```text
如果一张结构化票据发行价是 1,000 美元，
为什么文件里还会写 estimated value 是 959.40 美元、964.30 美元，甚至 878.40 美元？
```

这不是简单的“马上亏了多少”问题，而是一个读表入口。结构化票据通常把两样东西包在一起：

```text
发行人债务部分：发行人承诺按条款付款
嵌入式衍生品部分：付款公式跟股票、指数、利率、商品或汇率相关
```

发行价包含销售、结构设计、对冲和发行安排等成本；估计价值是发行人或其关联方在定价日用模型估出来的经济价值。二者不同，说明这不是像交易所股票那样“同一时点有连续公开买卖盘口”的产品。

### 参考的教材式概念顺序

1. Debt obligation：债务义务，票据首先是发行人的债。
2. Senior unsecured debt：高级无担保债，地位通常高于次级债，但没有具体资产抵押。
3. Issuer credit risk：发行人信用风险，发行人不能付款时，条款写得再好也可能无法兑现。
4. Guarantor：担保人，承诺支持发行人付款，但担保也取决于担保人信用。
5. Issue price：发行价，投资者认购时支付的价格。
6. Estimated value：估计价值，发行人按模型估计的定价日价值，不是保证回购价。
7. Underwriting fee / selling commission：承销费或销售佣金，发行和销售链条里的成本。
8. Proceeds to issuer：发行人实际收到的资金，通常低于投资者支付的公开发行价。
9. Secondary market bid：二级市场买入报价，经纪商或做市方愿意买回的价格。
10. Market making：做市，交易商提供报价，但结构化票据做市往往不是强制义务。
11. Bid-ask spread：买卖价差，买入报价和卖出报价之间的差。
12. Liquidity discount：流动性折价，难卖、卖得急或买方少时，价格可能被压低。

### 核心概念

结构化票据读表时，要把一张 1,000 美元票据拆成四层：

```text
第一层：发行人是谁，担保人是谁
第二层：1,000 美元发行价里，多少是估计价值，多少是销售/结构/对冲成本
第三层：未来付款由哪些观察日、障碍线和公式决定
第四层：如果中途想卖，谁可能报价，报价是否有义务，折价来自哪里
```

估计价值低于发行价，不等于投资者马上就能按估计价值卖出，也不等于一定会亏到估计价值。它提醒你：发行时的价格已经把销售、结构设计、对冲和发行人的资金成本安排放进去了。中途卖出时，报价还会再受到市场波动、利率、发行人信用、剩余期限、挂钩资产表现、仓位规模和对冲平仓成本影响。

### 用自己的话解释

可以把结构化票据想成一张定制合同：

```text
你付 1,000 美元
发行人拿到低于 1,000 美元的净资金
一部分差额支付销售和发行成本
发行人或关联方用模型估计债券部分和衍生品部分
未来是否付款，看发行人信用和公式
如果你提前退出，要看有没有人愿意报价
```

所以“高票息”不能单独看。条件票息较高，通常意味着你把某些风险交给了自己：本金下行风险、发行人信用风险、提前赎回风险、流动性风险、估值模型风险和机会成本。

### 常见误区

- 误区一：有担保人就像银行存款。担保人不是 FDIC 保险，担保仍取决于担保人的偿付能力。
- 误区二：estimated value 是最低保护价。很多文件明确说明估计价值不是未来价值，也不是二级市场最低买回价。
- 误区三：发行价 1,000 美元，所以随时能卖 1,000 美元。非上市结构化票据通常没有交易所连续盘口。
- 误区四：承销费只影响发行人，不影响投资者。销售、结构和对冲成本通常包含在发行价里，投资者实际承担这些成本的经济影响。
- 误区五：信用风险只在发行人破产时才重要。信用利差变化会影响二级市场估值，即使发行人没有违约。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC EDGAR 上 Jefferies 2026-07-10 pricing supplement 显示，该票据是 Jefferies Financial Group Inc. 发行的 senior unsecured obligations，挂钩 NDX、RTY 和 SPX 的 worst-performing underlying；每张票据发行价 1,000 美元，估计价值 964.30 美元，承销折扣和佣金为 3.10%，发行人所得为 96.90%，不在证券交易所上市。文件还说明所有付款取决于 Jefferies 信用风险；Jefferies LLC 可能做市，但没有义务做市，并且可随时停止。

JPMorgan Chase Financial Company LLC 2026-06-02 pricing supplement 显示，该票据由 JPMorgan Chase & Co. 完全且无条件担保；每 1,000 美元本金的 fees and commissions 为 22.25 美元，proceeds to issuer 为 977.75 美元，定价日估计价值为 959.40 美元。文件说明估计价值低于发行价，因为发行价包含 selling、structuring 和 hedging 成本；二级市场价格很可能低于原始发行价，并可能受内部二级市场资金利率、销售佣金、对冲利润、对冲成本和第三方数据或电子平台费用影响。

Citigroup 2026-04-27 pricing supplement 显示，发行人为 Citigroup Global Markets Holdings Inc.，担保人为 Citigroup Inc.，每张 1,000 美元本金的估计价值为 878.40 美元，承销费最高 45 美元，最低发行人所得为 955 美元；文件说明该证券不上市交易，不是银行存款，也不受 FDIC 或其他政府机构保险。

Federal Reserve H.15 2026-07-31 release 显示，截至 2026-07-30，effective federal funds rate 为 3.63%，4-week Treasury bill secondary market rate 为 3.64%，3-month Treasury bill secondary market rate 为 3.69%，10-year Treasury constant maturity 为 4.68%，30-year Treasury constant maturity 为 5.21%。这些利率提供了普通现金和国债收益率背景：当结构化票据展示更高条件票息时，要问它相对现金和国债多出来的部分，究竟对应哪些额外风险。

Jefferies 2026-05-31 Form 10-Q 提供了发行人层面的财务背景。该文件披露，截至 2026-05-31，Jefferies total long-term capital 为 25.31 billion 美元，long-term debt to equity capital ratio 为 1.390:1；Jefferies LLC、JFSI、JIL 和 Jefferies GmbH 等受监管实体披露了 net capital 和 excess net capital。这个 10-Q 不能直接告诉你某张票据会不会付款，但它是核验发行人信用背景的正式入口。

### 为什么重要

同样写着 1,000 美元本金，三个案例的发行价、估计价值和成本披露不同：

| 案例 | 发行价 | 定价日估计价值 | 主要成本或差额披露 | 流动性披露 |
| --- | ---: | ---: | --- | --- |
| Jefferies 2026-07-10 | 1,000 美元 | 964.30 美元 | 承销折扣和佣金 3.10%，发行人所得 96.90% | 不上市；Jefferies LLC 可做市但无义务 |
| JPMorgan 2026-06-02 | 1,000 美元 | 959.40 美元 | fees and commissions 22.25 美元，发行人所得 977.75 美元 | 二级市场价格可能低于发行价 |
| Citigroup 2026-04-27 | 1,000 美元 | 878.40 美元 | 承销费最高 45 美元，最低发行人所得 955 美元 | 不上市；非 FDIC 保险 |

初学者的读表顺序应当是：

```text
先看发行人和担保人
再看发行价、估计价值、费用和发行人所得
再看付款公式
最后看二级市场退出条件
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| Jefferies 票据规模 | 6,035,000 美元 | SEC EDGAR, 2026-07-10 | 产品规模 |
| Jefferies estimated value | 964.30 美元 per note | SEC EDGAR, 2026-07-10 | 估值差 |
| Jefferies underwriting discount | 3.10% | SEC EDGAR, 2026-07-10 | 成本 |
| JPMorgan estimated value | 959.40 美元 per 1,000 principal | SEC EDGAR, 2026-06-02 | 估值差 |
| JPMorgan fees and commissions | 22.25 美元 per note | SEC EDGAR, 2026-06-02 | 销售成本 |
| Citigroup estimated value | 878.40 美元 per security | SEC EDGAR, 2026-04-27 | 复杂指数票据估值差 |
| Citigroup underwriting fee | 最高 45 美元 per security | SEC EDGAR, 2026-04-27 | 成本 |
| EFFR / 3-month T-Bill / 10Y Treasury | 3.63% / 3.69% / 4.68% | Fed H.15, 2026-07-30 | 利率背景 |
| FINRA complex products | 复杂产品需增强监督和合理尽调 | FINRA Notice 12-03 | 监管背景 |

### 这些现实事件如何连接理论

第一条链：发行价到估计价值。

```text
投资者支付 issue price
-> 发行价包含销售、结构设计、对冲和平台等成本
-> 发行人用模型拆出债务部分和衍生品部分
-> 得到 estimated value
-> estimated value 通常低于 issue price
```

第二条链：发行人信用到二级市场价格。

```text
发行人信用变弱
-> 信用利差可能扩大
-> 同期限债务折现率上升
-> 票据债务部分价值下降
-> 二级市场 bid 可能下降
```

第三条链：挂钩资产和对冲成本。

```text
参考指数波动上升或价格接近障碍线
-> 嵌入式期权价值变化
-> 发行人对冲成本和风险变化
-> 二级市场报价可能变化
```

第四条链：流动性折价。

```text
票据不上市
-> 可交易买方少
-> 做市方没有持续报价义务
-> 卖出报价可能扣除 bid-ask spread 和 unwind hedge cost
-> 投资者可能需要接受 liquidity discount
```

### 至少一个真实市场机制案例

案例：把 Jefferies、JPMorgan 和 Citigroup 的 1,000 美元票据放在同一张读表卡里。

```text
Jefferies:
1,000 美元发行价
964.30 美元估计价值
3.10% 承销折扣和佣金
不上市，做市无义务

JPMorgan:
1,000 美元发行价
959.40 美元估计价值
22.25 美元 fees and commissions
977.75 美元 proceeds to issuer
二级市场价格可能低于发行价

Citigroup:
1,000 美元发行价
878.40 美元估计价值
最高 45 美元承销费
最低 955 美元发行人所得
不上市，非 FDIC 保险
```

这说明结构化票据的“价格”不是一个单点。至少有四个价格口径：

```text
Issue price：你认购时付多少
Estimated value：发行人定价日模型估多少
Account statement value：账户报表可能显示多少
Secondary market bid：你想卖时别人愿意出多少
```

学习时不要把四个口径混成一个。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC EDGAR 披露制度、FINRA 复杂产品监督、FINRA Rule 5121 冲突披露、经纪商适当性、发行人和担保人信用、非上市证券二级市场安排。
- 已确认事实：Jefferies 文件披露其关联 broker-dealer 参与分销，适用 FINRA Rule 5121 冲突规则；JPMorgan 文件披露 estimated value 低于 original issue price 的原因包括 selling、structuring 和 hedging 成本；FINRA Notice 12-03 要求复杂产品在推荐给散户前进行合理尽调和增强监督。
- 市场可能如何传导：利率和信用利差改变发行人债务部分价值；波动率、股息、指数水平和相关性改变嵌入式衍生品价值；二级市场流动性不足会把这些变化通过更宽报价体现出来。
- 仍需核验或观察：发行人后续 10-Q/10-K、评级或信用利差变化、二级市场实际 bid、是否仍有做市方、投资者账户报表估值口径、税务处理。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Issuer Credit Risk | 发行人信用风险 | 发行人不能按票据付款的风险 | 所有付款都先取决于发行人能否付款 |
| Guarantor | 担保人 | 对发行人付款提供担保的一方 | 担保不是政府保险，仍要看担保人信用 |
| Senior Unsecured Debt | 高级无担保债 | 没有特定抵押物、但清偿顺序高于次级债的债务 | 决定破产或重组时的法律地位 |
| Issue Price | 发行价 | 投资者认购时支付的价格 | 常见为每张 1,000 美元 |
| Estimated Value | 估计价值 | 定价日模型估出的票据价值 | 不是最低回购价，也不是未来价值 |
| Underwriting Fee | 承销费 | 分销和发行安排成本 | 解释发行价和估计价值差异 |
| Proceeds to Issuer | 发行人所得 | 扣除相关费用后发行人收到的资金 | 帮助理解资金流向 |
| Secondary Market Bid | 二级市场买入报价 | 做市方或交易商愿意买回的价格 | 决定中途退出能拿回多少 |
| Market Making | 做市 | 交易商提供买卖报价 | 非上市票据通常没有强制连续做市 |
| Bid-Ask Spread | 买卖价差 | 买入价和卖出价之间的差 | 卖出时的隐性成本 |
| Credit Spread | 信用利差 | 公司债相对无风险利率多付的收益补偿 | 信用变差时票据估值可能下降 |
| Liquidity Discount | 流动性折价 | 因难以卖出而被压低的价格 | 中途退出风险的核心 |
| Conflict of Interest | 利益冲突 | 发行、销售、计算、对冲可能由关联方参与 | 需要读披露，不只看产品宣传 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券与信用风险，第 33 课信用利差，第 68-71 课结构化票据、自动赎回、多标的和复杂指数。
- 本课哪些内容会在后续课程继续使用：estimated value、secondary market bid、market making、account statement value、适当性和持有期监控。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图，先分清债务、所有权、基金和衍生合约。

## 案例拆解

- 案例对象：Jefferies 2026-07-10、JPMorgan 2026-06-02 和 Citigroup 2026-04-27 三份结构化票据定价补充文件。
- 已确认事实：
  - 三个案例的发行价均以每 1,000 美元本金为基本单位。
  - 三个案例均披露 estimated value 低于 issue price。
  - Jefferies 和 Citigroup 案例披露不上市交易；Jefferies 案例披露做市没有持续义务。
  - JPMorgan 案例披露二级市场价格很可能低于原始发行价。
  - 三个案例均强调票据不是普通银行存款或无风险资产。
- 来源日期和链接：见本课“来源”。
- 分析推理：estimated value 与 issue price 的差异，是销售成本、结构设计、对冲成本、资金成本和发行人利润安排共同作用的结果；二级市场 bid 会在此基础上继续受市场和流动性影响。
- 后续验证指标：发行人财报、评级或信用利差、H.15 利率、挂钩指数水平、隐含波动率、二级市场实际报价、观察日结果。

## 一页读表顺序

```text
1. 发行人和担保人
   - issuer 是谁？
   - guarantor 是谁？
   - 是否是 senior unsecured obligation？

2. 发行价和估计价值
   - issue price 是多少？
   - estimated value 是多少？
   - 差额说明了哪些费用和成本？

3. 成本和资金流
   - underwriting fee / selling commission 是多少？
   - proceeds to issuer 是多少？
   - 是否有第三方平台费或对冲利润披露？

4. 二级市场
   - 是否上市？
   - 谁可能做市？
   - 做市是否有义务？
   - bid-ask spread 和 unwind hedging cost 是否披露？

5. 信用和替代方案
   - 同期限无风险利率是多少？
   - 发行人信用背景如何？
   - 更简单的债券、T-Bill 或 ETF 能否达到类似目标？
```

## 个人情境连接

- 对关注清单的启发：以后读结构化产品时，新增四列：`issue price`、`estimated value`、`fees/proceeds`、`secondary market disclosure`。
- 对持仓或基金选择的启发：如果基金持有 ELN 或结构化票据，要问基金披露的是公允价值、交易商报价还是模型估值。
- 对工作、收入、消费或风险管理的启发：任何定制合同都要看“谁承诺、谁担保、谁报价、退出时谁接手”，不只看名义收益。

## 结论边界

- 可以确定：本课所列三份 2026 年 424B2 文件均披露 estimated value 低于 issue price；结构化票据付款取决于发行人或担保人信用；非上市票据二级市场可能有限。
- 不能确定：本课不能预测 Jefferies、JPMorgan、Citigroup 的未来信用变化，不能预测任何票据未来付款、二级市场报价或投资结果。
- 需要继续观察：发行人财报和信用利差、H.15 利率、挂钩资产价格、观察日结果、做市报价、税务文件。
- 不构成投资建议的原因：本课只解释结构化票据估值和退出机制，不建议买入、卖出或持有任何票据、股票、基金、债券或衍生品。

## 练习题

1. 用一句话区分 issue price 和 estimated value。
2. 为什么 estimated value 不是最低保护价？
3. 如果一张票据不上市，二级市场退出会多出哪些风险？
4. 为什么发行人信用利差扩大，可能压低结构化票据的二级市场价格？
5. 打开一份 424B2，找出 issuer、guarantor、issue price、estimated value、fees、proceeds to issuer、listing 和 market making 披露。

## 学习交接

- 本课已经完成：把结构化票据从付款公式推进到发行人信用、估计价值、发行成本、做市报价和退出成本。
- 本课最重要的一句话：结构化票据不是只看 1,000 美元本金和条件票息，而是要同时看谁付款、估值怎么算、发行价包含什么、退出时谁报价。
- 需要复习的关键词：Issuer Credit Risk、Guarantor、Senior Unsecured Debt、Estimated Value、Issue Price、Underwriting Fee、Proceeds to Issuer、Secondary Market Bid、Market Making、Credit Spread、Liquidity Discount、Conflict of Interest。
- 还不稳定、下次要回看的地方：账户报表估值、观察日跟踪、适当性和中途卖出的决策流程。
- 适合下次打开仓库先读的文件：`lessons/2026-08-02-lesson-72-issuer-credit-secondary-market-valuation.md`

## 下节课安排

- 建议主题：第七十三课：结构化产品持有期监控与适当性入门：观察日、账户估值、客户画像与退出决策。
- 学习目标：理解 review date、observation date、interest barrier、trigger value、account statement value、indicative bid、reasonable-basis suitability、customer-specific suitability、liquidity need、time horizon 和 alternative product check。
- 建议案例：使用 JPMorgan 2026-06-02 least-performing callable contingent interest notes 和 Jefferies 2026-07-10 worst-performing notes，建立持有期监控表。
- 必须解释的关键词：Review Date、Observation Date、Interest Barrier、Trigger Value、Account Statement Value、Indicative Bid、Suitability、Customer Investment Profile、Liquidity Need、Time Horizon、Alternative Product Check。
- 下节课开始前需要联网核验的数据：JPMorgan 和 Jefferies 424B2 的观察日和二级市场披露、FINRA Suitability、FINRA Notice 12-03、SEC Regulation Best Interest 或相关投资者教育材料、最新 Fed H.15。

## 来源

- SEC EDGAR, Jefferies 2026-07-10 Pricing Supplement: https://www.sec.gov/Archives/edgar/data/96223/000114036126028453/ef20077971_424b2.htm
- SEC EDGAR, JPMorgan 2026-06-02 Pricing Supplement: https://www.sec.gov/Archives/edgar/data/19617/000191870426015650/form424b2.htm
- SEC EDGAR, Citigroup 2026-04-27 Pricing Supplement: https://www.sec.gov/Archives/edgar/data/831001/000095010326006435/dp245915_424b2-us26e0020d.htm
- SEC EDGAR, Jefferies 2026-05-31 Form 10-Q: https://www.sec.gov/Archives/edgar/data/96223/000009622326000025/jef-20260531.htm
- SEC EDGAR, JPMorgan Chase & Co. 2026-03-31 Form 10-Q filing detail: https://www.sec.gov/Archives/edgar/data/19617/000162828026029344/0001628280-26-029344-index.htm
- SEC Investor.gov, Investor Bulletin: Structured Notes: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
- FINRA Regulatory Notice 12-03: https://www.finra.org/rules-guidance/notices/12-03
- FINRA, Understanding Structured Notes With Principal Protection: https://www.finra.org/investors/insights/structured-notes-principal-protection
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
