# Time-IMM Dataset

Welcome to the Time-IMM dataset collection, released as part of our NeurIPS 2025 Datasets & Benchmarks Track submission. The full benchmark includes nine datasets. However, due to the data usage agreement for MIMIC-IV, we are not permitted to redistribute its processed data. Instead, we provide preprocessing scripts and instructions to help authorized users generate the processed MIMIC data locally. The other eight datasets are included in this release.

---

## 📁 Data Hierarchy

All datasets follow the structure below for compatibility:

```
{dataset_name}/
└── processed/
    └── {entity_id}/
        ├── time_series.csv         # Multivariate, irregular time-series data
        └── text.csv                # Associated unstructured text data
```

> ✅ **Example:** `data/EPA-Air/processed/Los_Angeles/time_series.csv` and `data/EPA-Air/processed/Los_Angeles/text.csv`

Each `{entity_id}` directory represents a unique data unit (e.g., a patient, sensor, or location) and should contain both structured and unstructured views of the data.
* `time_series.csv` contains three components:

  * `date_time`: timestamp of each observation
  * `record_id`: unique identifier for the entity (matches the folder name)
  * Remaining columns: numerical features corresponding to multivariate time-series data

* `text.csv` includes:

  * `date_time`: timestamp of the associated text entry
  * `record_id`: unique identifier for the entity
  * Final column: the unstructured textual observation (e.g., notes, summaries, logs)
---

## 🔄 MIMIC Preprocessing

Due to access restrictions, raw MIMIC data must be downloaded manually. Please follow the instruction here:

```
data/MIMIC/mimic_preprocess.ipynb
```

This will generate processed files in:

```
data/MIMIC/processed/{entity_id}/
├── time_series.csv
└── text.csv
```