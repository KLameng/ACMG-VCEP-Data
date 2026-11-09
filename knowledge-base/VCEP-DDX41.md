# ClinGen VCEP基因特异性规范：DDX41

> 来源：ClinGen Sequence Variant Interpretation (SVI) Criteria Specification Repository
> 数据日期：2026-11-02（GN159 v1.0 首次入库；2026-11-09 从 CSpec API 抓取原文生成）
> 官网版本：v1.0（GN159；Released 2026-11-02；lastUpdated 2026-11-02T16:44:00Z）
> ⚠️ 智能分析结果，仅供参考。临床变异评级请以ClinGen官方最新版本为准。

## 规范 1：GN159 — Myeloid Malignancy Variant Curation Expert Panel

### 覆盖疾病
- **MONDO:0014809**（遗传方式：Autosomal dominant inheritance）
- 疾病谱：DDX41 相关家族性髓系肿瘤易感（MDS/AML 等髓系恶性肿瘤）

### 通用说明
> 官网 Version 1.0（Released 2026-11-02；Myeloid Malignancy VCEP）。DDX41 为本规范首个版本，无历史版本可比对。
> 共享转录本 NM_016222.4。
> 数据来源：ClinGen CSpec Registry API `GET /cspec/api/SequenceVariantInterpretation/id/GN159`（2026-11-09 实测），逐条 criteriaCodes 原文整理。

### 基因特异性证据规则

#### PVS1
- 默认强度：Pathogenic Very Strong
- ACMG原始定义：Null variant (nonsense, frameshift, canonical +/−1 or 2 splice sites, initiation codon, single or multi-exon deletion) in a gene where loss of function (LOF) is a known mechanism of disease.
Caveats:
 * Beware of genes where LOF is not a known disease mechanism (e.g. GFAP, MYH7).
 * Use caution interpreting LOF variants at the extreme 3’ end of a gene.
 * Use caution with splice variants that are predicted to lead to exon skipping but leave the remainder of the protein intact.
 * Use caution in the presence of multiple transcripts.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ✅：**PVS1\_Very Strong:** Use appropriate _DDX41_ decision tree.

**PVS1\_Very Strong (RNA):** Use for an observed splicing defect.
- **Strong** ✅：**PVS1\_Strong:** Use appropriate _DDX41_ decision tree.

**PVS1\_Strong (RNA):** Use for an observed splicing defect.
- **Moderate** ✅：**PVS1\_Moderate:** Use appropriate _DDX41_ decision tree.

**PVS1\_Moderate (RNA):** Use for an observed splicing defect.
- **Supporting** ✅：**PVS1\_Supporting (RNA):** Use for an observed splicing defect.

#### PS1
- 默认强度：Pathogenic Strong
- ACMG原始定义：Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.
Example: Val->Leu caused by either G>C or G>T in the same codon.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ✅：**For missense variants:** 

*   **PS1:** Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.

**For splice site variants:** 

*   **PS1:** Follow recommendations by the ClinGen SVI Splicing Subgroup (PMID: 37352859).
- **Moderate** ✅：**For missense variants:** 

*   **PS1\_Moderate:** Same amino acid change as a previously established likely pathogenic variant regardless of nucleotide change.

**For splice site variants:** 

*   **PS1\_Moderate:** Follow recommendations by the ClinGen SVI Splicing Subgroup (PMID: 37352859).
- **Supporting** ✅：**For splice site variants:** 

*   **PS1\_Supporting:** Follow recommendations from the ClinGen SVI Splicing Subgroup (PMID: 37352859)

#### PS2
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：De novo (both maternity and paternity confirmed) in a patient with the disease and no family history.
Note: Confirmation of paternity only is insufficient. Egg donation, surrogate motherhood, errors in embryo transfer, etc. can contribute to non-maternity.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PS3
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Well-established in vitro or in vivo functional studies supportive of a damaging effect on the gene or gene product.
Note: Functional studies that have been validated and shown to be reproducible and robust in a clinical diagnostic laboratory setting are considered the most well-established.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PS4
- 默认强度：Pathogenic Very Strong
- ACMG原始定义：The prevalence of the variant in affected individuals is significantly increased compared to the prevalence in controls.
Note 1: Relative risk (RR) or odds ratio (OR), as obtained from case-control studies, is >5.0 and the confidence interval around the estimate of RR or OR does not include 1.0. See manuscript for detailed guidance.
Note 2: In instances of very rare variants where case-control studies may not reach statistical significance, the prior observation of the variant in multiple unrelated patients with the same phenotype, and its absence in controls, may be used as moderate level of evidence.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ✅：**PS4\_Very\_Strong**: lower bound of the OR’s confidence interval ≥ 350

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.
- **Strong** ✅：**PS4\_Strong**: lower bound of the OR’s confidence interval ≥ 18.7

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.
- **Moderate** ✅：**PS4\_Moderate**: lower bound of the OR’s confidence interval ≥ 4.33

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.
- **Supporting** ✅：**PS4\_Supporting**: lower bound of the OR’s confidence interval ≥ 2.08

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.

#### PM1
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Located in a mutational hot spot and/or critical and well-established functional domain (e.g. active site of an enzyme) without benign variation.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PM2
- 默认强度：Pathogenic Supporting
- ACMG原始定义：Absent from controls (or at extremely low frequency if recessive) in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.
Caveat: Population data for indels may be poorly called by next generation sequencing.
- **Stand Alone** ❌：`Not applicable`
- **Very Strong** ❌：`Not applicable`
- **Strong** ❌：`Not applicable`
- **Moderate** ❌：`Not Applicable`
- **Supporting** ✅：**PM2\_Supporting:** Variant must be completely absent from major population databases.

Caveats:

*   The mean coverage of _DDX41_ in the population database used should be at least 20x.
*   PM2\_Supporting not applicable if PS4 is met at any strength level.

#### PM3
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：For recessive disorders, detected in trans with a pathogenic variant
Note: This requires testing of parents (or offspring) to determine phase.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PM4
- 默认强度：Pathogenic Moderate
- ACMG原始定义：Protein length changes due to in-frame deletions/insertions in a non-repeat region or stop-loss variants.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable`
- **Moderate** ✅：**Protein extension variants:**

**PM4:** Per modified PM4 decision tree for stop-loss variants and In-frame indel including the stop codon.
- **Supporting** ❌：`Not Applicable`

#### PM5
- 默认强度：Pathogenic Strong
- ACMG原始定义：Novel missense change at an amino acid residue where a different missense change determined to be pathogenic has been seen before.
Example: Arg156His is pathogenic; now you observe Arg156Cys.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ✅：**Missense Variants:**

*   **PM5\_Strong:** Missense change at an amino acid residue where ≥ 2 different missense changes which have previously been determined to be pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than alternate residue of the known pathogenic/likely pathogenic variant.
- **Moderate** ✅：**Missense Variants:**

*   **PM5\_Moderate:** Missense change at an amino acid residue where a different missense change which has previously been determined to be pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than alternate residue of the known pathogenic/likely pathogenic variant
- **Supporting** ✅：**Missense Variants:**

*   **PM5\_Supporting:** Missense change at an amino acid residue where a different missense change which has previously been determined to be likely pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than the alternate residue of the known pathogenic/likely pathogenic.

**Null Variants**

*   **PM5\_Supporting:** Nonsense/frameshift variants in an exon which contains ≥2 P/LP null variants, and the variant is predicted to lead to NMD or NSD (_**DDX41**_ **PM5\_Supporting Table)**.

#### PM6
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Assumed de novo, but without confirmation of paternity and maternity.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PP1
- 默认强度：Pathogenic Strong
- ACMG原始定义：Co-segregation with disease in multiple affected family members in a gene definitively known to cause the disease.
Note: May be used as stronger evidence with increasing segregation data.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ✅：**PP1\_Strong**: ≥ 7 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.
- **Moderate** ✅：**PP1\_Moderate**: 5 or 6 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.
- **Supporting** ✅：**PP1\_Supporting**: 3 or 4 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

#### PP2
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Missense variant in a gene that has a low rate of benign missense variation and where missense variants are a common mechanism of disease.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### PP3
- 默认强度：Pathogenic Supporting
- ACMG原始定义：Multiple lines of computational evidence support a deleterious effect on the gene or gene product (conservation, evolutionary, splicing impact, etc.).
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm should not be counted as an independent criterion. PP3 can be used only once in any evaluation of a variant.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable`
- **Moderate** ❌：`Not Applicable`
- **Supporting** ✅：**For missense variants:**

**PP3:** AlphaMissense score ≥ 0.792

**For any variant (except canonical splice site variants):**

**PP3:**

*   SpliceAI ∆ scores ≥ 0.20 including the creation of cryptic splice sites.
*   Do not use for variants with a predicted splicing effect that is proven by RNA analysis. See **PVS1\_Variable (RNA)**.

#### PP4
- 默认强度：Pathogenic Strong
- ACMG原始定义：Patient’s phenotype or family history is highly specific for a disease with a single genetic etiology.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ✅：**PP4\_Strong:** OddsPath ≥ 18.7

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.
- **Moderate** ✅：**PP4\_Moderate:** OddsPath ≥ 4.33

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.
- **Supporting** ✅：**PP4\_Supporting:** OddsPath ≥ 2.08

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

#### BA1
- 默认强度：Benign Stand Alone
- ACMG原始定义：Allele frequency is above 5% in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.
- **Stand Alone** ✅：**BA1:** Minor allele frequency ≥ 0.0274 (2.74%) in any general continental population dataset with ≥ 2,000 alleles tested and variant present in ≥ 5 alleles.
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable for this VCEP`
- **Moderate** ❌：`Not Applicable for this VCEP`
- **Supporting** ❌：`Not Applicable for this VCEP`

#### BS1
- 默认强度：Benign Strong
- ACMG原始定义：Allele frequency is greater than expected for disorder.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ✅：**BS1:** Minor allele frequency between 0.0274 (2.74%) and 0.00274 (0.274%) in any general continental population dataset with ≥ 2,000 alleles tested and variant present in ≥ 5 alleles.
- **Moderate** ❌：`Not Applicable`
- **Supporting** ❌：`Not Applicable`

#### BS2
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Observed in a healthy adult individual for a recessive (homozygous), dominant (heterozygous), or X-linked (hemizygous) disorder, with full penetrance expected at an early age.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BS3
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Well-established in vitro or in vivo functional studies show no damaging effect on protein function or splicing.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BS4
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Lack of segregation in affected members of a family.
Caveat: The presence of phenocopies for common phenotypes (i.e. cancer, epilepsy) can mimic lack of segregation among affected individuals. Also, families may have more than one pathogenic variant contributing to an autosomal dominant disorder, further confounding an apparent lack of segregation.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BP1
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Missense variant in a gene for which primarily truncating variants are known to cause disease.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BP2
- 默认强度：Benign Supporting
- ACMG原始定义：Observed in trans with a pathogenic variant for a fully penetrant dominant gene/disorder or observed in cis with a pathogenic variant in any inheritance pattern.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable`
- **Moderate** ❌：`Not Applicable`
- **Supporting** ✅：**BP2:** Applicable per the original ACMG/AMP guidelines for a germline variant found in:

1.  _Trans_ with a pathogenic variant.
2.  _Cis_ with different pathogenic variants in at least 2 instances.
3.  Homozygosity in an unaffected individual.

Caveats:

*   VAF must be > 40%.
*   Do not use for variant identified in concert with a somatic hotspot variant (R525H, G530D, G530S, P321L, T227M, E345D, and D344E).

#### BP3
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：In frame-deletions/insertions in a repetitive region without a known function.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BP4
- 默认强度：Benign Supporting
- ACMG原始定义：Multiple lines of computational evidence suggest no impact on gene or gene product (conservation, evolutionary, splicing impact, etc)
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm cannot be counted as an independent criterion. BP4 can be used only once in any evaluation of a variant.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable`
- **Moderate** ❌：`Not Applicable`
- **Supporting** ✅：**For missense variants:**

*   **BP4:** AlphaMissense score ≤ 0.169

**For intronic/synonymous variants:**

*   **BP4:** SpliceAI ∆ scores ≤ 0.10
*   Do not use for synonymous/silent variants with a lack of splicing effect proven by RNA analysis. See **BP7\_Variable (RNA)**.
*   Do not use for canonical splice site variants.

#### BP5
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Variant found in a case with an alternate molecular basis for disease.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BP6
- 默认强度：（本 VCEP 全部强度不适用）
- ACMG原始定义：Reputable source recently reports variant as benign, but the evidence is not available to the laboratory to perform an independent evaluation.
- **全部强度不适用** ❌：全部强度不适用（官网 applicability 全部为 Not Applicable）

#### BP7
- 默认强度：Benign Supporting
- ACMG原始定义：A synonymous variant for which splicing prediction algorithms predict no impact to the splice consensus sequence nor the creation of a new splice site AND the nucleotide is not highly conserved.
- **Stand Alone** ❌：`Not Applicable for this VCEP`
- **Very Strong** ❌：`Not Applicable for this VCEP`
- **Strong** ❌：`Not Applicable`
- **Moderate** ❌：`Not Applicable`
- **Supporting** ✅：**BP7:** Applicable for

*   Synonymous variants – excluding the following last three and first two nucleotides in an exon – with SpliceAI ∆ scores ≤ 0.10.
*   Intronic variants that occur more than 6 nucleotides from exon ends and more than 20 nucleotides from exon starts and have SpliceAI ∆ scores ≤ 0.10.

**BP7\_Variable (RNA):** Applicable for variants with RNA data, with weighting based on the quality of the available RNA data.

### 组合规则（Rules for Combining Criteria）

> ⚠ 来源边界：官网 CSpec API（GN159 / RuleSet 1625925062）**只返回 28 条 criteriaCodes 与基因-疾病映射，不返回定制组合表**。以下为本技能群统一执行口径，不是官网原文。

1. **ACMG/AMP 2015 组合面板**（Richards 2015，见本技能群通用组合规则）：
   - Pathogenic：1 Very Strong + ≥1 Strong；或 1 Very Strong + ≥2 Moderate；或 1 Very Strong + 1 Moderate + 1 Supporting；或 1 Very Strong + ≥2 Supporting；或 ≥2 Strong；或 1 Strong + ≥3 Moderate；或 1 Strong + 2 Moderate + ≥2 Supporting；或 1 Strong + 1 Moderate + ≥4 Supporting。
   - Likely Pathogenic：1 Very Strong + 1 Moderate；或 1 Strong + 1 Moderate；或 1 Strong + ≥2 Supporting；或 ≥3 Moderate；或 2 Moderate + ≥2 Supporting；或 1 Moderate + ≥4 Supporting。
   - Benign / Likely Benign：按 BA1 单独成立，或 ≥2 Strong，或 1 Strong + ≥1 Moderate/Supporting 对称规则。
2. **Tavtigian 2020 贝叶斯点分制**（Very Strong=8 / Strong=4 / Moderate=2 / Supporting=1；Pathogenic ≥10，Likely Pathogenic 6–9，VUS 0–5，Likely Benign −1 至 −6，Benign ≤−7）。
3. 两套结论不一致时，按 `acmg-conflict-summary-output` 冲突消解矩阵处理：保留更强结论并在输出中标注分歧，不静默抹平。
4. 需要官网定制组合表时，以 cspec UI 附件为准（API 不提供该字段）。

### 不适用证据码

官网 applicability 全部标为 Not Applicable 的码：

```
PS2、PS3、PM1、PM3、PM6、PP2、BS2、BS3、BS4、BP1、BP3、BP5、BP6
```

- **PP5 / BP6**：ACMG/AMP 已废止码（官网 description 明确标注 deprecated），不得使用。

### 参考附件

- 官网 GN159 附件索引见 `clingen-vcep/attachment-index.csv`（本版 API 未返回附件列表，如需决策树/评分表请到 cspec UI 下载）。

### 官方链接

- ClinGen CSpec Registry（GN159）：https://cspec.genome.network/cspec/ui/svi/id/GN159
- API 原文：https://cspec.genome.network/cspec/api/SequenceVariantInterpretation/id/GN159
- GeneCards/Gene 参考：https://www.genenames.org/tools/search/#!/?query=DDX41
