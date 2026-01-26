# COVID-19-Vaccination-Stance-Detection-Dataset-Experiments


# COVID-19 Vaccination Stance Detection Project

## 📌 Overview

This repository contains datasets and resources for a research project focused on **stance detection toward COVID-19 vaccination** using Twitter data collected between **2021 and 2024**.

The main objective of this study is to analyze public opinions and stances regarding COVID-19 vaccination and to develop machine learning and deep learning models for **automatic stance detection**.

---

## 📊 Data Collection

We collected English tweets related to **COVID-19, vaccination, and public health** from Twitter using domain-specific health and vaccine-related keywords.

### 🗂️ Dataset 1: `CCTD-2022.csv`

* **Time period:** January 5, 2021 – December 31, 2022
* **Size:** 3,636 tweets
* **Scraping tools:** Twint, Snscrape
* **Columns:**

  * `Tweet_created_at`
  * `username`
  * `name`
  * `tweet_text`
  * `replies_count`
  * `retweets_count`
  * `likes_count`
  * `country_name`
  * `id`
  * `year`

---

### 🗂️ Dataset 2: `CCTD-2024.csv`

* **Time period:** December 11, 2020 – January 31, 2024
* **Size:** 2,845 tweets
* **Scraping tool:** Requests library
* **Global collection**
* **Additional metadata:** user-declared date of birth from Twitter bios
* **Columns:**

  * `Tweet_created_at`
  * `likes_count`
  * `replies_count`
  * `retweets_count`
  * `username`
  * `name`
  * `birth_date`
  * `country_name`
  * `tweet_text`
  * `id`
  * `year`

---

### 🔗 Combined Dataset

* **File:** `CCTD-2022_2024.csv`
* **Description:** Merged version of `CCTD-2022.csv` and `CCTD-2024.csv`
* **Total tweets:** 6,481
* **Unique users:** 5,329

---

## 🎯 Research Objective

The primary goal of this research is:

> **To detect users' stances toward COVID-19 vaccination** based on their Twitter posts.

This includes identifying supportive, opposing, and neutral attitudes using supervised learning models.

---

## 🏷️ Labeled Data Sources

To build labeled training data, we used two publicly available stance-labeled datasets:

1. **Cotfas et al. Dataset**
   [https://github.com/liviucotfas/covid-19-vaccinationstance-detection](https://github.com/liviucotfas/covid-19-vaccinationstance-detection)

2. **Poddar et al. Dataset**
   [https://github.com/sohampoddar26/covid-vax-stance](https://github.com/sohampoddar26/covid-vax-stance)

These datasets contain manually annotated stances toward COVID-19 vaccination.

---

## 🧠 Training Dataset Construction

Using the two labeled datasets above, we constructed a unified labeled dataset for model fine-tuning:

* **File:** `Cotfas_Poddar_Dataset.csv`

This dataset was used to train and fine-tune stance detection models.

---

## 📂 Data Splits

For fair model comparison and consistent evaluation across different models, the dataset was split as follows:

* **70%** for training
* **20%** for testing
* **10%** for validation

The corresponding files are:

* `train_data.csv` → Training set
* `valid_data.csv` → Validation set
* `test_data.csv` → Test set

📌 A **fixed test set** is used across all models to ensure reliable benchmarking and fair performance comparison.

---

## 📓 Notebooks Description

### 🔹 Age_Gender_Detection.ipynb

This notebook demonstrates:

* Gender detection based on users' names using the **GPT-4-Turbo** language model
* Gender and age detection using users' **profile images**

⚠️ *Note:* Profile images and usernames are **not shared** in this repository due to privacy considerations.

---

### 🔹 LabelWithChatGPT.ipynb

This notebook contains code for **stance detection** using models from the **GPT family**. It is used to automatically label users' stances toward COVID-19 vaccination.

---

### 🔹 preTrain_Bertcovid.ipynb

This notebook implements the **CT-BERT (COVID-Twitter-BERT)** language model for stance detection toward COVID-19 vaccination.

---

## 🔬 Applications

This repository supports research in:

* Stance detection
* Social media analysis
* Public health informatics
* COVID-19 misinformation studies
* NLP for health-related content

---

## 📁 Repository Structure

````text
.
├── CCTD-2022.csv
├── CCTD-2024.csv
├── CCTD-2022_2024.csv
├── Cotfas_Poddar_Dataset.csv
├── train_data.csv
├── valid_data.csv
├── test_data.csv
├── Age_Gender_Detection.ipynb
├── LabelWithChatGPT.ipynb
├── preTrain_Bertcovid.ipynb
└── README.md
```text
.
├── CCTD-2022.csv
├── CCTD-2024.csv
├── CCTD-2022_2024.csv
├── Cotfas_Poddar_Dataset.csv
├── train_data.csv
├── valid_data.csv
├── test_data.csv
└── README.md
````

---

## 📜 Citation

If you use this dataset or repository in your research, please cite the original datasets and this repository accordingly.

---

## ⚠️ Disclaimer

This data is collected for **research purposes only**. All data usage must comply with Twitter/X policies and ethical research standards.

---

## 🤝 Acknowledgments

We acknowledge the authors of the Cotfas and Poddar datasets for making their labeled resources publicly available for research purposes.
