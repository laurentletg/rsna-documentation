# MS Lesion Segmentation Tools

Overview of open-source models for automated white matter lesion segmentation in MS.

---

## LST — Lesion Segmentation Toolbox (Classic)

**LST** is a MATLAB/SPM12 toolbox for automated segmentation of T2-hyperintense white matter lesions, originally developed for MS.

- **Official site:** [applied-statistics.de/lst.html](https://www.applied-statistics.de/lst.html)
- **Documentation (PDF):** [LST v3.0.0 manual](https://www.applied-statistics.de/LST_documentation.pdf)
- **Requires:** MATLAB + SPM12

### Installation

1. Download `LST_3.0.0.zip` from the [official site](https://www.applied-statistics.de/lst.html)
2. Unzip into your SPM12 toolboxes folder: `<SPM12_root>/toolbox/LST/`
3. Open MATLAB → launch SPM12 → click **Toolbox** → select **LST**

### Algorithms

| Algorithm | Input | Notes |
|---|---|---|
| **LGA** (Lesion Growth Algorithm) | FLAIR + T1 | Original algorithm (Schmidt et al. 2012) |
| **LPA** (Lesion Prediction Algorithm) | FLAIR only | Faster; good for large cohorts |
| **Longitudinal** | Longitudinal FLAIR ± T1 | For detecting new/enlarging lesions |

Additional tools: lesion filling, lesion probability maps, report generation.

### Key Papers

- Schmidt et al. 2012 — LGA: *NeuroImage* 59(4):3774–3783
- Schmidt et al. 2019 — Longitudinal segmentation: see toolbox homepage

---

## LST-AI — Deep Learning Extension

**LST-AI** is a fully open-source deep learning successor to classic LST, developed at TU Munich. It uses an **ensemble of three 3D U-Nets** with a composite loss (binary cross-entropy + Tversky) to address class imbalance between lesion and non-lesion tissue. It also labels lesion locations according to McDonald criteria automatically.

- **GitHub:** [github.com/CompImg/LST-AI](https://github.com/CompImg/LST-AI)
- **Paper (NeuroImage: Clinical 2024):** [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2213158224000500) | [PMC full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC11088188/)

**Performance:** Dice > 0.62 on MSSEG-1, outperforming classic LST, SAMSEG, and nnUNet.

### Installation

=== "Docker (recommended)"

    ```bash
    # Pull image (CPU/GPU)
    docker pull jqmcginnis/lst-ai

    # Run (replace paths with absolute paths)
    docker run --rm \
      -v /path/to/input:/input \
      -v /path/to/output:/output \
      jqmcginnis/lst-ai \
      --t1 /input/t1.nii.gz \
      --flair /input/flair.nii.gz \
      --output /output
    ```

=== "pip (Linux)"

    ```bash
    # Install HD-BET dependency first
    git clone https://github.com/MIC-DKFZ/HD-BET
    pip install -e HD-BET

    # Install LST-AI
    pip install lst-ai
    ```

!!! warning "Platform support"
    Native pip install is tested on **Linux** only. For macOS use Docker.

---

## FLAMeS — Fully Lesion-Aware MS Segmentation

**FLAMeS** is a robust deep learning model for automated MS lesion segmentation, designed to generalize across diverse MRI acquisition parameters and scanner types.

- **HuggingFace Space (interactive demo):** [huggingface.co/spaces/FrancescoLR/FLAMeS](https://huggingface.co/spaces/FrancescoLR/FLAMeS)
- **Model weights:** [huggingface.co/FrancescoLR/FLAMeS-model](https://huggingface.co/FrancescoLR/FLAMeS-model)
- **Paper (Journal of Neuroimaging, 2025):** [Wiley](https://onlinelibrary.wiley.com/doi/abs/10.1111/jon.70085) | [PMC full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC12140514/)
- **Authors:** Dereskewicz E, La Rosa F, dos Santos Silva J, et al.

### Quick Start via HuggingFace Space

The easiest way to try FLAMeS is the interactive web demo — no installation required:

1. Go to [huggingface.co/spaces/FrancescoLR/FLAMeS](https://huggingface.co/spaces/FrancescoLR/FLAMeS)
2. Upload your NIfTI file (T2/FLAIR brain MRI)
3. Download the predicted lesion mask

!!! note "HuggingFace Zero GPU"
    The Space runs on HuggingFace's free Zero GPU tier — it may take a minute to cold-start.

### Citation

```bibtex
@article{dereskewicz2025flames,
  title   = {FLAMeS: A robust deep learning model for automated multiple sclerosis lesion segmentation},
  author  = {Dereskewicz, E and La Rosa, F and dos Santos Silva, J and others},
  journal = {Journal of Neuroimaging},
  year    = {2025},
  doi     = {10.1111/jon.70085}
}
```

---

## Comparison

| Tool | Input | Platform | DL | Open source | Best for |
|---|---|---|---|---|---|
| **LST (LGA)** | FLAIR + T1 | MATLAB/SPM | No | Yes | Classic pipeline, SPM users |
| **LST (LPA)** | FLAIR only | MATLAB/SPM | No | Yes | Quick single-modality run |
| **LST-AI** | FLAIR + T1 | Linux / Docker | Yes (U-Net) | Yes | Best accuracy, CLI/batch |
| **FLAMeS** | FLAIR | Web / Python | Yes | Yes | Quick demo, multi-site robustness |

---

## Other Tools (for reference)

- [CNN-MS Lesion Segmentation (Valverde)](https://github.com/sergivalverde/cnn-ms-lesion-segmentation) — Early CNN-based approach
- [ivadomed / MICCAI 2021 MS challenge](https://github.com/ivadomed/ms-challenge-2021) — Framework used for new lesion detection
- [Consensus comparison 2024 (Scientific Reports)](https://www.nature.com/articles/s41598-024-72649-9) — Benchmark of multiple automated methods
