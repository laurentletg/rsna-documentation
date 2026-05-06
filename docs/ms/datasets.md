# Public MS MRI Datasets

Open-access brain MRI datasets for MS lesion segmentation — suitable for students learning to train or evaluate segmentation models.

!!! tip "Where to start"
    If you just want to get started quickly:

    - **No registration needed:** [Mendeley 60-patient dataset](#brain-mri-60-ms-patients-mendeley) or [Open MS Data](#open-ms-data-muschelli)
    - **Best annotated benchmark:** [MSSEG-1 (MICCAI 2016)](#msseg-1-miccai-2016)
    - **Longitudinal / new lesions:** [MSSEG-2 (MICCAI 2021)](#msseg-2-miccai-2021-new-lesion-detection)

---

## Dataset Overview

| Dataset | Year | Subjects | Modalities | Access | Size |
|---|---|---|---|---|---|
| [ISBI 2015](#isbi-2015-longitudinal-ms-challenge) | 2015 | 5 train / 14 test | T1, T2, PD, FLAIR (longitudinal) | Free (registration) | ~82 sessions |
| [MSSEG-1](#msseg-1-miccai-2016) | 2016 | 53 | FLAIR, T1, T1-Gd, PD-T2 | Free (Shanoir) | 4 scanners, 7 raters |
| [MSSEG-2](#msseg-2-miccai-2021-new-lesion-detection) | 2021 | 100 | FLAIR (2 timepoints) | Free (Shanoir + DUA) | ~6 GB |
| [Shifts 2022](#shifts-challenge-2022) | 2022 | Multi-site | FLAIR + T1 | Free (Zenodo DUA) | Train/val/test splits |
| [Open MS Data](#open-ms-data-muschelli) | 2015 | Cross-sectional + longitudinal | co-registered, bias-corrected | Free (CC-BY) | GitHub |
| [Mendeley 60 patients](#brain-mri-60-ms-patients-mendeley) | 2022 | 60 | T1, T2, FLAIR | Free (CC-BY) | 1.5T, NIfTI |
| [MSLesSeg](#mslesseg-scientific-data-2025) | 2025 | 75 (115 scans) | T1, T2, FLAIR + clinical | Free (registration) | Multi-timepoint |
| [PediMS](#pedims-pediatric-ms) | 2025 | 9 (28 scans) | T1, T2, FLAIR | Free (CC-BY, figshare) | Pediatric |

---

## ISBI 2015 Longitudinal MS Challenge

Longitudinal dataset with two expert rater masks per session — ideal for evaluating longitudinal lesion detection.

- **Subjects:** 5 training, 14 test (mean 4.4 timepoints each, 82 MRI sessions total)
- **Modalities:** T1, T2, PD, FLAIR (3T, longitudinal)
- **Access:** Free after registration
- **Challenge site:** [smart-stats-tools.org/lesion-challenge-2015](https://smart-stats-tools.org/lesion-challenge-2015)
- **IACL data page:** [iacl.ece.jhu.edu — MSChallenge/data](https://iacl.ece.jhu.edu/index.php/MSChallenge/data)
- **Paper (NeuroImage 2017):** [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC5344762/)

---

## MSSEG-1 (MICCAI 2016)

The most widely used MS segmentation benchmark. Multi-site, multi-scanner, 7 expert raters with consensus segmentation.

- **Subjects:** 53 patients, 4 scanners
- **Modalities:** 3D FLAIR, T1, T1 post-Gd, PD-T2
- **Access:** Free via Shanoir-NG (free academic account required)
- **Data portal:** [portal.fli-iam.irisa.fr — MSSEG](https://portal.fli-iam.irisa.fr/msseg-challenge/english-msseg-data/)
- **Paper (NeuroImage 2021):** [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1053811921008624) | [PubMed](https://pubmed.ncbi.nlm.nih.gov/34563682/)

---

## MSSEG-2 (MICCAI 2021) — New Lesion Detection

Focused on detecting **new or enlarging lesions** between two timepoints — a clinically crucial task.

- **Subjects:** 100 patients from the French OFSEP cohort
- **Modalities:** 3D FLAIR (baseline + follow-up)
- **Access:** Free via Shanoir-NG after signing Data Usage Agreement (~6 GB)
- **Data portal:** [portal.fli-iam.irisa.fr/msseg-2](https://portal.fli-iam.irisa.fr/msseg-2/)
- **Challenge code (ivadomed):** [github.com/ivadomed/ms-challenge-2021](https://github.com/ivadomed/ms-challenge-2021)

---

## Shifts Challenge 2022

Multi-source dataset combining MSSEG and ISBI data, organized for benchmarking model robustness under dataset shift.

- **Access:** Free via Zenodo after signing DUA (CC-BY-NC-SA 4.0)
- **Zenodo Part 1:** [zenodo.org/records/7051658](https://zenodo.org/records/7051658)
- **Zenodo Part 2:** [zenodo.org/records/7051692](https://zenodo.org/records/7051692)
- **Grand Challenge page:** [shifts.grand-challenge.org](https://shifts.grand-challenge.org/medical-dataset/)
- **GitHub (data readers + examples):** [github.com/Shifts-Project/shifts/tree/main/mswml](https://github.com/Shifts-Project/shifts/tree/main/mswml)

---

## Open MS Data (Muschelli)

Pre-processed, co-registered, bias-corrected NIfTI files — good for getting started without heavy preprocessing.

- **Content:** Cross-sectional + longitudinal data; CC-BY license
- **Processing:** Co-registered to FLAIR, 1×1×1 mm isotropic
- **GitHub:** [github.com/muschellij2/open_ms_data](https://github.com/muschellij2/open_ms_data)
- **Tutorial:** [johnmuschelli.com/neuroc/ms_lesion](https://johnmuschelli.com/neuroc/ms_lesion/index.html)

---

## Brain MRI 60 MS Patients (Mendeley)

Directly downloadable, CC-BY dataset with expert consensus segmentations. No registration required.

- **Subjects:** 60 patients (46F/14M, mean age 33), 20 centres, 1.5T, acquired 2019–2020
- **Modalities:** T1, T2, FLAIR — each with consensus masks (2 radiologists + 1 neurologist)
- **Format:** NIfTI, CC-BY license
- **Download:** [data.mendeley.com/datasets/8bctsm8jz7/1](https://data.mendeley.com/datasets/8bctsm8jz7/1)
- **Paper:** [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC9043670/)

---

## MSLesSeg (Scientific Data 2025)

Recent multi-timepoint benchmark with clinical data included.

- **Subjects:** 75 patients, 115 scans, 1–4 timepoints (mean age 37 ± 10)
- **Modalities:** T1, T2, FLAIR + clinical metadata
- **Paper:** [Nature Scientific Data 2025](https://www.nature.com/articles/s41597-025-05250-y)

---

## PediMS — Pediatric MS

First public MRI dataset specifically for **pediatric MS** segmentation.

- **Subjects:** 9 patients, 28 scans, 1–6 timepoints; CC-BY 4.0
- **Modalities:** T1 (MPRAGE), T2, FLAIR + clinical data
- **Download (figshare):** [figshare.com — PediMS](https://figshare.com/articles/dataset/PediMS_A_Pediatric_Multiple_Sclerosis_Lesion_Segmentation_Dataset/28701065)
- **Paper:** [Nature Scientific Data 2025](https://www.nature.com/articles/s41597-025-05346-5) | [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12246483/)

---

## General Neuroimaging Platforms

- [**OpenNeuro**](https://openneuro.org/) — Broad open-access platform; searchable for MS datasets in BIDS format
- [**Kaggle MS Dataset**](https://www.kaggle.com/datasets/trainingdatapro/multiple-sclerosis-dataset) — Good for quick experimentation (free Kaggle login)
