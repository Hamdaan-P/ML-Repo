# Project Summary — Heart Disease Prediction Pipeline
**Author:** Hamdaan
**Date:** June 2026

---

## What I Found in the Data

The Heart Disease UCI dataset contains clinical records from 208 patients (after cleaning) collected at the Cleveland Clinic Foundation. Each patient has 13 clinical features — including age, chest pain type, cholesterol, and maximum heart rate — along with a binary label indicating whether heart disease was diagnosed.

The first and most important finding came from the class distribution: 127 patients (61%) had no heart disease and 81 (39%) did. This mild class imbalance meant that a model naively predicting "no disease" for every patient would achieve 61% accuracy while being completely useless clinically. I flagged this upfront and addressed it explicitly in the machine learning stage.

Age showed a statistically interesting but practically limited relationship with disease. Patients with heart disease averaged 57.3 years versus 52.0 years for those without — a 5.3 year gap. However, the age histogram revealed heavy overlap between the two groups between ages 50 and 65, confirming that age alone cannot reliably separate the classes. This illustrated directly why machine learning combines multiple features rather than relying on any single signal.

The correlation heatmap identified the three strongest predictors of heart disease: number of major vessels (0.55), thalassemia type (0.52), and ST depression (0.45). One finding that stood out was the negative correlation between maximum heart rate and heart disease (−0.43). This appears counterintuitive at first — but it makes clinical sense. The maximum heart rate here is measured during an exercise stress test. A healthy heart can sustain higher effort and achieve a higher peak, while a diseased heart fatigues faster and plateaus lower. The data confirmed established cardiology literature.

---

## Which Model I Chose and Why

I trained two classification models: Logistic Regression as an interpretable baseline and Random Forest as an ensemble method.

**Random Forest was the stronger overall model**, achieving 92.9% accuracy, 0.93 precision, 0.88 recall, and a 0.90 F1 score. Logistic Regression achieved perfect recall (1.00) but at the cost of precision (0.70) — meaning it flagged nearly every patient as sick to avoid missing anyone. While maximising recall has genuine value in medical screening, the extreme trade-off in Logistic Regression's case reflected over-compensation rather than true learning. Random Forest delivered a far better balance across all four metrics, with an F1 score 8 points higher.

The feature importance chart from Random Forest further validated its learning — the top-ranked features (num_major_vessels, thalassemia, st_depression, max_heart_rate) aligned precisely with the correlation heatmap findings from the EDA stage. This consistency between statistical analysis and model behaviour indicates the model learned clinically meaningful patterns rather than overfitting to noise.

Class imbalance was addressed using `class_weight='balanced'` in both models, which penalises errors on the minority class (disease) more heavily during training. For a mild 61/39 imbalance, this approach is sufficient and avoids the complexity of synthetic data generation methods like SMOTE.

---

## One Insight That Surprised Me

The most surprising finding was the asymptomatic chest pain pattern. Chest pain type 4 — labelled "asymptomatic" — was not only the most common category in the dataset but also had the strongest association with heart disease among all chest pain types. In plain language: the patients who reported *no* chest pain were more likely to have heart disease than those who reported classic cardiac symptoms.

This is a well-documented but clinically alarming phenomenon — silent ischemia, where the heart is under stress without the patient feeling it. From a data science perspective it reinforced an important lesson: domain knowledge cannot be replaced by pattern recognition alone. A purely data-driven model would correctly learn this association, but understanding *why* it exists is what separates a data scientist from a script runner.

---

*This project was completed as part of the ZaryahPlus Data Science Internship Programme, June 2026.*
