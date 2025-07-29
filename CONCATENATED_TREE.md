
# Concatenated Tree Inference with IQ-TREE 3

Run IQ-TREE 3 on the concatenated alignment with partition support:

```bash
iqtree3 -s concatenated_matrix.phylip \
  -p concatenated_matrix_iqtree.charsets \
  -st DNA \
  -m MFP+MERGE \
  -bb 1000 \
  -alrt 1000 \
  -nt AUTO \
  --safe \
  --rcluster 10 \
  --redo \
  -blmin 0.0001 -blmax 1.0 \
  -pre iqtree_concatenated
```
