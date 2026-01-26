rtcovid.ipynb

Implements **CT-BERT (COVID-Twitter-BERT)** models for stance detection.

---

## 📊 Key Findings

In this work, we propose a framework for detecting users’ stances toward a specific topic, aiming to extract insights into crisis situations, particularly epidemics. The framework is evaluated on public stances regarding COVID-19 vaccination, focusing on short texts related to disease and pregnancy. The dataset spans from December 11, 2020, to February 16, 2024, providing a holistic representation of vaccination-related discussions before, during, and after vaccine distribution.

Users’ stances are classified into three categories: Pro-Vaccine, Anti-Vaccine, and Neutral. Our results indicate that **domain-specific masked language models** and **autoregressive language models** achieve better performance than general masked language models. We also present a combined approach integrating an autoregressive language model with a ConvNet to estimate users’ age and gender, enabling collection of demographic information. Analysis shows that **gender and region** significantly influence public stances.

---

## 🔬 Applications

This repository supports research in:

* Stance detection
* Social media analysis
* Public health informatics
* COVID-19 misinformation studies
* NLP for health-related content

---

## 📜 Citation

If you use this dataset or repository in your research, please cite the original datasets and this repository accordingly.

---

## ⚠️ Disclaimer

This data is collected for **research purposes only**. All data usage must comply with Twitter/X policies and ethical research standards.

---

## 🤝 Acknowledgments

We acknowledge the authors of the Cotfas and Poddar datasets for making their labeled resources publicly available for research purposes.
