# COVID-19 Vaccination Stance Detection Project

## 📌 Overview

This repository contains datasets and code for the research project titled **"Evaluating Autoregressive and Masked Language Models for Context-Aware Stance Detection in Social Networks"**, recently submitted for publication.

The main objective of this study is to **detect users' stances toward COVID-19 vaccination** based on their Twitter posts. Tweets are labeled into three categories: **Neutral, Pro-Vaccine, and Anti-Vaccine**, using the model that achieves the highest evaluation performance.

---

## 📊 Data Collection

We collected English tweets related to **COVID-19, vaccination, and public health** using domain-specific health and vaccine-related keywords.

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

### 🗂️ Dataset 2: `CCTD-2024.csv`

* **Time period:** December 11, 2020 – January 31, 2024
* **Size:** 2,845 tweets
* **Scraping tool:** Requests library
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

### 🔗 Combined Dataset

* **File:** `CCTD-2022_2024.csv`
* **Description:** Merged version of `CCTD-2022.csv` and `CCTD-2024.csv`
* **Total tweets:** 6,481
* **Unique users:** 5,329

---

## 🎯 Research Objective and Approach

The primary objective of this research is to detect users’ stances toward COVID-19 vaccination from short-text. Users are labeled as Pro-Vaccine, Anti-Vaccine, or Neutral. To achieve stance prediction, we fine-tune a variety of pre-trained models, including both open-source and proprietary models, and investigate prompt-based and zero-shot learning for large language models (LLMs). Furthermore, we examine the efficacy of hybrid architectures that combine autoregressive models with convolutional neural networks (ConvNets) to extract user-level features from social network content. To achieve this, we utilize the following models:

### Masked Language Models (MLMs):

* RoBERTa-base
* DistilBERT
* BERT-base

### Autoregressive Language Models (ALMs):

* GPT-3.5-Turbo
* GPT-4-Turbo
* GPT-4o
* GPT-4o-mini
* Meta-LLaMA-3-8B

### Domain-Specific Models:

* COVID-Twitter-BERT v1
* COVID-Twitter-BERT v2

---

## 📊 Model Performance

The following table summarizes the accuracy of selected models on stance detection:

| Model                 | Accuracy |
| --------------------- | -------- |
| COVID-Twitter-BERT v2 | 0.86     |
| COVID-Twitter-BERT v1 | 0.82     |
| GPT-4-Turbo           | 0.80     |

The model **COVID-Twitter-BERT v2** achieved the highest accuracy of **0.86**.

---

## 🏷️ Labeled Data Sources

To build labeled training data, we used two publicly available stance-labeled datasets:

1. **Cotfas et al. Dataset**
   [https://github.com/liviucotfas/covid-19-vaccinationstance-detection](https://github.com/liviucotfas/covid-19-vaccinationstance-detection)

2. **Poddar et al. Dataset**
   [https://github.com/sohampoddar26/covid-vax-stance](https://github.com/sohampoddar26/covid-vax-stance)

These datasets provide manually annotated stances toward COVID-19 vaccination.

---

## 🧠 Training Dataset Construction

Using the two labeled datasets, we constructed a unified labeled dataset for model fine-tuning:

* **File:** `Cotfas_Poddar_Dataset.csv`

This dataset was split into:

* **70%** for training (`train_data.csv`)
* **20%** for testing (`test_data.csv`)
* **10%** for validation (`valid_data.csv`)

A **fixed test set** is used across all models for consistent benchmarking and performance comparison.

---

## 📓 Notebooks Description

### 🔹 Age_Gender_Detection.ipynb

This notebook demonstrates:

* Gender detection based on users' names using the **GPT-4-Turbo** language model
* Gender and age detection using users' **profile images**

⚠️ *Note:* Profile images and usernames are **not shared** due to privacy considerations.

### 🔹 LabelWithChatGPT.ipynb

Contains code for **stance detection** using models from the **GPT family**, used to automatically label users' stances.

### 🔹 preTrain_Bertcovid.ipynb

Implements **CT-BERT (COVID-Twitter-BERT)** models for stance detection.

---

## 📊 Key Findings

Our results indicate that **domain-specific masked language models** and **autoregressive language models** achieve better performance than general masked language models. We also present a combined approach integrating an autoregressive language model with a ConvNet to estimate users’ age and gender, enabling collection of demographic information. Analysis shows that **gender and region** significantly influence public stances.

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
