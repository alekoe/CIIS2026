# Precomputed prediction schema

Both CSV files contain one row per clip.

| Column | Meaning |
|---|---|
| `filename` | RAVDESS-compatible MP4 filename |
| `ground_truth` | Intended acted-expression label encoded in the filename |
| `p_angry` ... `p_sad` | Four-class normalized probability distribution |
| `predicted_label` | Argmax of the four-class distribution |
| `confidence` | Maximum four-class probability |
| `retained_probability_mass` | Probability retained before renormalization |
| `model_name` | Model repository used for inference |
| `inference_seconds_cpu` | Informative per-clip runtime from the preparation machine |

`retained_probability_mass` is essentially 1 for the four-label audio model. It can be lower for the seven-label video model because three expressions are excluded from the workshop taxonomy.

