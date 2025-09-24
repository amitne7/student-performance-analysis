**Timeline:** 02 Jan 2024 - 31 Jan 2024   
**Role:** Data Analyst      
**Type of Project:** Data analysis (Academic Project)   
**Location:** Huddersfield(UK)   
**Outcome:** Learned **EDA** techniques and **factor analysis** methodology, implemented **Random Forest Regression** model, implemented **Random Forest Classifier** for categorical prediction, Explored problem domain: student performance prediction and attribute correlations.

---

# Student Performance Analysis
Prediction of​ student’s ​performance using random forest regression​ 

Data set : https://archive.ics.uci.edu/dataset/320/student+performance

This document summarizes the exploratory data analysis (EDA), regression tasks, and classification tasks performed on the dataset. Each section contains findings supported by labeled figures and tables.  

---

## Quick Start
### 1. Clone repository
```bash
git clone https://github.com/amitne7/student-performance-analysis
cd student-performance-analysis
```
### 2. Create virtual environment
```bash
python -m venv .venv && source .venv/bin/activate
```
### 3. Install dependencies
```bash
pip install pandas numpy scikit-learn matplotlib seaborn factor_analyzer
```
### 4. Run notebook (executes all cells, saves output)
```bash
jupyter nbconvert --to notebook --execute "student-performance.ipynb" --output "artifacts/output.ipynb"
```

### 5. Open artifacts
```bash
jupyter notebook artifacts/output.ipynb
```

---

## 2.1 Question 1: Exploratory Data Analysis (EDA)

### 2.1.1 Size of the data
<img width="604" height="158" alt="image" src="https://github.com/user-attachments/assets/97a59b82-d0ed-40d5-9cc2-0b354a1e02c5" />

**Figure 1:** Python code snippet showing the size of the data.  
- The size of the data is **35,496**.

---

### 2.1.2 Number of variables or features in the data
<img width="619" height="263" alt="image2" src="https://github.com/user-attachments/assets/819a3002-1ee3-4e1e-a0a2-69ffe402a36c" />

**Figure 2:** Python code snippet showing rows and columns in the data.  
- There are **1,044 rows (samples)** and **34 columns (features)**.

---

### 2.1.3 Data types of the variables
<img width="797" height="771" alt="image3" src="https://github.com/user-attachments/assets/1da39815-ace5-44d2-9740-a632d990c5d1" />

**Figure 3:** Python code snippet showing variable data types.  
- **19 categorical variables (string type)**  
- **16 numerical variables (integer type)**

---

### 2.1.4 Missing data
<img width="1388" height="834" alt="image4" src="https://github.com/user-attachments/assets/22586bfd-c99b-4e21-8e36-7dd17c7ce098" />

**Figure 4:** Python code snippet showing missing values.  
- **No missing values detected in the dataset.**

---

### 2.1.5 Student absences against age
<img width="1112" height="702" alt="image5" src="https://github.com/user-attachments/assets/a02d2095-03b7-4bfa-8de1-0cb46ae1eef6" />

**Figure 5:** Bar graph showing *Age vs. Absences*.  
- Clear **positive correlation** between age and absences.  
- Absences increase notably for students aged **10 to 16**, ranging from **10 to 30 absences per student**.

---

### 2.1.6 Distribution of fathers' jobs
<img width="940" height="703" alt="image6" src="https://github.com/user-attachments/assets/4f052a59-9f8c-43c7-b0bb-e1d853aa4182" />

**Figure 6:** Histogram showing distribution of fathers' jobs.  
- Most fathers work in **"other jobs"**, followed by **service jobs**.  
- Few fathers in **teaching profession** and **home roles (<100)**.  
- **Least fathers in health professions.**

---

### 2.1.7 Age distribution by subject
<img width="985" height="687" alt="image7" src="https://github.com/user-attachments/assets/9c619e9b-c800-4092-a74c-f3d700c6f8fd" />

**Figure 7:** Bar chart showing age distribution against subject.  
- Both **Math** and **Portuguese** students peak at **12–14 years**.  
- Math students slightly younger (11–12 years), Portuguese students slightly older (16–17 years).

---

### 2.1.8 Student living area by parent status
<img width="1232" height="782" alt="image8" src="https://github.com/user-attachments/assets/b5971c23-85e7-4a1f-90e5-cb5525cf7ea2" />

**Figure 8:** Bar chart showing student percentage by parent living status.  
- **More students live with parents together** (rural > urban).  
- **Students with separated parents higher in urban areas** than rural.

---

### 2.1.9 Final score distribution (Box Plot)
<img width="980" height="663" alt="image9" src="https://github.com/user-attachments/assets/a07c6d3c-b548-433e-96fe-daf18736d487" />

**Figure 9:** Final score box plot.  
- Scores are **normally distributed** with:  
  - **Median = 5**  
  - **Q1 = 2.5, Q3 = 7.5** (IQR = 5)  
  - **Range: 0–10**, whiskers extend ~ -2.5 to 12.5  
- **Outliers** indicate some unusually high/low scores.

---

### 2.1.10 Advanced Question: Factor Analysis

<img width="1220" height="589" alt="imagea" src="https://github.com/user-attachments/assets/d9eca3f7-62c9-4815-9f42-86cf50e37cd0" />

**Figure 10:** Factor analysis results.  

**Key factor loadings (Top contributors):**
- **Factor 1:** Period scores, Final score, Final grade (>0.86 loading)  
- **Factor 2:** Mother and Father education (>0.74 loading)  
- **Factor 3:** Weekend/Weekday alcohol usage (>0.60 loading)  
- **Factor 4:** Sex (-0.62 loading), Study time (-0.32 loading)  
- **Factor 5:** Free time (0.47), Going out (0.71)

---

## 2.2 Question 2: Regression Task
**Model Performance Metrics:**
- **Mean Squared Error (MSE):** 0.0106  
- **Mean Absolute Error (MAE):** 0.0114  
- **Root Mean Squared Error (RMSE):** 0.9993  

> These small error values indicate a **highly accurate predictive model**, with RMSE close to 1, suggesting prediction errors are of similar scale to the target variable.

---
<img width="1354" height="715" alt="imageb" src="https://github.com/user-attachments/assets/79d923f4-1401-4641-8a48-14bc68580164" />

### 2.2.1 Feature Importance
**Figure 11:** Feature importance graph for regression task.

---

## 2.3 Advanced Question 2: Classification Task

### 2.3.1 Classification using Random Forest
- **Accuracy:** **81% (0.81)**

---

### 2.3.2 Confusion Matrix
<img width="810" height="539" alt="imagec" src="https://github.com/user-attachments/assets/69ae25d6-1541-401d-82ab-cc031df86182" />

**Figure 12:** Confusion matrix visualization.  
- **Classes 0 and 1:** High precision, recall, and F1-score.  
- **Class 2:** Lower recall and F1-score — misclassification occurs.

---

### 2.3.3 Improving Class 2 Performance
- **Increase data collection** for Class 2.  
- **Balance class distribution**.  
- **Experiment with other algorithms** and **feature engineering**.  
- **Perform error analysis** and **cost-sensitive learning**.

---

## Conclusions
1. The dataset is clean, with **no missing values**, and well-structured with **34 features**.  
2. EDA revealed key demographic and behavioral patterns (e.g., **age vs absences**, **parent job distributions**).  
3. **Regression model performs strongly** with low error rates.  
4. **Classification model (Random Forest)** achieves high accuracy overall but needs improvement in **Class 2 performance**.  
5. **Factor analysis identified educational background, alcohol usage, and exam scores as significant components.**

---

**Figures Reference:**  
- Figure 1: Dataset size  
- Figure 2: Rows and columns  
- Figure 3: Data types  
- Figure 4: Missing data check  
- Figure 5: Age vs Absences  
- Figure 6: Fathers’ job distribution  
- Figure 7: Age vs Subject distribution  
- Figure 8: Parent status by living area  
- Figure 9: Final score distribution box plot  
- Figure 10: Factor analysis results  
- Figure 11: Feature importance graph  
- Figure 12: Confusion matrix  

---

# Timeline
**Progress log week wise**
- [Progress log](PROGRESSLOG.md)





