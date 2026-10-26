# 🌊 Fourier

> **"Give me enough circles, and I will draw you the universe."**  
> An interactive visualizer and computational engine for the **Discrete Fourier Transform (DFT)** and **Epicyclic Curve Synthesis**.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/Nikhil8557/Fourier?style=social)](https://github.com/Nikhil8557/Fourier)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## 📽️ Demo

<!-- Drop your demo GIF or visual here -->
<p align="center">
  <img src="./assets/demo.gif" alt="Fourier Epicycles Animation" width="700px" />
  <em>https://nikhil8557.github.io/Fourier</em>
  <br>
  <em>Deconstructing paths into rotating vectors (epicycles) and recreating continuous curves.</em>
</p>

---

## 💡 What is This?

The Fourier Transform is one of the most elegant discoveries in mathematics and engineering. It states that **any continuous waveform or closed 2D shape can be decomposed into a sum of simple sinusoidal frequencies (rotating circles)**.

This project implements:
1. **Discrete Fourier Analysis**: Sampling spatial coordinates $(x, y)$ or time-domain signals and converting them into their frequency components.
2. **Epicycle Reconstruction Engine**: Visualizing each frequency mode as a rotating vector chained head-to-tail, reproducing complex drawings from pure trigonometry.
3. **Signal Decomposition**: Real-time frequency spectrum analysis and filtering.

---

## ✨ Features

- 🔄 **Epicyclic Path Tracing**: Watch spinning gears of math trace arbitrary drawings with customizable circle counts.
- 🎨 **Custom SVG / Path Support**: Import your own vector outlines or draw directly on the canvas.
- ⚡ **Optimized DFT / FFT**: Fast computation of amplitude, phase, and frequency for arbitrary sample sizes.
- 🎛️ **Interactive Controls**:
  - Adjust harmonic order / number of epicycles in real time.
  - Scale playback speed, trace retention, and frequency thresholds.
  - Filter out high-frequency noise or low-frequency drift.
- 📈 **Frequency Domain Inspector**: Live display of the power spectrum (magnitudes vs. frequencies).

---

## 🧮 How It Works (The Math)

Any 2D closed curve can be represented as a series of complex numbers:

$$z(t) = x(t) + i \cdot y(t)$$

We compute the **Discrete Fourier Transform (DFT)** of the $N$ sampled points:

$$X_k = \frac{1}{N} \sum_{n=0}^{N-1} x_n \cdot e^{-i \frac{2\pi}{N} k n}$$

Each Fourier coefficient $X_k$ yields:
- **Radius (Amplitude)**: $|X_k| = \sqrt{\text{Re}(X_k)^2 + \text{Im}(X_k)^2}$
- **Phase Offset (Initial Angle)**: $\theta_k = \text{atan2}(\text{Im}(X_k), \text{Re}(X_k))$
- **Frequency**: $k$ (cycles per period)

Chaining each rotating vector $r_k e^{i(k t + \theta_k)}$ head-to-tail traces the exact original contour as $t$ travels from $0$ to $2\pi$.

---

## 🚀 Getting Started

### Prerequisites

Ensure you have one of the following environments set up depending on your implementation:

- **Python** (≥ 3.8) with `numpy`, `matplotlib`, or `pygame`  
  *— OR —*
- **Node.js** (≥ 16.x) / Modern Web Browser (if using Canvas / p5.js)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Nikhil8557/Fourier.git
   cd Fourier
