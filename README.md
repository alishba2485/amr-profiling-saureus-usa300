# Antimicrobial Resistance Gene Profiling of *Staphylococcus aureus* USA300

Independent bioinformatics project screening a clinical MRSA (methicillin-resistant *Staphylococcus aureus*) genome for acquired antimicrobial resistance genes using ResFinder.

## Objective

To identify and characterize acquired antimicrobial resistance (AMR) determinants in the genome of *S. aureus* USA300, a well-characterized community-associated MRSA lineage, using a standard genomic epidemiology workflow.

## Data source

- **Organism:** *Staphylococcus aureus* USA300
- **Genome assembly:** GCA_000568455.1 (ASM56845v1)
- **Source:** NCBI Genome / NCBI Datasets
- **Format:** Genome assembly FASTA (.fna)

## Method

1. Downloaded the complete genome assembly (FASTA format) from NCBI Datasets.
2. Uploaded the genome to [ResFinder](https://genomicepidemiology.org) (Center for Genomic Epidemiology, DTU), screening against all antimicrobial resistance gene classes.
3. Parsed the resulting gene hit table and phenotype prediction table.
4. Cross-referenced each detected gene against its resistance mechanism for biological interpretation.

**Tools used:** ResFinder (web server), NCBI Datasets

## Results

Six acquired resistance genes were detected, all with high identity (98.98–100%) and full or near-full length coverage against reference sequences:

| Gene | Identity | Coverage | Location | Resistance phenotype |
|---|---|---|---|---|
| **mecA** | 100.00% | 100.0% | Chromosome | Beta-lactams (amoxicillin, ampicillin, cefepime, cefotaxime, cefoxitin, ceftazidime, ertapenem, imipenem, meropenem, piperacillin, and combinations) |
| **blaZ** | 100.00% | 100.0% | Plasmid pUSA01-ISMMS | Amoxicillin, ampicillin, penicillin, piperacillin |
| **aph(3')-III** | 100.00% | 100.0% | Plasmid pUSA01-ISMMS | Kanamycin, amikacin, neomycin, and related aminoglycosides |
| **ant(6)-Ia** | 99.69% | 70.5% | Plasmid pUSA01-ISMMS | Streptomycin |
| **msr(A)** | 98.98% | 100.0% | Plasmid pUSA01-ISMMS | Erythromycin, azithromycin, telithromycin, and streptogramin-class agents |
| **mph(C)** | 100.00% | 100.0% | Plasmid pUSA01-ISMMS | Erythromycin, spiramycin, telithromycin |

*Note: the erythromycin/telithromycin phenotype association for mph(C) is currently listed as "unpublished" in the ResFinder database — meaning it is a curator-submitted association rather than one tied to a specific peer-reviewed citation. The gene detection itself (100% identity, full-length match) is high-confidence.*

## Interpretation

- **mecA** is the defining genetic marker of methicillin resistance in *S. aureus*. It encodes an alternative penicillin-binding protein (PBP2a) with low affinity for beta-lactam antibiotics, allowing cell wall synthesis to continue even in the presence of these drugs — this confirms the genome is a true MRSA isolate, consistent with its USA300 designation.
- **blaZ** encodes a beta-lactamase that hydrolyzes the beta-lactam ring of penicillins, providing an additional, mecA-independent resistance mechanism.
- Four of the six genes (**blaZ, aph(3')-III, ant(6)-Ia, msr(A), mph(C)**) are located on plasmid pUSA01-ISMMS rather than the chromosome. Plasmid-borne resistance genes are of particular concern epidemiologically, as plasmids can transfer between bacterial cells via horizontal gene transfer, potentially spreading resistance beyond a single clonal lineage.
- **msr(A)** and **mph(C)** together account for macrolide resistance via two distinct mechanisms: msr(A) is an ABC-transporter-type efflux protein, while mph(C) is a phosphotransferase that chemically inactivates the antibiotic — their co-occurrence provides redundant resistance to the same drug class.

## Limitations

- This analysis detects the *presence* of resistance genes, not phenotypic (lab-confirmed) resistance — actual susceptibility can be influenced by gene expression, regulatory context, and other factors not captured by sequence screening alone.
- ResFinder identifies acquired resistance genes and does not screen for resistance-conferring point mutations in core genes (e.g. gyrA mutations for fluoroquinolone resistance), so this represents a partial picture of the strain's total resistance profile.
- This is a single reference genome analysis performed for skills demonstration; it reproduces known characteristics of a well-studied strain rather than presenting novel findings.

## Skills demonstrated

- Genome data retrieval from NCBI Datasets
- Command-line/web-based bioinformatics tool usage (ResFinder)
- Interpretation of sequence identity, coverage, and phenotype prediction outputs
- Biological interpretation of resistance mechanisms (target modification, enzymatic inactivation, efflux)
- Documentation of a reproducible bioinformatics workflow

## References

- ResFinder: Zankari E, et al. "Identification of acquired antimicrobial resistance genes." *J Antimicrob Chemother.* 2012.
- Genome assembly: NCBI GCA_000568455.1
