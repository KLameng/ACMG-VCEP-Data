# ClinGen VCEP基因特异性规范：CFTR（CFTR2 专家共识数据包）

> **⚠️ 来源口径（重要，2026-11-03 核实）**：**ClinGen CSpec 注册表无 CFTR 正式 VCEP 规范**（cspec.genome.network 检索确认；ClinGen 官网 VCEP 列表无 Cystic Fibrosis VCEP）。CFTR 变异分类的**权威来源是 CFTR2**（Sosnay PR et al. Nat Genet 2013;45(10):1160-7, PMID 23974870；ClinVar 中 CFTR 变异多标注 "reviewed by expert panel - CFTR2"）。
> 因此本文件为 **CFTR2 专家共识 + ClinVar 实践规则数据包**（非 ClinGen CSpec VCEP），供评级时路由读取 CFTR 特异规则（尤其 TG/polyT 单倍型维度）。使用前请核验 CFTR2 最新版本（https://cftr2.org/）。
> 数据日期：2026-11-03

### 覆盖疾病
- **囊性纤维化（CF）** MONDO:0009061（OMIM 219700）
- **CFTR 相关疾病（CFTR-RD）**：先天性双侧输精管缺如（CBAVD）、胰腺炎等

### 基因特异性证据规则

#### ⚠️ CFTR 特有维度：TG 重复 + polyT 单倍型（本数据包核心，var022/var029 缺的输入）

##### 背景（权威依据）
- CFTR intron 8/9 剪接受体区有 **polypyrimidine tract（polyT）**：长度 5T / 7T / 9T，影响 exon 10（部分命名 exon 9）剪接效率。
- **5T 等位**：约 5% 白人等位，产生约 95% exon9-minus RNA（Kiesewetter 1993），是**低外显率剪接等位**；trans 致病变异或纯合 → CFTR-RD（支气管扩张等）（ClinVar VCV000818605）。
- **TG 重复长度（TG11/TG12/TG13）** 进一步修正 5T 外显率：TG 越长，5T 的外显率越高（TG13-5T > TG12-5T > TG11-5T）。标准命名 `c.1210-34TG[12]T[5]`（= 5T;TG12 或 TG12-5T）。
- **R117H（c.350G>A p.Arg117His）依赖 polyT 单倍型定档**（ClinVar RCV000007528 / PMC2985951）：
  - `[R117H;(T)5]`（cis 5T）：**mild CF-causing complex allele**；trans 致病 → 典型 CF（伴胰腺功能保留）
  - `[R117H;(T)7]`（cis 7T）：**CFTR-RD 突变 / VVCC（varying clinical consequence）**；trans 致病 → 多为 CBAVD/轻度 CF 变异表型
  - `[R117H;(T)7]` 纯合：可无症状/胰腺炎/CAVD（低外显率）
- **CFTR2 分类**：R117H 在 CFTR2 中为 "mutation of varying clinical consequence"（793 CF 患者 808 等位）；整体分类 Pathogenic（low penetrance）。

##### 单倍型定档规则（评级用，写死）
评级 CFTR 变异（尤其 R117H、5T、TG 重复相关）时，**必须确定 polyT + TG 单倍型**（输入缺失 → DataPending，不得按通用规则硬判）：

| 单倍型 | 分类口径 | 备注 |
|---|---|---|
| `[R117H;5T]`（cis） | 致病（低外显率，CF-causing mild） | trans 严重致病 → 典型 CF 表型 |
| `[R117H;7T]`（cis） | VVCC / 倾向致病（CFTR-RD） | trans 严重致病 → CBAVD/轻度表型；纯合可无症状 |
| `[5T;TG13]` | 致病（低外显率，最高外显率 5T 单倍型） | TG 越长外显率越高 |
| `[5T;TG12]` | 倾向致病（低外显率） | 多数 CFTR-RD 病例 |
| `[5T;TG11]` | VUS/倾向良性（低外显率最低） | 需反式伙伴/功能数据定档 |
| `[7T;TG10]`（常见良性背景） | 良性多态 | 需排除 cis R117H |

> **规则来源**：ClinVar RCV000007528（Invitae/LabCorp 描述）+ PMC2985951（欧洲最佳实践指南）+ PMC9292755（T/TG 单倍型算法）+ CFTR2（Sosnay 2013 PMID 23974870）。
> **数据获取**：TG/polyT 单倍型是**输入侧数据**（来自检测报告/家系分析），经 G1 身份对象扩展字段 `haplotype_cftr` 传入；缺失 → DataPending → 门禁待补清单，**不得用通用 PM2/BS1 静默定档**（var022/var029 病根）。

#### CFTR2 专家共识要点（与通用规则的关系）
- CFTR 变异评级**先查本数据包单倍型维度**（若变异涉及 intron 8/9 polyT/TG 或 R117H），再走通用 ACMG 规则。
- 频率阈值（PM2/BS1/BA1）：CFTR 为 AR 病，通用阈值 + CFTR2 共识（R117H 等位频率 0.2-0.25% 白人，不超 1/100 致病阈值）。
- **PVS1**：LOF 机制确立（经典 CF）；深内含子变异需剪接实验（var028 对象——ClinVar 无直接收录时走采集层补剪接功能数据）。
- **PS1/PM5**：同密码子/同残基比对走通用规则 + 采集层穷尽检索（§3.4/§3.5 单源查无硬闸）。
- **BS1/BA1**：AR 通用阈值（BA1 MAF≥5% 不合 CFTR；BS1 按疾病预期频率）。

### 不适用证据码
PP5、BP6（已废弃）；其余按通用 ACMG 规则

### 官方链接
- CFTR2: https://cftr2.org/
- ClinVar R117H: https://www.ncbi.nlm.nih.gov/clinvar/RCV000007528/
- ClinVar 5T: https://www.ncbi.nlm.nih.gov/clinvar/variation/818605/
- Sosnay 2013 (CFTR2): PMID 23974870, https://pubmed.ncbi.nlm.nih.gov/23974870/
