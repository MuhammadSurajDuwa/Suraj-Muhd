# FLT3-Conserve: Weeks 6–8 Findings
## Python Conservation Scoring and Visualization

## Overview

This phase represents the computational capstone of the project — translating
the manual alignment findings from Weeks 3–4 into a fully programmatic,
quantitative analysis using Python. All code is available in
`notebooks/conservation_analysis.ipynb`.

## Tools and Libraries

- Python 3 (Anaconda distribution)
- BioPython — sequence and alignment file handling
- Pandas — data manipulation and domain annotation
- Matplotlib — visualization
- Jupyter Notebook — interactive analysis environment
- Git/GitHub — version control from command line

## Method

### 1. Sequence loading
Four FLT3 protein sequences (human, mouse, chimpanzee, dog) were loaded
programmatically from FASTA files using BioPython's SeqIO module.

### 2. Alignment loading
The ClustalW multiple sequence alignment generated in MEGA 12 (Week 5) was
exported as a FASTA alignment file and loaded using BioPython's AlignIO module.
Total alignment length: 1000 positions (993 + 7 gap-insertion columns).

### 3. Conservation scoring
For each of the 1000 alignment positions, a conservation score was calculated:

```
score = count of most common amino acid / total number of sequences (4)
```

Scores range from 0.5 (only 2 of 4 species agree) to 1.0 (all 4 species identical).

### 4. Domain annotation
A Pandas dataframe was built with one row per position, annotated with:
- Domain label (juxtamembrane: 591–597, kinase: 610–943, other)
- Mutation site label (D835Y, ITD_region, or none)

### 5. Visualization
A conservation plot was generated using Matplotlib showing:
- Conservation score across all 1000 positions (blue line)
- Kinase domain highlighted in orange (positions 610–943)
- Juxtamembrane region highlighted in green (positions 591–597)
- D835Y site marked with a red dashed vertical line

See `images/FLT3_conservation_plot.png` and `results/FLT3_conservation_plot.png`

## Results

### Overall conservation statistics

| Metric | Value |
|---|---|
| Total positions scored | 1000 |
| Average conservation score | 0.94 |
| Fully conserved positions (score = 1.0) | 810 (81%) |
| Variable positions (score < 1.0) | 190 (19%) |

FLT3 is highly conserved overall — 94% average conservation across 4 species
spanning ~90 million years of mammalian evolution.

### Conservation by domain

| Domain | Positions | Mean Conservation Score |
|---|---|---|
| Kinase domain (610–943) | 334 | **0.970** |
| Juxtamembrane region (591–597) | 7 | 0.929 |
| Other regions | 659 | 0.927 |

**The kinase domain is the most conserved region of FLT3** — mean score 0.970,
higher than both the juxtamembrane region and the rest of the protein.

### Key mutation sites

| Site | Position | Conservation Score | Domain |
|---|---|---|---|
| D835Y (FLT3-TKD) | 835 | **1.0** | Kinase |
| ITD region | 591–620 | 0.929 (mean) | Juxtamembrane |

Position 835 is perfectly conserved across all 4 species (score = 1.0) —
confirmed computationally, consistent with manual alignment findings in Week 3.

## Interpretation

### Kinase domain conservation supports D835Y pathogenicity
The kinase domain has the highest mean conservation score (0.970) of any
region in FLT3. Position 835 itself scores 1.0 — identical across human,
mouse, chimpanzee, and dog. This quantitative evidence supports the conclusion
that D835 is under strong evolutionary constraint, and mutations there
(D835Y) disrupt a functionally essential residue.

### Juxtamembrane conservation supports ITD pathogenicity
The juxtamembrane region scores 0.929 — conserved, but slightly less strictly
than the kinase domain. This is consistent with the nature of FLT3-ITD: rather
than disrupting a single strictly conserved residue (as D835Y does), ITD
duplicates a region that tolerates some positional variation but whose overall
architecture is essential for autoinhibition.

### Conservation gradient matches clinical severity gradient
The pattern of domain-level conservation scores mirrors clinical observations:

- Kinase domain (0.970) → D835Y → moderate adverse risk
- Juxtamembrane (0.929) → FLT3-ITD → high adverse risk

Note: higher conservation does not automatically predict higher clinical
aggressiveness — FLT3-ITD is clinically more adverse than D835Y despite
occurring in a slightly less conserved region. This is because clinical
aggressiveness depends on the *mechanism* of kinase dysregulation (ITD
abolishes autoinhibition completely) rather than conservation score alone.
This distinction is discussed in findings_week4.md.

## Limitations

- Only 4 species — a larger panel would produce more robust conservation scores
- Conservation scores do not account for biochemically similar substitutions
  (e.g. V→I scores as non-conserved despite being chemically similar)
- Alignment column numbers do not directly correspond to original sequence
  position numbers due to gap insertion — domain boundary annotations are
  approximate in the alignment coordinate space

## Files Generated

| File | Description |
|---|---|
| `notebooks/conservation_analysis.ipynb` | Full Python analysis notebook |
| `images/FLT3_conservation_plot.png` | Conservation plot with domain annotations |
| `results/FLT3_conservation_plot.png` | Same plot saved to results folder |
