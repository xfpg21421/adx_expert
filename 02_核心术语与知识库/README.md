# 02_核心术语与知识库

> **本目录用途**：项目的**词典层**。所有广告黑话的唯一权威出处。
> 其他目录的文档遇到术语，应链接到这里，而不是各自解释一遍——避免同一个词在 10 篇文档里有 10 种说法。

**在全局中的位置**：贯穿所有目录的基础设施。随研究增量补充，不追求一次写完。

---

## 文档清单

- [x] `术语总索引.md` —— 8 大分类入口 + 收录规范 + 全量术语索引 + 易混对照卡索引
- [ ] `交易与计费术语.md` —— CPM / CPC / CPA / CPS / CPL / CPI / oCPX、RTB、PMP、PGD、Floor Price、GSP / VCG、Take Rate、Rev Share
- [ ] `效果指标术语.md` —— Impression 的各种口径、CTR / CVR / eCPM / RPM、Fill Rate / Show Rate、ROAS / LTV / ARPU / CAC、Viewability、留存与漏斗指标
- [ ] `技术栈与协议术语.md` —— DSP / SSP / ADX / DMP / Ad Server、OpenRTB、VAST / VMAP / VPAID、MRAID、Prebid、Bid Request/Response、SDK、Pixel、Postback
- [ ] `身份隐私与合规术语.md` —— Cookie 三类、IDFA / GAID / CAID / OAID、Device Fingerprint、GDPR / CCPA / TCF / CMP、SKAN、Privacy Sandbox、个保法
- [ ] `归因术语.md` —— Last / First Click、Linear、Time Decay、U-Shape、DDA、MTA、MMM、Incrementality / Lift、GeoLift、Attribution Window、VTC、SAN
- [ ] `联盟与套利术语.md` —— Affiliate / Merchant / Offer / Payout / EPC、Sub ID、Deep Link、CPA Network、Arbitrage、MFA、Parking、RON、Tier 1/2/3、Cloaking
- [ ] `中英对照速查表.md` —— 纯表格，A→Z 排序，中文 ↔ 英文 ↔ 缩写 ↔ 一句话 ↔ 详见文档；用于快速 Ctrl+F

**建议顺序**：术语总索引（已建）→ 交易与计费 → 效果指标 → 技术栈与协议（这三类覆盖 80% 日常疑问）

---

## 写作要点

- 严格套用 [`../00_研究方法与协作规范/术语卡片模板.md`](../00_研究方法与协作规范/术语卡片模板.md)。
- **每条必有英文原文**——一手资料（IAB 标准、平台文档、财报）都是英文，没有英文原文的术语条目视为不合格。
- **易混术语必须成组辨析**，不要孤立解释。混淆清单见术语卡片模板 §四（16 组待补）。
- 涉及平台政策/抽成比例的条目，末尾加 `> 政策时点：YYYY-MM，需以当期官方文档复核`。
- 已失效的旧术语（如 Google Authorship、旧版 SKAN 机制）**保留并标 `【历史】`**，理解演进比知道现状更重要。

## 8 大分类（固定，不要自创）

`角色平台` `交易计费` `效果指标` `技术协议` `身份隐私` `归因` `联盟套利` `合规法务`

## 关联目录

- 项目级 60 词速查 → [`../README.md`](../README.md) §五
- 术语的来源场景 → 各业务目录
