## I learnt EMBOSS Needle (Global Pairwise Alignment)!

To complement the BLAST heuristic local alignment, I performed a global pairwise alignment
of human and mouse FLT3 protein sequences using EMBOSS Needle
(Needleman-Wunsch algorithm, BLOSUM62 matrix, gap open penalty 10, gap extend 0.5).

These is a snapshot of my results: (worth mentioning that BLAST will not really give you these information) 
- Identity: 854/1000 (85.4%)
- Similarity: 910/1000 (91.0%)
- Gaps: 7/1000 (0.7%)
- Alignment score: 4551.5

The low gap percentage (0.7%) explains the position numbering offset I mentioned in the previous file
between human and mouse sequences in the BLAST alignment, there are only 7 insertions
or deletions exist across the full length of both proteins, confirming that
FLT3 is structurally well-conserved between the two species.

### Conservation at the sites in question

**Position 835 (D835Y site):**
```
NP_004110.2  798  GMEFLEFKSCVHRDLAARNVLVTHGKVVKICDFGLARDIMSDSNYVVRGN  847
                  |||||||||||||||||||||||||||||||||||||||:|||:||||||
NP_034359.2  801  GMEFLEFKSCVHRDLAARNVLVTHGKVVKICDFGLARDILSDSSYVVRGN  850
```
Human position 835 = D (Aspartic acid)
Mouse equivalent position = D (Aspartic acid)
Alignment symbol = | (exact match)
**Finding confirmed: D835 is perfectly conserved between human and mouse.**

**ITD region (~positions 558–617):**
```
NP_004110.2  550  VCLLFIVVLTLLICHKYKKQFRYESQLQMVQVTGSSDNEYFYVDFREYEY  599
                  :||.|||||.:||||||||||||||||||:||||..||||||||||:|||
NP_034359.2  551  LCLPFIVVLIVLICHKYKKQFRYESQLQMIQVTGPLDNEYFYVDFRDYEY  600
```
The ITD region shows mostly conservative substitutions (: symbols) with a
notable non-conservative difference around positions 585–586 where SS (human)
is replaced by PL (mouse).
**Finding confirmed: ITD region is broadly conserved with some positional variation.**

### Comparison of BLAST vs EMBOSS Needle Results

| Metric | BLAST | EMBOSS Needle |
|---|---|---|
| Identity | 86.48% | 85.4% |
| Gaps | Not reported by BLAST | 0.7% (7 positions) |
| D835 conservation | D=D, \| symbol | D=D, \| symbol |
| ITD region pattern | SS→PL notable difference | SS→PL notable difference |

The small difference in identity (86.48% vs 85.4%) reflects the methodological
difference between local alignment (BLAST finds the best matching regions) and
global alignment (EMBOSS Needle aligns full sequences end to end, including
harder-to-align terminal regions). Both tools agree on all key biological findings.

Two independent alignment methods producing consistent results strengthens the conservation findings reported above.

### Note on BioEdit Visualization
Multiple sequence alignment of all 4 species (human, mouse, chimpanzee, dog)
was performed using BioEdit. Alignment screenshots showing conservation across
all species at the D835 site and ITD region are provided in the `images/` folder.
