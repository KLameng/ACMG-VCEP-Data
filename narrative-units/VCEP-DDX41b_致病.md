# DDX41（GN159）— Myeloid Malignancy VCEP 规范 v1.0

> 来源：ClinGen CSpec Registry API（GN159，2026-11-09 抓取；官网 Released 2026-11-02）
> 转录本：NM_016222.4

## 致病证据码（DDX41 v1.0 原文）

### PVS1

Null variant (nonsense, frameshift, canonical +/−1 or 2 splice sites, initiation codon, single or multi-exon deletion) in a gene where loss of function (LOF) is a known mechanism of disease.
Caveats:
 * Beware of genes where LOF is not a known disease mechanism (e.g. GFAP, MYH7).
 * Use caution interpreting LOF variants at the extreme 3’ end of a gene.
 * Use caution with splice variants that are predicted to lead to exon skipping but leave the remainder of the protein intact.
 * Use caution in the presence of multiple transcripts.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ✅
**PVS1\_Very Strong:** Use appropriate _DDX41_ decision tree.

**PVS1\_Very Strong (RNA):** Use for an observed splicing defect.

- **Strong** ✅
**PVS1\_Strong:** Use appropriate _DDX41_ decision tree.

**PVS1\_Strong (RNA):** Use for an observed splicing defect.

- **Moderate** ✅
**PVS1\_Moderate:** Use appropriate _DDX41_ decision tree.

**PVS1\_Moderate (RNA):** Use for an observed splicing defect.

- **Supporting** ✅
**PVS1\_Supporting (RNA):** Use for an observed splicing defect.


### PS1

Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.
Example: Val->Leu caused by either G>C or G>T in the same codon.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ✅
**For missense variants:** 

*   **PS1:** Same amino acid change as a previously established pathogenic variant regardless of nucleotide change.

**For splice site variants:** 

*   **PS1:** Follow recommendations by the ClinGen SVI Splicing Subgroup (PMID: 37352859).

- **Moderate** ✅
**For missense variants:** 

*   **PS1\_Moderate:** Same amino acid change as a previously established likely pathogenic variant regardless of nucleotide change.

**For splice site variants:** 

*   **PS1\_Moderate:** Follow recommendations by the ClinGen SVI Splicing Subgroup (PMID: 37352859).

- **Supporting** ✅
**For splice site variants:** 

*   **PS1\_Supporting:** Follow recommendations from the ClinGen SVI Splicing Subgroup (PMID: 37352859)


### PS4

The prevalence of the variant in affected individuals is significantly increased compared to the prevalence in controls.
Note 1: Relative risk (RR) or odds ratio (OR), as obtained from case-control studies, is >5.0 and the confidence interval around the estimate of RR or OR does not include 1.0. See manuscript for detailed guidance.
Note 2: In instances of very rare variants where case-control studies may not reach statistical significance, the prior observation of the variant in multiple unrelated patients with the same phenotype, and its absence in controls, may be used as moderate level of evidence.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ✅
**PS4\_Very\_Strong**: lower bound of the OR’s confidence interval ≥ 350

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.

- **Strong** ✅
**PS4\_Strong**: lower bound of the OR’s confidence interval ≥ 18.7

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.

- **Moderate** ✅
**PS4\_Moderate**: lower bound of the OR’s confidence interval ≥ 4.33

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.

- **Supporting** ✅
**PS4\_Supporting**: lower bound of the OR’s confidence interval ≥ 2.08

Caveats:

*   Cases should be limited to individuals with AML or MDS.
*   Make sure to only count unrelated probands if performing case-control analysis.
*   Perform case-control analysis with ancestry-matched group using the highest frequency of the variant in the appropriate continental population. If control data to be used is available in both a population database and an ancestry-specific database, preference should be given to the more robust control cohort; where appropriate, data from both sources may be combined to maximize effective control sample size while maintaining ancestral comparability.


### PM2

Absent from controls (or at extremely low frequency if recessive) in Exome Sequencing Project, 1000 Genomes or Exome Aggregation Consortium.
Caveat: Population data for indels may be poorly called by next generation sequencing.

- **Stand Alone** ❌ `Not applicable`
- **Very Strong** ❌ `Not applicable`
- **Strong** ❌ `Not applicable`
- **Moderate** ❌ `Not Applicable`
- **Supporting** ✅
**PM2\_Supporting:** Variant must be completely absent from major population databases.

Caveats:

*   The mean coverage of _DDX41_ in the population database used should be at least 20x.
*   PM2\_Supporting not applicable if PS4 is met at any strength level.


### PM4

Protein length changes due to in-frame deletions/insertions in a non-repeat region or stop-loss variants.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable`
- **Moderate** ✅
**Protein extension variants:**

**PM4:** Per modified PM4 decision tree for stop-loss variants and In-frame indel including the stop codon.

- **Supporting** ❌ `Not Applicable`

### PM5

Novel missense change at an amino acid residue where a different missense change determined to be pathogenic has been seen before.
Example: Arg156His is pathogenic; now you observe Arg156Cys.
Caveat: Beware of changes that impact splicing rather than at the amino acid/protein level.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ✅
**Missense Variants:**

*   **PM5\_Strong:** Missense change at an amino acid residue where ≥ 2 different missense changes which have previously been determined to be pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than alternate residue of the known pathogenic/likely pathogenic variant.

- **Moderate** ✅
**Missense Variants:**

*   **PM5\_Moderate:** Missense change at an amino acid residue where a different missense change which has previously been determined to be pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than alternate residue of the known pathogenic/likely pathogenic variant

- **Supporting** ✅
**Missense Variants:**

*   **PM5\_Supporting:** Missense change at an amino acid residue where a different missense change which has previously been determined to be likely pathogenic (after accounting for Grantham scores).
*   Caveats:
    *   Beware of changes that impact splicing rather than at the amino acid/protein level.
    *   Compare the Grantham scores of the original and variant residues to assess the similarities between the residues’ properties. Only applicable at the appropriate strength level if the alternate residue of the new variant is equal or higher than the alternate residue of the known pathogenic/likely pathogenic.

**Null Variants**

*   **PM5\_Supporting:** Nonsense/frameshift variants in an exon which contains ≥2 P/LP null variants, and the variant is predicted to lead to NMD or NSD (_**DDX41**_ **PM5\_Supporting Table)**.


### PP1

Co-segregation with disease in multiple affected family members in a gene definitively known to cause the disease.
Note: May be used as stronger evidence with increasing segregation data.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ✅
**PP1\_Strong**: ≥ 7 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

- **Moderate** ✅
**PP1\_Moderate**: 5 or 6 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

- **Supporting** ✅
**PP1\_Supporting**: 3 or 4 meioses observed within one family or across multiple families.

Caveats:

*   If PP4 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.


### PP3

Multiple lines of computational evidence support a deleterious effect on the gene or gene product (conservation, evolutionary, splicing impact, etc.).
Caveat: As many in silico algorithms use the same or very similar input for their predictions, each algorithm should not be counted as an independent criterion. PP3 can be used only once in any evaluation of a variant.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ❌ `Not Applicable`
- **Moderate** ❌ `Not Applicable`
- **Supporting** ✅
**For missense variants:**

**PP3:** AlphaMissense score ≥ 0.792

**For any variant (except canonical splice site variants):**

**PP3:**

*   SpliceAI ∆ scores ≥ 0.20 including the creation of cryptic splice sites.
*   Do not use for variants with a predicted splicing effect that is proven by RNA analysis. See **PVS1\_Variable (RNA)**.


### PP4

Patient’s phenotype or family history is highly specific for a disease with a single genetic etiology.

- **Stand Alone** ❌ `Not Applicable for this VCEP`
- **Very Strong** ❌ `Not Applicable for this VCEP`
- **Strong** ✅
**PP4\_Strong:** OddsPath ≥ 18.7

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

- **Moderate** ✅
**PP4\_Moderate:** OddsPath ≥ 4.33

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

- **Supporting** ✅
**PP4\_Supporting:** OddsPath ≥ 2.08

Caveats:

*   When calculating OddsPath, care should be taken to avoid selective inclusion of only positive cases (i.e., cases with germline variant under assessment and an acquired second somatic hit). All identified cases carrying the same germline variant, including those without a recurrent or non-recurrent somatic second hit, must be included to avoid biasing or skewing the OddsPath calculation and pathogenicity evaluation.
*   If PP1 is also applicable, evaluate PP4 first. The combination of PP4 and PP1 is capped at Strong (+4 points), in accordance with current SVI guidance.

