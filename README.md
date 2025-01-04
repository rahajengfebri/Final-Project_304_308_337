# Final-Project_304_308_337

## Daftar Isi
1. [Pendahuluan](#1-pendahuluan)<br>
   1.1 [Latar Belakang Masalah](#11-latar-belakang-masalah)<br>
   1.2 [Data dan Metodologi yang Digunakan](#12-data-dan-metodologi-yang-digunakan)<br>
   1.3 [Teknik Analisis yang Diusulkan](#13-teknik-analisis-yang-diusulkan)<br>
   1.4 [Manfaat Hasil Analisis](#14-manfaat-hasil-analisis)<br>
2. [Library/Package Python](#2--librarypackage-python)<br>
3. [Data Preparation](#3--data-preparation)<br>
   3.1 [Sumber Dataset](#31--sumber-dataset)<br>
   3.2 [Detail Dataset](#32--detail-dataset)<br>
4. [Eksplorasi dan analisa data](#4-eksplorasi-dan-analisa-data)<br>
   4.1 [Pemesanan dan Pembatalan Hotel Berdasarkan Musim](#41-pemesanan-dan-pembatalan-hotel-berdasarkan-musim)<br>
   4.2 [Pembatalan Pemesanan City Hotel dan Resort Hotel](#42-pembatalan-pemesanan-city-hotel-dan-resort-hotel)<br>


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

### 1.3 ⚙️ **Teknik Analisis yang Diusulkan**
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

### 1.4 🌟 **Manfaat Hasil Analisis**
#### **Wawasan yang strategis kepada seorang manajer hotel**
1. Dapat mengembangkan layanan untuk semua pelanggan.
2. Merancang Strategi pemasaran yang lebih baik.
3. Memaksimalkan operasional hotel ketika jumlah pelanggan meningkat tajam.

### **Manfaat Analisis bagi Konsumen**

1. Meningkatkan kualitas layanan hotel, sehingga pelanggan akan merasa lebih puas dan nyaman.
2. Membangun hubungan yang lebih baik dengan pelanggan untuk menciptakan pengalaman yang positif dan mendorong pelanggan untuk tetap memilih hotel tersebut di masa mendatang.
## 2. 📂 *Library/Package Python*

| **Library**                      | **Fungsi**                                                            |
|-----------------------------------|----------------------------------------------------------------------|
| [Google Colab Drive](https://colab.research.google.com/notebooks/intro.ipynb) | Menghubungkan Google Drive ke Google Colab.                           |
| [Pandas](https://pandas.pydata.org/) | Manipulasi dan analisis data dalam bentuk tabel (DataFrame).          |
| [Matplotlib](https://matplotlib.org/) | Membuat visualisasi data seperti grafik batang, garis, dan lainnya.   |
| [Seaborn](https://seaborn.pydata.org/) | Membuat visualisasi statistik dengan tampilan estetis.                |
| [Warnings](https://docs.python.org/3/library/warnings.html) | Menangani atau menyembunyikan peringatan yang tidak relevan.          |


## 3. 🌟 **Data Preparation**

### 3.1 📂 **Sumber Dataset**
Data yang digunakan dalam analisis ini berasal dari kumpulan data permintaan pemesanan hotel yang dikumpulkan oleh Antonio, Almeida, dan Nunes pada tahun 2019. Berikut link dataset yang digunakan [(Dataset)](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-02-11/readme.md)


### 3.2 🗃️ **Detail Dataset**

#### Tujuan dataset
Tujuan awal data yaitu untuk menyediakan informasi tentang perilaku pelanggan dalam pemesanan hotel, termasuk pola pemesanan, jenis layanan yang dipilih, serta faktor-faktor yang memengaruhi keputusan pemesanan.
#### Jumlah Dataset
Jumlah dataset 119.390 entri dan 32 variable
#### Kekhasan Dataset
- Dataset ini mencerminkan data riil yang dikumpulkan dari dua tipe hotel (resort hotel dan city hotel).
- Mencakup pola pemesanan, pembatalan, preferensi pelanggan, serta detail layanan yang dipesan.
- Karena data ini berasal dari hotel nyata, semua elemen data yang berkaitan dengan identitas hotel atau pelanggan telah dihapus untuk menjaga kerahasiaan.
#### Missing Value pada data
Berikut adalah penjelasan dalam bentuk tabel:  

| Kolom     | Penyebab Missing Value                                          |
|---------------|----------------------------------------------------------------------|
| `children`    | memiliki missing value terjadi karena tidak semua pelanggan yang memesan hotel membawa anak atau mungkin pelanggan tersebut tidak memiliki anak.                      |
| `country`     | memiliki missing value terjadi karena sistem tidak mewajibkan pelanggan untuk mengisi informasi negara saat melakukan pemesanan, sehingga beberapa data tidak tercatat.             |
| `agent`       | memiliki missing value terjadi karena beberapa pemesanan dilakukan tanpa melalui agen perjalanan, seperti pemesanan langsung ke hotel melalui website. |
| `company`     | memiliki missing value terjadi karena beberapa pemesanan dilakukan oleh individu, bukan melalui perusahaan atau institusi yang bertanggung jawab atas pembayaran pemesanan. |  
#### Strategi Imputasi
Berikut adalah strategi imputasi untuk menangani missing value dalam dataset:  

| Kolom     | Strategi Imputasi                                                                                        |
|---------------|----------------------------------------------------------------------------------------------------------------|
| `children`    | Missing value diimputasikan dengan nilai **0**, karena diasumsikan tidak ada anak yang ikut dalam pemesanan.    |
| `country`     | Missing value diimputasikan dengan kategori **"Unknown"**, karena tidak semua pelanggan mengisi negara asal.    |
| `agent`       | Missing value diimputasikan dengan kategori **"Direct Booking"**, karena pemesanan dilakukan tanpa agen.        |
| `company`     | Tidak diimputasikan, karena sebagian besar (56,58%) nilai hilang. Kolom ini dihapus karena tidak relevan dengan analisis. |  

## 4. **Eksplorasi dan analisa data**
### 4.1. **Pemesanan dan Pembatalan Hotel Berdasarkan Musim**

Untuk mempermudah analisis musiman, ditambahkan kolom **'season'** yang mengelompokkan bulan kedatangan tamu (**'arrival_date_month'**) ke dalam empat kategori musim:

1. **Musim Panas (Summer)**: Juni, Juli, Agustus
2. **Musim Gugur (Fall)**: September, Oktober, November
3. **Musim Dingin (Winter)**: Desember, Januari, Februari
4. **Musim Semi (Spring)**: Maret, April, Mei

Dengan pengelompokan ini, manajemen hotel dapat menganalisis tren musiman dan membuat keputusan berdasarkan pola permintaan dan pembatalan pada setiap musim. Ini membantu dalam persiapan operasional, seperti penambahan staf atau promosi di musim tertentu.

--- 
- Cara Kerja
1. **Fungsi `categorize_season(month)`**: Mengelompokkan bulan kedatangan tamu ke dalam musim (Summer, Fall, Winter, Spring).

2. **Menambahkan Kolom**: Menambah kolom **'season'** untuk musim dan **'cancellation_status'** untuk status pembatalan berdasarkan **'is_canceled'**.

3. **Pengelompokan & Hitung**: Mengelompokkan data berdasarkan musim dan status pembatalan, lalu menghitung jumlah pemesanan.

4. **Visualisasi**: Membuat barplot untuk visualisasi jumlah pemesanan per musim dengan status pembatalan.

5. **Tampilkan Data**: Menampilkan tabel analisis jumlah pemesanan berdasarkan musim dan status pembatalan.

Apakah penjelasan ini sudah cukup singkat?
![download](https://github.com/user-attachments/assets/097f178b-e68a-4bda-828d-a908a079c85e)
Dari hasil visualisasi diatas, dapat dilihat bahwa pemesanan paling banyak terjadi pada musim summer, khususnya pada bulan Juni, Juli, dan Agustus. Ini menunjukkan bahwa banyak tamu yang memilih untuk menginap di hotel selama liburan musim panas, yang biasanya bertepatan dengan liburan sekolah atau waktu-waktu liburan yang lebih panjang.
### 4.2 Pembatalan Pemesanan City Hotel dan Resort Hotel
Dalam analisis ini, kami membandingkan tingkat pembatalan pemesanan berdasarkan dua tipe hotel: City Hotel dan Resort Hotel. Tingkat pembatalan dihitung sebagai persentase dari total pemesanan yang dibatalkan. Perbandingan ini memungkinkan untuk memahami perbedaan tingkat pembatalan antara kedua tipe hotel, yang dapat membantu dalam perencanaan sumber daya dan strategi pemasaran.

Rumus untuk menghitung tingkat pembatalan (cancellation_rate) adalah sebagai berikut:

$$
\text{cancellation\_rate} = \left( \frac{\text{df['is\_canceled'].transform('mean')}}{\text{df.groupby('hotel')['is\_canceled'].transform('mean')}} \right) \times 100
$$

Penjelasan:
- **df['is_canceled'].transform('mean')**: Menghitung rata-rata tingkat pembatalan untuk seluruh data.
- **df.groupby('hotel')['is_canceled'].transform('mean')**: Menghitung rata-rata tingkat pembatalan per tipe hotel.
- **cancellation_rate**: Menghitung tingkat pembatalan sebagai persentase per hotel.

---
- **Cara Kerja:**

1. **Menghitung Tingkat Pembatalan**: Kolom **'cancellation_rate'** dihitung dengan mengelompokkan data berdasarkan **'hotel'** dan menghitung rata-rata kolom **'is_canceled'** untuk setiap tipe hotel, lalu mengalikannya dengan 100 untuk mendapatkan persentase pembatalan.
2. **Visualisasi**: Menggunakan **sns.barplot()** untuk membuat grafik batang yang menampilkan tingkat pembatalan berdasarkan tipe hotel, dengan warna yang berbeda untuk setiap tipe.
3. **Menambahkan Nilai Persentase**: Persentase tingkat pembatalan ditampilkan di atas setiap batang pada grafik menggunakan **plt.text()**.
4. **Menambahkan Legenda**: Legenda ditambahkan untuk membedakan City Hotel dan Resort Hotel menggunakan **plt.Line2D()**.

Hasil analisis ini memberikan wawasan mengenai perbedaan tingkat pembatalan antara tipe hotel, yang dapat membantu manajemen hotel untuk merencanakan strategi pengelolaan lebih baik.

![download (1)](https://github.com/user-attachments/assets/4bbad8a4-2bfb-471a-af6f-84a88f3d8458)

### 4.3
### 4.4 Type Costumer Berdasarkan Lama Pemesanan
Dalam analisis ini, kami membandingkan **Lead Time Category** berdasarkan **customer type**, termasuk kategori baru **transient-party**. **Lead Time** dibagi menjadi lima rentang waktu yang lebih detail:  

1. **0-7 Days**: Pemesanan sangat mendekati tanggal kedatangan.  
2. **8-30 Days**: Pemesanan dalam waktu 1-4 minggu sebelum kedatangan.  
3. **31-100 Days**: Pemesanan dalam waktu 1-3 bulan sebelum kedatangan.  
4. **101-365 Days**: Pemesanan dalam waktu 3 bulan hingga 1 tahun sebelum kedatangan.  
5. **More than 1 Year**: Pemesanan lebih dari 1 tahun sebelumnya.  

Perbandingan ini memungkinkan untuk memahami pola pemesanan jangka pendek dan panjang dari berbagai jenis pelanggan (**transient**, **contract**, **group**, dan **transient-party**). Wawasan ini membantu dalam mengidentifikasi kebutuhan pelanggan pada berbagai periode waktu untuk menyusun strategi pemasaran atau pengelolaan sumber daya yang lebih efektif.

---

**Cara Kerja:**  
1. Kolom **`lead_time`** dibagi ke dalam kategori menggunakan fungsi **`pd.cut`**, dengan rentang kategori yang telah ditentukan. Kategori disimpan dalam kolom baru bernama **`Lead_Time_Category`**.  
2. Data kemudian dikelompokkan berdasarkan **`customer_type`** dan **`Lead_Time_Category`** menggunakan **`groupby`** dan dihitung jumlah pemesanan per kelompok.  
3. Hasil pengelompokan dipresentasikan menggunakan grafik batang untuk menunjukkan distribusi jumlah pemesanan per kategori lead time pada masing-masing jenis pelanggan.  
4. Grafik diberi label dan warna untuk memudahkan interpretasi, serta menampilkan bagaimana setiap jenis pelanggan berperilaku terhadap waktu pemesanan.

Hasil analisis ini memberikan wawasan penting bagi pengelola hotel dalam memahami preferensi pelanggan dan pola pemesanan mereka untuk meningkatkan pengalaman pelanggan dan optimasi bisnis.
![download (7)](https://github.com/user-attachments/assets/c8118450-2453-439d-9525-a567af9c794b)

Berdasarkan analisis hubungan antara lead time dan customer type, pelanggan dengan tipe **Transient** mendominasi jumlah pemesanan, terutama pada kategori lead time 31-100 hari dan 101-365 hari, namun juga menunjukkan pemesanan mendadak (0-7 hari). Tipe **Contract** dan **Group** memiliki jumlah pemesanan yang sangat kecil, menunjukkan bahwa pemesanan pada kedua tipe ini tidak bergantung pada lead time dan lebih bersifat jangka panjang atau terkait dengan acara tertentu. Sementara itu, tipe **Transient-Party** menunjukkan pola yang mirip dengan **Transient**, tetapi dengan jumlah pemesanan yang lebih kecil. Kesimpulannya, lead time menjadi indikator penting dalam memprediksi kebutuhan kamar hotel, terutama untuk pelanggan **Transient**, yang dapat membantu dalam merencanakan strategi pemasaran dan pengelolaan sumber daya hotel yang lebih efektif.


# **Kesimpulan secara Menyeluruh** :
Berdasarkan hasil analisis yang kami lakukan, kami menyimpulkan bahwa hotel ini memiliki rating sedang, karena masih ada lumayan banyak tamu yang tidak memesan kembali. Hal ini bisa menjadi indikasi adanya ketidakpuasan dari tamu atau adanya aspek-aspek tertentu yang perlu diperbaiki dalam layanan yang diberikan. Kemungkinan penyebabnya adalah layanan yang kurang memadai, seperti fasilitas yang tidak sesuai harapan atau pelayanan yang tidak memuaskan. Selain itu, kurangnya strategi pemasaran yang efektif untuk menarik tamu lama kembali juga bisa menjadi faktor. Hotel mungkin belum memiliki program khusus seperti loyalty program atau penawaran spesial yang dapat memberikan insentif bagi tamu yang sudah pernah menginap. Oleh karena itu, penting bagi hotel untuk meningkatkan kualitas layanan dan menciptakan penawaran yang menarik untuk tamu lama agar mereka tertarik untuk menginap kembali.










