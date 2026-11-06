# 🛒 Performance Testing — Sociolla Web (E-Commerce Flow)

Dokumen dan repositori ini disusun untuk memenuhi **Tugas Praktikum Performance Testing** pada mata kuliah *Software Testing & Quality Assurance*. Repositori ini berisi rancangan *Test Plan*, kumpulan *Test Script* Apache JMeter, hasil data eksekusi, serta analisis performa pada 5 alur utama transaksi Web Sociolla.

---

## 👥 Kelompok & Pembagian Tugas

- 2310512079  Callysta Cendikia Diba Putri -> Alur 1 (Login) & Alur 2 (Search) + Master Integration
- 2310512158  Muhammad Okto Syaifudi -> Alur 3 (Cart) 
- 2310512071  Shabrina Rahmania -> Alur 4 (Checkout) 
- 2310512088  Muhammad Rafi Pramana -> Alur 5 (Payment) 

---

## 🎯 Target & Ruang Lingkup Pengujian

Pengujian difokuskan pada 5 alur transaksi belanja bertahap:
1. **Login & Profile:** Authentikasi pengguna dan pemrosesan *session/token*.
2. **Pencarian Produk:** Penggunaan kata kunci pencarian, filter kategori, dan detail produk.
3. **Keranjang Belanja (Cart):** Penambahan item, pembaruan kuantitas, dan hapus produk.
4. **Checkout:** Pemilihan alamat pengiriman, opsi kurir, dan draf pesanan.
5. **Payment Gateway:** Simulasi konfirmasi dan transaksi pembayaran.

---

## 📁 Struktur Repositori

```text
├── .gitignore
├── README.md
├── scripts/
│   ├── individual/             # Script JMX per alur fitur
│   │   ├── 01_login.jmx
│   │   ├── 02_search.jmx
│   │   ├── 03_cart.jmx
│   │   ├── 04_checkout.jmx
│   │   └── 05_payment.jmx
│   └── master/                 # Script JMX gabungan (End-to-End Flow)
│       └── master_sociolla_flow.jmx
├── results/                    # Output data pengujian (.jtl / .csv)
│   ├── load_test_result.jtl
│   └── stress_test_result.jtl
└── screenshots/                # Bukti grafik performa (JMeter Aggregate / Graph)
    ├── load_test_graph.png
    └── stress_test_graph.png
```
## ⚙️ Persyaratan Lingkungan (Prerequisites)

- **Java Development Kit (JDK):** Version 11 or higher
- **Apache JMeter:** Version 5.6.3 (CLI / GUI)
- **OS:** Linux (Ubuntu / GitHub Codespaces) or Windows 10/11

---

## 🚀 Cara Menjalankan Script Pengujian (CLI Mode)

Jalankan perintah berikut di terminal Linux / GitHub Codespaces:

### 1. Eksekusi Load Testing (Beban Normal)
```bash
jmeter -n -t scripts/master/master_sociolla_flow.jmx -l results/load_test_result.jtl -e -o results/load_report_html
```
### 2. Eksekusi Stress Testing (Beban Ekstrem)
```bash
jmeter -n -t scripts/master/master_sociolla_flow.jmx -l results/stress_test_result.jtl -e -o results/stress_report_html
```
Catatan Etika: Pengujian ini dilakukan semata-mata untuk kebutuhan simulasi akademis dalam lingkungan pengujian yang aman (staging / dummy endpoints) dan tidak diarahkan ke server produksi tanpa izin eksplisit.
### 3. File `.gitignore` (Mencegah File Sampah Di-upload)

Buat file bernama `.gitignore` di *root directory* agar file *log* atau temporary JMeter tidak mengotori repositori:

```text
# JMeter Logs & Temp Files
*.log
jmeter.log
*.jtl.tmp

# OS / Editor Files
.DS_Store
.vscode/
.idea/

# Large Result Files (Optional if heavy)
results/*_report_html/
