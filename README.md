# VCEP 基因特异评级数据仓库

> ACMG 变异评级技能群（`ACMG-Variant-Evaluation`）的**独立数据仓库**。技能群本身不含本数据层，运行时由本仓库提供 ClinGen VCEP 基因特异评级规则与版本基线。

## 定位

- **用途**：为技能群的 `ev-*` 证据码判定与 `check_vcep_version.py` 版本校验提供基因特异评级数据（ClinGen VCEP cspec 快照 + 版本清单）。
- **独立入仓**：数据与本仓库版本关联（数据版本号见 `VERSION`），技能群发版时同步记录与 VCEP 数据仓库的关联状态。
- **更新**：数据更新由外部升版监控触发，不依赖技能群运行。定版时跑技能群 `scripts/check_vcep_version.py --refresh-baseline` 重新生成 `vcep-version-manifest.csv`。

## 版本

| 字段 | 值 |
|---|---|
| 数据版本 | v1.4.4 |
| 基因规范数 | 132（另有 CFTR 补充专家共识包，不计入 ClinGen 正式 VCEP 统计） |
| VCEP 专家组数 | 43 |
| 快照日期 | 2026-11-12（正文基线 2026-06-13 + 逐基因官网复核） |
| 官网复核 | 133 个基因逐 GN 拉取 ClinGen CSpec API，逐证据码机器比对（2026-11-12 复核版本标注） |
| 来源 | ClinGen CSpec（https://cspec.genome.network/cspec/） |

## 内容结构

| 文件/目录 | 说明 |
|---|---|
| `gene-gn-file-mapping.csv` / `.md` | 基因 ↔ GN 编号 ↔ 规范文件映射（133 行） |
| `vcep-version-manifest.csv` | 版本基线清单（133 条 + 表头，**11 列**：原 7 列 + `本地版本` / `本地版本来源` / `本地版本抽取日期` / `滞后状态`；`cspecStatus` 列标注 `legacy归档·无替代版`） |
| `knowledge-base/` | 每基因一份合并规范 `VCEP-<基因>.md` + 索引 + 核查报告 + 官方附件 |
| `narrative-units/` | VCEP 基因特异叙事单元（1725 个，规范叙述 1717 + 索引叙述 8） |
| `attachment-index.csv` | 附件索引 |
| `SKILL.md` | 数据载体技能说明（clingen-vcep 1.4.4） |
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

## v1.4.4 相对 v1.4.0 的增量（2026-11-12）

> 本节记录 v1.4.4 这一批。README 的版本历史此前停在 v1.4.0 节：v1.4.1 / v1.4.2 的增量未在此补记——此处如实标出该记录缺口，不以推测填充。
> 本版**同时包含 v1.4.3（2026-11-11）的基因数口径修正**（133 = 132 正式 VCEP + 1 个 CFTR2 补充包），详见 `clingen-vcep` CHANGELOG v1.4.3。

1. **58 个基因补「官网版本」标注**：逐 GN 调 ClinGen CSpec API 取 `version` / `lastUpdated` / `cspecStatus`，写入 `VCEP-<基因>.md` 文件头，格式 `> 官网版本：Version X（GNnn，lastUpdated，Released）`；多规范基因（如 RYR1 三 GN）逐个列出。**标注不用于声明「正文即该版本」**，只记官网现网版本与核对日期。
2. **`vcep-version-manifest.csv` 7 列扩为 11 列**：新增 `本地版本` / `本地版本来源` / `本地版本抽取日期` / `滞后状态`。`本地版本` 取文件头 `> 官网版本` 行记载的**核验当时官网版本**，不是正文转录版本；抽不到的写「未标注」，**不用官方版本回填冒充**。
3. **滞后显式化**：归一化比对得 130 `fresh` / 1 `非CSpec(CFTR2)` / **2 `LAG`**——`IDUA`（标注 1.1，官网 1.2）、`MAP2K2`（标注 1.0，官网 2.3）。LAG 含义为「文件头的官网核验记录已过期，须重新核验并重抓正文」，**不是「正文即旧版」**。
4. **两个 LAG 文件头加警示**：`⚠ 2026-11-12 复核：官网已升级至 X.Y（lastUpdated …），本文件正文未随包声明版本，待重抓核对`。

## 数据来源与许可范围

### 数据来源

- **规范正文与版本元数据**：ClinGen Criteria Specification Registry（CSpec，https://cspec.genome.network/cspec/）。2026-11-09 按 133 个基因的 GN 编号逐个拉取并做逐证据码机器比对；2026-11-12 复核全部 133 个基因的官网版本标注。
- **官方附件**：随各 VCEP 规范一并发布的原始附件，按原样归档于 `knowledge-base/knowledge-base/attachments/`。
- **CFTR 补充段落**：ClinGen CSpec 无 CFTR 正式 VCEP。本仓库的四段 CFTR 叙述取自 CFTR2 专家共识（Sosnay et al. 2013, PMID 23974870）与 ClinVar expert-panel reviewed 记录，属共识口径摘要，已在对应文件头注明，不计入 ClinGen 正式 VCEP 统计。

### 原始内容归属

- ClinGen 公布其 curated content 采用 **CC0 1.0 Universal 公有领域贡献**发布，同时要求使用方署名 ClinGen 并说明数据来源（见 https://www.clinicalgenome.org/about/terms-of-use/ ）。原始规范文本、官方附件及版本元数据的著作权与归属为 ClinGen 及各 VCEP 专家组。
- 本仓库与 ClinGen 无隶属关系，**不是 ClinGen 官方发布物**，不代表 ClinGen 或其专家组的立场。

### 本仓库许可证覆盖范围

- `LICENSE`（Apache License 2.0）**仅覆盖本项目自身的整理工作**，包括：目录与文件组织、`gene-gn-file-mapping.csv`、`vcep-version-manifest.csv`、`narrative-units/` 下的叙述整理、`00-索引` 与核查报告、脚本与文档。
- Apache-2.0 **不覆盖** ClinGen 原始规范正文与官方附件；这些内容的使用请遵循 ClinGen 的条款（CC0 1.0 + 署名要求），本仓库不对其另行授权。
- 若上述两者在具体使用场景下冲突，以原始内容的官方条款为准。

### 建议引用方式

- 引用原始规范：ClinGen. *[具体 VCEP 规范名称]*. Clinical Genome Resource. https://cspec.genome.network/cspec/ （accessed 2026-11-12）.
- 引用本仓库整理层：KLameng. *ACMG-VCEP-Data v1.4.4*. https://github.com/KLameng/ACMG-VCEP-Data （accessed YYYY-MM-DD）.

> 本仓库为评级辅助的快速检阅通道，不构成临床诊断或治疗依据；实际判定须回 ClinGen CSpec 官网核实当期最新版本。
