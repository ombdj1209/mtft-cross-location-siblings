# VISUELLE 2.0, official short-observation protocol

WAPE in %, MAE in units, mean ± sd over seeds. Validation = most recent 10 % of training pairs.

## 2-1

| Model | seeds | WAPE | MAE | new-product WAPE | seen-product WAPE | Cov80 |
|---|---|---|---|---|---|---|
| Naive (our re-run) | – | 101.93 | 1.128 | | | |
| SES (our re-run) | – | 97.86 | 1.082 | | | |
| TFT | 5 | 68.07 ± 0.46 | 0.75 ± 0.01 | 67.83 ± 0.50 | 68.58 ± 0.40 | 0.87 |
| MTFT-Picnic | 5 | 68.54 ± 0.92 | 0.76 ± 0.01 | 68.33 ± 0.93 | 69.00 ± 0.90 | 0.87 |
| MTFT-Picnic + siblings | 5 | 65.25 ± 0.14 | 0.72 ± 0.00 | 65.04 ± 0.15 | 65.70 ± 0.19 | 0.87 |
| MTFT+ v3 (ours) | 5 | 65.73 ± 0.69 | 0.73 ± 0.01 | 65.60 ± 0.69 | 66.03 ± 0.69 | 0.87 |
| Chronos-2 + covariates + cross-learning | 1 | 97.35 | 1.08 | 95.98 | 100.28 | 0.80 |
| Chronos-2 + covariates | 1 | 96.11 | 1.06 | 94.69 | 99.15 | 0.79 |
| Chronos-2 | 1 | 96.46 | 1.07 | 94.83 | 99.95 | 0.76 |

Paired product-cluster bootstrap, MTFT+ v3 (ours) − comparator (WAPE points, 95 % CI), and per-seed wins:

| Comparator | ΔWAPE | wins |
|---|---|---|
| TFT | **-2.34 [-2.52, -2.16]** | 5/5 |
| MTFT-Picnic | **-2.81 [-3.05, -2.59]** | 5/5 |
| MTFT-Picnic + siblings | **+0.48 [+0.37, +0.59]** | 1/5 |
| Chronos-2 + covariates + cross-learning | **-31.62 [-32.68, -30.54]** | 5/5 |
| Chronos-2 + covariates | **-30.38 [-31.36, -29.40]** | 5/5 |
| Chronos-2 | **-30.73 [-31.74, -29.74]** | 5/5 |

Controls, A − B (WAPE points, 95 % CI; all test pairs / new products only), per-seed wins of A:

| A | B | ΔWAPE all | ΔWAPE new products | wins |
|---|---|---|---|---|
| MTFT-Picnic + siblings | MTFT-Picnic | **-3.29 [-3.52, -3.08]** | **-3.29 [-3.59, -3.02]** | 5/5 |
| MTFT-Picnic | TFT | **+0.48 [+0.30, +0.66]** | **+0.50 [+0.28, +0.77]** | 1/5 |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | **+0.48 [+0.37, +0.59]** | **+0.55 [+0.41, +0.68]** | 1/5 |

Published (Skenderi et al. 2022; in the released training code the validation loader is built from the test split):

| Method | WAPE | MAE |
|---|---|---|
| Naive | 101.922 | 1.13 |
| SES | 97.85 | 1.08 |
| kNN | 87.11 | 0.94 |
| kNN + image | 88.97 | 0.96 |
| CrossAttnRNN | 23.2 | 0.26 |
| CrossAttnRNN w/ images | 23.7 | 0.26 |

## 2-10

| Model | seeds | WAPE | MAE | new-product WAPE | seen-product WAPE | Cov80 |
|---|---|---|---|---|---|---|
| Naive (our re-run) | – | 118.24 | 1.308 | | | |
| SES (our re-run) | – | 111.34 | 1.232 | | | |
| TFT | 5 | 67.61 ± 0.26 | 0.75 ± 0.00 | 67.54 ± 0.24 | 67.75 ± 0.35 | 0.84 |
| MTFT-Picnic | 5 | 67.68 ± 0.55 | 0.75 ± 0.01 | 68.30 ± 0.65 | 66.36 ± 0.43 | 0.84 |
| MTFT-Picnic + siblings | 5 | 66.84 ± 0.06 | 0.74 ± 0.00 | 67.32 ± 0.15 | 65.81 ± 0.19 | 0.84 |
| MTFT+ v3 (ours) | 5 | 65.66 ± 0.27 | 0.73 ± 0.00 | 65.72 ± 0.33 | 65.53 ± 0.29 | 0.85 |
| Chronos-2 + covariates + cross-learning | 1 | 115.43 | 1.28 | 114.95 | 116.45 | 0.78 |
| Chronos-2 + covariates | 1 | 114.24 | 1.26 | 113.61 | 115.57 | 0.78 |
| Chronos-2 | 1 | 111.09 | 1.23 | 110.10 | 113.22 | 0.77 |

Paired product-cluster bootstrap, MTFT+ v3 (ours) − comparator (WAPE points, 95 % CI), and per-seed wins:

| Comparator | ΔWAPE | wins |
|---|---|---|
| TFT | **-1.94 [-2.33, -1.57]** | 5/5 |
| MTFT-Picnic | **-2.02 [-2.43, -1.63]** | 5/5 |
| MTFT-Picnic + siblings | **-1.17 [-1.58, -0.74]** | 5/5 |
| Chronos-2 + covariates + cross-learning | **-49.77 [-51.88, -47.72]** | 5/5 |
| Chronos-2 + covariates | **-48.57 [-50.57, -46.62]** | 5/5 |
| Chronos-2 | **-45.43 [-47.19, -43.67]** | 5/5 |

Controls, A − B (WAPE points, 95 % CI; all test pairs / new products only), per-seed wins of A:

| A | B | ΔWAPE all | ΔWAPE new products | wins |
|---|---|---|---|---|
| MTFT-Picnic + siblings | MTFT-Picnic | **-0.85 [-1.24, -0.46]** | **-0.99 [-1.56, -0.39]** | 5/5 |
| MTFT-Picnic | TFT | +0.08 [-0.34, +0.52] | **+0.76 [+0.23, +1.27]** | 3/5 |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | **-1.17 [-1.58, -0.74]** | **-1.59 [-2.17, -1.00]** | 5/5 |

Published (Skenderi et al. 2022; in the released training code the validation loader is built from the test split):

| Method | WAPE | MAE |
|---|---|---|
| Naive | 118.176 | 1.31 |
| SES | 111.265 | 1.23 |
| kNN | 91.13 | 0.98 |
| kNN + image | 97.97 | 1.06 |
| CrossAttnRNN | 35.13 | 0.39 |
| CrossAttnRNN w/ image | 32.25 | 0.36 |

## demand

| Model | seeds | WAPE | MAE | new-product WAPE | seen-product WAPE | Cov80 |
|---|---|---|---|---|---|---|
| train mean curve (our re-run) | – | 89.38 | 1.050 | | | |
| train median curve (our re-run) | – | 77.32 | 0.909 | | | |
| TFT | 5 | 65.00 ± 0.34 | 0.76 ± 0.00 | 65.07 ± 0.36 | 64.86 ± 0.51 | 0.85 |
| MTFT-Picnic | 5 | 64.46 ± 0.26 | 0.76 ± 0.00 | 65.14 ± 0.30 | 63.03 ± 0.48 | 0.84 |
| MTFT-Picnic + siblings | 5 | 64.01 ± 0.30 | 0.75 ± 0.00 | 64.90 ± 0.39 | 62.16 ± 0.25 | 0.85 |
| MTFT+ v3 (ours) | 5 | 63.07 ± 0.43 | 0.74 ± 0.01 | 63.73 ± 0.58 | 61.68 ± 0.17 | 0.85 |
| Chronos-2 + covariates + cross-learning | 1 | 100.57 | 1.18 | 100.50 | 100.71 | 0.81 |
| Chronos-2 + covariates | 1 | 100.57 | 1.18 | 100.50 | 100.71 | 0.80 |
| Chronos-2 | 1 | 100.57 | 1.18 | 100.50 | 100.71 | 0.67 |

Paired product-cluster bootstrap, MTFT+ v3 (ours) − comparator (WAPE points, 95 % CI), and per-seed wins:

| Comparator | ΔWAPE | wins |
|---|---|---|
| TFT | **-1.94 [-2.37, -1.51]** | 5/5 |
| MTFT-Picnic | **-1.39 [-1.85, -0.94]** | 5/5 |
| MTFT-Picnic + siblings | **-0.95 [-1.41, -0.54]** | 5/5 |
| Chronos-2 + covariates + cross-learning | **-37.51 [-37.88, -37.12]** | 5/5 |
| Chronos-2 + covariates | **-37.51 [-37.88, -37.12]** | 5/5 |
| Chronos-2 | **-37.51 [-37.88, -37.12]** | 5/5 |

Controls, A − B (WAPE points, 95 % CI; all test pairs / new products only), per-seed wins of A:

| A | B | ΔWAPE all | ΔWAPE new products | wins |
|---|---|---|---|---|
| MTFT-Picnic + siblings | MTFT-Picnic | -0.44 [-0.92, +0.04] | -0.24 [-0.91, +0.48] | 4/5 |
| MTFT-Picnic | TFT | **-0.55 [-1.06, -0.03]** | +0.06 [-0.57, +0.68] | 5/5 |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | **-0.95 [-1.41, -0.54]** | **-1.17 [-1.80, -0.54]** | 5/5 |

Published (Skenderi et al. 2022; in the released training code the validation loader is built from the test split):

| Method | WAPE | MAE |
|---|---|---|
| CrossAttnRNN w/ image | 83.33 | 0.97 |
