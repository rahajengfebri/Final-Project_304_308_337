# Final-Project_304_308_337

## Daftar Isi
1. [Pendahuluan](#1--pendahuluan)
   1. [Latar Belakang Masalah](#latar-belakang-masalah)
   2. [Data dan Metodologi yang Digunakan](#data-dan-metodologi-yang-digunakan)
      
## Hotel Booking 
![image](https://github.com/user-attachments/assets/4e3306c2-6618-4be2-b528-f819aa16932f)

## 1. 📚 **Pendahuluan**  
### 1.1. 📝 **Latar Belakang Masalah**
Industri perhotelan terus berkembang dengan cepat, dan pemahaman yang mendalam mengenai perilaku pelanggan sangat penting dalam merancang strategi yang tepat. Laporan ini menyajikan analisis data pemesanan hotel untuk mengidentifikasi pola yang dapat membantu hotel dalam meningkatkan operasional dan layanan mereka.

Pernyataan masalah utama yang dibahas meliputi:

1. Pola Preferensi Pelanggan
Menganalisis preferensi pelanggan dalam memilih tipe hotel (Resort atau City Hotel) untuk membantu hotel menyusun strategi pemasaran yang lebih tepat dan terarah.

2. Puncak Pemesanan dan Pengaruh Musim pada Pemesanan
Mengidentifikasi waktu puncak pemesanan berdasarkan bulan dan tanggal, serta bagaimana musim memengaruhi tingkat pemesanan. Analisis ini membantu hotel dalam merencanakan kapasitas dan strategi promosi musiman secara lebih efisien.

3. Paket Makanan yang Paling Sering Dipesan
Mengidentifikasi paket makanan yang paling sering dipesan oleh pelanggan untuk memungkinkan hotel dalam mengoptimalkan penawaran makanan dan meningkatkan pengalaman pelanggan.

4. Jenis Pemesanan yang Paling Sering Digunakan
Menganalisis jenis pemesanan yang paling sering digunakan oleh pelanggan (Contract, Group, Transient, atau Transient-party), serta bagaimana hal ini mempengaruhi pengelolaan reservasi dan operasional hotel.

Dengan analisis mendalam terhadap data ini, laporan ini bertujuan untuk memberikan wawasan yang membantu hotel dalam merancang strategi pemasaran, mengelola sumber daya secara efisien, serta meningkatkan kepuasan pelanggan.

### 1.2. 📊 **Data dan Metodologi yang Digunakan**
#### **Dataset**

Dataset ini berisi informasi tentang reservasi hotel dengan total 119.390 entri dan 32 kolom yang mencakup berbagai aspek terkait pemesanan. 

| No | Variabel                        | Deskripsi                                                                                                                |
|----|---------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| 1  | hotel                           | Tipe hotel: H1 = Resort Hotel, H2 = City Hotel                                                                           |
| 2  | is_canceled                     | Indikator apakah pemesanan dibatalkan (1) atau tidak (0)                                                                 |
| 3  | lead_time                       | Jumlah hari antara tanggal pemesanan masuk ke sistem hotel (PMS) dan tanggal kedatangan                                  |
| 4  | arrival_date_year               | Tahun dari tanggal kedatangan                                                                                           |
| 5  | arrival_date_month              | Bulan dari tanggal kedatangan                                                                                           |
| 6  | arrival_date_week_number        | Nomor minggu dalam tahun untuk tanggal kedatangan                                                                       |
| 7  | arrival_date_day_of_month       | Hari dalam bulan dari tanggal kedatangan                                                                                |
| 8  | stays_in_weekend_nights         | Jumlah malam di akhir pekan (Sabtu/Minggu) yang dipesan                                                                 |
| 9  | stays_in_week_nights            | Jumlah malam di hari kerja (Senin-Jumat) yang dipesan                                                                   |
| 10 | adults                          | Jumlah orang dewasa dalam pemesanan                                                                                     |
| 11 | children                        | Jumlah anak-anak dalam pemesanan                                                                                        |
| 12 | babies                          | Jumlah bayi dalam pemesanan                                                                                             |
| 13 | meal                            | Paket makanan: Undefined/SC (tidak ada), BB (Bed & Breakfast), HB (Half board), FB (Full board)                         |
| 14 | country                         | Negara asal tamu dalam format ISO 3166-3                                                                                |
| 15 | market_segment                  | Segmentasi pasar untuk pemesanan: Agen Perjalanan (TA) atau Operator Tur (TO)                                           |
| 16 | distribution_channel            | Saluran distribusi untuk pemesanan                                                                                      |
| 17 | is_repeated_guest               | Indikator apakah tamu pernah memesan sebelumnya (1) atau tidak (0)                                                      |
| 18 | previous_cancellations          | Jumlah pemesanan sebelumnya yang dibatalkan                                                                             |
| 19 | previous_bookings_not_canceled  | Jumlah pemesanan sebelumnya yang tidak dibatalkan                                                                       |
| 20 | reserved_room_type              | Kode jenis kamar yang dipesan (anonim)                                                                                  |
| 21 | assigned_room_type              | Kode jenis kamar yang diberikan (bisa berbeda dari yang dipesan)                                                        |
| 22 | booking_changes                 | Jumlah perubahan pada pemesanan                                                                                         |
| 23 | deposit_type                    | Jenis deposit: No Deposit, Non Refund, Refundable                                                                       |
| 24 | agent                           | ID agen perjalanan yang membuat pemesanan                                                                               |
| 25 | company                         | ID perusahaan yang membuat atau membayar pemesanan                                                                      |
| 26 | days_in_waiting_list            | Jumlah hari pemesanan berada dalam daftar tunggu                                                                        |
| 27 | customer_type                   | Jenis pelanggan: Contract, Group, Transient, Transient-party                                                            |
| 28 | adr                             | Tarif harian rata-rata (Average Daily Rate)                                                                             |
| 29 | required_car_parking_spaces     | Jumlah tempat parkir yang diminta oleh tamu                                                                             |
| 30 | total_of_special_requests       | Jumlah permintaan khusus dari tamu                                                                                      |
| 31 | reservation_status              | Status pemesanan: Canceled, Check-Out, No-Show                                                                          |
| 32 | reservation_status_date         | Tanggal ketika status terakhir pemesanan ditetapkan                                                                     |

Namun, dataset ini memiliki beberapa nilai yang hilang pada kolom seperti jumlah anak-anak (children), agen pemesanan (agent), dan perusahaan (company). Terutama, data perusahaan hanya terisi pada sekitar 6.797 entri dari total 119.390 entri.

### 1.3 Teknik Analisis yang Diusulkan
#### **A. Variabel-variabel berikut untuk dianalisis**
1. Hotel (Jenis hotel yang dipesan).
2. Arrival Date (Month dan Day of Month).
3. Meal (Jenis paket makanan yang dipesan).
4. is_repeated_guest (Pelanggan yang pernah memesan sebelumnya).
5. Customer Type (Jenis pemesanan pelanggan).

#### **B. Metodologi yang Digunakan**
1. Menangani Missing Value
2. Exploratory Data Analysis (EDA) yaitu mengidentifikasi pola dan tren untuk memahami perilaku pelanggan.
3. Analisis Deskriptif untuk mengidentifikasi tren berdasarkan waktu, jenis pemesanan, dan preferensi pelanggan.

### 1.4 Manfaat Hasil Analisis
#### **Wawasan yang strategis kepada seorang manajer hotel**
1. Dapat mengembangkan layanan untuk semua pelanggan.
2. Merancang Strategi pemasaran yang lebih baik.
3. Memaksimalkan operasional hotel ketika jumlah pelanggan meningkat tajam.

### **Manfaat Analisis bagi Konsumen**

1. Meningkatkan kualitas layanan hotel, sehingga pelanggan akan merasa lebih puas dan nyaman.
2. Membangun hubungan yang lebih baik dengan pelanggan untuk menciptakan pengalaman yang positif dan mendorong pelanggan untuk tetap memilih hotel tersebut di masa mendatang.

### 3.1 Sumber Dataset
Data yang digunakan dalam analisis ini berasal dari kumpulan data permintaan pemesanan hotel yang dikumpulkan oleh Antonio, Almeida, dan Nunes pada tahun 2019. Berikut link dataset yang digunakan [(Dataset) ](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-02-11/readme.md)
#### Tujuan dataset
Tujuan awal data yaitu untuk menyediakan informasi tentang perilaku pelanggan dalam pemesanan hotel, termasuk pola pemesanan, jenis layanan yang dipilih, serta faktor-faktor yang memengaruhi keputusan pemesanan.

## **3. Hasil Analysis Problem Question**

### A. Apakah terdapat pola dalam preferensi pelanggan terhadap tipe hotel tertentu? Hotel mana yang lebih sering dipilih oleh pelanggan, apakah Resort Hotel atau City Hotel?

![download (1)](https://github.com/user-attachments/assets/2466f5b6-b5ab-4239-be00-af4bc7911ac1)

City Hotel lebih disukai oleh konsumen, terutama untuk perjalanan bisnis atau singkat, karena lokasinya yang strategis. Namun, Resort Hotel memiliki peluang untuk menarik lebih banyak konsumen selama musim liburan jika strategi pemasaran difokuskan pada pengalaman liburan yang menarik.

### B. Pada bulan dan tanggal berapa puncak pemesanan hotel biasanya terjadi? Apakah terdapat musim tertentu yang memengaruhi tingkat pemesanan hotel?
![download (2)](https://github.com/user-attachments/assets/90d9ae0f-f810-40be-bdae-8827f6b9cb4c)

- Konsumen cenderung memilih hotel selama musim liburan, terutama pada bulan Juli, Agustus, dan Mei, yang merupakan waktu yang populer untuk berlibur di Eropa. Ini menunjukkan bahwa konsumen lebih sering melakukan pemesanan di periode tersebut.
- Banyak konsumen yang melakukan pemesanan hotel pada tanggal 5, antara 15-20, dan akhir bulan, yang kemungkinan besar terkait dengan pengaturan keuangan pribadi atau fleksibilitas jadwal kerja.

### C. Paket makanan apa yang paling sering dipesan oleh pelanggan, dan bagaimana hotel dapat mengoptimalkan layanan berdasarkan preferensi tersebut?

![download (4)](https://github.com/user-attachments/assets/5aec5786-4e3c-40d5-8893-af0a120d643a)

Konsumen lebih cenderung memilih paket Bed and Breakfast (BB) karena menawarkan nilai lebih dan sesuai dengan kebutuhan mereka. Paket Half Board (HB) dan Special (SC) juga populer, namun konsumen lebih memilih paket dengan harga yang lebih kompetitif dan menu yang lebih sesuai dengan selera mereka.

### D. Jenis pemesanan apa yang paling sering digunakan oleh pelanggan (Contract, Group, Transient, atau Transient-party), dan bagaimana distribusinya memengaruhi manajemen reservasi hotel?

![download (5)](https://github.com/user-attachments/assets/04221e5b-442c-4ab3-a598-5a05bec820a3)

Sebagian besar pemesanan berasal dari Transient (perjalanan individu atau keluarga kecil) yang menginginkan fleksibilitas dalam pemesanan. Konsumen dalam kategori Transient-Party juga populer, namun dengan jumlah lebih kecil, sementara Contract dan Group lebih jarang dipilih.

# Temuan Informasi Baru 
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


# **Kesimpulan secara Menyeluruh** :
Berdasarkan hasil analisis yang kami lakukan, kami menyimpulkan bahwa hotel ini memiliki rating sedang, karena masih ada lumayan banyak tamu yang tidak memesan kembali. Hal ini bisa menjadi indikasi adanya ketidakpuasan dari tamu atau adanya aspek-aspek tertentu yang perlu diperbaiki dalam layanan yang diberikan. Kemungkinan penyebabnya adalah layanan yang kurang memadai, seperti fasilitas yang tidak sesuai harapan atau pelayanan yang tidak memuaskan. Selain itu, kurangnya strategi pemasaran yang efektif untuk menarik tamu lama kembali juga bisa menjadi faktor. Hotel mungkin belum memiliki program khusus seperti loyalty program atau penawaran spesial yang dapat memberikan insentif bagi tamu yang sudah pernah menginap. Oleh karena itu, penting bagi hotel untuk meningkatkan kualitas layanan dan menciptakan penawaran yang menarik untuk tamu lama agar mereka tertarik untuk menginap kembali.










