# PROGRESS LOG
> These progress log from January 2024, includes literature review, methodology, evaluation, and documentation steps.
---

## Week-wise Schedule (4 Months)
| Week  | Date | Activities                                                                                                         | Estimated Time (hrs) |
|-------|-----------------|---------------------------------------------------------------------------------------------------|-----------------------|
| **1** | 02-09 Jan, 2024 | - Conducted literature review on random forest regression and ensemble learning. <br> - Explored problem domain: student performance prediction and attribute correlations. <br> - Reviewed research papers (Breiman, Dietterich, Freund & Schapire, etc.) on bias, variance, and model robustness. <br> - Identified datasets [student-math data source](student-mat.csv), [student-por data source](student-por.csv). <br> - Defined project scope: EDA, regression, and classification tasks. | **12 hrs** |
| **2** | 10-17 Jan, 2024 | - Learned **EDA** techniques and **factor analysis** methodology. <br> - Studied evaluation metrics (MSE, MAE, RMSE, Accuracy, Confusion Matrix). <br> - Preprocessed datasets: merged math & Portuguese datasets, encoded categorical variables, validated no missing values. <br> - Performed initial EDA with plots: Age vs Absences, Father’s job distribution, Age distribution by subject, Parent status vs area, and Box plot of final score distribution. | **14 hrs** |
| **3** | 20-27 Jan, 2024 | - Implemented **Random Forest Regression** model. <br> - Achieved strong performance (MSE: `0.0106`, MAE: `0.0113`, RMSE: `0.9993`). <br> - Generated **feature importance graph** to identify key predictors. <br> - Conducted **Factor Analysis** (5 factors), extracted loadings, and visualized eigenvalues via scree plot. <br> - Documented EDA results with plots and interpretations. | **16 hrs** |
| **4** | 28-31 Jan, 2024 | - Implemented **Random Forest Classifier** for categorical prediction (`final_grade`: poor, average, well). <br> - Achieved **81% accuracy**. <br> - Created confusion matrix: strong results for classes 0 & 1, weaker for class 2. <br> - Performed error analysis and suggested improvements (balancing, feature engineering, more data). <br> - Compiled **literature review** on algorithmic vs statistical modeling. <br> - Finalized report with appendices containing full reproducible Python code. | **18 hrs** |

---
**Total Estimated Effort:** ~60 hours
