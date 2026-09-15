# NYC Public Schools SAT Performance & Participation Prediction

##  Project Overview  
This project analyzes and models **New York City public school SAT performance** to uncover meaningful insights and predict **high student test participation** (≥ 80%).  
It integrates **exploratory data analysis (EDA)** with a **baseline machine learning model** to provide both **descriptive analytics** and **predictive capabilities**.  

The work is divided into two main parts:  
1. **Data Analysis & Visualization** – Understanding school performance trends, borough comparisons, correlations, and participation patterns.  
2. **Predictive Modeling** – Using Logistic Regression to classify schools as high or low participation.  

---

##  Objectives  
- Identify **top-performing schools** in NYC based on SAT scores.  
- Compare **borough-wise performance** across math, reading, and writing.  
- Measure **correlations** between different SAT subject scores.  
- Analyze the **impact of participation rates** on performance.  
- Identify **outlier schools** significantly above or below borough averages.  
- Predict **high vs low student participation** based on school features.  

---

##  Dataset  

**File**: `schools.csv`  
**Columns**:  
- `school_name` – Name of the school  
- `borough` – NYC borough  
- `average_math`, `average_reading`, `average_writing` – Average SAT scores per subject  
- `percent_tested` – Percentage of students tested  
- Derived Features:  
  - `total_SAT` – Combined SAT score  
  - `high_participation` – Binary target variable

---

##  Key Insights  

### **1. Top Math Performers**
- Schools with average math scores above **640** were filtered.  
- *Stuyvesant High School* led in math performance, followed by *Bronx High School of Science* and *Staten Island Technical High School*.  

### **2. Top 10 Schools by Total SAT Score**
- Stuyvesant High School scored **2144** — highest in NYC.  
- *Bronx High School of Science* and *Staten Island Technical High School* both scored **2041**.  
- Several specialized science, math, and early college schools dominate the top list.  

### **3. Borough with Highest Score Variation**
- **Manhattan** had the **largest standard deviation** in combined SAT scores, showing a wide range of school performance — from very high to low.  

### **4. Average Performance by Borough**
- **Staten Island**: Highest average across all subjects and most consistent scores.  
- **Bronx**: Lowest averages overall.  
- **Manhattan**: High averages but wide variation in performance.  

### **5. Subject Correlation**
- Very strong positive correlation between subjects:  
  - Math & Reading: **0.93**  
  - Math & Writing: **0.93**  
  - Reading & Writing: **0.99**  
- Students strong in one subject tend to excel in others, especially reading and writing.  

### **6. Impact of Participation Rate**
- Schools with **≥80% participation** scored **~80–100 points higher per subject** and **~300 points higher in total**.  
- Suggests a strong relationship between participation and performance.  

### **7. Distribution of Scores by Borough**
- **Staten Island**: Highest and most consistent scores.  
- **Bronx**: Lowest median, tight spread at lower end.  
- **Manhattan**: Widest score spread, with many high and low outliers.  
- All boroughs had high-performing outliers, especially Manhattan and Queens.  

---

##  Machine Learning Model  

**Model**: Logistic Regression (Baseline)  
**Target**: `high_participation` (1 = ≥80%, 0 = <80%)  

### **Performance Metrics**
- Accuracy: **82.67%**  
- F1 Score (High Participation): **0.43**  
- ROC-AUC: **0.64**  

**Confusion Matrix:**
|                | Pred Low | Pred High |
|----------------|----------|-----------|
| **Actual Low** | 57       | 1         |
| **Actual High**| 12       | 5         |

**Interpretation**:
- Model predicts **low participation schools** well.  
- Struggles with **high participation recall** due to class imbalance. 

---

##  Tech Stack  

- **Python**: pandas, numpy, matplotlib, seaborn  
- **Scikit-learn**: Logistic Regression, preprocessing, metrics  
- **Jupyter Notebook**: Interactive analysis and visualization  

---

##  Visualizations  

- **Bar Charts** – Top-performing schools, borough averages  
- **Heatmap** – Correlation between SAT subjects  
- **Box Plots** – Score distribution by borough  
- **Confusion Matrix Heatmap** – Prediction vs actual outcomes  

---

##  Next Steps  

- Address **class imbalance** with SMOTE or oversampling.  
- Explore **tree-based models** (Random Forest, XGBoost) for improved recall.  
- Engineer **additional features** (e.g., socioeconomic data, attendance rates).  

---

##  License  
This project is licensed under the MIT License – free to use and adapt.  

---

 

