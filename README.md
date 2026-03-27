# 🎬 Data Warehouse Project: IMDB Top 1000 Movies & TV Shows

<p align="center">
  <img src="https://img.shields.io/badge/Project-Business%20Intelligence-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Database-SQLite-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Python-ETL-yellow?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

---

## 📌 Overview
Proyek ini bertujuan untuk membangun **Data Warehouse** berbasis dataset **IMDB Top 1000 Movies & TV Shows** menggunakan pendekatan **Star Schema**.  

Pipeline mencakup proses **ETL (Extract, Transform, Load)**, penyimpanan dalam database, serta analisis data untuk menghasilkan insight yang relevan dalam konteks **Business Intelligence**.

---

## 🎯 Objectives
- Membersihkan dan menstandarkan data IMDB.
- Membangun model dimensional (Star Schema).
- Menyimpan data dalam Data Warehouse (SQLite).
- Menghasilkan insight berbasis query dan visualisasi.
- Mendukung pengambilan keputusan berbasis data.

---

## 🔗 Important Links
- 📂 Repository:  
  https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset.git  
- 📊 Dataset Source:  
  https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows  

---

## 👥 Team Members
| Nama | NIM |
|------|------|
| Yudha Tri Atmaja | 2409116095 |
| Mochammad Rezky Ramadhan | 2409116029 |
| Muhammad Ilyasa' Izzuddin | 2409116033 |
| Sayid Rafi Athaya | 2409116036 |

---

## 🛠️ Tech Stack
| Category | Tools |
|----------|------|
| Programming | Python |
| Data Processing | Pandas, NumPy |
| Database | SQLite |
| Visualization | Matplotlib, Seaborn, Plotly |
| Environment | Jupyter Notebook / Google Colab |

---

## 📊 Dataset Information
- 📁 File: `Dataset/imdb_top_1000.csv`
- 📌 Total Data: 1000 records
- 📈 Key Features:
  - Movie Info: `Series_Title`, `Released_Year`, `Genre`
  - Rating Metrics: `IMDB_Rating`, `Meta_score`
  - Popularity: `No_of_Votes`, `Gross`
  - Cast & Crew: `Director`, `Star1`–`Star4`
  - Description: `Overview`

---

## 🏗️ Data Warehouse Architecture

### ⭐ Star Schema Design

**Fact Table**
- `fact_movie_performance`

**Dimension Tables**
- `dim_movie`
- `dim_director`
- `dim_genre`
- `dim_time`
- `dim_certificate`

📦 Output Database:
```
DataWarehouse/imdb_datawarehouse.db
```

---

## ⚙️ ETL Process

### 1️⃣ Extract
- Mengambil data dari file CSV (`imdb_top_1000.csv`)

### 2️⃣ Transform
- Data cleaning:
  - `Runtime`, `Gross`, `Released_Year`
- Handling missing values:
  - `Certificate`, `Meta_score`, `Gross`
- Feature engineering:
  - `Decade`
  - `Era`
  - `Primary_Genre`
  - `Rating_Category`

### 3️⃣ Load
- Membuat tabel dimensi & fakta
- Menyimpan ke SQLite Data Warehouse

### 4️⃣ Analysis
- Distribusi rating film
- Genre paling populer
- Top directors
- Tren film per dekade
- Analisis gross revenue
- Korelasi antar metrik

📂 ETL Scripts:
- `ETL/imdb_datawarehouse_colab.py`
- `ETL/IMDB_DataWarehouse_Colab.ipynb`

---

## 📁 Repository Structure
```bash
BI/
├── Dataset/
│   └── imdb_top_1000.csv
├── ETL/
│   ├── IMDB_DataWarehouse_Colab.ipynb
│   └── imdb_datawarehouse_colab.py
├── DataWarehouse/
│   ├── imdb_datawarehouse.db
│   ├── plot_rating_distribution.png
│   ├── plot_genre_count.png
│   ├── plot_top_directors.png
│   ├── plot_trend_decade.png
│   ├── plot_top_gross.png
│   ├── plot_correlation.png
│   ├── plot_certificate.png
│   └── plot_top_popular.png
├── Laporan/
│   ├── Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top 1000_IMDB.docx
│   └── Laporan.rar
└── Tugas/
    └── tugas_bi.jpeg
```

---

## 🚀 How to Run

### ▶️ Option 1: Python Script
```bash
cd BI
python ETL/imdb_datawarehouse_colab.py
```

### ▶️ Option 2: Notebook
- Buka file:
```
ETL/IMDB_DataWarehouse_Colab.ipynb
```
- Jalankan per cell di Jupyter / Google Colab

📌 Output:
```
DataWarehouse/imdb_datawarehouse.db
```

---

## 📈 Sample Insights
Beberapa insight yang dihasilkan:
- Film dengan rating tertinggi didominasi genre tertentu
- Director tertentu memiliki konsistensi rating tinggi
- Tren film meningkat signifikan di dekade modern
- Korelasi antara jumlah vote dan rating cukup kuat

---

## 📄 Documentation
- 📑 Laporan Utama:  
  `Laporan/Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top 1000_IMDB.docx`

- 📦 Arsip:  
  `Laporan/Laporan.rar`

---

## ✨ Final Notes
Proyek ini menunjukkan implementasi lengkap **Business Intelligence pipeline**, mulai dari data mentah hingga menjadi insight yang dapat digunakan untuk analisis dan pengambilan keputusan.

---

<p align="center">
  Made with 💻 for Business Intelligence Course
</p>
