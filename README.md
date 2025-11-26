# Job Change Prediction – HR Analytics Power BI Dashboard

This project is an interactive **HR Analytics Dashboard** built in **Microsoft Power BI** to analyze and understand **candidate job change behavior** using the `aug_train.csv` dataset.

The dashboard helps HR teams and stakeholders identify:
- Which candidates are more likely to **change jobs**
- How **experience, training hours, education, company type/size, and city** impact job change decisions
- Which segments of the workforce are at **higher risk** of switching

---

## 🚀 Project Highlights

- Built a **Job Change Prediction – HR Analytics Dashboard** in Power BI  
- Cleaned and transformed the raw dataset (`aug_train.csv`) using **Power Query**  
- Created **DAX measures** for core KPIs like:
  - Total Candidates  
  - Job Switchers  
  - Non-Switchers  
  - Switch %  
  - Average Training Hours  
- Designed a **professional HR-themed UI** with:
  - Slicers synced across pages (gender, education, experience, company type)  
  - Consistent color scheme (e.g., Green → Won’t Change, Red → Will Change)  
  - Data labels, titles, and section headers for better storytelling  

---

## 📊 Dataset

- **File:** `aug_train.csv`  
- **Key Columns:**
  - `enrollee_id` – Unique candidate ID  
  - `city`, `city_development_index`  
  - `gender`, `relevent_experience`, `enrolled_university`  
  - `education_level`, `major_discipline`  
  - `experience` (e.g., `<1`, `5`, `>20`)  
  - `company_size`, `company_type`  
  - `last_new_job` (e.g., `1`, `2`, `>4`, `never`)  
  - `training_hours`  
  - `target` – **0 = Will not change job, 1 = Will change job**

---

## 🧠 Dashboard Pages

### 1️⃣ Job Change Overview
High-level view for HR and management:
- Total Candidates, Job Switchers, Switch % (KPI cards)
- Donut chart: **Job Change Split (Will Change vs Will Not Change)**
- Experience vs job change patterns
- Slicers: gender, education level, experience, company type, company size

---

### 2️⃣ Demographics Analysis
Focus on candidate profiles:
- Education level vs job change
- Major discipline vs job change
- Gender-based job change comparison
- Enrolled university vs job change behavior

---

### 3️⃣ Employment & Training Insights
Focus on current employment and upskilling:
- Company size vs job change
- Company type vs job change
- Last new job vs switch %
- Training hours vs job change trends

---

### 4️⃣ City & Development Index
Location-based analysis:
- City-wise job change %  
- Relationship between **city_development_index** and **Switch %**
- City summary table (Total candidates, Job switchers, Switch %)

---

## 🧮 Key DAX Measures (Examples)

```DAX
Total Candidates =
COUNTROWS(aug_train)

Job Switchers =
CALCULATE([Total Candidates], aug_train[target] = 1)

Job Non-Switchers =
CALCULATE([Total Candidates], aug_train[target] = 0)

Switch % =
DIVIDE([Job Switchers], [Total Candidates])

Avg Training Hours =
AVERAGE(aug_train[training_hours])

Avg City Dev Index =
AVERAGE(aug_train[city_development_index])
