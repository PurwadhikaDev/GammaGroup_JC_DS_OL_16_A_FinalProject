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

Bila seandainya biaya untuk reservasi kamar standard sebesar 100,42 Euro (Berdasarkan ADR kamar tipe standar yang paling murah) dan andaikan jumlah reservasi yang hotel dapatkan untuk suatu kurun waktu sebanyak 200 (dimana andaikan 100 Cancelled dan 100 tidak canceled), maka hitungannya kurang lebih seperti ini:

**1. Tanpa Model (Semua Reservasi Diproses Seperti Biasa)**

Jika tidak ada model prediksi, maka semua reservasi akan diproses tanpa mempertimbangkan kemungkinan pembatalan.
-	Pendapatan Potensial (Jika semua menginap)
200 x 100,42 = 20.084 euro
-	Kerugian Akibat Pembatalan
100 x 100,42 = 10.042 euro
-	Pendapatan Aktual setelah Pembatalan
20.084 – 10.042 = 10.042 euro
Tanpa model, kerugian akibat pembatalan mencapai 10.042 euro 

**2. Dengan Model Prediksi Pembatalan**
-	Recall canceled 72%, maka model dapat mengidentifikasi 72% dari 100 reservasi yang akan dibatalkan (72 reservasi).
-	Recall untuk non-canceled 76%, maka Model dapat mengidentifikasi 76% dari 100 reservasi yang benar-benar tidak akan dibatalkan (76 reservasi).
-	False positive (reservasi yang sebenarnya tidak dibatalkan tetapi diprediksi akan dibatalkan) = 24% (24 reservasi).
-	False negative (reservasi yang sebenarnya dibatalkan tetapi diprediksi tidak akan dibatalkan) = 28% (28 reservasi).

**3. Prediksi model**

**1. Reservasi yang diprediksi akan dibatalkan (Positif model)**

72% x 100 = 72 Reservasi
-	Apabila hotel bisa menawarkan promosi (misal diskon atau fleksibilitas re-schedule) untuk mengurangi pembatalan dan berhasil mempertahankan 30% pelanggan, maka: 30% x 72 = 22 reservasi tetap menginap
-	Pendapatan tambahan dari pelanggan yang tetap meinginap: 22 x 100,42 = 2.209,24 euro

**2. Reservasi yang salah diprediksi (Actual tidak canceled, prediksi canceled) (False positive)**

24% x 100 = 24 reservasi

**3. Reservasi yang salah diprediksi (Actual Canceled, prediksi tidak canceled) (False negative)**

29% x 100 = 29 reservasi
-	Pendapatan yang hilang akibat pembatalan ini: 28 x 100,42 = 2.811,76 euro

**4. Pendapatan setelah menggunakan model**
-	Pendapatan dari reservasi non-canceled tetap: 100 x 100,42 = 10,042 euro
-	Pendapatan tambahan dari reservasi yang berhasil di selamatkan: 2.209,24 euro
-	Total pendapatan setelah strategi mitigasi: 10.042 + 2.209,24 = 12.219,282 euro
-	Kerugian akibat false negatives yang tidak dapat diselamatkan: 2.811,76 euro

## **Kesimpulan**
-	Tanpa model, pendapatan 10.042 euro, dengan kerugian 10.042 euro akibat pembatalan.
-	Dengan model, pendapatan meningkat menjadi 12.219,282 euro, karena model memungkinkan hotel mempertahankan 22 reservasi yang seharusnya dibatalkan.
-	Penghematan sebesar 2.209,24 euro dengan strategi mitigasi berdasarkan prediksi model.
-	Model masih memiliki false negatives, yang menyebabkan kerugian 2.811,76 euro.

## **Rekomendasi**
### **Rekomendasi Model**

Untuk dapat meningkatkan recall, dapat dilakukan:
-	**Kumpulkan lebih banyak data**, Khususnya dalam kasus ketidakseimbangan target, sebaiknya jumlah data pemesanan yang dibatalkan lebih seimbang dengan data pemesanan yang tidak dibatalkan, jika memungkinkan.
-	**Penyesuaian threshold prediksi (misalnya menurunkan dari 0.5 ke 0.4).**
-	**Menggunakan model balancing lain seperti focal loss atau cost-sensitive learning.**
-	**Melakukan hyperparameter tuning lebih lanjut untuk meningkatkan recall.**

### **Rekomendasi Bisnis**
- Membuat kebijakan untuk pemberian voucher pada tamu dengan lead time lebih dari 25 hari.
- Membuat kebijakan baru untuk harga kamar saat high season dan low season.
- Pembuatan kesepakatan baru terkait deposit dengan TA/TO serta GDS. 
- Memastikan kelengkapan informasi mengenai fasilitas, layanan, dan keunggulan hotel di website.
- Menetapkan syarat pembatalan untuk reservasi, dimana tamu wajib memberikan review atau alasan pembatalan.
- Menetapkan kebijakan baru untuk biaya deposit saat memesan langsung pada pihak hotel (Melalui Website resmi hotel maupun datang secara langsung ke hotel).
- Menggunakan model machine learning yang telah dibuat sebagai solusi untuk menentukan strategi pemasaran yang tepat sasaran.

### **Link Tautan**
- Link streamlit : https://finalprojectgamma.streamlit.app/
- Link tableau : https://public.tableau.com/app/profile/aldira.putri.damayanti/viz/FinalProjectGamma/Dashboard1
  ![Image](https://github.com/user-attachments/assets/60153b5f-f25c-48b9-a585-153c8a1b1adc)
