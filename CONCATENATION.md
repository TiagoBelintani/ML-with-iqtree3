
# Alignment Concatenation and Partition Preparation

## Step 1: Generate list of loci

```bash
find alinhamentos_50_finais -name "*.fasta" | sort > loci_list.txt
```

## Step 2: Concatenate and generate .charsets

```bash
AMAS.py concat \
  -i $(cat loci_list.txt | tr '\n' ' ') \
  -f fasta \
  -d dna \
  -u phylip \
  -t concatenated_matrix.phylip \
  -o concatenated_matrix.charsets
```

## Step 3: Convert Partitions

Convert the `.charsets` file generated by AMAS to IQ-TREE 3 format using this tool:

👉 https://github.com/TiagoBelintani/Charset-converter-for-IQ-TREE-/tree/main
