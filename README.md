# CENSOR NDSS 2025 Reproduction — CIFAR10 Gradient Inversion Attack

Implementation and reproduction study of gradient inversion attacks and privacy defenses inspired by the NDSS 2025 paper:

> **CENSOR: Defense Against Gradient Inversion via Orthogonal Subspace Bayesian Sampling**

This project demonstrates how attackers can reconstruct private training images from gradients in federated learning systems.

---

# Features

* Federated learning privacy simulation
* Gradient inversion attack
* CIFAR10 adaptation
* Defense vs No-Defense comparison
* PSNR / SSIM / LPIPS evaluation
* Google Colab compatible
* Simplified educational implementation
* NDSS-style privacy leakage analysis

---

# Project Motivation

Federated learning shares gradients instead of raw data.

However, modern research has shown:

```text
Gradients themselves can leak private information.
```

This project demonstrates:

* how gradient inversion attacks work
* how attackers reconstruct images from gradients
* how defenses reduce reconstruction quality

---

# Concepts Used

* Federated Learning
* Gradient Leakage
* Gradient Inversion Attack
* CNN-based reconstruction
* Privacy defense mechanisms
* PSNR
* SSIM
* LPIPS

---

# Dataset

* CIFAR10
* Automatically downloaded using TorchVision

---

# Metrics Used

| Metric | Purpose                |
| ------ | ---------------------- |
| PSNR   | Pixel-level similarity |
| SSIM   | Structural similarity  |
| LPIPS  | Perceptual similarity  |

---

# Example Results

## Without Defense

| Metric | Result |
| ------ | ------ |
| PSNR   | ~46    |
| SSIM   | ~0.99  |
| LPIPS  | ~0.000 |

Near-perfect reconstruction.

---

## With Defense

| Metric | Result |
| ------ | ------ |
| PSNR   | ~30    |
| SSIM   | ~0.91  |
| LPIPS  | ~0.001 |

Defense significantly reduces reconstruction quality.

---

# Reconstruction Pipeline

```text
Original Image
↓
Compute Gradients
↓
Apply Defense (optional)
↓
Attacker receives gradients
↓
Initialize dummy image
↓
Gradient matching optimization
↓
Reconstructed image
↓
Evaluate PSNR / SSIM / LPIPS
```

---

# Installation

```bash
pip install torch torchvision torchaudio
pip install matplotlib
pip install scikit-image
pip install lpips
```

---

# Run

Execute the notebook or script directly in:

* Google Colab
* VS Code
* Jupyter Notebook

---

# Key Insight

This project demonstrates that:

```text
Gradients are not fully private.
```

Even without direct access to training images,
attackers can reconstruct visual information from gradients alone.

---

# Research Connection

Inspired by:

**CENSOR: Defense Against Gradient Inversion via Orthogonal Subspace Bayesian Sampling**
(NDSS 2025)

Official repository:
[https://github.com/KaiyuanZh/CENSOR](https://github.com/KaiyuanZh/CENSOR)

---

# Simplification Notice

This repository contains a simplified educational implementation.

It does NOT fully reproduce:

* GIFD
* BigGAN priors
* Bayesian sampling
* Orthogonal subspace optimization

used in the original paper.

Instead, it focuses on:

* understanding the attack flow
* demonstrating privacy leakage
* visualizing reconstruction quality

---

# Future Improvements

* BigGAN latent optimization
* GIFD implementation
* LPIPS optimization loss
* Differential privacy defenses
* Diffusion-model priors
* Stronger federated defenses

---

# Results Interpretation

| Metric | Better Reconstruction Means |
| ------ | --------------------------- |
| PSNR   | Higher                      |
| SSIM   | Higher                      |
| LPIPS  | Lower                       |

---

# Author

Reproduction and CIFAR10 adaptation by Shivam Kuntal.

---

# Disclaimer

This project is for:

* educational purposes
* privacy research
* federated learning security analysis

Do not use for malicious purposes.
