# Time-IMM Dataset

[![arXiv](https://img.shields.io/badge/arXiv-2506.10412-b31b1b.svg)](https://arxiv.org/abs/2506.10412)
[![GitHub Stars](https://img.shields.io/github/stars/blacksnail789521/Time-IMM?style=social)](https://github.com/blacksnail789521/Time-IMM/stargazers)
[![](https://img.shields.io/badge/Project-Website-blue?style=flat)](https://blacksnail789521.github.io/time-imm-project-page/)
[![How to Cite](https://img.shields.io/badge/Cite-bibtex-orange)](#citation)

<p align="center"><sub>
✨ If you find our <em>paper</em> useful, a <strong>star ⭐ on GitHub</strong> helps others discover it and keeps you updated on future releases.
</sub></p>

## Overview

Welcome to the Time-IMM dataset collection, released as part of our NeurIPS 2025 Datasets & Benchmarks Track submission. The full benchmark includes nine datasets. However, due to the data usage agreement for MIMIC-IV, we are not permitted to redistribute its processed data. Instead, we provide preprocessing scripts and instructions to help authorized users generate the processed MIMIC data locally. The other eight datasets are included in this release.


## Data Hierarchy

All datasets follow the structure below for compatibility:

```
data/
└── {dataset_name}/
    └── processed/
        └── {entity_id}/
            ├── time_series.csv         # Multivariate, irregular time-series data
            └── text.csv                # Associated unstructured text data
```

> **Example:** `data/EPA-Air/processed/Los_Angeles/time_series.csv` and `data/EPA-Air/processed/Los_Angeles/text.csv`

Each `{entity_id}` directory represents a unique data unit (e.g., a patient, sensor, or location) and should contain both structured and unstructured views of the data.
* `time_series.csv` contains three components:

  * `date_time`: timestamp of each observation
  * `record_id`: unique identifier for the entity (matches the folder name)
  * Remaining columns: numerical features corresponding to multivariate time-series data

* `text.csv` includes:

  * `date_time`: timestamp of the associated text entry
  * `record_id`: unique identifier for the entity
  * Final column: the unstructured textual observation (e.g., notes, summaries, logs)

## MIMIC Preprocessing

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

## Citation

If you find this resource useful, please cite our paper.
```bibtex
@inproceedings{
chang2025timeimm,
title={Time-{IMM}: A Dataset and Benchmark for Irregular Multimodal Multivariate Time Series},
author={Ching Chang and Jeehyun Hwang and Yidan Shi and Haixin Wang and Wei Wang and Wen-Chih Peng and Tien-Fu Chen},
booktitle={The Thirty-ninth Annual Conference on Neural Information Processing Systems Datasets and Benchmarks Track},
year={2025},
url={https://openreview.net/forum?id=yeqrrn51TL}
}