# FLT3-Conserve: Week 5 Findings
## Phylogenetic Analysis of FLT3 Across 4 Species

## Method
Multiple sequence alignment was performed using ClustalW in MEGA 12.
A phylogenetic tree was constructed using the Neighbor-Joining method
with Poisson correction model. Bootstrap replicates: 1000.
Raw FASTA files were preprocessed from the command line using sed to
remove Windows line endings before analysis. |in Hausa| (Wannan abun ya ban wahala)

## Tree Topology
- Human and chimpanzee cluster together (most closely related). See [image](../images/FLT3_phylogenetic_tree.png).
- Dog and mouse cluster separately from primates
- Tree topology matches known evolutionary relationships — validates
  sequences are genuine orthologs


## Key Findings
- Branch lengths are short overall — FLT3 evolves slowly, consistent
  with strong functional constraint on a critical receptor tyrosine kinase
- Mouse branch is longer than chimp branch — consistent with known rodent
  rate acceleration and the 86.48% vs 93.15% identity seen in Week 3 BLAST
- Slow evolutionary rate supports conservation findings at D835 and
  juxtamembrane region from Weeks 3 and 4

## Clinical Relevance
FLT3's slow evolutionary rate reflects strong purifying selection —
mutations are generally harmful and selected against. This provides
evolutionary context for why FLT3-ITD and FLT3-TKD are pathogenic:
they disrupt a protein whose sequence has been conserved because it is
functionally essential. The conservation of the kinase domain also
explains why targeted inhibitors (midostaurin, gilteritinib) bind
effectively — the drug target has not drifted significantly across
evolutionary time.

## Limitations
- Of course Only 4 species — a larger panel would produce a more robust tree
- Bootstrap values not displayed — would quantify branching confidence
- Single gene tree may not perfectly reflect species relationships

## Tools
MEGA 12, ClustalW, Neighbor-Joining method, command line (sed, git)

## Up Next
Weeks 6-8: Python conservation scoring and visualization across all
993 positions with domain and mutation site annotation.