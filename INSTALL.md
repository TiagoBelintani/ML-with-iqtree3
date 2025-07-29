
# Installation Instructions

This guide walks you through installing all required dependencies for running the phylogenomic pipeline.

## Conda Installation

If you don’t have conda, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) first.

Then run:

```bash
conda create -n phylo -c bioconda iqtree=2 amas parallel python=3.10
conda activate phylo
```

This will install:

- IQ-TREE 3 (phylogenetic inference)
- AMAS (alignment concatenation and partition generation)
- GNU Parallel (for parallel processing)
- Python 3.10 (for helper scripts)
