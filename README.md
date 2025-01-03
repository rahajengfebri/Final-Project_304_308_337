# Final-Project_304_308_337

![image](https://github.com/user-attachments/assets/67e963e4-4995-4702-a06f-f73078fe48a3)
![image](https://github.com/user-attachments/assets/4e3306c2-6618-4be2-b528-f819aa16932f)



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

A. Apakah terdapat pola dalam preferensi pelanggan terhadap tipe hotel tertentu? Hotel mana yang lebih sering dipilih oleh pelanggan, apakah Resort Hotel atau City Hotel?

![download (1)](https://github.com/user-attachments/assets/2466f5b6-b5ab-4239-be00-af4bc7911ac1)

City Hotel lebih disukai oleh konsumen, terutama untuk perjalanan bisnis atau singkat, karena lokasinya yang strategis. Namun, Resort Hotel memiliki peluang untuk menarik lebih banyak konsumen selama musim liburan jika strategi pemasaran difokuskan pada pengalaman liburan yang menarik.


B. Pada bulan dan tanggal berapa puncak pemesanan hotel biasanya terjadi? Apakah terdapat musim tertentu yang memengaruhi tingkat pemesanan hotel?
![download (2)](https://github.com/user-attachments/assets/90d9ae0f-f810-40be-bdae-8827f6b9cb4c)

- Konsumen cenderung memilih hotel selama musim liburan, terutama pada bulan Juli, Agustus, dan Mei, yang merupakan waktu yang populer untuk berlibur di Eropa. Ini menunjukkan bahwa konsumen lebih sering melakukan pemesanan di periode tersebut.
- Banyak konsumen yang melakukan pemesanan hotel pada tanggal 5, antara 15-20, dan akhir bulan, yang kemungkinan besar terkait dengan pengaturan keuangan pribadi atau fleksibilitas jadwal kerja.



C. Paket makanan apa yang paling sering dipesan oleh pelanggan, dan bagaimana hotel dapat mengoptimalkan layanan berdasarkan preferensi tersebut?

![download (4)](https://github.com/user-attachments/assets/5aec5786-4e3c-40d5-8893-af0a120d643a)

Konsumen lebih cenderung memilih paket Bed and Breakfast (BB) karena menawarkan nilai lebih dan sesuai dengan kebutuhan mereka. Paket Half Board (HB) dan Special (SC) juga populer, namun konsumen lebih memilih paket dengan harga yang lebih kompetitif dan menu yang lebih sesuai dengan selera mereka.


D. Jenis pemesanan apa yang paling sering digunakan oleh pelanggan (Contract, Group, Transient, atau Transient-party), dan bagaimana distribusinya memengaruhi manajemen reservasi hotel?

![download (5)](https://github.com/user-attachments/assets/04221e5b-442c-4ab3-a598-5a05bec820a3)

Sebagian besar pemesanan berasal dari Transient (perjalanan individu atau keluarga kecil) yang menginginkan fleksibilitas dalam pemesanan. Konsumen dalam kategori Transient-Party juga populer, namun dengan jumlah lebih kecil, sementara Contract dan Group lebih jarang dipilih.


## Temuan Baru 
![download (6)](https://github.com/user-attachments/assets/6e21a17c-85f6-438e-848e-0f96e51929b8)

Dari hasil visualisasi diatas, dapat dilihat bahwa pemesanan paling banyak terjadi pada musim summer, khususnya pada bulan Juni, Juli, dan Agustus. Ini menunjukkan bahwa banyak tamu yang memilih untuk menginap di hotel selama liburan musim panas, yang biasanya bertepatan dengan liburan sekolah atau waktu-waktu liburan yang lebih panjang.

![download (7)](https://github.com/user-attachments/assets/c8118450-2453-439d-9525-a567af9c794b)

Berdasarkan grafik yang disajikan, hubungan antara lead time (jumlah hari antara tanggal pemesanan masuk ke sistem dan tanggal kedatangan) dengan customer type dapat dianalisis sebagai berikut:

1. Customer Type "Contract"

Jumlah pemesanan tercatat sangat kecil untuk semua kategori lead time.
Hal ini menunjukkan bahwa pemesanan tipe kontrak kemungkinan besar tidak bergantung pada lead time, karena biasanya dilakukan dalam skema perjanjian jangka panjang antara pihak hotel dan perusahaan atau organisasi tertentu.

2. Customer Type "Group"

Pemesanan tipe ini juga sangat sedikit di semua kategori lead time.
Fenomena ini mengindikasikan bahwa tipe grup tidak mendominasi dalam dataset yang dianalisis. Pemesanan grup cenderung dilakukan untuk keperluan acara tertentu yang memiliki pola lead time yang berbeda.

3. Customer Type "Transient"

Jenis pelanggan ini mendominasi jumlah pemesanan, terutama pada kategori lead time:
31-100 Hari dan 101-365 Hari, dengan jumlah pemesanan tertinggi.
Pemesanan dalam kategori 0-7 Hari juga signifikan, mengindikasikan adanya kebutuhan mendadak atau pemesanan last-minute.
Pola ini menunjukkan bahwa pelanggan transient cenderung memesan jauh hari, namun sebagian kecil juga memesan mendekati tanggal kedatangan.

4. Customer Type "Transient-Party"

Pola pada kategori ini mirip dengan "Transient" tetapi dengan jumlah yang lebih kecil.
Kategori lead time yang mendominasi tetap berada di rentang 31-100 Hari dan 101-365 Hari, dengan pemesanan dalam kategori lead time lebih pendek seperti 0-7 Hari yang lebih jarang.

**Kesimpulan**

- Pelanggan Transient merupakan kelompok dominan dalam data ini, dengan lead time yang bervariasi tetapi cenderung memesan jauh hari (31-365 hari).
- Pelanggan dengan tipe Contract dan Group memiliki jumlah pemesanan yang jauh lebih kecil, sehingga tidak terlalu terpengaruh oleh faktor lead time.
- Lead time menjadi indikator penting dalam memprediksi kebutuhan kamar hotel, khususnya untuk pelanggan transient, sehingga dapat digunakan untuk menyusun strategi pemasaran yang lebih efektif.


**Kesimpulan secara Menyeluruh** :
Berdasarkan hasil analisis yang kami lakukan, kami menyimpulkan bahwa hotel ini memiliki rating sedang, karena masih ada lumayan banyak tamu yang tidak memesan kembali. Hal ini bisa menjadi indikasi adanya ketidakpuasan dari tamu atau adanya aspek-aspek tertentu yang perlu diperbaiki dalam layanan yang diberikan. Kemungkinan penyebabnya adalah layanan yang kurang memadai, seperti fasilitas yang tidak sesuai harapan atau pelayanan yang tidak memuaskan. Selain itu, kurangnya strategi pemasaran yang efektif untuk menarik tamu lama kembali juga bisa menjadi faktor. Hotel mungkin belum memiliki program khusus seperti loyalty program atau penawaran spesial yang dapat memberikan insentif bagi tamu yang sudah pernah menginap. Oleh karena itu, penting bagi hotel untuk meningkatkan kualitas layanan dan menciptakan penawaran yang menarik untuk tamu lama agar mereka tertarik untuk menginap kembali.










