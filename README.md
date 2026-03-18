## Model Benchmark Results

| Model         | Precision | VQA  | TextVQA |
|---------------|----------|------|---------|
| SmolVLM2-2.2b | BF16     | 62.77 | 64.5    |

### Quantized Results

| Model         | Precision | Block Size | VQA   | TextVQA |
|---------------|----------|------------|-------|---------|
| SmolVLM2-2.2b | MXINT8   | 32         | 63.17 | 64.19   |
|               |          | 128        | 62.11 | 64.33   |
| SmolVLM2-2.2b | MXINT4   | 32         | 73.43 | 59.3    |
|               |          | 128        | 73.08 | 57.29   |
| SmolVLM2-2.2b | MXINT2   | 32         | 0     | 0       |
|               |          | 128        | 0     | 0       |

---

### Observations:
- **BF16** is the baseline.
- **MXINT8** shows performance similar to BF16.
- **MXINT4** improves VQA but shows poor performance TextVQA.
- **MXINT2** collapses completely, all zero scores.