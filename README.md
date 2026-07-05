# Galaxy Quantum Enhancement Analysis

## Overview
Comparative analysis of original and quantum-enhanced galaxy images to evaluate 
the effectiveness of a quantum image enhancement algorithm applied to low-light 
astronomical observations. Uses the Galaxy Zoo 2 dataset (61,578 images) as baseline.

## Key Results

| Metric | Original | Enhanced | Finding |
|--------|----------|----------|---------|
| RMSE (cross-domain) | 0.115 | 0.283 | Domain gap confirmed |
| RMSE (after adaptation) | 0.115 | 0.120 | Morphological info preserved |
| Edge Strength | 11.78 | 74.29 | **6.3× improvement** |
| Laplacian Variance | 4.69 | 263.46 | **56× improvement** |
| Asymmetry Index | 0.648 | 0.479 | **26% lower (p<0.001)** |
| Gini Coefficient | 0.601 | 0.713 | 18% higher (p<0.001) |

## Analyses Performed
1. Regression RMSE against Galaxy Zoo volunteer vote fractions
2. Edge Strength
3. Laplacian Variance
4. Structural Coherence
5. Galaxy Edge Signal-to-Noise Ratio
6. Silhouette Score
7. Concentration, Asymmetry, Smoothness (CAS system)
8. Gini and M20 morphological indices
9. Sérsic Profile Analysis (effective radius, Sérsic index, fit quality)
10. Classification accuracy (7-class morphological taxonomy)

## Sersic Profile Analysis
I analysed the effective radius, sersic index and fit quality of the original and enhanced images and compared them.

## Classification Accuracy Check
Also, I analysed classification accuracy of a sample of enhanced galaxy images with respect to its original counterparts. This sample had been chosen in a way that there remains equal weights of the different types of galaxies, as decided by the vote fractions of the Galaxy Zoo Challenge.

## Novel Finding: Ring at r_e/2
Enhanced images exhibit a characteristic ring artefact at r ≈ 0.528 × r_e 
(statistically consistent with r_e/2, p=0.176), corresponding to the 
bulge-disk transition boundary. Sérsic index decreases from 0.869 to 0.508, 
indicating systematic amplification of disk-scale structure through quantum 
interference at the bulge-disk boundary.

## Gini-M20 Analysis
Enhanced galaxies shift systematically toward the merger/irregular region 
in Gini-M20 space (ΔG=+0.112, ΔM20=-0.314). Cross-validation with volunteer 
classifications confirms this shift is artefact-driven rather than reflecting 
real morphological changes (p=0.467).

## Tech Stack
Python | PyTorch | Zoobot | scikit-learn | OpenCV | SciPy | Google Colab

## Dataset & Citations

**Dataset:**
Willett, K. W. et al. (2013). Galaxy Zoo 2: detailed morphological classifications
for 304,122 galaxies from the Sloan Digital Sky Survey.
*Monthly Notices of the Royal Astronomical Society*, 435(4), 2835–2860.
https://doi.org/10.1093/mnras/stt1458

Kaggle Competition: Galaxy Zoo — The Galaxy Challenge
https://www.kaggle.com/c/galaxy-zoo-the-galaxy-challenge

**Model:**
Walmsley, M. et al. (2023). Zoobot: Adaptable Deep Learning Models for Galaxy Morphology.
*Journal of Open Source Software*, 8(85), 5312.
https://doi.org/10.21105/joss.05312

**Baseline Reference:**
Dieleman, S., Willett, K. W., & Dambre, J. (2015).
Rotation-invariant convolutional neural networks for galaxy morphology prediction.
*Monthly Notices of the Royal Astronomical Society*, 450(2), 1441–1459.
https://doi.org/10.1093/mnras/stv632

**Morphological Indices:**
Lotz, J. M., Primack, J., & Madau, P. (2004).
A new nonparametric approach to galaxy morphological classification.
*The Astronomical Journal*, 128(1), 163.
https://doi.org/10.1086/421849
