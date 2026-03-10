# Data Warehouse: IMDB Top 1000 Movies & TV Shows

## 📚 Daftar Isi
- [🔗 Link Penting](#-link-penting)
- [📝 Deskripsi Proyek](#-deskripsi-proyek)
  - [Tujuan](#tujuan)
- [👥 Profil Kelompok](#-profil-kelompok)
- [🛠️ Tech Stack](#️-tech-stack)
- [📊 Dataset](#-dataset)
- [🏗️ Arsitektur Data Warehouse](#️-arsitektur-data-warehouse)
  - [Star Schema](#star-schema)
- [⚙️ Proses ETL](#️-proses-etl)
- [📁 Struktur Repo](#-struktur-repo)
- [🚀 Cara Menjalankan](#-cara-menjalankan)
- [📄 Laporan](#-laporan)

## 🔗 Link Penting
- Repository: `https://github.com/mocharezky04/bi-uts-IMDB-Movies-Dataset.git`
- Dataset sumber: `https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows`

## 📝 Deskripsi Proyek
Proyek ini membangun **Data Warehouse** dari dataset **IMDB Top 1000 Movies & TV Shows** menggunakan pendekatan **Star Schema**.  
Pipeline mencakup proses **Extract, Transform, Load (ETL)**, lalu dilanjutkan analisis SQL dan visualisasi insight.

### Tujuan
- Membersihkan dan menstandarkan data IMDB agar siap analisis.
- Membuat model dimensional (star schema) untuk analisis BI.
- Menyajikan insight dalam bentuk query dan plot.
- Menyusun laporan tugas Business Intelligence.

## 👥 Profil Kelompok
- Yudha Tri Atmaja
- Mochammad Rezky Ramadhan
- Muhammad Ilyasa' Izzuddin
- Sayid Rafi Athaya

## 🛠️ Tech Stack
- Python (Pandas, NumPy)
- SQLite
- Jupyter Notebook / Google Colab
- Matplotlib, Seaborn, Plotly

## 📊 Dataset
- File: [`Dataset/imdb_top_1000.csv`](./Dataset/imdb_top_1000.csv)
- Jumlah data: 1000 entri film/TV show
- Fitur utama:
  - `Series_Title`, `Released_Year`, `Genre`, `Certificate`
  - `IMDB_Rating`, `Meta_score`, `No_of_Votes`, `Gross`
  - `Director`, `Star1`–`Star4`, `Overview`

## 🏗️ Arsitektur Data Warehouse
Model menggunakan **Star Schema**:

### Star Schema
- **Fact Table**
  - `fact_movie_performance`
- **Dimension Tables**
  - `dim_movie`
  - `dim_director`
  - `dim_genre`
  - `dim_time`
  - `dim_certificate`

Output database:
- [`DataWarehouse/imdb_datawarehouse.db`](./DataWarehouse/imdb_datawarehouse.db)

## ⚙️ Proses ETL
1. **Extract**
   - Load data CSV `imdb_top_1000.csv`.
2. **Transform**
   - Cleaning `Runtime`, `Gross`, `Released_Year`.
   - Penanganan missing values (`Certificate`, `Meta_score`, `Gross`).
   - Penambahan kolom turunan (`Decade`, `Era`, `Primary_Genre`, `Rating_Category`).
3. **Load**
   - Membuat dan mengisi tabel dimensi + tabel fakta di SQLite.
4. **Analisis**
   - Distribusi rating, genre terbanyak, top director, tren dekade, gross revenue, korelasi metrik.

Script ETL:
- [`ETL/imdb_datawarehouse_colab.py`](./ETL/imdb_datawarehouse_colab.py)
- [`ETL/IMDB_DataWarehouse_Colab.ipynb`](./ETL/IMDB_DataWarehouse_Colab.ipynb)

## 📁 Struktur Repo
```text
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

## 🚀 Cara Menjalankan
1. Masuk ke folder `BI`.
2. Jalankan script ETL:
   ```bash
   python ETL/imdb_datawarehouse_colab.py
   ```
3. Pastikan file output database terbentuk di `DataWarehouse/imdb_datawarehouse.db`.
4. Alternatif: buka notebook `ETL/IMDB_DataWarehouse_Colab.ipynb` di Colab/Jupyter untuk run per sel.

## 📄 Laporan
- Dokumen laporan utama:
  - [`Laporan/Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top 1000_IMDB.docx`](./Laporan/Laporan_DataWarehouse_Kelompok_5_Business_Intelligence_Top%201000_IMDB.docx)
- Arsip laporan:
  - [`Laporan/Laporan.rar`](./Laporan/Laporan.rar)
