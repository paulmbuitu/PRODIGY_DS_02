# Titanic Data Cleaning & Exploratory Data Analysis (EDA) in Power BI

## 📌 Project Overview
This project is **Task-02** from my Prodigy InfoTech Internship program, focusing on **data cleaning** and **exploratory data analysis** (EDA) using the Titanic dataset from Kaggle.

The dataset was split into two files:
- **features.csv**: Passenger details such as demographics, ticket, and travel information.
- **survived.csv**: Survival status (0 = Did not survive, 1 = Survived).

I merged and transformed the data using **Power BI** (Power Query), created new features, handled missing values, and built an **interactive dashboard** for exploring survival patterns.

---

## 🛠 Tools & Technologies
- **Power BI Desktop**
- **Power Query Editor** (Data Cleaning & Feature Engineering)
- **DAX** (Measures & Calculations)
- **Data Visualization** (Interactive Dashboard)

---

## 🔍 Data Cleaning & Feature Engineering
**Steps Performed:**
1. **Load & Merge Datasets**  
   - Merged on `PassengerId` using Left Outer Join.
2. **Data Type Assignment**  
   - Ensured proper types for numerical, categorical, and text fields.
3. **Feature Extraction & Transformation**
   - Extracted `Title` from passenger names.
   - Created `Deck` from cabin letters.
   - Added `FamilySize` and `IsAlone` indicators.
4. **Missing Value Handling**
   - Filled `Age` with median age per title.
   - Filled `Fare` with median per passenger class.
   - Filled missing `Embarked` with most common port.
5. **Column Cleanup**
   - Removed unnecessary fields like `Ticket` and `Cabin` (original column).

---

## 📊 Exploratory Data Analysis
The dashboard explores:
- **Survival distribution** (Donut Chart)
- **Survival by Passenger Class and Sex** (100% Stacked Column)
- **Age distribution** (Histogram with survival rates)
- **Fare vs Age relationship** (Scatter Plot with bubble size = family size)
- **Passenger details table** (interactive with slicers)

---

## 📈 Key DAX Measures
```DAX
TotalPassengers = COUNTROWS('MergeFareCleaned')
SurvivedCount = SUM('MergeFareCleaned'[Survived])
SurvivalRate = DIVIDE([SurvivedCount], [TotalPassengers], 0)
MedianFare = MEDIAN('MergeFareCleaned'[CleanedFare])
AvgAge = AVERAGE('MergeFareCleaned'[Age])
```

---

## 🚀 Insights Gained

- Females had a significantly higher survival rate than males.
- First-class passengers survived at higher rates compared to other classes.
- Children and families had different survival patterns compared to solo travelers.
- Higher fares generally correlated with higher survival likelihood.

