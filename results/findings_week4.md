# Week 4 Findings
## Domain Analysis

## Overview

In this session I focused on formally identifying the domain boundaries of FLT3
using two independent databases (NCBI and UniProt), cross-checking their annotations,
and assessing conservation at the juxtamembrane critical region across all 4 species.
Full motif discovery and domain-level conservation analysis will be added when covered
formally in the course (Week 4 content).

## Domain Boundaries

### From NCBI (NP_004110.2)

| Region | Start | End | Notes |
|---|---|---|---|
| Signal peptide | 1 | 27 | Cleaved in mature protein |
| Ig-like domain | 256 | 345 | Extracellular, ligand binding |
| Transmembrane region | 544 | 563 | Anchors protein in cell membrane |
| Juxtamembrane region | 591 | 597 | Critical autoinhibitory region, ITD site |
| Protein kinase domain | 572 | 947 | Catalytic domain, contains D835 |

### From UniProt (P36888)

| Region | Start | End | Notes |
|---|---|---|---|
| Ig-like C2-type domain | 253 | 343 | Extracellular |
| Juxtamembrane region | 591 | 597 | Important for normal kinase regulation |
| Protein kinase domain | 610 | 943 | Catalytic domain |

### Comparison: NCBI vs UniProt

| Region | NCBI | UniProt | Agreement |
|---|---|---|---|
| Juxtamembrane | 591–597 | 591–597 |  Exact match |
| Kinase domain | 572–947 | 610–943 |  Minor difference |

The juxtamembrane boundaries are identical across both databases. The kinase domain
shows a minor difference in start/end positions and this reflects different criteria
used by each database for defining domain boundaries (not a biological discrepancy!).
UniProt annotation (610–943) is used as the primary reference for functional
boundaries going forward, as UniProt applies more stringent functional curation.

## Juxtamembrane Region Conservation (591–597)

Multiple sequence alignment of all 4 species (human, mouse, chimpanzee, dog) in
BioEdit ClustalW shows that the juxtamembrane critical region (positions 591–597)
is **fully conserved across all 4 species** — identical amino acids at every position
in this short but functionally critical stretch.

This is consistent with UniProt's annotation describing this region as essential for
"normal regulation of kinase activity and for maintaining the kinase in an inactive
state in the absence of bound ligand."

## Mechanistic Note: Phosphorylation Sites in the Juxtamembrane Region

NCBI lists several phosphotyrosine sites within and immediately adjacent to the
juxtamembrane region (positions 572, 574, 589, 591, 599). These are sites of
autocatalytic phosphorylation that occur during normal FLT3 activation by its ligand.
FLT3-ITD bypasses this normal phosphorylation-dependent activation entirely by
duplicating a stretch of the juxtamembrane domain, abolishing its autoinhibitory
function constitutively, independent of ligand binding.

The full conservation of this region across species (despite it being the ITD
mutation site) reflects how structurally essential this region is for normal kinase
regulation. FLT3-ITD does not disrupt it by point mutation but by duplication —
a fundamentally different mechanism from FLT3-TKD (D835Y), which disrupts a single
conserved residue in the activation loop by substitution.

## Clinical Relevance

The domain boundary analysis provides structural context for the clinical distinction
between FLT3-ITD and FLT3-TKD:

- **FLT3-ITD** disrupts a fully conserved autoinhibitory region (591–597) by
  duplication. This abolishes the brake mechanism that keeps FLT3 inactive, producing
  strong constitutive kinase activation and adverse prognosis
- **FLT3-TKD (D835Y)** disrupts a single conserved residue in the activation loop
  of the kinase domain — a more precise molecular insult producing moderate
  constitutive activation and comparatively less adverse prognosis

Both mutation types hit conserved regions — but they hit them differently, which
helps explain why they behave differently clinically.

## Pending: Full Motif Analysis

Formal motif discovery within each domain will be added to this
document when covered in the course. Known ATP binding site positions from NCBI
(616–619, 622, 624, 642, 644, 675, 691–694, 811, 815–816, 818, 828–829) will be
assessed for conservation across species at that point.

## Tools Used This Week
- NCBI GenBank (NP_004110.2) — domain feature annotations
- UniProt (P36888) — functional domain boundaries and descriptions
- BioEdit ClustalW — multiple sequence alignment visualization
