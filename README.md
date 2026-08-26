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
