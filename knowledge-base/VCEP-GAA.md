# ClinGen VCEP基因特异性规范：GAA

> 来源：ClinGen Sequence Variant Interpretation (SVI) Criteria Specification Repository
> 数据日期：2026-06-13
> 官网版本：Version 2.0（GN010，lastUpdated 2021-06-02，Released）；来源 ClinGen CSpec API，核对 2026-11-12
> ⚠️ 智能分析结果，仅供参考。临床变异评级请以ClinGen官方最新版本为准。

## 规范 1：GN010 — Lysosomal Diseases Variant Curation Expert Panel

### 覆盖疾病
- **MONDO:0009290**（遗传方式：未指定）

### 基因特异性证据规则

#### PVS1
- 默认强度：Pathogenic Very Strong
- ACMG原始定义：Null variant (nonsense, frameshift, canonical +/−1 or 2 splice sites, initiation codon, single or multi-exon deletion) in a gene where loss of function (LOF) is a known mechanism of disease.
Caveats:
 * Beware of genes where LOF is not a known disease mechanism (e.g. GFAP, MYH7).
 * Use caution interpreting LOF variants at the extreme 3’ end of a gene.
 * Use caution with splice variants that are predicted to lead to exon skipping but leave the remainder of the protein intact.
 * Use caution in the presence of multiple transcripts.
- **Very Strong** ✅：Null variant in a gene where loss of function is a known mechanism of disease or in frame loss of an exon that contains residues involved in the active site of GAA.
 * Any nonsense, frameshift, or splice variant creating a premature stop codon before codon 916.
 * In frame deletions of an entire exon containing critical active site/substrate binding residues (exons 8 and 10), or for which another variant removing the exon is known to be pathogenic (exons 2 and 18).
- **Strong** ✅：Null variant in a gene where loss of function is a known mechanism of disease.
 *  In frame loss of an exon which is part of the catalytic barrel domain and contains pathogenic/likely pathogenic nontruncating variants (exons 6 and 9).
 * Initiator codon variant.
- **Moderate** ✅：Null variant in a gene where loss of function is a known mechanism of disease.
 * Premature termination codon in the 3’ end of GAA (3’ to codon 916), not predicted to be detected by nonsense-mediated decay.
 * Predicted exon-skipping due to canonical splice variant or exon deletion resulting in an in frame deletion of <10% of the gene product (exons 17, 19, and 20).

#### PS1
- 默认强度：Pathogenic Strong
- ACMG原始定义：Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.
Example: Val->Leu caused by either G>C or G>T in the same codon.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.
- **Strong** ✅：Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.

#### PS3
- 默认强度：Pathogenic Strong
- ACMG原始定义：Well-established in vitro or in vivo functional studies supportive of a damaging effect on the gene or gene product.
Note: Functional studies that have been validated and shown to be reproducible and robust in a clinical diagnostic laboratory setting are considered the most well-established.
- **Strong** ✅：Well-established in vitro or in vivo functional studies supportive of a damaging effect.
 * RT-PCR evidence of mis-splicing for non-canonical intronic variants with no evidence of normal splice products.
- **Moderate** ✅：Well-established in vitro or in vivo functional studies supportive of a damaging effect.
 * <5% wild type GAA activity when the variant is expressed in a heterologous cell type and evidence of abnormal GAA synthesis and/or processing.
 * RT-PCR evidence of mis-splicing for non-canonical intronic variants with evidence of normal splice products.
- **Supporting** ✅：Well-established in vitro or in vivo functional studies supportive of a damaging effect.
 * <30% wild type GAA activity when the variant is expressed in a heterologous cell type.
 * RT-PCR evidence of mis-splicing for non-canonical intronic variants with evidence of normal splice products.

#### PM1
- 默认强度：Pathogenic Moderate
- ACMG原始定义：Located in a mutational hot spot and/or critical and well-established functional domain (e.g. active site of an enzyme) without benign variation.
- **Moderate** ✅：Located in a mutational hot spot and/or critical and well-established functional domain without benign variation.
 * Missense substitution or in frame deletion of residues important in the active site architecture and substrate binding of GAA: D282, W376, D404, L405, I441, W481, W516, D518, M519, R600, W613, D616, W618, F649, L650, H674.

#### PM2
- 默认强度：Pathogenic Moderate
- ACMG原始定义：Absent from controls (or at extremely low frequency if recessive) in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.
Caveat: Population data for indels may be poorly called by next generation sequencing.
- **Moderate** ✅：Low frequency in population databases.
 * Minor allele frequency <0.1% (0.001) in all continental populations with >2000 alleles in gnomAD.

#### PM3
- 默认强度：Pathogenic Moderate
- ACMG原始定义：For recessive disorders, detected in trans with a pathogenic variant
Note: This requires testing of parents (or offspring) to determine phase.
- **Very Strong** ✅：Detected in trans with a pathogenic variant. Points-based system. See main specifications document.
- **Strong** ✅：Detected in trans with a pathogenic variant. Points-based system. See main specifications document.
- **Moderate** ✅：Detected in trans with a pathogenic variant. Points-based system. See main specifications document.
- **Supporting** ✅：Detected in trans with a pathogenic variant. Points-based system. See main specifications document.

#### PM4
- 默认强度：Pathogenic Moderate
- ACMG原始定义：Protein length changes due to in-frame deletions/insertions in a non-repeat region or stop-loss variants.
- **Moderate** ✅：Protein length changes due to in-frame deletions/insertions in a nonrepeat region or stop-loss variants.
 * In frame deletion/insertions of two or more amino acids but less than one exon.
- **Supporting** ✅：Protein length changes due to in-frame deletions/insertions in a nonrepeat region or stop-loss variants.
 * In frame deletion/insertions of one amino acid.

#### PM5
- 默认强度：Pathogenic Moderate
- ACMG原始定义：Novel missense change at an amino acid residue where a different missense change determined to be pathogenic has been seen before.
Example: Arg156His is pathogenic; now you observe Arg156Cys.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.
- **Moderate** ✅：Missense change at an amino acid residue where a different missense change determined to be pathogenic has been seen before.
- **Supporting** ✅：Missense change at an amino acid residue where a different missense change determined to be 'likely pathogenic' has been seen before.

#### PP3
- 默认强度：Pathogenic Supporting
- ACMG原始定义：Multiple lines of computational evidence support a deleterious effect on the gene or gene product (conservation, evolutionary, splicing impact, etc.).
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm should not be counted as an independent criterion. PP3 can be used only once in any evaluation of a variant.
- **Supporting** ✅：Multiple lines of computational evidence support a deleterious effect on the gene or gene product.
 * REVEL score >0.7 for missense variants.
 * In frame deletion or insertion predicted deleterious by 2 out of 3 tools (PROVEAN, MutationTaster, MutPred-InDel).
 * Predicted impact on splicing by SpliceAI (score >0.5).

#### PP4
- 默认强度：Pathogenic Supporting
- ACMG原始定义：Patient’s phenotype or family history is highly specific for a disease with a single genetic etiology.
- **Moderate** ✅：Phenotype specific for disease with single genetic etiology.
 * Points-based system. See main specifications document
- **Supporting** ✅：Phenotype specific for disease with single genetic etiology.
 * Points-based system. See main specifications document

#### BA1
- 默认强度：Benign Stand Alone
- ACMG原始定义：Allele frequency is above 5% in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.
- **Stand Alone** ✅：Common in population databases.
 * Highest minor allele frequency >0.01 (>1%) in any continental population in gnomAD with >2000 alleles.

#### BS1
- 默认强度：Benign Strong
- ACMG原始定义：Allele frequency is greater than expected for disorder.
- **Strong** ✅：Allele frequency greater than expected for disease.
 * Highest minor allele frequency >0.005 (>0.5%) in any continental population in gnomAD with >2000 alleles.

#### BS2
- 默认强度：Benign Strong
- ACMG原始定义：Observed in a healthy adult individual for a recessive (homozygous), dominant (heterozygous), or X-linked (hemizygous) disorder, with full penetrance expected at an early age.
- **Strong** ✅：Observed in the homozygous state in a healthy adult.
 * Homozygous individual of any age with normal GAA activity.

#### BS3
- 默认强度：Benign Strong
- ACMG原始定义：Well-established in vitro or in vivo functional studies show no damaging effect on protein function or splicing.
- **Supporting** ✅：Well-established in vitro or in vivo functional studies shows no damaging effect on protein function.
 * >50% activity when the variant is expressed in a heterologous cell type, or >30% activity if there is also evidence of normal synthesis and processing.

#### BP2
- 默认强度：Benign Supporting
- ACMG原始定义：Observed in trans with a pathogenic variant for a fully penetrant dominant gene/disorder or observed in cis with a pathogenic variant in any inheritance pattern.
- **Supporting** ✅：Observed in cis with a pathogenic variant.

#### BP4
- 默认强度：Benign Supporting
- ACMG原始定义：Multiple lines of computational evidence suggest no impact on gene or gene product (conservation, evolutionary, splicing impact, etc)
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm cannot be counted as an independent criterion. BP4 can be used only once in any evaluation of a variant.
- **Supporting** ✅：Multiple lines of computational evidence suggest no impact on gene or gene product.
 * REVEL score <0.5 for missense variants.
 * In frame deletion or insertion predicted benign by PROVEAN, MutationTaster, and MutPred-InDel.
 * No predicted impact on splicing by SpliceAI (score <0.2)

#### BP7
- 默认强度：Benign Supporting
- ACMG原始定义：A synonymous variant for which splicing prediction algorithms predict no impact to the splice consensus sequence nor the creation of a new splice site AND the nucleotide is not highly conserved.
- **Supporting** ✅：A synonymous (silent) variant for which splicing prediction algorithms predict no impact to the splice consensus sequence nor the creation of a new splice site AND the nucleotide is not highly conserved.

### 不适用证据码
PS2、PS4、PM6、PP1、PP2、PP5、BS4、BP1、BP3、BP5、BP6

## ⚠️ GAA 专项口径：leaky splice 非纯 LOF + 同义禁 PVS1（var124/var129 病根，2026-11-03 补）

> **实证（66 条归因）**：var124 GAA splicing 金 P 判 VUS（RT-PCR leaky splice 被当纯 LOF 处理）；var129 GAA 同义金 LB 误给 PVS1_VS+PM2→P（严重反向）。两条均源于**把"剪接异常/同义"直接当 PVS1 LOF 硬凑**。

### 规则一：leaky splice（漏读剪接）不是纯 LOF，不得直接给 PVS1_VeryStrong
- **leaky splice 定义**：剪接变异导致部分转录本异常剪接（exon skipping），但**保留部分正常剪接产物**（RT-PCR 见正常剪接条带 + 异常条带并存）。
- **判定**：
  1. 有 RT-PCR/RNA 证据表明**存在正常剪接产物（leaky）** → 该变异**不构成完全 LOF**，PVS1 不得 VeryStrong；
  2. 按 GAA VCEP PVS1 档位核验：可否给 PVS1_Moderate（3' 端 PTC，如 3' to codon 916）/ PVS1_Strong（框内丢失催化桶外显子 6/9）；**leaky splice 通常落 Moderate 或更低**；
  3. 同时按 GAA VCEP **PS3 口径**核验：RT-PCR 证据支持异常剪接（PS3_Moderate：非经典内含子变异无正常剪接产物；PS3_Supporting：有正常剪接产物）——leaky splice 有正常产物 → **PS3_Supporting 档**（不是 PVS1）。
- **BS1 组合**：若该变异等位频率超 GAA BS1 阈值（最高 MAF>0.5% 且 >2000 等位），须与 PVS1 降档后联合判定，不得忽略（var124 有 BS1 未组合）。
- **数据来源**：剪接实验数据走采集层（ClinVar/文献层功能实验证据 + PMID 关联），DataPending 不得硬凑。

### 规则二：同义变异严禁 PVS1
- **同义变异（synonymous）不是无义（nonsense）**，PVS1（LOF：nonsense/frameshift/canonical splice/initiation codon/大片段缺失）**对同义变异一律不适用**。
- 同义变异按 **BP7/BP4** 走（SpliceAI 取到 ≤0.2/≤0.5 判 BP7 候选；REVEL 不适用同义）；误给 PVS1 是 var129 严重反向的根因，评级时若见同义+PVS1 组合必须拦下（对照 ClinVar 锚）。
- **硬闸**：GAA 同义变异 → PVS1 强制 not_applicable（机制=同义，无 LOF），走 BP7/BP4 路径；ClinVar Benign/LB 锚对照。

### 官方链接
- [ClinGen CSpec 文档页面](https://cspec.genome.network/cspec/ui/svi/doc/GN010)
