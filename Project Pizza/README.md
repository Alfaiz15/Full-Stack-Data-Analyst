# 🍕 Data-Driven Operations: Analisis Kinerja Penjualan Pizza (2015)

## 📌 Ringkasan Eksekutif

Proyek ini menyajikan analisis komprehensif atas data transaksi penjualan pizza selama setahun (2015) untuk mengidentifikasi *Key Performance Indicators* (KPI) operasional dan peluang peningkatan Revenue. Seluruh analisis dilakukan menggunakan fitur-fitur canggih pada **Microsoft Excel/Google Sheets**, dan hasilnya dirangkum dalam *Dashboard* Interaktif untuk mendukung keputusan strategis pada aspek *Forecasting*, *Inventaris*, dan *Pricing*.

**Fokus Analisis:** Optimasi Operasi dan Wawasan Data Bisnis.

## 🎯 Tujuan Utama (Business Questions)

Analisis ini secara spesifik bertujuan menjawab pertanyaan-pertanyaan kunci yang diajukan oleh Tim Manajemen (lihat `Data Pizza.xlsx - Question.csv`):

1.  Berapa Total Revenue, Total Order, dan **Average Order Value (AOV)**?
2.  Bagaimana tren pendapatan bulanan (*Seasonality*)?
3.  Apa saja **10 Pizza Terlaris** (*Top Sellers*) berdasarkan kuantitas?
4.  Bagaimana kontribusi Revenue berdasarkan **Kategori** dan **Ukuran** pizza?

## 🛠️ Tools dan Data

* **Primary Tool:** Microsoft Excel / Google Sheets
* **Data Source:** `Data Pizza.xlsx - Raw Data Pizza Sales.csv` (Data Transaksi Harian)
* **Output:** Dashboard Interaktif (`Dashboard.csv`) dan Pivot Table (`Pivot Table.csv`).

## ⚙️ Workflow Analisis Data (Excel/Sheets Focused)

### Fase 1: Data Cleansing & Feature Engineering

Menciptakan kolom-kolom baru (`Feature Engineering`) untuk memungkinkan agregasi dan analisis mendalam.

| Kolom Baru | Perhitungan | Fungsi Excel Kunci | Tujuan Operasional |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | Harga x Kuantitas | **`= unit_price * quantity`** | Menghitung total penjualan per item. |
| **Nama Bulan** | Ekstraksi Bulan dari tanggal. | **`=TEXT(order_date, "mmmm")`** | Analisis Tren & Forecasting. |
| **Nama Hari** | Ekstraksi Hari dari tanggal. | **`=TEXT(order_date, "dddd")`** | Analisis *Workload* dan Jadwal Staf. |
| **Total Order Unik** | Agregasi ID pesanan unik. | **`=COUNTA(UNIQUE(order_id_column))`** | Menghitung beban kerja operasional sebenarnya. |

### Fase 2: Pivot Table dan Agregasi (Inti Analisis)

Menggunakan fitur **Pivot Table** untuk merangkum 49.574 baris data menjadi wawasan yang terstruktur.

1.  **KPI Global:** Menghitung **Total Revenue** (`SUM`), **Total Order** (`COUNT UNIQUE`), dan **AOV** ($\frac{\text{Total Revenue}}{\text{Total Order}}$).
2.  **Tren Pendapatan:** **Rows:** `Nama Bulan`, **Values:** `SUM of Total Revenue`.
3.  **Top 10 Sellers:** **Rows:** `pizza_name`, **Values:** `SUM of quantity` (Menggunakan **Value Filter: Top 10**).
4.  **Revenue Segmentasi:** **Rows:** `pizza_category`, **Columns:** `pizza_size`, **Values:** `SUM of Total Revenue`.

### Fase 3: Dashboard Visualisasi dan Interaktivitas

Membuat *Dashboard* yang ringkas dan kuat, dihubungkan langsung ke Pivot Table.

| Visualisasi | Tipe Chart | Wawasan yang Diperkuat |
| :--- | :--- | :--- |
| **Tren Revenue Bulanan** | Line Chart | Menunjukkan *Seasonality* yang kuat (**Puncak Juli**, **Lembah September**). |
| **Quantity by Category** | Donut Chart | Menetapkan prioritas bahan baku: **Classic (30%)** dan **Supreme (24%)** mendominasi volume. |
| **Revenue by Size** | Stacked Bar Chart | Menentukan strategi *Upselling*: Ukuran **Large (L)** adalah pendorong Revenue utama. |
| **Interaktivitas** | Slicer | Menghubungkan *Slicer* (`pizza_category`) ke semua *chart* untuk analisis *ad-hoc* (misalnya, menganalisis performa *hanya* kategori Chicken). |

## 💡 Key Insights dan Rekomendasi Strategis

Analisis data menghasilkan rekomendasi *actionable* yang menargetkan peningkatan efisiensi dan pendapatan:

| Insight | Rekomendasi Strategis (Operations & Revenue) |
| :--- | :--- |
| **Seasonality Kuat** | **Forecasting & Marketing:** Alokasikan anggaran promosi dan diskon untuk bulan **September** dan **November** (bulan lembah) untuk menstabilkan Revenue. |
| **Dominasi Produk** | **Operations Efficiency:** Lakukan studi waktu dan gerak (*Time & Motion Study*) pada resep **The Classic Deluxe Pizza** dan **The Barbecue Chicken Pizza** untuk mengurangi *preparation time* dan menghindari *bottleneck* dapur. |
| **AOV Potensial** | **Pricing Strategy:** Fokus pada *Upselling* ke ukuran **Large** dan membuat paket (*bundling*) yang strategis, karena ukuran L terbukti paling bernilai secara Revenue. |
| **Fokus Kategori** | **Inventory Management:** Tingkatkan *buffer stock* untuk bahan baku kategori **Classic** dan **Supreme** untuk mencegah *stock-out* pada periode *peak* bulanan (misalnya, Juli). |

---

### Lihat Dashboard dan Data Lengkap

* [**Dashboard Hasil Analisis**](link_ke_dashboard_google_sheets_atau_excel_online)
* [**Raw Data Pizza Sales**](Data%20Pizza.xlsx%20-%20Raw%20Data%20Pizza%20Sales.csv)
