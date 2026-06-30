# Dashboard Analisis Penjualan & Performa Seller

Web aplikasi analisis penjualan dengan dashboard interaktif yang membantu seller memahami performa bisnisnya — dilengkapi segmentasi pelanggan otomatis, forecasting penjualan, dan analisis dampak diskon menggunakan algoritma data science.

**🔗 Live Demo:** [dashboard-penjualan-kelompok1.streamlit.app](https://dashboard-penjualan-kelompok1.streamlit.app)

---

## Preview

> Tambahkan screenshot dashboard di sini — lihat bagian [Cara Menambahkan Screenshot](#-cara-menambahkan-screenshot) di bawah.

![Dashboard Preview](screenshots/overview.png)

---

## Fitur Utama

| Fitur | Deskripsi |
|---|---|
| **Tren & Overview** | Visualisasi tren penjualan bulanan, sales per region, komposisi kategori |
| **Produk Terlaris** | Ranking produk berdasarkan sales, profit, atau quantity |
| **Segmentasi Customer** | Pengelompokan pelanggan otomatis menggunakan RFM Analysis + K-Means Clustering |
| **Forecasting** | Prediksi penjualan 1–6 bulan ke depan dengan Holt-Winters Exponential Smoothing |
| **Market Basket Analysis** | Deteksi produk yang sering dibeli bersamaan |
| **Peta Sebaran** | Choropleth map sales & profit margin per state |
| **Dampak Diskon** | Analisis korelasi antara diskon dan profit margin |
| **Filter Interaktif** | Filter dinamis berdasarkan tanggal, region, kategori, dan segmen pelanggan |

---

## Algoritma & Teknik yang Digunakan

| Algoritma | Fungsi | Library |
|---|---|---|
| **RFM Analysis** | Menilai pelanggan dari Recency, Frequency, Monetary | pandas |
| **K-Means Clustering** | Segmentasi pelanggan otomatis ke 4 kelompok nilai | scikit-learn |
| **StandardScaler** | Standarisasi skala fitur sebelum clustering | scikit-learn |
| **Holt-Winters Exponential Smoothing** | Forecasting penjualan dengan tren + seasonality | statsmodels |
| **Market Basket Analysis** | Analisis co-occurrence produk dalam transaksi | itertools |
| **Korelasi Pearson** | Mengukur hubungan diskon terhadap profit margin | numpy/pandas |

---

## Tech Stack

- **Frontend & Dashboard:** [Streamlit](https://streamlit.io/)
- **Data Processing:** Pandas, NumPy
- **Machine Learning:** Scikit-learn, Statsmodels
- **Visualisasi:** Plotly Express
- **Bahasa:** Python 3.12

---

## Struktur Project

```
dashboard-penjualan/
├── app.py                  # Entry point dashboard Streamlit
├── requirements.txt        # Daftar dependencies
├── .streamlit/
│   └── config.toml         # Konfigurasi tema
├── data/
│   └── Sample_-_Superstore.csv
└── utils/
    ├── data_loader.py      # Load & cleaning data
    └── analysis.py         # Algoritma analisis (RFM, K-Means, Forecasting, dll)
```

---

## Cara Menjalankan di Lokal

1. **Clone repository**
   ```bash
   git clone https://github.com/USERNAME/dashboard-penjualan.git
   cd dashboard-penjualan
   ```

2. **Buat virtual environment** (opsional tapi disarankan)
   ```bash
   python -m venv venv
   source venv/bin/activate    # Mac/Linux
   venv\Scripts\activate       # Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Jalankan dashboard**
   ```bash
   streamlit run app.py
   ```

5. Buka browser ke `http://localhost:8501`

---

## Dataset

Sumber: [Kaggle — Superstore Sales Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

9.994 baris transaksi retail periode 2014–2017, dengan atribut seperti Order Date, Customer, Region, Category, Sales, Profit, Discount, dan Quantity.

---

## Insight Utama dari Analisis

- Penjualan menunjukkan pola musiman yang konsisten, dengan lonjakan signifikan setiap kuartal 4 (akhir tahun)
- Segmentasi K-Means berhasil mengidentifikasi 4 kelompok pelanggan dengan karakteristik berbeda — termasuk 8% pelanggan *High Value* yang menyumbang revenue signifikan
- Ditemukan korelasi negatif sangat kuat (**r = -0.86**) antara diskon dan profit margin — diskon di atas 20% rata-rata membuat transaksi merugi
- Beberapa state dengan total sales tinggi justru memiliki profit margin negatif, mengindikasikan kebijakan diskon yang perlu dievaluasi

---

## Pengembangan Selanjutnya

- [ ] Autentikasi multi-seller
- [ ] Model forecasting lanjutan (Prophet/LSTM)
- [ ] Export laporan otomatis ke PDF/Excel
- [ ] Market basket analysis dengan algoritma Apriori/FP-Growth

---

## Author

**Falda**
Project ini dibuat sebagai tugas akhir mata kuliah **Algoritma & Data Science**.

---

## Lisensi

Project ini dibuat untuk tujuan pembelajaran/akademik.
