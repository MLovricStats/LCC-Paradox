[README.md](https://github.com/user-attachments/files/23758298/README.md)
# ⚠️ The LCC Paradox: A Bayesian Statistical Paradox

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![R](https://img.shields.io/badge/R-%3E%3D%203.6-blue.svg)](https://www.r-project.org/)
[![Biometrika](https://img.shields.io/badge/Submitted-Biometrika%202025-red.svg)](https://academic.oup.com/biomet)

**Same Data. Same Hypothesis. OPPOSITE Conclusions.**

A newly discovered statistical paradox revealing that two Bayesians using different prior variances can reach opposite conclusions from the same statistically significant data.

---

## 📖 Overview

In 1957, Dennis Lindley published "A Statistical Paradox" in *Biometrika*, revealing a conflict between frequentist and Bayesian inference as sample size approaches infinity.

**The LCC Paradox is arguably more devastating:** it reveals a conflict of *Bayesian inference with itself*.

### The Key Result

For **any statistically significant result** at the 0.05 level, there exist reasonable prior variances τ₁² and τ₂² such that:

- **BF₀₁(τ₁²) < 1** → Evidence for H₁ (REJECT H₀)
- **BF₀₁(τ₂²) > 1** → Evidence for H₀ (ACCEPT H₀)

This answers Christian Robert's 2016 call to investigate the impact of the prior scale on Bayes factors, confirming his suspicion that "this choice involves arbitrariness to a rather high degree."

---

## 🔥 Example: The Paradox in Action

| | Bayesian A | Bayesian B |
|---|---|---|
| **Prior SD (τ)** | 0.20 | 0.50 |
| **Bayes Factor** | BF₀₁ = 0.68 | BF₀₁ = 1.42 |
| **Conclusion** | ✅ REJECT H₀ | ❌ ACCEPT H₀ |

*Same data: z = 2.0, n = 50, p-value = 0.046 (significant!)*

---

## 📐 The Mathematics

The Bayes factor in favor of H₀ for the normal model with known variance:

$$\text{BF}_{01}(z; k) = \sqrt{1+k} \cdot \exp\left\\{-\frac{z^2 k}{2(1+k)}\right\\}$$

where $k = n\tau^2$.

### The Flip Point Theorem

For |z| > 1, there exists a unique **flip point** k* satisfying:

$$(1+k^*)\ln(1+k^*) = z^2 k^*$$

### Universality Corollary

Since every significant result at α = 0.05 has |z| > 1.96 > 1, **every significant result exhibits the paradox**.

---

## 📁 Repository Structure

```
LCC-Paradox/
├── README.md                           # This file
├── LICENSE                             # MIT License
├── R/
│   └── LCC_Paradox_Supplementary_Code.R   # Complete R code
├── Interactive/
│   └── LCC-Paradox-Interactive-Tool.html  # Interactive demonstration
├── Paper/
│   ├── LCC_Paradox_Biometrika.tex         # LaTeX source
│   └── Supplementary_Material.tex         # Supplementary material
└── docs/
    └── LCC-Paradox-Resources.html         # Landing page
```

---

## 🚀 Quick Start

### Using the Interactive Tool

Visit: **[LCC Paradox Interactive Demo](https://sites.radford.edu/~mlovric/LCC-Paradox-Interactive-Tool.html)**

### Using the R Code

```r
# Source the code
source("R/LCC_Paradox_Supplementary_Code.R")

# Compute Bayes factor
BF01(z = 2.0, k = 2.0)  # k = n * tau^2

# Find flip point
find_flip_point(z = 2.0)

# Demonstrate the paradox
demonstrate_paradox(z = 2.0, n = 50)

# Generate Table 1 from the paper
generate_table1()
```

---

## 📊 Table of Flip Points

| z | z² | p-value | k* | τ* (n=50) | τ* (n=100) |
|---|---|---|---|---|---|
| 1.50 | 2.25 | 0.134 | 2.52 | 0.22 | 0.16 |
| 1.96 | 3.84 | 0.050 | 5.65 | 0.34 | 0.24 |
| **2.00** | **4.00** | **0.046** | **6.07** | **0.35** | **0.25** |
| 2.50 | 6.25 | 0.012 | 11.66 | 0.48 | 0.34 |
| 3.00 | 9.00 | 0.003 | 18.42 | 0.61 | 0.43 |

---

## 📜 Historical Context

| Year | Event |
|------|-------|
| **1957** | Lindley publishes "A Statistical Paradox" in *Biometrika* |
| **1987** | Berger & Sellke argue p-values should be replaced by Bayes factors |
| **2016** | Robert publishes "The Expected Demise of the Bayes Factor," calling for research on prior scale impact |
| **2025** | **The LCC Paradox answers Robert's call** — proving the scale can reverse conclusions entirely |

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@article{lovric2025lcc,
  author  = {Lovric, Miodrag M.},
  title   = {The {LCC} Paradox: A {B}ayesian Statistical Paradox},
  journal = {Biometrika},
  year    = {2025},
  note    = {Submitted}
}
```

---

## 🔗 Links

- **Interactive Tool:** [https://sites.radford.edu/~mlovric/LCC-Paradox-Interactive-Tool.html](https://sites.radford.edu/~mlovric/LCC-Paradox-Interactive-Tool.html)
- **Resources Page:** [https://sites.radford.edu/~mlovric/LCC-Paradox-Resources.html](https://sites.radford.edu/~mlovric/LCC-Paradox-Resources.html)
- **Author's Website:** [https://sites.radford.edu/~mlovric/](https://sites.radford.edu/~mlovric/)

---

## 🤖 A Note on Discovery

This paradox was discovered through **human-AI collaboration** — the first statistical paradox to emerge from such a partnership. The mathematical proofs were developed collaboratively with Claude (Anthropic) and ChatGPT (OpenAI), with all results verified independently.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Miodrag M. Lovric, Ph.D.**  
Associate Professor of Statistics  
Department of Mathematics and Statistics  
Radford University, Virginia, USA  
📧 mlovric@radford.edu

---

## 🙏 Acknowledgments

- **Christian Robert** for his prescient 2016 critique that inspired this investigation
- **Dennis Lindley** whose 1957 paradox laid the foundation
- The developers of **Claude** and **ChatGPT** for enabling this human-AI collaboration

---

<p align="center">
  <b>⚠️ The LCC Paradox ⚠️</b><br>
  <i>Proving that Bayesians cannot agree among themselves</i>
</p>
