# 🍽️ RestoServe - Waiter POS & Restaurant Floor Management System

Aplikasi web front-end untuk sistem operasional pelayan (*waiter*), manajemen denah meja 2 lantai (*top-down blueprint layout*), pelacakan durasi pesanan (*order timer & late alert*), serta katalog informasi komposisi bahan dan alergen makanan.

Proyek ini dibangun tanpa dependensi *framework* rumit (Vanilla HTML, CSS, JavaScript) dan dioptimalkan untuk diakses melalui peramban web maupun di-hosting langsung via **GitHub Pages**.

---

## 📌 Fitur Utama

### 1. Visual Floor Management (Top-Down Blueprint)
- **Denah 2 Lantai**:
  - **Lantai 1**: Area kasir/POS, bar minuman, pintu masuk utama, tangga, dapur/pickup window, serta variasi meja 2-kursi, 4-kursi, 6-kursi, dan bilik sofa (*booth*).
  - **Lantai 2**: Area ruang makan tertutup (*VIP Room A & B*), tangga turun, toilet, dan area balkon luar terbuka (*smoking area*).
- **Auto-Scaling Canvas Engine**: Menggunakan kanvas virtual beresolusi tetap ($800 \times 600\text{ px}$) dengan perhitungan transformasi skala adaptif. Tata letak denah, bentuk meja, dan elemen dinding tidak bergeser atau rusak saat browser diubah ke mode layar penuh (*full screen*), setengah layar (*split screen*), ataupun orientasi *portrait*.

### 2. Status & Order Timer Tracking
- **Indikator Status Meja**:
  - 🟢 **Kosong (Available)**: Meja siap digunakan tamu baru.
  - 🟡 **Menunggu (Waiting)**: Pesanan telah dikirim ke dapur dan stopwatch waktu tunggu aktif.
  - 🔴 **Telat (Late Alert)**: Indikator visual merah berkedip otomatis aktif jika durasi tunggu melebihi batas toleransi ($\ge 15$ menit).
  - 🔵 **Disajikan (Served)**: Makanan sudah diantar ke meja tamu.
- **Badge Notifikasi Meja Telat**: Penghitung global di bagian bilah atas (*topbar*) untuk memantau jumlah pesanan yang melebihi batas waktu pelayanan secara *real-time*.

### 3. Panel Pemesanan Cepat & Fleksibilitas Navigasi
- Pemilihan meja fleksibel: dapat langsung diklik pada denah arsitektur visual atau dipilih melalui menu *dropdown* dan tombol navigasi panah berurutan ($\leftarrow$ / $\rightarrow$).
- Keranjang pemesanan instan per meja dengan kontrol kuantitas dan kalkulasi total tagihan otomatis.
- Alur kerja status terstruktur: **Kirim ke Dapur** $\rightarrow$ **Makanan Disajikan** $\rightarrow$ **Kosongkan Meja**.

### 4. Panduan Komposisi Menu & Alergen (`menu.html`)
- Katalog hidangan lengkap dengan foto/ikon, harga, serta deskripsi rasa.
- Rincian komposisi bahan utama makanan (*ingredients*).
- Label peringatan alergen visual (*Gluten, Dairy, Egg, Soy, Peanuts, dsb.*).
- Fitur pencarian cerdas berbasis nama masakan maupun bahan tertentu (misal: mencari kata *"susu"* atau *"gluten"*).

---

## 🗂️ Struktur Berkas Proyek

```text
├── index.html       # Antarmuka utama (Denah 2 lantai, auto-scaler, panel POS)
├── menu.html        # Katalog informasi menu, komposisi bahan, dan peringatan alergen
├── css/
│   └── style.css    # Lembar gaya global, desain blueprint, palet status, dan responsivitas
├── js/
│   └── main.js      # Logika state meja, stopwatch interval, katalog pesanan, dan penskalaan kanvas
└── README.md        # Dokumentasi teknis proyek dan panduan kolaborasi
