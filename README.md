# 🚦 UK Road Accident Dashboard (Power BI Project)

This project is a **Power BI dashboard solution** for analyzing road accident trends in the UK. Inspired by the *Data Tutorials* YouTube series, the goal was to simulate a real-world business intelligence solution involving multiple stakeholders such as the Ministry of Transport, police departments, and the public.

Unlike other projects (e.g., Alex The Analyst), this work places a heavy focus on **visual design**, stakeholder-oriented KPIs, and dashboard storytelling. All visuals and data transformations were implemented in **Power BI** using **direct CSV imports**.

---

## 📁 Dataset Source

The dataset was sourced from a public repository:  
🔗 [Google Drive - Road Accident Dataset](https://drive.google.com/drive/folders/1pCNs-TRPznlbAn712gAGy7XfBnWs2QJm)

---

## 🧰 Tools & Technologies Used

| Tool           | Purpose                               |
|----------------|----------------------------------------|
| Power BI       | Data import, transformation, and dashboard creation |
| Power Query    | Data cleaning and shaping              |
| DAX            | Creating measures and KPIs             |
| PowerPoint     | Background design (optional aesthetic layer) |
| GitHub         | Documentation & versioning             |

---

## 👥 Stakeholders

- Ministry of Transport  
- Police departments  
- Emergency Services (Ambulance)  
- Public safety organizations  
- Media and journalists  

---

## 📊 Dashboard KPIs & Visuals

### 🔹 Primary KPIs

1. **Total Casualties (Current Year)**  
2. **Total Accidents (Current Year)**  
3. **Year-on-Year (YoY) Growth for Casualties and Accidents**  
   - `TOTALYTD()` and `SAMEPERIODLASTYEAR()` DAX functions used
   - Displayed with cards and formatted with colors (e.g., red for decline)

```DAX
CY_Casualties = TOTALYTD(SUM(Data[Number_of_casualties]), Calendar[Date])
PY_Casualties = CALCULATE(SUM(Data[Number_of_casualties]), SAMEPERIODLASTYEAR(Calendar[Date]))
YOY_Growth = DIVIDE(CY_Casualties - PY_Casualties, PY_Casualties)
```

### 🔹 Secondary KPIs & Charts

- **Casualties by Accident Severity** (filtered)
- **Casualties by Vehicle Type** (grouped, multi-row table)
- **Monthly Casualty Trend Comparison** (Area Chart: CY vs PY)
- **Urban vs Rural Accidents** (Pie/Donut Chart with percentages)
- **Casualties by Light Conditions (Day/Night)** (Donut chart)
- **Geographic Breakdown** (Map with latitude/longitude)
- **Casualties by Road Type** (Stacked Bar Chart)

---

## 🧹 Data Cleaning & Modeling

- Imported directly into Power BI from CSV
- Used **Transform Data** (Power Query) to:
  - Fix typos like "Fetal" → "Fatal"
  - Ensure complete data (no missing rows or nulls found)
  - Generate a **Calendar Table** for time intelligence

```DAX
Calendar = CALENDAR(MIN(Data[Accident Date]), MAX(Data[Accident Date]))
Year = YEAR('Calendar'[Date])
Month = FORMAT('Calendar'[Date], "mmm")
Month Number = MONTH('Calendar'[Date])
```

- Linked `Data[Accident Date]` to `Calendar[Date]` using a 1:many relationship

---

## 🖼️ Visual Design Notes

- Visual consistency maintained by:
  - Removing gridlines, axis titles, and chart backgrounds
  - Using white font for dark backgrounds
  - Importing custom background from PowerPoint as `.jpg`
  - Adding **card visuals** for KPIs
  - Sorting months using "Month Number" column
  - Formatting pie charts with percentage labels and color differentiation

---

## 📚 Skills Demonstrated

- **Power BI End-to-End Workflow**
- **Data Cleaning using Power Query**
- **DAX for KPIs, YOY calculations, time intelligence**
- **Data Visualization & Dashboard Design**
- **Stakeholder-oriented BI Thinking**
- **Calendar table modeling and relationships**

---

## 🧠 Key Learning Points

- Hands-on experience building analytical dashboards for real-world use cases  
- Handling large datasets with 300K+ rows and 21 columns  
- Improving storytelling via design and interactivity  
- Creating dynamic Year-on-Year comparisons and breakdowns  

---

## 🧑‍💼 Author

**Yeo Chee En Luke**  
Statistician & Computer Scientist  
---

## 🎥 Acknowledgements

This project is based on the following [Data Tutorials video](https://www.youtube.com/watch?v=Hn9f13uoLAQ&list=PLNr6y7fJuf_f9wCIPQTun4pMosf5e4fFk&index=4).  
While the project scope follows the video structure, all cleaning, modeling, and visualizations are done independently and customized with my own thought process and creative design choices.

---


![image](https://github.com/user-attachments/assets/8f53a1b3-00a3-4969-ae3b-feb170cc80bd)
