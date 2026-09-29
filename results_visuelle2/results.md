# MTFT+ v3 results

Data seeds: [0, 1, 2, 3, 4, 5]. Mean ± sd across seeds (sd omitted for single-seed rows).

## Article × FC level (test)

| Model | seeds | val loss | WAPE | MASE | wQL | Cov80 | cold-start WAPE | cold-start wQL | new-in-shop WAPE |
|---|---|---|---|---|---|---|---|---|---|
| TFT | 5 | 0.3229 ± 0.0013 | 0.6547 ± 0.0022 | 0.4728 ± 0.0027 | 0.4227 ± 0.0024 | 0.854 ± 0.0115 | 0.6457 ± 0.0023 | 0.4155 ± 0.0025 | 0.6926 ± 0.0046 |
| MTFT-Picnic | 5 | 0.3224 ± 0.0027 | 0.6515 ± 0.0019 | 0.4711 ± 0.0036 | 0.4197 ± 0.0015 | 0.862 ± 0.0056 | 0.6420 ± 0.0019 | 0.4120 ± 0.0015 | 0.6954 ± 0.0040 |
| MTFT-Picnic + siblings | 5 | 0.3151 ± 0.0013 | 0.6446 ± 0.0048 | 0.4704 ± 0.0041 | 0.4145 ± 0.0033 | 0.854 ± 0.0080 | 0.6349 ± 0.0052 | 0.4071 ± 0.0033 | 0.6816 ± 0.0036 |
| MTFT+ v3 (ours) | 5 | 0.3145 ± 0.0021 | 0.6434 ± 0.0036 | 0.4672 ± 0.0048 | 0.4140 ± 0.0031 | 0.855 ± 0.0046 | 0.6344 ± 0.0035 | 0.4070 ± 0.0032 | 0.6792 ± 0.0031 |
| Chronos-2 + covariates + cross-learning | 1 | n/a | 1.0306 | 0.9178 | 0.7379 | 0.757 | 0.9936 | 0.7191 | 1.1627 |
| Chronos-2 + covariates | 1 | n/a | 1.0303 | 0.9211 | 0.7334 | 0.744 | 0.9927 | 0.7126 | 1.1759 |
| Chronos-2 | 1 | n/a | 1.0252 | 0.8991 | 0.7118 | 0.751 | 0.9904 | 0.6899 | 1.1657 |

## Paired article-cluster bootstrap: ours − comparator (negative = ours better), 95 % CI

| Comparator | seeds | ΔWAPE all | ΔwQL all | ΔWAPE cold-start | ΔwQL cold-start | per-seed WAPE wins |
|---|---|---|---|---|---|---|
| TFT | 5 | **-0.0113 [-0.0129, -0.0098]** | **-0.0088 [-0.0101, -0.0074]** | **-0.0113 [-0.0130, -0.0097]** | **-0.0085 [-0.0099, -0.0071]** | 5/5 |
| MTFT-Picnic | 5 | **-0.0081 [-0.0100, -0.0061]** | **-0.0057 [-0.0074, -0.0039]** | **-0.0076 [-0.0096, -0.0056]** | **-0.0050 [-0.0068, -0.0031]** | 5/5 |
| MTFT-Picnic + siblings | 5 | -0.0012 [-0.0031, +0.0006] | -0.0006 [-0.0021, +0.0011] | -0.0005 [-0.0024, +0.0014] | -0.0001 [-0.0018, +0.0016] | 2/5 |
| Chronos-2 + covariates + cross-learning | 5 (zero-shot) | **-0.3872 [-0.3992, -0.3757]** | **-0.3240 [-0.3326, -0.3159]** | **-0.3592 [-0.3701, -0.3483]** | **-0.3121 [-0.3203, -0.3041]** | 5/5 |
| Chronos-2 + covariates | 5 (zero-shot) | **-0.3869 [-0.3986, -0.3756]** | **-0.3195 [-0.3280, -0.3116]** | **-0.3583 [-0.3690, -0.3477]** | **-0.3056 [-0.3137, -0.2977]** | 5/5 |
| Chronos-2 | 5 (zero-shot) | **-0.3818 [-0.3929, -0.3710]** | **-0.2978 [-0.3055, -0.2904]** | **-0.3560 [-0.3662, -0.3458]** | **-0.2830 [-0.2905, -0.2756]** | 5/5 |

Bold = 95 % interval excludes zero. Wins = seeds on which the first model has the lower WAPE (the bootstrap resamples articles, not training runs).

## Controls: A − B (negative = A better), 95 % CI

| A | B | ΔWAPE all | ΔwQL all | ΔWAPE cold-start | per-seed WAPE wins (A) |
|---|---|---|---|---|---|
| MTFT-Picnic + siblings | MTFT-Picnic | **-0.0069 [-0.0084, -0.0054]** | **-0.0051 [-0.0064, -0.0039]** | **-0.0071 [-0.0088, -0.0056]** | 5/5 |
| MTFT-Picnic | TFT | **-0.0032 [-0.0049, -0.0015]** | **-0.0031 [-0.0045, -0.0016]** | **-0.0037 [-0.0054, -0.0019]** | 4/5 |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | -0.0012 [-0.0031, +0.0006] | -0.0006 [-0.0021, +0.0011] | -0.0005 [-0.0024, +0.0014] | 2/5 |

## Product level (article-national totals of the bottom-up forecasts): A − B, 95 % CI

| A | B | ΔWAPE | ΔwQL | ΔWAPE cold-start |
|---|---|---|---|---|
| MTFT+ v3 (ours) | TFT | **-0.0182 [-0.0222, -0.0141]** | **-0.0165 [-0.0193, -0.0136]** | **-0.0163 [-0.0207, -0.0119]** |
| MTFT+ v3 (ours) | MTFT-Picnic | **-0.0105 [-0.0154, -0.0055]** | **-0.0108 [-0.0145, -0.0069]** | **-0.0076 [-0.0128, -0.0019]** |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | +0.0001 [-0.0047, +0.0048] | +0.0015 [-0.0019, +0.0049] | +0.0018 [-0.0031, +0.0071] |
| MTFT-Picnic + siblings | MTFT-Picnic | **-0.0106 [-0.0144, -0.0070]** | **-0.0123 [-0.0149, -0.0099]** | **-0.0093 [-0.0133, -0.0055]** |
| MTFT-Picnic | TFT | **-0.0077 [-0.0117, -0.0037]** | **-0.0057 [-0.0086, -0.0027]** | **-0.0088 [-0.0130, -0.0044]** |
| MTFT+ v3 (ours) | MTFT-Picnic + siblings | +0.0001 [-0.0047, +0.0048] | +0.0015 [-0.0019, +0.0049] | +0.0018 [-0.0031, +0.0071] |

## Hierarchy: WAPE / wQL / Cov80 by level (MinT + conformal unless stated)

| Model | Method | national | fulfilment centre | article-national | article × FC |
|---|---|---|---|---|---|
| TFT | MinT + conformal | 3.0103 / 2.9107 / 0.12 | 3.0056 / 2.8281 / 0.20 | 0.6126 / 3.4091 / 0.49 | 0.7510 / 0.5018 / 0.72 |
| TFT | MinT-WLS + conformal | 0.1098 / 0.0923 / 1.00 | 0.1825 / 0.1398 / 0.81 | 0.3978 / 3.1844 / 0.55 | 0.6968 / 0.4469 / 0.77 |
| MTFT-Picnic | MinT + conformal | 3.0455 / 2.9463 / 0.12 | 3.0416 / 2.8653 / 0.20 | 0.6066 / 3.3958 / 0.50 | 0.7467 / 0.4965 / 0.73 |
| MTFT-Picnic | MinT-WLS + conformal | 0.1084 / 0.0919 / 1.00 | 0.1833 / 0.1402 / 0.81 | 0.3958 / 3.1754 / 0.56 | 0.6942 / 0.4434 / 0.78 |
| MTFT-Picnic + siblings | MinT + conformal | 3.0032 / 2.9046 / 0.12 | 3.0054 / 2.8304 / 0.21 | 0.6039 / 3.3138 / 0.51 | 0.7428 / 0.4938 / 0.72 |
| MTFT-Picnic + siblings | MinT-WLS + conformal | 0.1110 / 0.0927 / 1.00 | 0.1901 / 0.1444 / 0.81 | 0.3932 / 3.0923 / 0.57 | 0.6903 / 0.4405 / 0.77 |
| MTFT+ v3 (ours) | bottom-up | 0.0988 / 0.0718 / 0.99 | 0.1549 / 0.1135 / 0.77 | 0.3241 / 0.2776 / 0.42 | 0.6434 / 0.4140 / 0.86 |
| MTFT+ v3 (ours) | base | 0.1438 / 0.1057 / 0.94 | 0.3111 / 0.2414 / 0.67 | 0.5951 / 0.5486 / 0.56 | 0.6434 / 0.4140 / 0.86 |
| MTFT+ v3 (ours) | MinT | 3.0375 / 2.8932 / 0.12 | 3.0395 / 2.9137 / 0.16 | 0.6010 / 0.5581 / 0.38 | 0.7395 / 0.4925 / 0.71 |
| MTFT+ v3 (ours) | MinT + conformal | 3.0375 / 2.9385 / 0.12 | 3.0395 / 2.8646 / 0.21 | 0.6010 / 3.2968 / 0.51 | 0.7395 / 0.4920 / 0.72 |
| MTFT+ v3 (ours) | MinT-WLS | 0.1157 / 0.0823 / 0.91 | 0.1942 / 0.1385 / 0.72 | 0.3918 / 0.3468 / 0.39 | 0.6872 / 0.4400 / 0.76 |
| MTFT+ v3 (ours) | MinT-WLS + conformal | 0.1157 / 0.0943 / 1.00 | 0.1942 / 0.1462 / 0.81 | 0.3918 / 3.0772 / 0.58 | 0.6872 / 0.4394 / 0.77 |
| Chronos-2 + covariates + cross-learning | MinT + conformal | 4.4430 / 4.3389 / 0.00 | 4.4217 / 4.2190 / 0.07 | 0.9219 / 4.7741 / 0.41 | 1.0887 / 0.8293 / 0.73 |
| Chronos-2 + covariates + cross-learning | MinT-WLS + conformal | 0.3417 / 0.2653 / 0.38 | 0.3590 / 0.2557 / 0.57 | 0.6545 / 4.5030 / 0.43 | 1.0078 / 0.7497 / 0.78 |
| Chronos-2 + covariates | MinT + conformal | 4.2977 / 4.1935 / 0.00 | 4.2764 / 4.0749 / 0.09 | 0.9269 / 4.3996 / 0.40 | 1.0862 / 0.8204 / 0.72 |
| Chronos-2 + covariates | MinT-WLS + conformal | 0.3020 / 0.2355 / 0.50 | 0.3299 / 0.2354 / 0.59 | 0.6627 / 4.1309 / 0.43 | 1.0077 / 0.7428 / 0.78 |
| Chronos-2 | MinT + conformal | 4.2273 / 4.1232 / 0.00 | 4.2125 / 4.0130 / 0.10 | 0.9117 / 3.7604 / 0.42 | 1.0809 / 0.8006 / 0.72 |
| Chronos-2 | MinT-WLS + conformal | 0.2275 / 0.1575 / 0.56 | 0.2703 / 0.1881 / 0.67 | 0.6516 / 3.4940 / 0.45 | 1.0050 / 0.7254 / 0.77 |

MinT λ̂ range 0.595–0.790; max coherence error 0.0e+00.

Validation-only choice between MinT-shrink and MinT-WLS (fit on the first half of the validation origins, national + FC WAPE on the second half): shrink 0 / WLS 23 of 23 runs (mean val WAPE shrink 0.420, WLS 0.159).

## Modality attribution (ours): image / text / fused

| seed | promo days | non-promo days |
|---|---|---|
