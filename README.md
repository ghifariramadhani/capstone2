# capstone2
Capstone Project Module 2 Transjakarta EDA
# **Latar Belakang**  
  
  Transjakarta adalah sebuah sistem transportasi Bus Rapid Transit (BRT) pertama di Asia Tenggara dan Selatan yang beroperasi sejak tahun 2004 di Jakarta, Indonesia. TransJakarta dirancang sebagai moda transportasi massal pendukung aktivitas ibukota yang sangat padat. Dengan jalur lintasan terpanjang di dunia (251.2 km), serta memiliki 260 halte yang tersebar dalam 13 koridor, Transjakarta yang awalnya beroperasi mulai Pkl. 05.00 – Pkl. 22.00 WIB, kini beroperasi 24 jam.

# **Pernyataan Masalah**  
  
Jakarta memiliki populasi lebih dari 10 juta penduduk. Dibangunnya TransJakarta (TJ) bertujuan untuk mengurangi tingkat kemacetan di Jakarta. Walaupun belum terlalu terlihat bahwa TJ dapat mengurangi tingkat kemacetan dengan drastis, maka saya disini akan menganalisis data tersebut dan memberikan saran yang terbaik agar TJ dapat mengurangi tingkat kemacetan.  
    
Tujuan dari dilakukannya *Exploratory Data Analysis* adalah untuk memahami jadwal rute dari tiap TransJakarta di Jakarta dan memberikan saran untuk meningkatkan performa berupa penambahan armada bagi TransJakarta tersebut.

# **Membaca Dataset**

Dataset bersumber dari kaggle dan dapat diunduh pada Link : https://www.kaggle.com/datasets/dikisahkan/transjakarta-transportation-transaction?select=dfTransjakarta.csv.  
Berikut adalah interpretasi kolom data :  

1. **transID**:  Unique transaction id for every transaction  
2. **payCardID**:  Customers main identifier. The card customers use as a ticket for entrance and exit.  
3. **payCardBank**: Customers card bank issuer name  
4. **payCardName**: Customers name that is embedded in the card.  
5. **payCardSex**: Customers sex that is embedded in the card  
6. **payCardBirthDate**: Customers birth year  
7. **corridorID**: Corridor ID / Route ID as key for route grouping.  
8. **corridorName**: Corridor Name / Route Name contains Start and Finish for each route.  
9. **direction**: 0 for Go, 1 for Back. Direction of the route.  
10. **tapInStops**: Tap In (entrance) Stops ID for identifying stops name  
11. **tapInStopsName**: Tap In (entrance) Stops Name where customers tap in.  
12. **tapInStopsLat**: Latitude of Tap In Stops  
13. **tapInStopsLon**: Longitude of Tap In Stops  
14. **stopStartSeq**: Sequence of the stops, 1st stop, 2nd stops etc. Related to direction.  
15. **tapInTime**: Time of tap in. Date and time  
16. **tapOutStops**: Tap Out (Exit) Stops ID for identifying stops name  
17. **tapOutStopsName**: Tap out (exit) Stops Name where customers tap out.  
18. **tapOutStopsLat**: Latitude of Tap Out Stops  
19. **tapOutStopsLon**: Longitude of Tap Out Stops  
20. **stopEndSeq**: Sequence of the stops, 1st stop, 2nd stops etc. Related to direction.  
21. **tapOutTime**: Time of tap out. Date and time  
22. **payAmount**: The number of what customers pay. Some are free. Some not.  

Jumlah baris dan kolom pada dataset tersebut adalah (37900,22) sebelum data cleaning.
Setelah dilakukan data cleaning, terlihat bahwa total baris yang ada berkurang dari 37900 baris menjadi 31730. Disaat melakukan pengecekan pada dataset, terlihat suatu yang ganjal yaitu dtype pada tapInTime dan tapOutTime yang berupa object, dimana seharusnya dtype pada waktu itu adalah datetime. Oleh karena itu, akan dirubah dtype tersebut menjadi datetime secara manual. 

**Kesimpulan**  
<br> Dari analisa tersebut dapat disimpulkan bahwa:
<br> 
* Penggunaan TransJakarta paling banyak adalah pada pukul 6 WIB dan 17 WIB dimana jam tersebut adalah jam untuk memulai aktivitas dan menyelesaikan aktivitas
* tapIn terbanyak ada pada halte BKN sebanyak 274 taps dan tapOut terbanyak ada pada halte Penjaringan sebanyak 208 taps
* Usia terbanyak pada penggunaan TransJakarta adalah pada tahun kelahiran 1992,1994,1981,1987,1985 (31 Tahun, 29 Tahun, 42 Tahun, 36 Tahun, 38 Tahun)
* Penggunaan TransJakarta paling banyak adalah pada koridor Cibubur - Balai Kota sebanyak 362 pengguna. Sedangkan, pengguna TransJakarta paling sedikit adalah pada koridor Kampung Rambutan - Blok M sebanyak 16 pengguna.

**Saran**
<br> Dapat diberikan saran berupa:
<br>
* Akomodasikan TransJakarta lebih banyak pada waktu penduduk memulai aktivitas mereka agar income juga menjadi lebih banyak dan tidak perlu mengakomodasikan terlalu banyak TransJakarta pada waktu siang hari (Pukul 11-13 WIB) dikarenakan pengguna TJ pada waktu tersebut dapat dilihat sangat sedikit.
* Dikarenakan tapIn dan tapOut terbanyak ada pada BKN dan Penjaringan, maka armada harus ditempatkan lebih banyak pada daerah tersebut.
* Koridor Cibubur - Balai Kota memiliki pengguna sebanyak 362 dan koridor Kampung Rambutan - Blok M memiliki pengguna sebanyak 16, maka pengalokasian TransJakarta harus ditempatkan lebih banyak pada koridor Cibubur - Balai Kota dan ditempatkan lebih sedikit pada koridor Kampung Rambutan - Blok M agar meminimalisir kerugian yang akan ditanggung.
