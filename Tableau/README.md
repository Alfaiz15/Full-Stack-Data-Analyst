# ✈️ Root Cause Analysis Keterlambatan Penerbangan: End-to-End Data Workflow (Excel - Tableau)

## 📌 Ringkasan Proyek (Project Executive Summary)

Proyek ini adalah studi kasus mendalam untuk mengidentifikasi **akar masalah (Root Causes)** di balik ribuan menit keterlambatan penerbangan. Menggunakan data historis, saya menerapkan *end-to-end data workflow* dari pembersihan data hingga visualisasi profesional, dengan tujuan memberikan *actionable insights* kepada tim **Operations** untuk meningkatkan kinerja ketepatan waktu (*On-Time Performance*).

## 🛠️ Tools dan Data

* **Data Acquisition & Engineering:** Microsoft Excel / Google Sheets
* **Visualisasi & Dashboarding:** Tableau Desktop
* **Data Source:** `Airline_Delay_Cause.csv` (Data bulanan penyebab keterlambatan).

---

## ⚙️ Fase 1: Data Cleansing & Feature Engineering (Excel Focus)

Fase ini berfokus pada transformasi data mentah menjadi metrik yang siap dianalisis.

| Tugas | Tujuan Operasional | Metrik Kunci (Rumus Excel/Sheets) |
| :--- | :--- | :--- |
| **Data Integrity Check** | Memastikan keseragaman entitas (nama bandara, maskapai). | `TRIM()`, `UNIQUE()`, `Data > Remove Duplicates` |
| **Total Delay** | Menghitung total waktu tunda per baris (menit). | `= SUM(carrier_delay, weather_delay, ...)` |
| **Kontribusi Penyebab** | Mengukur *share* setiap faktor (*Carrier*, *Weather*, *NAS*) dalam total delay. | `= [carrier_delay] / [Total Delay]` |
| **Pemisahan Tanggal** | Menggabungkan kolom tahun dan bulan menjadi satu metrik waktu. | `=DATE(year, month, 1)` |

---

## 📊 Fase 2: Analisis & Visualisasi Kunci (Pivot Table & Tableau)

### 2.1 Analisis Pivot Table (Excel)

Mengidentifikasi fokus analisis sebelum visualisasi.

* **KPI Utama:** Menghitung rata-rata *Total Waktu Delay* bulanan.
* **Root Cause Dominan:** Mengelompokkan `Total Delay` berdasarkan penyebab utama (**Carrier**, **Weather**, **NAS**).
* **Hotspot Operasional:** Mengurutkan bandara berdasarkan **SUM** `Total Waktu Delay` (*Top 10 Airport*).

### 2.2 Visualisasi Tableau

Visualisasi dirancang untuk mengkomunikasikan *bottleneck* operasional secara cepat.

| Visualisasi | Tipe Chart | Wawasan Operasional yang Ditampilkan |
| :--- | :--- | :--- |
| **Peta Keterlambatan** | **Geo-Spatial Map** | Menunjukkan lokasi bandara/negara bagian dengan *delay* tertinggi (Hotspot Operasional). |
| **Kontribusi Delay** | **Stacked Bar Chart** | Membandingkan persentase masalah **Internal** (*Carrier Delay*) vs **Eksternal** (*Weather/NAS Delay*). |
| **Tren Musiman** | **Line Chart** | Memantau perubahan *delay* total dari waktu ke waktu, terutama dampak *Weather Delay* pada bulan-bulan tertentu. |

---

## 💡 Key Insights & Rekomendasi Strategis

Analisis ini memberikan dasar bagi keputusan *Operations* yang tepat sasaran:

1.  **Jika Carrier Delay Tinggi:** Fokus perbaikan harus pada *internal operations* (jadwal *maintenance* dan manajemen kru).
2.  **Jika Weather/NAS Delay Tinggi:** Rekomendasikan penambahan *buffer time* yang strategis pada rute dan bulan yang paling terdampak untuk mitigasi risiko.
3.  **Targeted Improvement:** Daftar 10 bandara teratas menjadi target prioritas untuk *review* alur kerja dan koordinasi *Air Traffic Control*.

---

**Apakah Anda ingin saya memberikan detail lebih lanjut pada salah satu fase di atas (misalnya, membuat contoh data *dummy* untuk Excel)?**
