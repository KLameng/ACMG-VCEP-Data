# VCEP 基因特异评级数据仓库

> ACMG 变异评级技能群（`ACMG-Variant-Evaluation`）的**独立数据仓库**。技能群本身不含本数据层，运行时由本仓库提供 ClinGen VCEP 基因特异评级规则与版本基线。

## 定位

- **用途**：为技能群的 `ev-*` 证据码判定与 `check_vcep_version.py` 版本校验提供基因特异评级数据（ClinGen VCEP cspec 快照 + 版本清单）。
- **独立入仓**：数据与本仓库版本关联（数据版本号见 `VERSION`），技能群发版时同步记录与 VCEP 数据仓库的关联状态。
- **更新**：数据更新由外部升版监控触发，不依赖技能群运行。定版时跑技能群 `scripts/check_vcep_version.py --refresh-baseline` 重新生成 `vcep-version-manifest.csv`。

## 版本

| 字段 | 值 |
|---|---|
| 数据版本 | v1.4.0 |
| 基因规范数 | 132（另有 CFTR 补充专家共识包，不计入 ClinGen 正式 VCEP 统计） |
| VCEP 专家组数 | 43 |
| 快照日期 | 2026-11-09（正文基线 2026-06-13 + 逐基因官网复核） |
| 官网复核 | 133 个基因逐 GN 拉取 ClinGen CSpec API，逐证据码机器比对（2026-11-09） |
| 来源 | ClinGen CSpec（https://cspec.genome.network/cspec/） |

## 内容结构

| 文件/目录 | 说明 |
|---|---|
| `gene-gn-file-mapping.csv` / `.md` | 基因 ↔ GN 编号 ↔ 规范文件映射（133 行） |
| `vcep-version-manifest.csv` | 版本基线清单（133 条；`cspecStatus` 列标注 `legacy归档·无替代版`） |
| `knowledge-base/` | 每基因一份合并规范 `VCEP-<基因>.md` + 索引 + 核查报告 + 官方附件 |
| `narrative-units/` | VCEP 基因特异叙事单元（1725 个，规范叙述 1717 + 索引叙述 8） |
| `attachment-index.csv` | 附件索引 |
| `SKILL.md` | 数据载体技能说明（clingen-vcep 1.4.0） |
| `CHANGELOG.md` | 数据仓库变更记录 |
| `VERSION` | 数据版本号 |
| `LICENSE` | Apache License 2.0 |

> ⚠️ **定位声明**：本数据为 ClinGen VCEP 规则快照，作为评级辅助快速检阅通道；每次用到 VCEP 规则须联网核实 ClinGen cspec 最新版，以数据库最新更新为准。

## v1.4.0 相对 v1.3.0 的增量

1. **15 个基因补版本账**（MECP2 / VWF / KCNQ1 / DICER1 / PMS2 / MSH6 / MSH2 / MLH1 / SERPINC1 / CTLA4 / GALT / ACADVL / ADA / CYP1B1 / SLC6A8）：文件头新增「官网版本」行（GN / 版本 / Released / lastUpdated / 复核日期）。
2. **CTLA4 PVS1 修正**：补回 `codons 2–172`、`codons 173–182` 两条截短边界规则；Strong 改为官方 `codons 183–201` 规则（此前误抄 exon 3 内容）。
3. **ADA PP4_Strong 脚注补触发条件**（CNV 检测的适用前提）。
4. **manifest 增加 legacy 语义**：19 个官方归档基因标注 `legacy归档·无替代版`，`legacyReplaced` 仅在官网真为 true 时写值。
5. **check_vcep_version.py 语义修正**：区分「legacy 归档（不阻断）」与「真被替代（阻断）」。

## 获取与授权

- 数据源自 ClinGen CSpec **公开数据**。
- 本仓库采用 **Apache License 2.0** 分发。
