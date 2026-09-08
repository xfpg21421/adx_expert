# 07_追踪Cookie与归因

> **本目录用途**：回答**"怎么知道广告有效果、功劳算给谁"**。这是广告技术的"记账系统"，
> 也是过去五年变化最剧烈的领域（ATT、第三方 Cookie 淘汰、SKAdNetwork、Privacy Sandbox）。

**在全局中的位置**：技术主干的第二个专项深化，同时是**实战困惑最集中**的目录——
"为什么平台后台、MMP、GA4、财务收入四个数不一样"这类问题的答案都在这里。

---

## 文档清单

### 追踪层（数据怎么采集）
- [ ] `广告追踪体系总览.md` —— 一张图串起：标识 → 采集（Pixel/SDK/服务端）→ 传输 → 匹配 → 归因 → 报表 → 结算
- [ ] `Cookie原理与分类.md` —— Cookie 机制（Domain / Path / Expires / SameSite / Secure / HttpOnly）、一方 vs 三方、写入与读取时机、浏览器隐私策略演进
- [ ] `第三方Cookie消亡与替代方案.md` —— Chrome 政策时间线与反复、Safari ITP / Firefox ETP 现状、替代方案全景（Privacy Sandbox / Unified ID / 上下文 / 一方数据）
- [ ] `设备标识体系-IDFA-GAID-CAID-OAID.md` —— iOS ATT 与 IDFA 授权率现状、Android Privacy Sandbox、CAID 争议与合规性、OAID、各标识可用性与精度对照
- [ ] `追踪像素与SDK埋点.md` —— Pixel 的实现与局限、SDK 埋点体系、事件设计规范、埋点丢数的常见原因、服务端 vs 客户端埋点权衡
- [ ] `曝光与点击追踪链路.md` —— 曝光宏（`AUCTION_PRICE` 等）、点击跳转与重定向链、Tracking URL 结构、去重与防刷、监测代码部署位置
- [ ] `服务端追踪与S2S回传.md` —— Postback / Server-to-Server 原理、Click ID 传递、回传时延与重试、为什么比客户端可靠、Meta CAPI / Google Enhanced Conversions

### 归因层（功劳怎么分配）
- [ ] `归因模型总览.md` —— 规则型（Last/First/Linear/Time Decay/U-Shape）vs 算法型（DDA/Shapley）；各模型的**偏差方向**；平台默认口径对照表
- [ ] `多触点归因MTA.md` —— 用户级路径归因实现、跨设备跨渠道打通难点、Shapley Value 计算、MTA 在隐私时代的失效与转型
- [ ] `营销组合模型MMM.md` —— 聚合数据回归、Adstock 与 Saturation 曲线、贝叶斯 MMM（Google LightweightMMM / Meta Robyn）、与 MTA 的互补关系
- [ ] `增量实验与因果归因.md` —— **唯一因果口径**：对照组设计、Geo Test、Ghost Ads、PSA 实验、Holdout、Lift 计算与常见错误
- [ ] `MMP移动归因平台.md` —— AppsFlyer / Adjust / Kochava / Branch / Singular 对比；归因优先级与去重逻辑、SAN 对接、Raw Data 出口、扣量与作弊防护
- [ ] `SKAdNetwork与Apple隐私归因.md` —— SKAN 2.0→3.0→4.0 演进、Conversion Value 编码、Postback 窗口与层级、Crowd Anonymity、粗值/细值、SSOT 方案、实战局限

### 实战层
- [ ] `归因口径对账方法.md` —— 为什么平台后台 / MMP / GA4 / 财务收入四个数不一样；口径差异清单；对账流程与容差标准

**建议顺序**：追踪体系总览 → 归因模型总览 → SKAdNetwork → 归因口径对账（认知 + 实战两头兼顾）→ 其余按需

---

## 写作要点

- **严格区分两层**：「追踪」是数据采集（能不能拿到），「归因」是功劳分配（拿到了怎么算）。
  90% 的混淆来自把两层混为一谈。每篇文档开头先声明自己讲哪一层。
- 归因模型必须写清**偏差方向**，不只写定义：

| 模型 | 系统性偏向 | 谁会喜欢它 |
|---|---|---|
| Last Click | 偏向漏斗底部（搜索、再营销、优惠券站） | 效果渠道、Affiliate |
| First Click | 偏向漏斗顶部（展示、信息流） | 品牌渠道 |
| Linear | 平均化，掩盖真实贡献 | 不想做取舍时 |
| DDA / Shapley | 需要足够数据量，小样本不可靠 | 大型广告主 |
| Incrementality | 唯一因果口径，但成本高、周期长 | CFO / 增长负责人 |

- **口径对账**是本目录最有实战价值的产出，要写成可直接执行的 Checklist：
  归因窗口差异 / 是否含 VTC / 去重逻辑 / 时区 / 币种 / 是否扣 IVT / 平台自报 vs 第三方。
- 涉及 Apple / Google 政策的一律标 `[政策]` + 时点，且列入 `研究进度看板.md` §六 失效复核清单（每季度复核）。

## 关联目录

- 转化数据如何回流成训练样本 → [`../05_技术架构与系统实现/实时数据管道与特征系统.md`](../05_技术架构与系统实现/)
- 延迟反馈建模 → [`../05_技术架构与系统实现/CVR预估与延迟反馈.md`](../05_技术架构与系统实现/)
- 归因劫持与作弊 → [`../13_反作弊与流量质量/归因劫持与SDK欺骗.md`](../13_反作弊与流量质量/)
- Affiliate 追踪链路 → [`../09_联盟营销Affiliate/联盟追踪技术与Postback.md`](../09_联盟营销Affiliate/)
- 隐私法规 → [`../08_海外广告生态/海外隐私法规-GDPR-CCPA-TCF.md`](../08_海外广告生态/)
- 无 Cookie 时代的整体推演 → [`../16_前沿趋势与专题/无Cookie时代的身份方案.md`](../16_前沿趋势与专题/)
