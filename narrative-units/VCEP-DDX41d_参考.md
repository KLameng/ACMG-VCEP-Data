# DDX41（GN159）— Myeloid Malignancy VCEP 规范 v1.0

> 来源：ClinGen CSpec Registry API（GN159，2026-11-09 抓取；官网 Released 2026-11-02）
> 转录本：NM_016222.4

## 一、不适用证据码

官网 applicability 全部为 Not Applicable，不得使用：

- BP1、BP3、BP5、BP6、BS2、BS3、BS4、PM1、PM3、PM6、PP2、PP5、PS2、PS3

## 二、组合规则（执行口径，非官网 API 原文）

> 官网 CSpec API 只返回 28 条 criteriaCodes 与基因-疾病映射，不返回定制组合表。

1. ACMG/AMP 2015 组合面板（Richards 2015），与本技能群通用组合规则一致。
2. Tavtigian 2020 点分制：Very Strong=8、Strong=4、Moderate=2、Supporting=1；Pathogenic ≥10，Likely Pathogenic 6–9，VUS 0–5，Likely Benign −1 至 −6，Benign ≤−7。
3. 两套结论冲突时按 acmg-conflict-summary-output 冲突消解矩阵处理，保留更强结论并标注分歧。

## 三、官方链接

- cspec UI：https://cspec.genome.network/cspec/ui/svi/id/GN159
- cspec API：https://cspec.genome.network/cspec/api/SequenceVariantInterpretation/id/GN159
- 附件（决策树/评分表）：本版 API 未返回附件列表，需到 cspec UI 下载；索引见 clingen-vcep/attachment-index.csv

## 四、数据来源与免责

- 本叙述单元由 ClinGen CSpec API 返回的 criteriaCodes 原文整理，未添加非官网内容（组合规则段除外，已标注为执行口径）。
- 临床变异评级最终以 ClinGen cspec 官网最新版为准；本地与官网冲突时官网优先。
