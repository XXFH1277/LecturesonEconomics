# 第九十二课：AI 数据中心容量约束入门：电力、并网、冷却、芯片交付和建设周期

## 基本信息

- 日期：2026-08-31
- 数据截至：2026-08-31（Asia/Shanghai）。公司事实使用 Microsoft FY2026 Form 10-K、Alphabet Q2 2026 Form 10-Q 和 Alphabet 2026 proxy；电力系统事实使用 EIA 2026 年 8 月 STEO、AEO2026、DOE 2026 Draft National Transmission Needs Study、PJM 2026 Load Forecast 和 NERC Large Loads Action Plan。
- 主题：为什么云厂商有订单、有资金、有芯片需求，仍可能无法立即形成可出售的 AI 算力。
- 学习目标：理解 Power Availability、Grid Interconnection、MW、MWh、Transmission、Cooling、Commissioning、Construction Lead Time、Capacity Constraint 和 Large Load。
- 相关对象：Microsoft、Alphabet、美国数据中心、电网运营机构和公用事业公司。
- 核心来源：
  - Microsoft FY2026 Form 10-K: https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm
  - Alphabet Q2 2026 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1652044/000165204426000071/goog-20260630.htm
  - Alphabet 2026 proxy water-cooling discussion: https://www.sec.gov/Archives/edgar/data/1652044/000130817926000342/goog-20260424.htm
  - EIA August 2026 Short-Term Energy Outlook: https://www.eia.gov/outlooks/steo/report/elec_coal_renew.php
  - EIA AEO2026 data-center server energy analysis: https://www.eia.gov/todayinenergy/detail.php?id=67704
  - DOE 2026 Draft National Transmission Needs Study release: https://www.energy.gov/oe/articles/does-office-electricity-publishes-2026-draft-national-transmission-needs-study
  - PJM 2026 Load Forecast Report: https://www.pjm.com/-/media/DotCom/library/reports-notices/load-forecast/2026-load-report.pdf
  - NERC Large Loads Action Plan: https://www.nerc.com/initiatives/large-loads-action-plan

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课建立了“投入 -> 资产启用 -> 收入 -> 利润 -> 现金”的回报链。今天追问第一处最容易断掉的环节：

```text
服务器已经订了，客户也在排队，
为什么计算容量还不能马上交付？
```

因为数据中心不是一堆服务器，而是一套必须同时成立的系统：

```text
可建设土地
-> 规划和许可
-> 电网接入与电力供应
-> 变电、配电和备用电源
-> 建筑、网络和冷却
-> 服务器、GPU 和交换机交付
-> 安装、测试和 commissioning
-> 稳定运行后才能出售算力
```

任何一项延迟，前面的资金都可能先进入在建资产，却暂时不能产生完整收入。

### 先分清 MW 和 MWh

- MW（Megawatt，兆瓦）：功率，表示某一时刻需要多大的供电能力。
- MWh（Megawatt-hour，兆瓦时）：能量，表示一段时间实际用了多少电。

白话类比：

```text
MW 像水管每小时最大能流多少水；
MWh 像一天总共用了多少桶水。
```

一个持续使用 100 MW 的负荷，运行 10 小时会消耗约 1,000 MWh。电网规划既要考虑高峰时能否提供足够 MW，也要考虑全年能量、燃料和成本。

### 什么是并网

Grid Interconnection 是电网接入。大型数据中心接入前，公用事业公司或区域电网运营机构通常需要研究：

- 现有输电和变电设施能否承载新负荷；
- 是否需要新建线路、变压器或变电站；
- 高峰时段是否有足够发电和容量；
- 故障或极端天气下能否保持可靠性；
- 谁支付专项设施和网络升级费用。

“附近有电厂”不等于“数据中心可以立即通电”。发电、输电、变电和配电必须在同一时间链上匹配。

### 容量约束的六层地图

| 层级 | 约束 | 财务或经营后果 |
| --- | --- | --- |
| 土地与许可 | zoning、环保审查、社区意见、施工许可 | 项目延迟、土地和合规成本上升 |
| 发电与输电 | 发电能力、线路容量、可靠性标准 | 并网等待、长期购电承诺 |
| 电气设备 | 变压器、开关设备、备用电源 | 交付周期延长、预付款增加 |
| 建筑与冷却 | 建筑、供水、冷却塔或空气冷却 | 资本开支、用水和能耗上升 |
| IT 设备与网络 | GPU、CPU、服务器、光模块、交换机 | 采购承诺、设备短缺、价格上升 |
| 调试与运营 | 安装、测试、人员、稳定运行 | 资产尚未启用、折旧和收入时点推迟 |

### 为什么冷却也是容量约束

芯片耗电后大部分能量最终变成热。冷却系统必须把热量移走，否则设备无法稳定运行。

常见方案包括：

- 风冷：用空气和制冷设备散热；
- 水冷：通过冷却水系统带走热量；
- 液冷：液体更靠近服务器或芯片换热；
- 混合方案：根据地区气候、水资源和设备密度组合使用。

冷却不是免费附属品。它会增加电力、设备、用水、维护和建设需求。高密度 AI 机柜还可能要求重新设计配电与冷却。

### 什么是 Commissioning

Commissioning 可译为“调试投运”。建筑完工不等于资产已经可用。数据中心需要测试供电、备用系统、网络、冷却、安全和软件编排，确认整套系统在正常和故障场景下运行。

这一步解释了上一课的会计现象：

```text
在建资产完成调试
-> 达到预定可使用状态
-> 开始折旧
-> 才能逐步承载客户工作负载
```

### 常见误区

- 误区一：有长期购电合同就一定已经有电。合同、发电项目建设、并网和实际交付是不同环节。
- 误区二：MW 和 MWh 可以互换。一个是瞬时能力，一个是时间累计能量。
- 误区三：买到 GPU 就完成扩容。网络、供电、冷却和调试必须同步。
- 误区四：并网只是行政审批。它还涉及可靠性研究和实际电网升级。
- 误区五：所有公布的数据中心项目都会按计划落地。重复申请、选址变化和取消会让负荷预测高估。
- 误区六：容量受限永远利好。长期无法交付也可能让客户转向竞争者并推高成本。

## 第二大板块：实时背景与市场传导

### Microsoft 10-K 已把物理瓶颈写进风险因素

Microsoft FY2026 10-K 明确披露，数据中心容量依赖可许可、可建设的土地，可预测且可负担的能源，网络供应，以及包括 GPU 在内的服务器和零部件。

公司还列出可能限制扩容的因素：

- 电力可用性限制和取得电力连接延迟；
- 停电、短缺、能源成本上升和公用事业或监管要求；
- 分区、环境审查、许可和社区反对；
- 技术、工程、施工和运营人员短缺；
- 半导体、网络设备、电力系统和冷却设备供应约束；
- 关键部件扩产需要多年投资和交付周期。

截至 2026-06-30，Microsoft 还披露了 346 亿美元的新建筑、改造和租赁改良承诺，主要与数据中心有关。这个金额代表建设承诺，不等于已经投运的容量。

### EIA：数据中心正在改变电力需求路径

EIA 2026 年 8 月 STEO 预计，美国电力部门发电量从 2025 年的 4,430 BkWh 增至 2026 年的 4,508 BkWh，并预计 2027 年达到 4,632 BkWh。EIA 把近年来增长的一部分归因于数据中心电力需求。

同一份 STEO 还把 Texas 2027 年负荷增长预测从上月的 14% 下调至 6%，原因是 2026-08-03 公布的数据中心开发暂停和项目复核。这个例子说明：

```text
负荷预测不是已经发生的用电量，
项目许可、重复申请和建设进度都会改变预测。
```

EIA AEO2026 的长期情景预计，数据中心服务器用电在 2025 年约占商业部门用电的 7%，到 2050 年在不同情景下可能占 22% 至 33%。这是模型情景，不是确定结果。EIA 还假设数据中心楼面制冷需求平均最高可达到普通商业楼面的 2.9 倍能耗强度，说明冷却必须进入容量分析。

### PJM：大负荷增长把“预测准确性”变成基础设施问题

PJM 2026 Load Forecast 预计，未来十年夏季峰值负荷平均每年增长 3.6%，2036 年夏季峰值达到 222,106 MW，比十年起点增加 65,733 MW；净能量负荷预计未来十年平均每年增长 5.3%。这些都是预测值。

PJM 同时改进数据中心和其他大负荷项目的审核，原因是项目可能重复申报、延期或不落地。高估会导致过度采购和不必要建设，低估则可能损害可靠性。

### DOE 与 NERC：约束已进入输电规划和可靠性规则

DOE 2026 Draft National Transmission Needs Study 指出，数据中心、制造业和其他大型工业负荷增长带来新增输电需求；研究识别当前和未来容量约束及拥塞，并强调新发电、新负荷接入和可靠性需要共同规划。

NERC Large Loads Action Plan 则把 computational loads 纳入专门工作，2026 年推进负荷建模、注册标准和扰动表现要求。原因是大型计算负荷规模大、集中，而且可能快速改变用电量，传统模型未必能完整描述其电网影响。

### Alphabet：冷却方案是能源、水和选址的权衡

Alphabet 在 2026 proxy 中表示，公司估计水冷数据中心技术相较风冷平均可降低约 10% 的能源消耗和能源相关排放，但具体结果因地点和技术而异。公司也表示，在高水风险地区会考虑风冷、再生水或海水等替代方案。

这是一个典型的约束权衡：

```text
更节能的冷却方式
可能需要更多水资源；
减少淡水使用的方案
可能增加能耗、设备或建设成本。
```

### 市场和财务传导

```text
并网或设备交付延迟
-> 在建资产停留更久
-> 可售容量低于计划
-> 云收入确认推迟
-> 资本占用和融资成本增加
-> 回收期延长
```

反过来，如果电力、设备和许可按时到位：

```text
资产完成调试
-> 可用容量增加
-> 客户工作负载迁入
-> 云收入和折旧同时上升
-> 利润与自由现金流进入下一阶段验证
```

## 政治、制度和规则视角

### 已确认事实

- Microsoft 最新 10-K 已将土地、能源、并网、供应链、冷却、许可、人员和社区意见列为数据中心扩张风险。
- EIA、DOE、PJM 和 NERC 都已在 2026 年官方材料中单独讨论数据中心或大型计算负荷。
- Alphabet 披露冷却技术需要在能源、水资源和所在地风险之间权衡。

### 分析推理

- 数据中心竞争不只发生在芯片和模型层，还发生在土地控制、电力获取、并网排队、设备供应和施工执行。
- 更早锁定长期电力和关键设备，可能提高交付确定性，但也可能增加 take-or-pay、预付款和需求预测错误风险。
- 公共电网升级成本由谁承担，会影响数据中心项目经济性和居民电价争议。

### 仍需观察

- 预测中的数据中心负荷有多少真正获得土地、许可、融资和电力合同。
- 电网升级和新发电能否按数据中心建设速度投运。
- 高密度 AI 服务器是否改变用水、冷却和备用电源设计。
- 云厂商是否继续披露容量受限，还是转向利用率和价格竞争。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| MW | 兆瓦 | 某一时刻的供电或用电能力 | 衡量峰值负荷和接入容量 |
| MWh | 兆瓦时 | 一段时间累计使用的电量 | 衡量能源消费和电费 |
| Power Availability | 电力可用性 | 当地能否稳定提供所需电力 | 决定项目能否投运 |
| Grid Interconnection | 电网接入、并网 | 把大型负荷安全接入电网的流程 | 常是建设时间瓶颈 |
| Transmission | 输电 | 远距离、大规模输送电力的网络 | 线路拥塞会限制负荷增长 |
| Large Load | 大型负荷 | 用电规模很大的单一客户或设施 | 可能像小城市一样影响电网 |
| Cooling | 冷却 | 把服务器产生的热量移走 | 决定设备密度、能耗和用水 |
| Commissioning | 调试投运 | 完工后测试整套系统并投入使用 | 决定折旧和收入起点 |
| Construction Lead Time | 建设交付周期 | 从规划到投运需要的时间 | 影响回报周期 |
| Capacity Constraint | 容量约束 | 某个环节无法支持更多算力 | 需求强也可能无法交付 |

## 回顾提示

- 建议回顾：第 17 课 CapEx 与自由现金流、第 90 课 PPE 和资产启用、第 91 课投资回报复查。
- 本课会继续使用：MW/MWh、并网、调试投运、容量约束和替代信号。
- 如果看不懂，可以先回到：第 5 课债券、利率和基础设施融资，第 90 课资本开支口径。

## 案例拆解

假设某数据中心项目计划接入 500 MW，服务器已经订购，但公用事业公司要求新建变电站，预计晚 18 个月完成。

1. 服务器采购是否等于 500 MW 容量已经可用？
2. 延迟期间哪些项目可能继续占用现金？
3. 何时才适合把项目视为已开始产生完整折旧和云收入？

参考思路：服务器只是系统一部分；土地、建设、预付款、利息和设备可能继续占用资金；完成并网、安装、测试和调试投运后，容量才进入收入验证。

## 个人情境连接

- 对公司研究：看到“新增数据中心”时，继续问土地、电力合同、并网、设备和投运时间，而不是只记录投资金额。
- 对基金研究：云计算、半导体、电力设备、公用事业和天然气暴露可能通过同一条数据中心链条相关联。
- 对风险管理：把预测、已签约、在建、已通电和已投运分成不同状态，避免把计划当事实。

## 结论边界

### 可以确定

- AI 数据中心容量由土地、电力、电网、冷却、网络、设备、人员和调试共同决定。
- 2026 年官方材料显示数据中心负荷已进入美国电力需求、输电规划和可靠性监管议程。
- 公司和电网运营机构的负荷数字中包含预测，不能等同于已投运用电。

### 不能确定

- 不能从全美或 PJM 预测精确推算某一家云厂商的未来容量或利润。
- 不能断言所有宣布项目都会建设，也不能因并网延迟断言项目最终失败。
- Alphabet 的 10% 节能是公司估计且因地点和技术而异，不能普遍套用。
- 本课不构成投资建议。

## 练习题

1. 用自己的话解释 MW 和 MWh，并举一个 100 MW 负荷运行 5 小时的例子。
2. 把数据中心从选址到投运写成不少于六步的流程。
3. 从 Microsoft 10-K 找出四类物理容量风险，并对应一个财务后果。
4. 为什么 PJM 要审核大负荷预测中的重复或不成熟项目？
5. 水冷和风冷之间可能有哪些能源、水资源和成本权衡？

## 学习交接

- 本课已经完成：把数据中心容量约束拆成土地许可、电力并网、电气设备、建筑冷却、IT 网络和调试运营六层。
- 最重要的一句话：订单和资本开支只有在整套基础设施完成调试后，才会变成可出售容量。
- 需要复习：MW、MWh、Grid Interconnection、Large Load、Cooling、Commissioning。
- 还需继续：并网升级和发电成本最终由数据中心、云客户还是普通电力用户承担。
- 下次打开：本课与 `lessons/2026-08-30-lesson-91-ai-infrastructure-roi-utilization-depreciation-fcf.md`。

## 下节课安排

- 第九十三课：数据中心购电与电网成本入门：PPA、大负荷费率、共址发电、灵活用电和成本分摊。
- 学习目标：理解数据中心怎样获得长期电力，以及电网升级成本如何通过合同和费率分配。
- 建议案例：FERC 2026 Large Load Show Cause Orders、Amazon 和 Alphabet 最新能源合同披露。
- 必须解释：PPA、Take-or-pay、Large Load Tariff、Demand Charge、Cost Recovery Agreement、Co-location、Flexible Load。

## 来源

- Microsoft FY2026 Form 10-K: https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm
- Alphabet Q2 2026 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1652044/000165204426000071/goog-20260630.htm
- Alphabet 2026 proxy: https://www.sec.gov/Archives/edgar/data/1652044/000130817926000342/goog-20260424.htm
- EIA August 2026 STEO: https://www.eia.gov/outlooks/steo/report/elec_coal_renew.php
- EIA AEO2026 data-center analysis: https://www.eia.gov/todayinenergy/detail.php?id=67704
- DOE 2026 Draft National Transmission Needs Study release: https://www.energy.gov/oe/articles/does-office-electricity-publishes-2026-draft-national-transmission-needs-study
- PJM 2026 Load Forecast Report: https://www.pjm.com/-/media/DotCom/library/reports-notices/load-forecast/2026-load-report.pdf
- NERC Large Loads Action Plan: https://www.nerc.com/initiatives/large-loads-action-plan
