Week 3 Findings (sequence alignment, clinical significance of my findings so far). 
## Sequence Alignment — BLAST Results and Conservation at Mutation Sites

## Method

I used Human FLT3 protein (NP_004110.2, 993 aa) as query in pairwise BLAST searches
(blastp) against three species: mouse (*Mus musculus*), chimpanzee (*Pan troglodytes*),
and dog (*Canis lupus familiaris*). Then I used organism filter in each search to
restrict results to the target species. Alignment outputs were then examined manually at the two
clinically significant regions: the D835 site (tyrosine kinase domain) and the ITD
region (juxtamembrane domain, approximately positions 571–620).

## These were my BLAST Results: Overall Sequence Identity

| Comparison | E-value | % Identity | Subject Accession |
|---|---|---|---|
| Human vs Mouse | 0.0 | 86.48% | NP_034359.2 |
| Human vs Chimp | 0.0 | 93.15% | XP_021785212.2 |
| Human vs Dog | 0.0 | 91.84% | NP_001018647.1 |

All three comparisons returned E-values of 0.0, confirming that FLT3 homology across
these species is not due to chanc.

The percent identity pattern follows expected evolutionary relationships: chimpanzee (which is most
closely related to human) shows the highest identity at 93.15%, followed by dog at
91.84%, and mouse at 86.48%.

## Important Note I saw (had to seek help here): Position Numbering Offsets

An observation from the alignment: human FLT3 and mouse FLT3 do not share
identical position numbering. In the alignment section I manually examined, the human query began
at position 796 while the mouse subject began at position 799 — a 3-position offset.
This reflects small insertions or deletions (indels) earlier in the sequence that shift
position numbers between species.

This confirms that direct position-by-position numerical comparison between species
(without alignment) is unreliable. So I was careful not to rely on manual numbering.

## Finding 1: D835 Site (Tyrosine Kinase Domain) is fully conserved

Alignment region examined (human positions 796–855):

```
Query  796  AKGMEFLEFKSCVHRDLAARNVLVTHGKVVKICDFGLARDIMSDSNYVVRGNARLPVKWM  855
            AKGMEFLEFKSCVHRDLAARNVLVTHGKVVKICDFGLARDI+SDS+YVVRGNARLPVKWM
Sbjct  799  AKGMEFLEFKSCVHRDLAARNVLVTHGKVVKICDFGLARDILSDSSYVVRGNARLPVKWM  858
```

Human position 835 = **D (Aspartic acid)**
Mouse equivalent position (838) = **D (Aspartic acid)**

Dog alignment (human vs dog) also confirmed **D at position 835**, with exact match
(| symbol) in the alignment middle row.

Chimpanzee confirmed **D at position 835** — consistent with the high overall identity
(93.15%) and close evolutionary relationship to human.

**Summary:** Position 835 carries D (Aspartic acid) in all four species examined —
human, mouse, chimpanzee, and dog. This position is fully conserved across approximately
80–90 million years of mammalian evolution.

## Finding 2: ITD Region (Juxtamembrane Domain) is mostly Conserved, with variation.

Alignment region examined (human positions 558–617):

```
Query  558  LTLLICHKYKKQFRYESQLQMVQVTGSSDNEYFYVDFREYEYDLKWEFPRENLEFGKVLG  617
            L +LICHKYKKQFRYESQLQM+QVTG  DNEYFYVDFR+YEYDLKWEFPRENLEFGKVLG
Sbjct  559  LIVLICHKYKKQFRYESQLQMIQVTGPLDNEYFYVDFRDYEYDLKWEFPRENLEFGKVLG  618
```

The ITD region shows mostly conserved sequence with some positions differing:
- Several positions show **+** symbols (conservative substitutions i.e chemically similar
  amino acids, e.g. V↔I, which are both nonpolar)
- Positions ~585–586 show a notable difference: **SS (human) → PL (mouse)** — a
  non-conservative substitution where two serine residues in human are replaced by
  proline and leucine in mouse

The region is broadly conserved but shows more variation than the D835 kinase domain
site.

## We can infer that conservation differs between the two mutation sites

Comparing the two clinically significant regions:

| Region | Conservation | Middle row character |
|---|---|---|
| D835 (kinase domain) | Perfect, identical in all species | All \| symbols |
| ITD region (juxtamembrane) | Mostly conserved, some variation | Mix of \|, +, and spaces |

This difference in conservation patterns between the two mutation sites is clinically
meaningful:

**D835** sits in the activation loop of the kinase domain — a region so functionally
critical that it has remained identical across tens of millions of years of mammalian
evolution. Mutating D835 to Y (D835Y) disrupts a residue that evolution has
not tolerated changing, which helps explain at a molecular level why this mutation
constitutively activates the kinase and drives leukemogenesis.

**The ITD region** shows broader conservation (the region overall is clearly homologous
across species) but individual positions within it tolerate some variation. This is the nature of FLT3-ITD mutations. They are not single point mutations
at one critical residue, but rather duplications of a stretch of sequence. The
juxtamembrane domain appears to tolerate more positional variation while still
maintaining its overall structural role, and it is the duplication of this stretch
(rather than a change at one conserved residue) that disrupts its autoinhibitory
function.

## Clinical Relevance

FLT3-ITD and FLT3-TKD mutations are treated as distinct
entities with different prognostic implications. While ITD carries adverse risk, TKD
carries comparatively less severe risk. The conservation patterns observed here
offer a structural-evolutionary basis for why these two mutation types might behave
differently:

- FLT3-TKD (D835Y) disrupts a perfectly conserved, functionally critical residue —
  a precise molecular insult at an evolutionarily protected site
- FLT3-ITD duplicates a region that, while broadly conserved, shows more positional
  flexibility. This is a different kind of disruption, affecting domain architecture rather
  than a single critical residue

These findings are preliminary and based on a small species panel (4 species). Formal
multiple sequence alignment across a larger species panel would strengthen these
conclusions.

## My next step.

- I will go into formal domain analysis to identify full boundaries of juxtamembrane and
  kinase domains, assess conservation within each domain comprehensively rather than
  just at specific sites
