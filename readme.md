# 🌿 Kaggle Competition: CSIRO - Image2Biomass Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Kaggle](https://img.shields.io/badge/Kaggle-Competition-20BEFF)
![Status](https://img.shields.io/badge/Status-Active-green)

> **Build models that predict pasture biomass from images, ground-truth measurements, and publicly available datasets.**

This repository contains the solution and code for the [CSIRO - Image2Biomass Prediction](https://www.kaggle.com/competitions/csiro-biomass/overview) competition hosted on Kaggle.

---

## 👥 Team Members

| Name | Student ID |
| :--- | :--- |
| **Bintang Muhammad Madani** | 24/551937/PPA/06990 |
| **Rafli Irfansyah Kusumawardhana** | 24/551889/PPA/06988 |
| **Surya Karunia Ramadhan** | 24/551217/PPA/06964 |

---

## 📖 Project Overview

Farmers often walk into a paddock and ask one question: **“Is there enough grass here for the herd?”** It sounds simple, but the answer is complex. Pasture biomass—the amount of feed available—determines when animals can graze, when fields need a break, and how to keep pastures productive season after season. 

* **The Problem:** Current methods like "clip and weigh" are accurate but slow, while plate meters can be unreliable in variable conditions. Remote sensing helps but lacks granular detail on species separation.
* **The Goal:** Estimate pasture biomass correctly to prevent feed waste, improve animal welfare, and ensure healthier soils.
* **The Solution:** This project aims to build a machine learning model that predicts pasture biomass using images, ground-truth measures, and publicly available datasets (including NDVI values) across Australian pastures.

---

## 🎯 Evaluation Metric

The model performance is evaluated using a **globally weighted coefficient of determination ($R^2$)**. 

Instead of calculating $R^2$ separately for each target and averaging, a single weighted $R^2$ is computed over all (image, target) pairs combined. Each row in the dataset is weighted according to its target type:

| Target Variable | Description | Weight |
| :--- | :--- | :--- |
| `Dry_Green_g` | Green biomass component | **0.1** |
| `Dry_Dead_g` | Dead/dry biomass component | **0.1** |
| `Dry_Clover_g` | Clover biomass component | **0.1** |
| `GDM_g` | Green Dry Matter | **0.2** |
| `Dry_Total_g` | Total Dry Matter | **0.5** |

*The heavy weighting on `Dry_Total_g` (0.5) indicates that accurate prediction of total biomass is the primary objective.*

---