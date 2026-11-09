# clingen-vcep CHANGELOG

## v1.4.0（2026-11-09）

- **官网全量复核（133 基因逐 GN 拉 CSpec API + 逐证据码机器比对）**：识别出快照后升版的 15 个基因、官方归档的 19 个 legacy 基因，并逐条核对到档位级。
- **19 个 legacy 基因定性矫正**：官方全部为 `legacy=true` / `legacyReplaced=false` / `legacyFullySuperseded=null`，即**仅归档旧记录、不存在替代版**；本地内容仍是该基因当前唯一有效版本。`check_vcep_version.py` 原把 legacy 与 legacyReplaced 混判，产生 19 条伪告警，本次修正为区分「归档（不阻断）」与「真被替代（阻断）」；manifest 对应 19 行标注 `Released｜legacy归档·无替代版`。
- **15 个升版基因版本账补齐**（MECP2 / VWF / KCNQ1 / DICER1 / PMS2 / MSH6 / MSH2 / MLH1 / SERPINC1 / CTLA4 / GALT / ACADVL / ADA / CYP1B1 / SLC6A8）：文件头新增「官网版本」行，写明 GN、版本、Released、lastUpdated 与 2026-11-09 复核标记。
- **CTLA4 PVS1 实质修正（GN122 v2.0）**：Very Strong 补回 `codons 2–172（触发 NMD）` 与 `codons 173–182（跨膜域）` 两条截短边界规则；Strong 由误抄的 exon 3 规则改为官方 `codons 183–201（不触发 NMD、C 端截短 >10%）`。修正前该基因截短变异无法按官边界定档。
- **ADA PP4_Strong 脚注补全（GN114 v2.2）**：补回「若无法在不依赖外源 ADA 补充/基因治疗得分的情况下达到 PP4_Strong，则必须做 CNV 检测」的触发条件，以及 `enzyme replacement` 情形。
- **VWF 双规范比对校正**：GN081（AD 型）与 GN090（AR 型）各自独立核对，确认本地两章与各自官网原文一致，此前 13 条差异系比对脚本合并两章所致，属伪差异。
- **其余差异逐条核定为排版级**（弯引号 vs 直引号、`<` 转义、措辞改写、语法微调），不改内容。
- **结构性校验**：`check_vcep_structure.py` C1–C4 全通过（FAIL=0，WARN=3 均为设计允许的详略差异）。

## v1.3.0（2026-11-09）

- **新增 `VCEP-DDX41.md`（GN159 v1.0，Myeloid Malignancy Variant Curation Expert Panel）**：官网 Released 2026-11-02（lastUpdated 2026-11-02T16:44:00Z），共享转录本 NM_016222.4，覆盖 MONDO:0014809（DDX41 相关家族性髓系肿瘤易感，AD 遗传）。按 ClinGen CSpec API 返回的 28 条 criteriaCodes 原文整理；13 个码全强度不适用（PS2/PS3/PM1/PM3/PM6/PP2/BS2/BS3/BS4/BP1/BP3/BP5/BP6），PP5/BP6 为 ACMG 已废止码。组合规则段标注"官网 API 未返回定制组合表，按 Richards 2015 面板 + Tavtigian 2020 点分制执行口径"。
- **建 `vcep-version-manifest.csv`（首个全量基线）**：该文件此前不存在 → `check_vcep_version.py` 对所有基因返回 `baseline_missing`，"发现升级 0" 属静默假绿。本次按 mapping 全量基因逐条拉 ClinGen CSpec API，写入 基因/GN编号/官方CSpec版本/lastUpdated/cspecStatus/legacyReplaced/最后检测日期。
- **PAH v2.0 → v2.1**：仅 PM1 活性位点残基名勘误 **Glu289 → Gly289**（官网 v2.1，Released 2026-11-03），其余残基列表、强度阈值、组合规则均无变更，不影响判定结果。
- **ATM 版本账补齐**：正文自 v1.5 起已按官网 v1.6 补录（PM5_sup 边界改 p.Leu3048 上游含 p.Arg3047*、BP4+BP7(RNA) 联用澄清、PS4 布尔运算、gnomAD 使用指引），本次仅同步文件头数据日期与 manifest 基线，**规则正文未改**。
- **PALB2 v1.2 → v1.3**：正文 PM5_sup 已是 v1.3 口径（p.His1184 上游，含 p.Tyr1183*），本次更正头部版本声明——此前头部标 v1.2 而正文按 v1.3 写，属版本账自相矛盾。PVS1 四档官网原文仍为 "Use PALB2 PVS1 Decision Tree"，WD40 相关更新在附件决策树内，正文无需改写。
- **`00-索引.md` 对齐**：声明改为 133 基因（132 ClinGen VCEP + 1 CFTR2 数据包）/ 43 个 VCEP 专家组 / 132 条已发布规范，消除长期 C4 WARN（原声明 120 条 vs 实际 131 主文件）。
- **narrative 同步**：新增 `VCEP-DDX41a_概述与疾病.md` / `b_致病.md` / `c_良性.md` / `d_参考.md` 四段。
- **三处对齐进度**：① 本地 clingen-vcep 已更新；② 私有仓 ACMG-VCEP-Data 本机未定位到，待确认位置后同步升版本号 + 记 commit；③ 技能群侧版本号随本轮发版同步。

## v1.2.0（2026-11-03）

- **新增 VCEP-CFTR.md（CFTR2 专家共识数据包）**：ClinGen CSpec 无 CFTR 正式 VCEP，以 CFTR2（Sosnay 2013 PMID 23974870）+ ClinVar 实践为权威来源，新建 `knowledge-base/VCEP-CFTR.md`，核心为 **TG 重复 + polyT 单倍型维度**（5T/7T + TG11-13 定档表，[R117H;5T]=mild CF-causing / [R117H;7T]=CFTR-RD VVCC）。覆盖 66 条归因 var022/var029。
- **VCEP-GAA.md 补 GAA 专项口径**：leaky splice 非纯 LOF（PVS1 不得 VeryStrong，按 PS3_Supporting/降档处理）+ 同义变异严禁 PVS1（走 BP7/BP4）+ BS1 须组合。覆盖 var124/var129。
- **VCEP-USH2A.md 补逐变异裁定记录**：var097/098/102/105/106 五条归因按机制固化裁定指引（非经典剪接→MaxEntScan+PM3、截短→PVS1+PM3 组合、同义→BP7/ClinVar 锚），衔接证据采集层取数纪律。
- **三处同步**：00-索引.md 基因声明 131→132（CFTR 标 `cftr2`）；knowledge_graph.json gene_vcep_index 补 CFTR 条目；check_vcep_structure C1-C4 全过（FAIL=0，WARN 均为设计允许项）。

> 2026-10-15 description 瘦身整改（P1-1）：SKILL.md frontmatter `description` 精简为「职责 + 触发」，移除数据规模细节（131 基因 / 43 VCEP / 120 规范），完整规模信息仍保留于正文第 1.1 / 1.2 节。

## v1.1.0（2026-10-15）

- description 瘦身：移除「131 个基因 / 43 个 VCEP 专家组 / 120 条已发布规范」等数据规模细节，保留职责与触发场景，长度 376→约 200 字符。
