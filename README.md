# Towards Enhancing Shadow Removal from Images

Official implementation of the paper published in *Multimedia Tools and Applications* (Vol. 84, pp. 18419–18444, 2025).

[![Paper](https://img.shields.io/badge/DOI-10.1007%2Fs11042--024--19824--2-blue)](https://doi.org/10.1007/s11042-024-19824-2)

## Overview

Shadows degrade the performance of downstream vision tasks by altering
colour, contrast, and apparent object boundaries. This work removes them
from single RGB images in two stages.

The first stage is a generative adversarial network built around two
specialised generators that use spatial attention and nearest-neighbour
upsampling — the latter chosen over transposed convolution to avoid
checkerboard artefacts in the reconstructed regions.

The second stage is a classical post-processing step. Learned models
alone tend to leave residual shadow traces and visible seams at shadow
boundaries, so the output is refined using histogram matching, custom
filtering, and explicit shadow-boundary detection and estimation.

## Extended ISTD Dataset

We also release **Extended ISTD**, a benchmark of 5,352 triplets
(shadow / shadow-mask / shadow-free) that broadens the original ISTD
set to include dark, hard-edged, and multi-colour contrast shadows.

## Results

| Metric | Whole image | Shadow region |
|---|---|---|
| RMSE (ISTD test) | 5.68 | 2.80 |

Relative to the compared baselines, this represents improvements of up
to 111.4% in RMSE and 23.86% in PSNR.



## Extended ISTD Dataset

Extended ISTD contains 5,352 image triplets (shadow / shadow-mask /
shadow-free), broadening the original ISTD benchmark to cover dark,
hard-edged, and multi-colour contrast shadows.

**[Download (Google Drive)](https://drive.google.com/file/d/1HGpbqxVUU0-qzTmNMN7gMHtvA9YsiXjr/view?usp=sharing)** · ~1.7 GB

Or from the command line:

```bash
pip install gdown
gdown 1HGpbqxVUU0-qzTmNMN7gMHtvA9YsiXjr
```

### Structure

```text
Extended_ISTD/
├── train/
│   ├── shadow/
│   ├── mask/
│   └── shadow_free/
└── test/
    ├── shadow/
    ├── mask/
    └── shadow_free/
```


## Citation

If you use this code or the Extended ISTD dataset in your research,
please cite our paper:

```bibtex
@article{tariq2025shadow,
  title   = {Towards enhancing shadow removal from images},
  author  = {Tariq, Muhammad Hamza and Salman, Ahmad and Khurshid, Khawar},
  journal = {Multimedia Tools and Applications},
  volume  = {84},
  number  = {17},
  pages   = {18419--18444},
  year    = {2025},
  month   = may,
  doi     = {10.1007/s11042-024-19824-2},
  url     = {https://doi.org/10.1007/s11042-024-19824-2},
  issn    = {1573-7721},
  publisher = {Springer US}
}
```

**Plain text (APA):**

> Tariq, M. H., Salman, A., & Khurshid, K. (2025). Towards enhancing shadow removal from images. *Multimedia Tools and Applications, 84*(17), 18419–18444. https://doi.org/10.1007/s11042-024-19824-2

**IEEE:**

> M. H. Tariq, A. Salman, and K. Khurshid, "Towards enhancing shadow removal from images," *Multimedia Tools and Applications*, vol. 84, no. 17, pp. 18419–18444, 2025.
