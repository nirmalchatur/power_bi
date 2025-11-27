# 🌍 Air Quality Index (AQI) Analysis using Big Data Analytics

## 📌 Overview
This project analyzes **global air pollution data** using **Big Data technologies** (Hadoop, Pig, Hive).  
The goal is to:
- Identify the most polluted countries and cities.
- Categorize air quality levels (Good, Moderate, Unhealthy, Hazardous).
- Support better environmental decision-making through data-driven insights.

Developed as part of a **Group Presentation** at **MIT Academy of Engineering, Pune**.


---

## 📊 Dataset
We used the **Global Air Pollution Dataset** from Kaggle:  
[🔗 Kaggle Dataset](https://www.kaggle.com/datasets/hasibalmuzdadid/global-air-pollution-dataset)

### Sample Columns:
- `Country`
- `City`
- `AQI Value`
- `AQI Category`
- `CO AQI Value`
- `Ozone AQI Value`
- `NO2 AQI Value`
- `PM2.5 AQI Value`

---

## ⚙️ Methodology

### 1️⃣ Hadoop (HDFS Operations)
- Stored dataset in HDFS: `/user/cloudera/airquality2/airquality.csv`
- Commands used:
  - `hdfs dfs -ls /`
  - `hdfs dfs -cat /user/cloudera/airquality2/airquality.csv | head`
  - Copy/Move operations for backup and versioning.

### 2️⃣ Apache Pig (Data Processing)
- Loaded dataset using `PigStorage(',')`.
- Filtered valid AQI records.
- Queries performed:
  - **Top 10 countries with maximum Good AQI cities.**
  - **Top 10 most polluted cities (highest AQI values).**
  - **Count by AQI Category (Good, Moderate, Unhealthy, Hazardous).**

### 3️⃣ Apache Hive (Data Warehousing)
- Created Hive table `air_table1`.
- Queries performed:
  - **Top 10 countries with maximum Good AQI cities.**
  - **Average AQI by country + category.**
  - **Unhealthy cities % contribution by country.**

---

## 📈 Results

### ✅ Top 10 Countries with Best Air Quality
- Brazil (1125 Good cities)  
- Russian Federation (1025)  
- United States of America (1001)  
- Germany (717)  
- Japan (432)  
- France (414)  
- Spain (372)  
- United Kingdom (319)  
- Italy (283)  
- Netherlands (274)  

### ❌ Top 10 Most Polluted Cities
- Ratangarh (India) – AQI 500 (Hazardous)  
- Nuh (India) – AQI 500 (Hazardous)  
- Phalodi (India) – AQI 500 (Hazardous)  
- Bilari (India) – AQI 500 (Hazardous)  
- Durango (USA) – AQI 500 (Hazardous)  
- Gohana (India) – AQI 500 (Hazardous)  
- Pilani (India) – AQI 500 (Hazardous)  
- Jahangirpur (India) – AQI 500 (Hazardous)  
- Gopamau (India) – AQI 500 (Hazardous)  
- Kasganj (India) – AQI 500 (Hazardous)  

### 📊 AQI Category Distribution
- Good: 9688  
- Moderate: 9088  
- Unhealthy: 2215  
- Unhealthy for Sensitive Groups: 1568  
- Very Unhealthy: 286  
- Hazardous: 191  

---

## 🚀 How to Reproduce
1. **Setup Hadoop, Pig, Hive** on Cloudera VM or similar environment.
2. Upload dataset to HDFS:
   ```bash
   hdfs dfs -put airquality.csv /user/cloudera/airquality2/
