# STATS 101C — Obesity Status Classification (Random Forest, KNN, Logistic)

Predictive modeling of **obesity status** using 29 demographic, lifestyle, and clinical predictors; final feature set (15 variables) selected via **VIF screening**, **AIC stepwise**, and **random forest importance**; best model achieved **~99.06%** hold-out/Kaggle accuracy. 

---

## What’s in this repo
- `101C_finalProject.Rmd` — full R analysis (EDA → imputation → feature selection → models → evaluation).
- `STATS 101C Final Report.pdf` — written report with figures and results


---

## Data & Preprocessing
- **Dataset:** 29 predictors spanning demographics (age, gender, race), vitals (height, BP, cholesterol), lifestyle (diet, physical activity, transport), and history (family overweight, comorbidities).  
- **Missingness:** ~8% per predictor handled via **MICE** (multivariate imputation by chained equations).
- **Feature selection:**  
  - Multicollinearity filter with **VIF** (threshold ≈ 5).  
  - **AIC stepwise** regression to balance fit vs complexity.  
  - **Random forest** mean decrease in accuracy for importance ranking.  
  - Final **15 features** combine the strongest signals (e.g., Height, Age, FAF, NCP, CH2O, Race, MTRANS, FAVC, family history, etc.).

---

## Models & Results
- **Logistic Regression:** baseline, ~66% accuracy. 
- **KNN (k=5, scaled, 10-fold CV):** ~94.8–95.0% accuracy (test/Kaggle).  
- **Random Forest (10-fold CV, 15 features):** **98.9% test** and **~99.06% Kaggle**; key drivers include **water intake, age, height, physical activity**, with height/age/race high in importance. 

---