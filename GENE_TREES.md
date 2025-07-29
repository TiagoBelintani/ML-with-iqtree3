
# Gene Tree Inference (Per-Locus)

Generate ML trees for each gene using IQ-TREE and GNU Parallel.

## Step 1: Create list of loci

```bash
find 50p -name "*.fasta" | sort > loci_list.txt
```

## Step 2: Run IQ-TREE in parallel

```bash
run_iqtree () {
    FILE="$1"
    BASENAME=$(basename "$FILE" .fasta)
    DIR=$(dirname "$FILE")

    iqtree3 \
      -s "$FILE" \
      -st DNA \
      -m MFP \
      -bb 1000 \
      -alrt 1000 \
      -nt 4 \
      --redo \
      -pre "$DIR/${BASENAME}"
}

export -f run_iqtree
parallel -j 4 run_iqtree :::: loci_list.txt
```
