## Model Benchmark Results












Rerun phi-4-mulitmodal-instruct for bf16 since those results are gone










| Model         | Precision | VQA  | TextVQA |
|---------------|----------|------|---------|
| SmolVLM2-2.2b | BF16     | 62.77 | 64.5    |
| Phi-4-multimodal-instruct | BF16     | 71.57 | 63.03    |
| Molmo-7B-D | BF16     | 59.07 | 56.63    |

### Quantized Results

| Model         | Precision | Block Size | VQA   | TextVQA |
|---------------|----------|------------|-------|---------|
| SmolVLM2-2.2b | MXINT8   | 32         | 63.17 | 64.19   |
|               |          | 128        | 62.11 | 64.33   |
| SmolVLM2-2.2b | MXINT4   | 32         | 73.43 | 59.3    |
|               |          | 128        | 73.08 | 57.29   |
| SmolVLM2-2.2b | MXINT2   | 32         | 0.00     | 0.00       |
|               |          | 128        | 0.00     | 0.00       |
| SmolVLM2-2.2b | INT8   | - | 54.63 | 60.81    |
| SmolVLM2-2.2b | INT4   | -    | 0.00   | 0.00  |
| SmolVLM2-2.2b | INT2   | -         | 0.00     | 0.00       |
| Phi-4-multimodal-instruct | MXINT8   | 32         | 71.57 | 62.93   |
|               |          | 128        | - | -   |
| Phi-4-multimodal-instruct | MXINT4   | 32         | 67.64 | 59.06    |
|               |          | 128        | - | -   |
| Phi-4-multimodal-instruct | MXINT2   | 32         | 0.00     | 0.00       |
|               |          | 128        | -     | -       |
| Phi-4-multimodal-instruct | INT8   | - | 70.33 | 61.70    |
| Phi-4-multimodal-instruct | INT4   | -    | 0.02   | 0.00  |
| Phi-4-multimodal-instruct | INT2   | -         | 0.00     | 0.00       |
| Molmo-7B-D | MXINT8   | 32         | 59.00 | 56.37   |
|               |          | 128        | - | -   |
| Molmo-7B-D | MXINT4   | 32         | 56.29 | 52.92    |
|               |          | 128        | - | -   |
| Molmo-7B-D | MXINT2   | 32         | 0.00     | 0.00       |
|               |          | 128        | -     | -       |
| Molmo-7B-D | INT8   | - | 58.97 | 57.29    |
| Molmo-7B-D | INT4   | -    | 0.47   | 0.05  |
| Molmo-7B-D | INT2   | -         | 0.07     | 0.41       |


---

### Observations:
- **BF16** is the baseline.
- **MXINT8** shows performance similar to BF16.
- **MXINT4** improves VQA but shows poor performance TextVQA.
- **MXINT2** collapses completely, all zero scores.