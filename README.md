# Final-Project_304_308_337

![image](https://github.com/user-attachments/assets/ef8b9eda-a9b8-4e41-95a9-93169a15708b)

**1. Pendahuluan**

**A. Dataset**
Dataset ini berisi informasi tentang reservasi hotel dengan total 119.390 entri dan 32 kolom yang mencakup berbagai aspek terkait pemesanan. Dataset ini mencatat dua jenis hotel, yaitu Resort Hotel dan City Hotel, serta status apakah reservasi dibatalkan (is_canceled). Informasi penting lainnya mencakup waktu antara pemesanan dan kedatangan tamu (lead_time), tanggal kedatangan seperti tahun (arrival_date_year), bulan (arrival_date_month), dan nomor minggu kedatangan (arrival_date_week_number). Jumlah malam menginap di akhir pekan (stays_in_weekend_nights) dan hari kerja (stays_in_week_nights) juga tercatat, bersama dengan jumlah orang dewasa (adults), anak-anak (children), dan bayi (babies) yang termasuk dalam reservasi.

Selain itu, dataset ini mencakup informasi seperti paket makanan yang dipesan (meal), negara asal tamu (country), dan segmen pasar dari mana tamu berasal (market_segment). Data juga mencatat apakah tamu merupakan pelanggan berulang (is_repeated_guest), tipe kamar yang dipesan (reserved_room_type), tipe kamar yang diberikan (assigned_room_type), serta pendapatan harian rata-rata hotel (Average Daily Rate atau adr). Status reservasi (reservation_status) dan tanggal status tersebut diperbarui terakhir kali (reservation_status_date) turut disertakan.

Namun, dataset ini memiliki beberapa nilai yang hilang pada kolom seperti jumlah anak-anak (children), agen pemesanan (agent), dan perusahaan (company). Terutama, data perusahaan hanya terisi pada sekitar 6.797 entri dari total 119.390 entri.

**B. Problem Question**
1. Apakah terdapat pola dalam preferensi pelanggan terhadap tipe hotel tertentu? Hotel mana yang lebih sering dipilih oleh pelanggan, apakah Resort Hotel atau City Hotel?
2. Pada bulan dan tanggal berapa puncak pemesanan hotel biasanya terjadi? Apakah terdapat musim tertentu yang memengaruhi tingkat pemesanan hotel?
3. Paket makanan apa yang paling sering dipesan oleh pelanggan, dan bagaimana hotel dapat mengoptimalkan layanan berdasarkan preferensi tersebut?
4. Jenis pemesanan apa yang paling sering digunakan oleh pelanggan (Contract, Group, Transient, atau Transient-party), dan bagaimana distribusinya memengaruhi manajemen reservasi hotel?


**C. Wawasan yang strategis kepada seorang manajer hotel**

Dapat mengembangkan layanan untuk semua pelanggan.
Merancang Strategi pemasaran yang lebih baik.
Memaksimalkan operasional hotel ketika jumlah pelanggan meningkat tajam.

**D. Manfaat Analisis bagi Konsumen**

1. Meningkatkan kualitas layanan hotel, sehingga pelanggan akan merasa lebih puas dan nyaman.
2. Membangun hubungan yang lebih baik dengan pelanggan untuk menciptakan pengalaman yang positif dan mendorong pelanggan untuk tetap memilih hotel tersebut di masa mendatang.

**2. Analisis Data**

**A. Variabel-variabel berikut untuk dianalisis**
1. Hotel (Jenis hotel yang dipesan).
2. Arrival Date (Month dan Day of Month).
3. Meal (Jenis paket makanan yang dipesan).
4. is_repeated_guest (Pelanggan yang pernah memesan sebelumnya).
5. Customer Type (Jenis pemesanan pelanggan).

**B. Metodologi yang Digunakan**
1. Menangani Missing Value
2. Exploratory Data Analysis (EDA) yaitu mengidentifikasi pola dan tren untuk memahami perilaku pelanggan.
3. Analisis Waktu yaitu menggunakan variabel arrival_date_month dan arrival_date_day_of_month untuk menentukan bulan dan tanggal dengan jumlah pemesanan terbanyak.
4. Menyusun wawasan dari analisis yang dilakukan.


**3. Hasil Analisis**



A.    ![download (1)](https://github.com/user-attachments/assets/2466f5b6-b5ab-4239-be00-af4bc7911ac1)
Distribusi Pemesanan Berdasarkan Tipe Hotel: Jumlah pemesanan untuk City Hotel mencapai 79.330, sedangkan Resort Hotel hanya 40.060. Perbedaan signifikan ini menunjukkan bahwa City Hotel lebih populer, kemungkinan karena lokasinya yang lebih strategis untuk perjalanan bisnis dan singkat, sementara Resort Hotel lebih jarang dipilih, yang umumnya dipilih untuk liburan yang lebih jarang dilakukan.

Pola Preferensi Pelanggan: Pelanggan lebih sering memilih City Hotel, kemungkinan karena akses yang lebih mudah ke pusat bisnis. Resort Hotel lebih jarang dipilih, karena lebih cocok untuk liburan atau wisata, yang biasanya terjadi lebih jarang dibandingkan perjalanan bisnis.

Perbandingan Proporsi Pemesanan: Sekitar 66,5% dari total pemesanan memilih City Hotel, sementara 33,5% memilih Resort Hotel. Proporsi ini menunjukkan dominasi City Hotel sebagai pilihan utama pelanggan, yang lebih sering dipilih untuk keperluan perjalanan bisnis daripada liburan.

Implikasi Potensial: City Hotel memiliki peluang untuk terus menarik pelanggan yang fokus pada perjalanan bisnis, dengan memperkuat fasilitas yang mendukung kegiatan bisnis. Di sisi lain, Resort Hotel perlu mengevaluasi strategi pemasaran untuk meningkatkan pemesanan, terutama pada musim liburan atau akhir pekan, yang dapat meningkatkan kunjungan.

Kesimpulan: City Hotel menjadi pilihan utama pelanggan berdasarkan data pemesanan, sedangkan Resort Hotel memiliki potensi untuk berkembang lebih jauh jika strategi pemasaran lebih efektif, terutama pada musim liburan.


![download (2)](https://github.com/user-attachments/assets/90d9ae0f-f810-40be-bdae-8827f6b9cb4c)




![download (4)](https://github.com/user-attachments/assets/5aec5786-4e3c-40d5-8893-af0a120d643a)



![download (5)](https://github.com/user-attachments/assets/04221e5b-442c-4ab3-a598-5a05bec820a3)



![download (6)](https://github.com/user-attachments/assets/6e21a17c-85f6-438e-848e-0f96e51929b8)


![download (7)](https://github.com/user-attachments/assets/c8118450-2453-439d-9525-a567af9c794b)











