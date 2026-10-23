# VCEP 基因特异评级数据仓库

> ACMG 变异评级技能群（`ACMG-Variant-Evaluation`）的**独立数据仓库**。技能群本身不含本数据层，运行时由本仓库提供 ClinGen VCEP 基因特异评级规则与版本基线。

## 定位

- **用途**：为技能群的 `ev-*` 证据码判定与 `check_vcep_version.py` 版本校验提供**基因特异评级数据**（Cligen VCEP cspec 快照 + 版本清单）。
- **独立入仓**：数据与本仓库版本关联（见 MANIFEST 的 `vcep_data_version`），技能群发版时同步记录与 VCEP 数据仓库的关联状态。
- **更新**：数据更新由外部升版监控触发，不依赖技能群运行。定版时跑技能群 `scripts/check_vcep_version.py --refresh-baseline` 重新生成 `vcep-version-manifest.csv`。

## 版本

| 字段 | 值 |
|---|---|
| 数据版本 | v1.1.0 |
| 基因数 | 131 |
| VCEP 数 | 43 |
| 快照日期 | 2026-10-23 |
| 来源 | ClinGen CSpec（https://cspec.genome.network/cspec/） |

## 内容结构

| 文件/目录 | 说明 |
|---|---|
| `gene-gn-file-mapping.csv` / `.md` | 基因 ↔ GeneReviews/基因特异规则映射（131 基因） |
| `vcep-version-manifest.csv` | VCEP 版本基线清单（131 条，含 legacy 标注） |
| `narrative-units/` | VCEP 基因特异叙事单元（1721 个） |
| `knowledge-base/` | 知识库辅助数据 |
| `attachment-index.csv` | 附件索引 |
| `SKILL.md` | 数据载体技能说明（clingen-vcep） |
| `CHANGELOG.md` | 数据仓库变更记录 |

> ⚠️ **定位声明**：本数据为 ClinGen VCEP 规则快照，作为评级辅助快速检阅通道；每次用到 VCEP 规则须联网核实 ClinGen cspec 最新版，以数据库最新更新为准。

## 获取与授权

- 数据源自 ClinGen CSpec **公开数据**。
- 本仓库采用 **Apache License 2.0** 分发。
