# **Hotel Booking Cancellation Prediction**

**Anggota Kelompok**
1. Muhamad Fajri
2. Dewi Sartika Candra
3. Aldira Putri Damayanti

## **Business Context**
Kebutuhan masyarakat akan akomodasi yang nyaman saat bepergian membuat industri perhotelan terus berkembang. Dua jenis hotel yang paling sering dibandingkan berdasarkan lokasi dan target pasarnya adalah Resort Hotel dan City Hotel.
- **Resort Hotel** biasanya terletak di daerah wisata dan mengutamakan pengalaman menginap yang santai serta fasilitas rekreasi.
- **City Hotel** berada di pusat kota dan sering digunakan oleh wisatawan bisnis atau tamu yang membutuhkan akses mudah ke transportasi dan pusat bisnis.

Namun, tren perjalanan saat ini menunjukkan bahwa banyak orang menginginkan kombinasi antara bisnis dan rekreasi [bleisure travel](https://blog.hotelogix.com/business-leisure-travel-trends/), yang membuat city hotel perlu menyesuaikan fasilitasi mereka agar lebih menarik bagi wisatawan.
Di tengah upaya menarik pelanggan, salah satu tantangan terbesar yang dihadapi city hotel yaitu **pembatalan reservasi yang cukup tinggi (42,72%)**. Hal ini berdampak langsung pada pendapatan dan efisiensi operasional hotel.

Pembatalan reservasi yang tinggi menyebabkan:
- **Kerugian finansial**, terutama jika kamar yang dibatalkan tidak dapat terisi kembali.
- **Ketidakseimbangan dalam alokasi sumber daya**, seperti pengelolaan staf dan persediaan logistik.
- **Dampak operasional pada layanan non-kamar**, seperti katering, layanan kebersihan, dan aktivitas wisata.

## **Business Problem**
- City Hotel menghadapi persaingan ketat dalam menarik pelanggan, terutama dengan munculnya tren **bleisure travel**, di mana wisatawan menggabungkan perjalanan bisnis dengan rekreasi. Untuk tetap kompetitif, City Hotel perlu menyesuaikan fasilitas dan layanan mereka agar lebih relevan dengan kebutuhan pelanggan masa kini.
- Namun, salah satu tantangan terbesar dalam mencapai tujuan ini adalah **tingkat pembatalan reservasi yang tinggi**, yang berdampak langsung pada pendapatan dan efisiensi operasional. Jika hotel tidak memahami faktor utama yang menyebabkan pembatalan, mereka akan kesulitan dalam menyusun strategi untuk menarik dan mempertahankan pelanggan, termasuk bleisure traveler.

**Stakeholder yang terlibat:**
1. **Manajemen Hotel**
    - Bertanggung jawab atas strategi keseluruhan hotel, termasuk kebijakan harga, kebijakan pembatalan, dan pengelolaan sumber daya.
    - Memerlukan wawasan dari analisis data untuk mengambil keputusan yang dapat meningkatkan tingkat okupansi dan mengurangi dampak finansial dari pembatalan.
2. **Customer Service (CS) & Reservasi**
    - Berinteraksi langsung dengan tamu, menangani pemesanan dan pembatalan reservasi.
    - Memerlukan informasi mengenai alasan umum pembatalan untuk meningkatkan pelayanan dan memberikan solusi yang lebih baik kepada pelanggan.
3. **Tim Pemasaran**
    - Bertanggung jawab atas strategi promosi dan branding hotel, termasuk menarik segmen bleisure travelers.
    - Memerlukan insight dari analisis pembatalan untuk menyesuaikan kampanye pemasaran dan mengurangi kemungkinan pelanggan membatalkan reservasi.

## **Goals**
Tujuan dari prediksi pembatalan reservasi adalah untuk membantu hotel mengurangi dampak negatif pembatalan dan meningkatkan efisiensi operasional melalui pendekatan berbasis data. Secara spesifik, tujuan utama dari analisis ini adalah:
- **Membangun model prediksi** yang dapat mengidentifikasi pelanggan yang berpotensi membatalkan reservasi sebelum tanggal check-in.
- **Menganalisis faktor-faktor utama** yang berkontribusi terhadap pembatalan reservasi, seperti metode pembayaran, durasi menginap, musim perjalanan, dan harga.
- **Memberikan rekomendasi strategis** untuk mengurangi pembatalan, penyesuaian kebijakan pembatalan, atau strategi pemasaran yang lebih efektif.
- **Meningkatkan akurasi dalam pengelolaan reservasi** untuk meminimalkan kamar kosong dan mengoptimalkan pendapatan hotel.
Dengan model prediksi ini, hotel dapat mengoptimalkan strategi bisnisnya, meningkatkan efisiensi operasional, serta mengurangi risiko pembatalan secara signifikan.

## **Analytic Approach**
Jadi yang akan kita lakukan adalah **menganalisa data untuk menemukan pola yang membedakan pelanggan yang membatalkan reservasi dan yang tidak**. Kemudian, kita akan membangun **model klasifikasi** yang akan membantu **City Hotel memprediksi probabilitas seorang tamu akan membatalkan reservasi atau tidak**. Dengan model ini, hotel dapat mengambil langkah-langkah preventif untuk mengurangi pembatalan, seperti menyesuaikan kebijakan harga, memberikan insentif bagi pelanggan tertentu, atau meningkatkan strategi pemasaran yang lebih efektif.

## **Metric Evaluation**
Untuk mengurangi pembatalan hotel, hasil akhir model dibagi menjadi dua kategori berikut:

Target:

    0: Tidak cancel
    1: Cancel

| Aktual / Prediksi | Negatif (Tidak Cancel) | Positif (Cancel) |
| --- | --- | --- |
| Negatif (Tidak Cancel) | Aktual tidak cancel, Prediksi tidak cancel (TN)  | Aktual tidak cancel, Prediksi cancel (FP) |
| Positif (Cancel) | Aktual cancel, Prediksi tidak cancel (FN) | Aktual Cancel, Prediksi Cancel (TP) |

**False Negative: Kamarnya jadi kosong tidak tersewa**
- Model gagal mendeteksi bahwa tamu akan membatalkan reservasi, **sehingga hotel tidak bisa mengantisipasi pembatalan ini**.
- Akibatnya, kamar tersebut tidak dapat dipesan oleh pelanggan lain, sehingga **hotel kehilangan pendapatan**.

**False Positif: Kamar diberikan ke tamu lain, padahal pelanggan asli tetap datang**
- Model salah memprediksi bahwa tamu akan membatalkan, padahal sebenarnya mereka tetap datang.
- Jika hotel menerapkan strategi **overbooking**, ini bisa menyebabkan **kekurangan kamar**, dan tamu yang datang malah tidak mendapatkan kamar yang dipesan.

## **Business Calculation**

## **Kesimpulan**

## **Rekomendasi**

---
