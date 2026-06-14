# Chronic Kidney Disease (CKD) Classification Using NHANES Data

This repository contains a data analysis and machine learning pipeline for processing, cleaning, and formatting chronic kidney disease (CKD) health survey data. The analysis uses dataset records derived from the **National Health and Nutrition Examination Survey (NHANES)** to organize patients into clinical staging classes.

---

## 📌 Project Overview

The objective of this project is to filter multi-dimensional clinical, demographic, and laboratory data into essential biometrics used for evaluating kidney function, specifically tracking structural damage and filtration metrics ($eGFR$).

### Key Features of the Pipeline:
*   **Targeted Demographics Drop:** Eliminates non-predictive features (e.g., patient IDs, ethnicity, smoking history) to focus solely on physiological indicators.
*   **Strict Null-Value Handing:** Removes incomplete clinical profiles ensuring high-fidelity rows ($24.7\%$ row reduction for clean laboratory records).
*   **Duplicate Excision:** Detects and drops identical entries ($3,697$ records removed) to prevent model overfitting.
*   **Clinical Class Mapping:** Translates textual strings of CKD stages into multi-class integers ($0$ through $6$).

---

## 📊 Dataset & Staging Schema

The script processes a **11,933-row** configuration down to **6,199 operational profiles** following statistical data cleansing.

The project maps the standard clinical progression metrics across $7$ operational groups:

| Textual Stage Class | Target Mapping Class | Clinical Description |
| :--- | :---: | :--- |
| **No CKD** | `0` | Normal kidney function |
| **Stage 1** | `1` | Kidney Damage with normal/high $eGFR$ |
| **Stage 2** | `2` | Mildly Decreased $eGFR$ |
| **Stage 3a** | `3` | Mild-to-Moderate Decreased $eGFR$ |
| **Stage 3b** | `4` | Moderate-to-Severe Decreased $eGFR$ |
| **Stage 4** | `5` | Severely Decreased $eGFR$ |
| **Stage 5** | `6` | Kidney Failure ($eGFR < 15$ or Dialysis) |

---

## 🧪 Core Biological Features Retained

After feature reduction, the model focuses on the following core laboratory variables:

*   `serum_creatinine`: Waste product used to estimate kidney filtration efficiency.
*   `blood_urea_nitrogen` (BUN): Measures the amount of urea nitrogen in the blood.
*   `albumin_serum`: Abundant blood protein; levels can indicate nutritional status or systemic stress.
*   `urine_creatinine`: Urinary metric used to normalize total concentration distributions.
*   `urine_albumin`: Small amounts of protein leaked in urine (indicative of early damage).
*   `albumin_creatinine_ratio` (ACR): Primary diagnostic metric for kidney damage.
*   `egfr`: Estimated Glomerular Filtration Rate ($mL/min/1.73m^2$), the definitive measure of overall kidney function.

---


