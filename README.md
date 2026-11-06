# 🛒 Performance Testing — Sociolla Web (E-Commerce Flow)

Dokumen dan repositori ini disusun untuk memenuhi **Tugas Praktikum Performance Testing** pada mata kuliah *Software Testing & Quality Assurance*. Repositori ini berisi rancangan *Test Plan*, kumpulan *Test Script* Apache JMeter, hasil data eksekusi, serta analisis performa pada 5 alur utama transaksi Web Sociolla.

---

## 👥 Kelompok & Pembagian Tugas

| NIM | Nama | Alur Scripting (JMeter) | 
| :--- | :--- | :--- | :--- |
| 2310512079 | Callysta Cendikia Diba Putri | Alur 1 (Login) & Alur 2 (Search) + *Master Integration* |
| 2310512158 | Muhammad Okto Syaifudi | Alur 3 (Cart) | 
| 2310512071 | Shabrina Rahmania | Alur 4 (Checkout) |
| 2310512088 | Muhammad Rafi Pramana | Alur 5 (Payment) |

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
