> **来源**：CFTR2 专家共识（Sosnay PR et al. Nat Genet 2013;45(10):1160-7, PMID 23974870）+ ClinVar expert-panel reviewed 标注
> 数据日期：2026-11-03｜官网复核日期：2026-11-09
> 说明：ClinGen CSpec 无 CFTR 正式 VCEP，本段为 CFTR2 共识口径摘要，非 ClinGen 官方 VCEP 规则原文

## 规范 1：GN cftr2 — CFTR2 专家共识

### 致病方向判定要点
- **CFTR2 分类体系**：CF-causing / mutation of varying clinical consequence（VVCC）/ non-CF-causing / unknown，与 ACMG/AMP 五级非一一映射，评级时以 CFTR2 分类 + 通用面板组合使用
- **最常见 CF-causing 变异**：p.Phe508del（c.1521_1523delCTT），CFTR2 收录 CF 等位中占比最高
- **R117H（c.350G>A p.Arg117His）必须按 polyT 单倍型定档**：
  - `[R117H;5T]`（cis 5T）→ mild CF-causing complex allele；trans 严重致病 → 典型 CF（胰腺功能保留）
  - `[R117H;7T]`（cis 7T）→ VVCC / CFTR-RD；trans 严重致病 → 多为 CBAVD 或轻度表型
- **5T 等位外显率由 TG 重复长度修正**：TG13-5T > TG12-5T > TG11-5T
- 单倍型（polyT + TG）属输入侧数据（`haplotype_cftr` 字段）；缺失 → DataPending，**不得用通用 PM2/BS1 静默定档**
