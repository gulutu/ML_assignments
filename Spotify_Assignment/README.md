# Spotify Data Exploration with Pandas 🎵  

## 📌 Overview  
This project is an exploratory data analysis (EDA) of a **Spotify streaming history dataset** (provided by the instructor). Using **Python (pandas, matplotlib, seaborn)**, the analysis covers the entire workflow from **raw CSV files** to **insightful visualizations**, while answering the tasks in the assignment.  

The goal was to:  
- Clean and preprocess multiple Spotify streaming history files  
- Explore overall listening habits (unique artists, top tracks, time patterns)  
- Define and measure skip behavior (<30s rule)  
- Conduct a focused **case study on Ariana Grande** to compare perception vs. reality in listening habits    

---

## 📂 Dataset  
- Personal Spotify streaming history, retrieved from the export function in Spotify, provided by the lecturer.
- 14 CSV files spanning over a year.
- **Key Columns**:  
  - `endTime` – timestamp of when a track finished  
  - `artistName` – artist  
  - `trackName` – track title  
  - `msPlayed` – play duration in milliseconds (later converted to seconds)  

---

## 🛠️ Skills & Tools Demonstrated  
- **Python**: pandas, matplotlib, seaborn  
- **Data Wrangling**: merging, cleaning, handling missing values, time formatting  
- **EDA**: grouping, aggregations, descriptive statistics  
- **Visualization**: bar charts, line plots, histograms, pie charts  
- **Analytical Thinking**: defining skip metrics, comparing artists, storytelling with data  

---

## 🔎 Analysis Workflow  

### Part 1 – Initial Exploration  
- Imported one month of data  
- Converted `endTime` to `datetime`  
- Counted **495 unique artists** and **1308 unique songs**  
- Previewed basic listening behavior with descriptive statistics  

### Part 2 – Full Year Data  
- Imported and concatenated **14 CSV files** into one DataFrame  
- Filtered only **2023 data** for analysis  
- Removed missing values and converted playtime from ms → seconds  
- Calculated and visualized:  
  - **Top 10 artists** by playtime  
  - **Top 10 tracks** by playtime  
<img width="1026" height="632" alt="top_10_2023" src="https://github.com/user-attachments/assets/61e0e731-e5c4-4132-a2ce-77a8b5a468b8" />
<img width="1046" height="548" alt="top_10_songs" src="https://github.com/user-attachments/assets/10e35179-b396-49dd-ae99-e3bf5573164c" />


### Part 3 – Extended Analysis  
- **Time-of-day listening patterns** (average listening per hour)  
- Compared **Leonard Cohen vs. Rage Against the Machine** (morning vs. evening listening habits)  
- Defined **skipped songs**: <30 seconds playtime  
- Built **skip-rate per artist** and identified artists with highest/lowest skip rates  
- Visualized skipped vs. non-skipped songs with a pie chart  
<img width="1003" height="569" alt="image" src="https://github.com/user-attachments/assets/9b72c75e-1e3c-43a6-bb7d-8e5fd2fef905" />
<img width="856" height="492" alt="image" src="https://github.com/user-attachments/assets/d565fd59-24b6-45e1-88ad-468c472bcc14" />
<img width="606" height="581" alt="image" src="https://github.com/user-attachments/assets/3fec0320-e043-4004-b91d-c957b8f94deb" />



### Part 4 – Case Study: Ariana Grande  
- Filtered all Ariana Grande tracks into a separate DataFrame  
- Compared her **skip-rate** to the full distribution of all artists  
- Showed whether her songs were skipped more or less than average  
- Provided insights into why she appeared as a **top-streamed artist**, despite stated preferences for rock/indie  
<img width="848" height="471" alt="image" src="https://github.com/user-attachments/assets/25353e61-2979-4110-9da1-dcccfe9cd7de" />

---

