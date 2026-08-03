# 第七十四课：结构化产品税务与报表口径入门：OID、1099、开放交易、CPDI 与现金不等于税

## 基本信息

- 日期：2026-08-03
- 数据截至：2026-08-03（Asia/Shanghai）。IRS Publication 550 采用 2025 版、IRS 页面显示 2026-03-09 发布并于 2026-06-27 更新；Form 1099-B 采用 IRS 2026 版说明；结构化票据案例采用 SEC EDGAR 已核验的 2026 年 424B2 文件；Federal Reserve H.15 采用 2026-07-31 发布、数据截至 2026-07-30。
- 主题：为什么结构化票据的现金流、账户估值和税务收入不是同一个口径。
- 学习目标：理解 original issue discount、Form 1099-OID、Form 1099-B、contingent payment debt instrument、comparable yield、projected payment schedule、open transaction、ordinary interest income、capital gain/loss、basis adjustment 和 Section 871(m)。
- 相关资产：JPMorgan Chase Financial Company LLC 10 年期 callable range accrual notes、JPMorgan Chase Financial Company LLC S&P 500 capped return enhanced notes、10 年期美国国债收益率、IRS 投资收入申报规则。
- 核心来源：
  - IRS, Publication 550 (2025), Investment Income and Expenses: https://www.irs.gov/publications/p550
  - IRS, About Form 1099-B, Proceeds from Broker and Barter Exchange Transactions: https://www.irs.gov/forms-pubs/about-form-1099-b
  - SEC EDGAR, JPMorgan Chase Financial Company LLC, Callable Range Accrual Notes linked to the 10-Year Constant Maturity Treasury Rate due January 22, 2036, Pricing Supplement dated 2026-01-16: https://www.sec.gov/Archives/edgar/data/19617/000121390026006120/ea0273514-01_424b2.htm
  - SEC EDGAR, JPMorgan Chase Financial Company LLC, Capped Return Enhanced Notes linked to the S&P 500 Index due May 6, 2032, Pricing Supplement dated 2026-05-04: https://www.sec.gov/Archives/edgar/data/19617/000121390026052890/ea0289370-01_424b2.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-31: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲到结构化票据持有期要看观察日、账户估值和实际 bid。今天换一个常被忽视的问题：

```text
我今年没有拿到多少现金，
为什么税表上可能显示我有应税收入？
```

对零基础学习者来说，先把三种口径拆开：

```text
现金口径：今年实际收到多少利息、票息、分配或卖出款
税务口径：IRS 或产品税务处理认为今年应确认多少收入、利得或亏损
估值口径：账户或基金报表上显示这项资产现在值多少
```

三者可能相同，也可能完全不同。结构化票据尤其容易出现差异，因为它同时带有债务、衍生品、发行人信用、提前赎回和税法分类问题。

### 参考的教材式概念顺序

1. Taxable income：应税收入，税法要求计入收入的金额。
2. Cash payment：现金支付，实际到账的钱。
3. Original Issue Discount，OID：原始发行折价，债务工具发行价低于到期赎回价时形成的利息型收入。
4. Form 1099-OID：报告 OID 和部分其他利息的税表。
5. Form 1099-B：经纪商报告卖出股票、债券、期权、债务工具等交易款项的税表。
6. Contingent Payment Debt Instrument，CPDI：或有付款债务工具，未来付款金额不固定，但税务上按债务规则处理。
7. Comparable Yield：可比收益率，发行人用于计算 CPDI 税务应计收入的假设收益率。
8. Projected Payment Schedule：预计付款表，税务计算用的假设现金流，不是付款承诺。
9. Open Transaction：开放交易，一些预付金融合约式票据可能按卖出、赎回或到期时再确认收益或损失的方式处理。
10. Basis Adjustment：成本基础调整，税务上把已确认收入、已收到款项等放进持仓成本计算。

### 核心概念

结构化票据税务入门最重要的一句话是：

```text
先看发行文件写的是哪一种税务处理，
再看 1099 表格，
最后把现金流、应税收入和成本基础分开记录。
```

不是所有结构化票据都按同一种方式纳税。至少会遇到两类常见披露：

```text
CPDI / OID 路径：
税务上按或有付款债务工具处理
-> 可能每年按 comparable yield 确认 OID
-> 当年应税收入可能不同于当年收到的现金

Open transaction 路径：
税务上按开放交易或预付金融合约思路处理
-> 通常更关注卖出、赎回或到期时的收益/损失
-> 但文件会说明 IRS 或法院可能不同意
```

所以学习时不能只问“票息率是多少”，还要问“这张票据在税务上被当成什么”。

### 用自己的话解释

可以把结构化票据想成一张有两套账的合同：

```text
经济账：
我付了多少钱
我收到了多少现金
现在估值是多少
未来公式怎么付钱

税务账：
税法今年让我确认多少收入
这些收入是利息、普通收入、资本利得还是其他口径
我的 adjusted basis 怎么变
卖出或到期时怎么和过去确认过的收入对上
```

OID 的直觉是：如果税务规则认为你在持有一个会随时间累积经济收益的债务工具，即使现金还没有完全收到，也可能要求你把一部分收益按年计入收入。CPDI 的难点在于：未来真实付款不确定，所以发行人会给出一个税务用的假设收益率和预计付款表。

### 常见误区

- 误区一：没有收到现金就一定没有税务收入。OID 和 CPDI 可能让应税收入先于现金出现。
- 误区二：收到 1099-OID 才需要申报。IRS Publication 550 说明，应税 OID 即使没有收到 1099-OID 也要报告。
- 误区三：所有结构化票据都是 OID。部分股票或指数挂钩票据可能披露为 open transaction 处理。
- 误区四：1099-B 只和股票有关。IRS 对 Form 1099-B 的说明包括股票、商品、债务工具、期权等经纪交易。
- 误区五：发行文件里的 projected payment schedule 是收益承诺。它是税务计算用的假设表，不是市场预测，也不是付款保证。

## 第二大板块：实时背景与市场传导

### 发生了什么

IRS Publication 550 当前版本说明，OID 是一种利息，通常随债务工具期限应计入收入，即使投资者没有收到发行人的现金支付。该出版物还说明，Form 1099-OID 会显示年度 OID 和部分其他利息；应税 OID 即使没有收到 1099-OID 也要报告。

JPMorgan Chase Financial Company LLC 2026-01-16 的 callable range accrual notes 挂钩 10-Year Constant Maturity Treasury Rate，票据到期日为 2036-01-22，发行价每张 1,000 美元，selling commissions 为每张 25 美元，发行人所得为每张 975 美元，定价日 estimated value 为每张 946.50 美元。该票据的 interest factor 为 8.30% per annum，但只有在对应日 10 年期 CMT 不高于 5.00% barrier 时才按天累积利息；若高于 barrier，该日利息为 0。

同一份 2026-01-16 pricing supplement 在税务部分说明，发行人拟将该票据按 contingent payment debt instrument 处理；若该处理被尊重，投资者通常需要按 comparable yield 每年确认 OID，并根据实际付款和 projected payment schedule 的差额调整。文件给出的 comparable yield 为 5.07% compounded quarterly；按其表格，每 1,000 美元本金的 2026 年 accrued OID 为 47.31 美元，到 2035 年底累计 accrued OID 为 491.59 美元，到 2036-01-22 为 494.59 美元。文件同时提醒，预计付款表只为税务计算服务，不是实际付款预测或保证。

JPMorgan Chase Financial Company LLC 2026-05-04 的 S&P 500 capped return enhanced notes 则披露另一种税务路径。该票据不支付常规利息或股息，定价日 estimated value 为每 1,000 美元本金 984.20 美元，最终收益取决于 S&P 500 Index 平均初始值和平均最终值。税务部分说明，特殊税务顾问认为按当前市场条件，将该票据作为非债务工具的 open transaction 处理是合理的；如果这种处理被尊重，持有超过一年时收益或损失通常按长期资本收益或损失处理。但文件也明确提醒，IRS 或法院可能不尊重这种处理，未来税务指引也可能改变结果。

Federal Reserve H.15 2026-07-31 release 显示，截至 2026-07-30，effective federal funds rate 为 3.63%，10-year Treasury constant maturity 为 4.68%，30-year Treasury constant maturity 为 5.21%。这给 range accrual notes 的利率背景一个现实锚点：当 10 年期 CMT 接近 5.00% barrier 时，票据的现金利息是否累积会变得更敏感。

### 为什么重要

同样是 JPMorgan 发行或担保链条里的结构化票据，税务读法可能不同：

| 案例 | 经济结构 | 税务披露路径 | 初学者要看的问题 |
| --- | --- | --- | --- |
| 2026-01-16 range accrual notes | 10 年期 CMT 低于 barrier 才按天累息 | 拟按 CPDI 处理，并按 comparable yield 计算 OID | 今年税务收入是否不同于实际收息 |
| 2026-05-04 capped return enhanced notes | 不付常规利息，最终看 S&P 500 表现 | 税务顾问认为 open transaction 处理合理 | 到期或卖出时资本利得/损失如何确认 |

这说明：

```text
产品名字像“note”
不代表每张 note 的税务口径都相同
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| IRS Pub 550 当前版 | 2025 版，IRS 页面显示 2026-03-09 发布 | IRS | OID 和 1099 基础 |
| Range accrual notes issue price | 1,000 美元 per note | SEC EDGAR, 2026-01-16 | 发行价 |
| Range accrual notes estimated value | 946.50 美元 per note | SEC EDGAR, 2026-01-16 | 估值差 |
| Range accrual notes interest factor | 8.30% per annum | SEC EDGAR, 2026-01-16 | 条件利息 |
| Range accrual notes reference rate barrier | 10Y CMT 5.00% | SEC EDGAR, 2026-01-16 | 是否累息的开关 |
| Range accrual notes comparable yield | 5.07% compounded quarterly | SEC EDGAR, 2026-01-16 | CPDI 税务计算 |
| Range accrual notes 2026 accrued OID | 47.31 美元 per 1,000 principal | SEC EDGAR, 2026-01-16 | 现金与税务差异 |
| S&P 500 enhanced notes estimated value | 984.20 美元 per 1,000 principal | SEC EDGAR, 2026-05-04 | open transaction 案例 |
| EFFR / 10Y CMT / 30Y CMT | 3.63% / 4.68% / 5.21% | Fed H.15, 2026-07-30 | 利率背景 |

### 这些现实事件如何连接理论

第一条链：CPDI 到 OID。

```text
票据被拟定为 contingent payment debt instrument
-> 发行人给 comparable yield 和 projected payment schedule
-> 投资者按税务规则逐年确认 OID
-> 实际现金与应税收入可能不一致
-> 卖出、赎回或到期时再用 adjusted basis 对账
```

第二条链：利率到 range accrual 现金流。

```text
10Y CMT <= 5.00% barrier 的日子越多
-> 该期间 accrual days 越多
-> 现金利息越接近 interest factor

10Y CMT > 5.00% barrier 的日子越多
-> 该期间 accrual days 越少
-> 现金利息可能下降甚至为零
```

第三条链：open transaction 到资本利得。

```text
票据不按债务工具处理
-> 持有期间未必按 OID 路径逐年确认
-> 卖出、赎回或到期时确认收益或损失
-> 如果 IRS 不同意，税务时间和性质可能改变
```

第四条链：1099 到个人记录。

```text
收到 1099-OID / 1099-B / 1099-DIV
-> 先核对发行文件和经纪商记录
-> 再核对成本基础、已确认收入和现金流
-> 必要时找税务专业人士处理
```

### 至少一个真实市场机制案例

案例：2026-01-16 JPMorgan range accrual notes 的“现金不等于税”。

```text
本金单位：1,000 美元
到期日：2036-01-22
现金利息公式：看每个日历日 10Y CMT 是否不高于 5.00%
税务处理：拟按 CPDI
税务收益率：5.07% compounded quarterly
2026 年税务 OID：47.31 美元 per 1,000 principal
```

如果某一年市场利率高于 barrier 的日子很多，现金利息可能减少；但税务表仍可能按 comparable yield 和 projected payment schedule 计算当年的 OID 或调整。这个案例的重点不是记住 5.07%，而是知道：

```text
实际到账现金
税务应计收入
到期真实付款
三者可能走不同路径
```

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：IRS 投资收入申报规则、Form 1099 信息报告、SEC EDGAR 发行披露、结构化票据税务不确定性、非美国持有人 Section 871(m) 股息等价物规则。
- 已确认事实：IRS Publication 550 把 OID 作为利息型收入讨论；JPMorgan 2026-01-16 文件披露 CPDI/OID 路径；JPMorgan 2026-05-04 文件披露 open transaction 路径和 IRS 可能不同意的风险；Form 1099-B 覆盖经纪商处理的多类证券和衍生交易。
- 市场可能如何传导：利率变化影响 range accrual notes 的现金利息和估值；税务分类影响投资者税后回报；1099 表格和账户报表口径差异会影响个人现金流规划。
- 仍需核验或观察：每个纳税人的身份、税务居民地、账户类型、买入价格、卖出价格、经纪商 1099、发行人税务补充、未来 IRS 或法院解释。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Original Issue Discount (OID) | 原始发行折价 | 债务工具发行价低于到期赎回价形成的利息型收入 | 可能没收到现金也要确认 |
| Form 1099-OID | OID 税表 | 报告年度 OID 和部分其他利息 | 帮助核对税务收入 |
| Form 1099-B | 经纪交易税表 | 报告卖出证券、债务工具、期权等交易款项 | 卖出票据时常用 |
| Contingent Payment Debt Instrument (CPDI) | 或有付款债务工具 | 未来付款不固定的债务工具 | 结构化票据常见税务路径 |
| Comparable Yield | 可比收益率 | 税务计算用的假设收益率 | 决定年度 OID |
| Projected Payment Schedule | 预计付款表 | 税务计算用的假设现金流 | 不是实际收益承诺 |
| Open Transaction | 开放交易 | 通常到卖出、赎回或到期时再确定收益损失的处理思路 | 与 OID 路径不同 |
| Ordinary Interest Income | 普通利息收入 | 按利息口径纳税的收入 | 税率和申报位置可能不同 |
| Capital Gain/Loss | 资本利得/损失 | 卖出资产或到期结算产生的盈亏 | 和利息收入不是同一性质 |
| Adjusted Basis | 调整后成本基础 | 原始成本加减已确认收入和已收款项后的税务成本 | 决定卖出或到期时盈亏 |
| Section 871(m) | 股息等价物预扣规则 | 对部分挂钩美国股票或指数的金融工具适用的非美国持有人预扣规则 | 跨境投资者要特别核验 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券与利率，第 33 课信用利差，第 68-73 课结构化票据、估计价值、持有期监控和适当性。
- 本课哪些内容会在后续课程继续使用：OID、1099、税务口径、账户估值、成本基础、基金分配税性。
- 如果看不懂本课，可以先回到：第 10 课财务报表三张表，先理解“现金流”和“收入确认”本来就可能不同步。

## 案例拆解

- 案例对象：JPMorgan 2026-01-16 callable range accrual notes linked to 10-Year CMT。
- 已确认事实：
  - 发行价为每张 1,000 美元。
  - selling commissions 为每张 25 美元，发行人所得为每张 975 美元。
  - 定价日 estimated value 为每张 946.50 美元。
  - interest factor 为 8.30% per annum。
  - 10-Year CMT barrier 为 5.00%。
  - 税务披露拟按 CPDI 处理，comparable yield 为 5.07% compounded quarterly。
  - projected payment schedule 和 accrued OID 表用于税务计算，不是实际付款保证。
- 来源日期和链接：见本课“来源”。
- 分析推理：该票据的现金收入取决于每日利率是否满足 barrier；税务收入则取决于 CPDI/OID 规则。两条线都重要，但不能互相替代。
- 后续验证指标：10Y CMT 每日水平、经纪商 1099-OID、Form 1099-B、实际利息付款、发行人信用、是否提前赎回、个人税务身份。

## 个人情境连接

- 对关注清单的启发：结构化产品关注清单新增三列：`tax treatment`、`1099 form expected`、`cash vs taxable income mismatch`。
- 对持仓或基金选择的启发：高分配或高票息产品要看税后回报，不能只看税前现金流。
- 对工作、收入、消费或风险管理的启发：如果个人现金流紧张，税务上先确认收入但现金没有同步到账，会影响年度缴税和预算安排。

## 结论边界

- 可以确定：IRS Publication 550 将 OID 作为利息型收入讨论；JPMorgan 2026-01-16 range accrual notes 披露 CPDI/OID 税务路径；JPMorgan 2026-05-04 S&P 500 enhanced notes 披露 open transaction 税务路径；H.15 已给出 2026-07-30 的利率背景。
- 不能确定：本课不能判断任何具体投资者最终应缴多少税，不能替代税务、法律或会计意见，也不能预测 IRS、法院或未来法规如何处理某张票据。
- 需要继续观察：经纪商年度税表、发行人税务补充、实际付款、卖出或到期价格、未来 IRS 指引、个人账户类型和税务居民身份。
- 不构成投资建议的原因：本课只解释结构化产品税务和报表口径，不建议买入、卖出或持有任何票据、基金、股票、债券或衍生品。

## 练习题

1. 用一句话区分现金收入、税务收入和账户估值。
2. 为什么 CPDI 票据可能出现“没有收到对应现金，但当年有 OID”的情况？
3. 发行文件里的 comparable yield 为什么不是实际收益承诺？
4. 打开任意一份 424B2，找出 tax treatment、estimated value、issue price 和是否有 projected payment schedule。
5. 如果你卖出一张结构化票据，为什么可能同时要看 Form 1099-B、过去的 OID 和 adjusted basis？

## 学习交接

- 本课已经完成：把结构化票据从持有期监控推进到税务分类、OID、1099、CPDI、open transaction 和现金/税务/估值三口径。
- 本课最重要的一句话：结构化票据的实际到账现金、年度应税收入和账户显示估值不是同一个数字，必须分别记录。
- 需要复习的关键词：OID、Form 1099-OID、Form 1099-B、CPDI、Comparable Yield、Projected Payment Schedule、Open Transaction、Ordinary Interest Income、Capital Gain/Loss、Adjusted Basis、Section 871(m)。
- 还不稳定、下次要回看的地方：基金持有 ELN 时，普通投资者看到的是基金 NAV 和分配税性，而不是自己直接持有票据时的 1099-OID 路径。
- 适合下次打开仓库先读的文件：`lessons/2026-08-03-lesson-74-structured-product-tax-reporting-oid-1099.md`

## 下节课安排

- 建议主题：第七十五课：基金持仓穿透与 ELN 暴露入门：N-PORT、NAV、公允价值层级、发行人集中度与分配税性。
- 学习目标：理解 fund holdings、Form N-PORT、NAV、fair value hierarchy、Level 1、Level 2、Level 3、ELN exposure、issuer concentration、Rule 144A、valuation designee 和 distribution tax character。
- 建议案例：使用 JPMorgan Equity Premium Income ETF 的 2026-03-31 N-PORT/portfolio schedule，拆解 common stocks、equity-linked notes、short-term investments、Level 1/Level 2 和发行人集中度。
- 必须解释的关键词：Form N-PORT、NAV、ELN Exposure、Issuer Concentration、Fair Value、Level 1、Level 2、Level 3、Rule 144A、Valuation Policy、Distribution Tax Character。
- 下节课开始前需要联网核验的数据：最新可公开的 JEPI N-PORT 或基金官方持仓、SEC N-PORT 披露规则、SEC Rule 2a-5 公允价值规则、IRS 1099-DIV 或基金分配税性材料、最新 Fed H.15。

## 来源

- IRS, Publication 550 (2025), Investment Income and Expenses: https://www.irs.gov/publications/p550
- IRS, About Form 1099-B: https://www.irs.gov/forms-pubs/about-form-1099-b
- SEC EDGAR, JPMorgan 2026-01-16 Callable Range Accrual Notes Pricing Supplement: https://www.sec.gov/Archives/edgar/data/19617/000121390026006120/ea0273514-01_424b2.htm
- SEC EDGAR, JPMorgan 2026-05-04 Capped Return Enhanced Notes Pricing Supplement: https://www.sec.gov/Archives/edgar/data/19617/000121390026052890/ea0289370-01_424b2.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
