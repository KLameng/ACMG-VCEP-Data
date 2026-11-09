# DDX41（GN159）— Myeloid Malignancy VCEP 规范 v1.0

> 来源：ClinGen CSpec Registry API（GN159，2026-11-09 抓取；官网 Released 2026-11-02）
> 转录本：NM_016222.4

## 良性证据码（DDX41 v1.0 原文）

### BA1

Allele frequency is above 5% in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.

- **Stand Alone** ✅
**BA1:** Minor allele frequency ≥ 0.0274 (2.74%) in any general continental population dataset with ≥ 2,000 alleles tested and variant present in ≥ 5 alleles.

- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable for this VCEP`
- **Moderate** ❌ `Not Applicable for this VCEP`
- **Supporting** ❌ `Not Applicable for this VCEP`

### BS1

Allele frequency is greater than expected for disorder.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ✅
**BS1:** Minor allele frequency between 0.0274 (2.74%) and 0.00274 (0.274%) in any general continental population dataset with ≥ 2,000 alleles tested and variant present in ≥ 5 alleles.

- **Moderate** ❌ `Not Applicable`
- **Supporting** ❌ `Not Applicable`

### BP2

Observed in trans with a pathogenic variant for a fully penetrant dominant gene/disorder or observed in cis with a pathogenic variant in any inheritance pattern.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable`
- **Moderate** ❌ `Not Applicable`
- **Supporting** ✅
**BP2:** Applicable per the original ACMG/AMP guidelines for a germline variant found in:

1.  _Trans_ with a pathogenic variant.
2.  _Cis_ with different pathogenic variants in at least 2 instances.
3.  Homozygosity in an unaffected individual.

Caveats:

*   VAF must be > 40%.
*   Do not use for variant identified in concert with a somatic hotspot variant (R525H, G530D, G530S, P321L, T227M, E345D, and D344E).


### BP4

Multiple lines of computational evidence suggest no impact on gene or gene product (conservation, evolutionary, splicing impact, etc)
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm cannot be counted as an independent criterion. BP4 can be used only once in any evaluation of a variant.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable`
- **Moderate** ❌ `Not Applicable`
- **Supporting** ✅
**For missense variants:**

*   **BP4:** AlphaMissense score ≤ 0.169

**For intronic/synonymous variants:**

*   **BP4:** SpliceAI ∆ scores ≤ 0.10
*   Do not use for synonymous/silent variants with a lack of splicing effect proven by RNA analysis. See **BP7\_Variable (RNA)**.
*   Do not use for canonical splice site variants.


### BP7

A synonymous variant for which splicing prediction algorithms predict no impact to the splice consensus sequence nor the creation of a new splice site AND the nucleotide is not highly conserved.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable`
- **Moderate** ❌ `Not Applicable`
- **Supporting** ✅
**BP7:** Applicable for

*   Synonymous variants – excluding the following last three and first two nucleotides in an exon – with SpliceAI ∆ scores ≤ 0.10.
*   Intronic variants that occur more than 6 nucleotides from exon ends and more than 20 nucleotides from exon starts and have SpliceAI ∆ scores ≤ 0.10.

**BP7\_Variable (RNA):** Applicable for variants with RNA data, with weighting based on the quality of the available RNA data.

