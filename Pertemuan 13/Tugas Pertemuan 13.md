## Perbedaan Antara Concurrent dan Parallel Dalam Sistem Operasi

**Concurrent (Bersamaan):**

- Definisi : Concurrent merujuk pada kemampuan sistem untuk menjalankan beberapa tugas secara bersamaan.
- Cara Kerja : Dalam konteks sistem operasi, concurrency dapat terjadi ketika beberapa tugas dimulai secara bersamaan dan kemudian dilakukan dalam periode waktu yang bersamaan atau beririsan.
- Mekanisme : Namun, penting untuk dicatat bahwa dalam banyak kasus, tugas-tugas ini tidak benar-benar berjalan secara paralel pada level instruksi mesin. Sebaliknya, sistem operasi menggunakan mekanisme seperti time-sharing atau multitasking untuk memberikan ilusi tugas-tugas tersebut berjalan secara bersamaan.
- Contoh : Contoh konkret dari concurrency adalah sistem operasi yang menjalankan beberapa proses atau thread secara bersamaan di atas satu atau beberapa CPU.

**Parallel (Paralel) :**

- Definisi : Parallel merujuk pada kemampuan sistem untuk benar-benar menjalankan beberapa tugas secara bersamaan pada level instruksi mesin.
- Cara Kerja : Dalam konteks sistem operasi, parallelisme terjadi ketika beberapa tugas benar-benar dieksekusi secara bersamaan pada beberapa unit pemrosesan, seperti CPU atau core CPU.
- Mekanisme : Hal ini memungkinkan tugas-tugas tersebut untuk mendapatkan keuntungan dari peningkatan kecepatan eksekusi dan kinerja karena mereka benar-benar berjalan secara bersamaan.
- Contoh : Contoh konkret dari parallelisme adalah sistem komputer yang menggunakan beberapa core CPU atau multiple processor units (MPU) untuk menjalankan tugas-tugas secara bersamaan tanpa membagi sumber daya CPU secara bersamaan.

Ilustrasi Gambar :

![pict1](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/1d691480-969a-40eb-aaf7-c5e69b31cb19)

Penjelasan :

Parallel (Paralel) :
Pada diagram pertama (kiri), dua tugas (Task 1 dan Task 2) dijalankan secara bersamaan di dua core yang berbeda. Ini menunjukkan parallelism, di mana dua tugas benar-benar berjalan secara paralel pada dua unit pemrosesan (core) yang berbeda. Ini mencerminkan bagaimana tugas-tugas dapat dieksekusi secara simultan tanpa harus berbagi waktu pada satu core, sehingga meningkatkan efisiensi dan kecepatan eksekusi.

Concurrent (Bersamaan) :
Diagram kedua (tengah) menunjukkan dua core yang menjalankan beberapa sub-tugas (Task 1.1, Task 1.2, dst., dan Task 2.1, Task 2.2, dst.) secara bersamaan, tetapi masing-masing core melakukan switching antara sub-tugas ini. Ini adalah contoh concurrency, di mana tugas-tugas dibagi menjadi bagian-bagian kecil yang dijalankan bergantian pada satu atau lebih core. Ini mencerminkan bagaimana sistem operasi dapat membuat ilusi bahwa banyak tugas berjalan secara bersamaan dengan membagi waktu pemrosesan antar tugas.

Concurrent and Parallel (Bersamaan dan Paralel) :
Diagram ketiga (kanan) menunjukkan kombinasi dari concurrency dan parallelism. Dua core menjalankan beberapa sub-tugas (Task 1.1, Task 1.2, dst., dan Task 2.1, Task 2.2, dst.) secara bersamaan, tetapi juga parallel. Setiap core menjalankan sub-tugas yang berbeda secara bergantian, namun ada juga eksekusi simultan di antara core-core tersebut. Ini mencerminkan situasi di mana sistem operasi memanfaatkan parallelism di tingkat perangkat keras (core) serta concurrency di tingkat perangkat lunak (task scheduling), untuk mencapai efisiensi maksimum.

Kaitan dengan Penjelasan Sebelumnya:
- Concurrent (Bersamaan) : Seperti dijelaskan sebelumnya, concurrency melibatkan pelaksanaan beberapa tugas secara bersamaan melalui pembagian waktu dan switching cepat antara tugas-tugas. Diagram kedua menunjukkan bagaimana ini dilakukan di level core.
- Parallel (Paralel) : Parallelism adalah eksekusi simultan dari tugas-tugas di beberapa unit pemrosesan. Diagram pertama menunjukkan eksekusi tugas-tugas yang benar-benar berjalan paralel pada core yang berbeda.
- Concurrent and Parallel : Kombinasi ini menggabungkan dua konsep sebelumnya, seperti yang ditunjukkan dalam diagram ketiga, untuk memaksimalkan penggunaan sumber daya dan efisiensi eksekusi.

## Perbedaan Antara Concurrent dan Serial dalam Sistem Operasi

**Concurrent (Bersamaan) :**

- Definisi : Concurrent merujuk pada kemampuan sistem untuk menjalankan beberapa tugas secara bersamaan.
- Cara Kerja : Dalam konteks sistem operasi, concurrency dapat terjadi ketika beberapa tugas dimulai secara bersamaan dan kemudian dilakukan dalam periode waktu yang bersamaan atau beririsan.
- Mekanisme : Namun, penting untuk dicatat bahwa dalam banyak kasus, tugas-tugas ini tidak benar-benar berjalan secara paralel pada level instruksi mesin. Sebaliknya, sistem operasi menggunakan mekanisme seperti time-sharing atau multitasking untuk memberikan ilusi bahwa tugas-tugas tersebut berjalan secara bersamaan.
- Contoh : Contoh konkret dari concurrency adalah sistem operasi yang menjalankan beberapa proses atau thread secara bersamaan di atas satu atau beberapa CPU.

**Serial (Serial) :**

- Definisi : Serial merujuk pada pendekatan di mana tugas atau proses dijalankan satu per satu.
- Cara Kerja : Dalam konteks sistem operasi, tugas-tugas dalam eksekusi serial harus diselesaikan satu per satu tanpa adanya interleaving dalam eksekusi.
- Mekanisme : Sistem operasi menyelesaikan eksekusi satu tugas sepenuhnya sebelum beralih ke tugas berikutnya, tanpa menggunakan time-sharing atau multitasking.
- Contoh : Contoh konkret dari eksekusi serial adalah batch processing di mana data diproses dalam urutan yang telah ditentukan tanpa interleaving.

Ilustrasi Gambar :  

![pict2](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/df511f4b-e118-4153-beab-2728e657aedc)

Penjelasan : 

Serial (Serial) :
Diagram pertama (kiri) menunjukkan bagaimana beberapa tugas (Task 0, Task 1, Task 2) dijalankan satu per satu. Setiap tugas harus selesai sebelum tugas berikutnya dapat dimulai. Ini menunjukkan eksekusi serial, di mana tidak ada dua tugas yang berjalan bersamaan. Sistem operasi menyelesaikan satu tugas sepenuhnya sebelum beralih ke tugas berikutnya. Eksekusi serial sederhana untuk diimplementasikan dan tidak memerlukan mekanisme pengalihan konteks yang kompleks. Namun, ini mungkin kurang efisien dalam penggunaan sumber daya CPU karena hanya satu tugas yang berjalan pada satu waktu.

Concurrent (Bersamaan) :
Diagram kedua (kanan) menunjukkan bagaimana beberapa tugas (Task 0, Task 1, Task 2, Task 3) dijalankan secara bersamaan atau beririsan dalam waktu. Setiap tugas tidak perlu menunggu tugas lainnya selesai sepenuhnya. Ini menunjukkan eksekusi concurrent, di mana sistem operasi menggunakan teknik seperti time-sharing untuk mengalokasikan waktu CPU ke beberapa tugas secara bergantian, sehingga memberikan ilusi bahwa semua tugas berjalan secara bersamaan. Eksekusi concurrent lebih efisien dalam penggunaan sumber daya CPU karena beberapa tugas dapat berjalan dalam waktu yang beririsan. Meskipun demikian, mekanisme ini memerlukan pengelolaan konteks dan switching yang lebih kompleks dibandingkan dengan eksekusi serial.

Kaitan dengan Penjelasan Sebelumnya:
Serial (Serial) : Seperti dijelaskan sebelumnya, eksekusi serial melibatkan menjalankan tugas satu per satu tanpa ada tumpang tindih dalam waktu. Diagram pertama menunjukkan bagaimana tugas-tugas tersebut dijalankan secara berurutan.
Concurrent (Bersamaan) : Eksekusi concurrent melibatkan pelaksanaan beberapa tugas secara bersamaan melalui pembagian waktu dan switching cepat antara tugas-tugas. Diagram kedua menunjukkan bagaimana ini dilakukan dengan mengalokasikan waktu CPU ke beberapa tugas secara bergantian.

## Dining Philosophers Problem

Dining Philosophers Problem adalah sebuah masalah klasik dalam ilmu komputer yang mengilustrasikan tantangan dalam sinkronisasi dan manajemen sumber daya dalam lingkungan multithreading atau multiprocessing. Masalah ini digambarkan sebagai sekelompok filsuf yang duduk di sekitar meja bundar dengan piring makanan di depan mereka. Di antara setiap dua filsuf ada sebuah garpu, dan untuk makan, seorang filsuf harus mengambil dua garpu yang bersebelahan.

Tantangannya adalah memastikan bahwa setiap filsuf dapat makan tanpa terjebak dalam situasi mati kelaparan (starvation) atau deadlock, di mana setiap filsuf memiliki satu garpu dan menunggu garpu yang lain. Dalam skenario ini, ada beberapa konflik :

- Persaingan untuk Sumber Daya : Filsuf-filsuf bersaing untuk mengambil garpu, yang merupakan sumber daya terbatas. Jika dua filsuf di sebelah kanan dan kiri sebuah garpu mencoba mengambilnya secara bersamaan, dapat terjadi deadlock.

- Penjadwalan Sumber Daya : Penting untuk mengatur penjadwalan pengambilan garpu untuk menghindari situasi di mana semua garpu diambil oleh satu set filsuf, menyebabkan kelaparan bagi yang lain.

Strategi umum yang digunakan untuk menyelesaikan Dining Philosophers Problem termasuk:

1.  Solusi Pengurutan: Menetapkan urutan pengambilan garpu, seperti mengambil garpu kiri kemudian garpu kanan, untuk mencegah deadlock.

2.  Penggunaan Penguncian (Locking) : Menggunakan mekanisme penguncian atau mutex untuk memastikan bahwa hanya satu filsuf yang dapat mengakses garpu pada satu waktu.

3.  Pendekatan Non-blocking : Mengimplementasikan logika yang memungkinkan seorang filsuf untuk mencoba mengambil garpu tanpa menghalangi yang lain, dan jika tidak tersedia, melepaskan kembali garpu yang sudah diambil.

4.  Pembatasan Persaingan Sumber Daya : Mengatur batasan pada jumlah filsuf yang diizinkan untuk mengambil garpu secara bersamaan untuk mencegah persaingan berlebihan terhadap sumber daya.

Dengan menerapkan strategi ini, Dining Philosophers Problem dapat diatasi dengan memastikan bahwa setiap filsuf memiliki akses yang adil dan aman terhadap garpu tanpa mengalami deadlock atau kelaparan. Masalah ini sering digunakan sebagai studi kasus dalam desain dan analisis sistem paralel dan terdistribusi.

## Reader-Writer Problem

Reader-Writer Problem adalah masalah klasik dalam ilmu komputer yang mengilustrasikan tantangan sinkronisasi akses bersama ke sumber daya yang bersifat statis dan dinamis antara beberapa proses atau thread. Dalam konteks ini, sumber daya yang dimaksud bisa berupa data atau struktur data tertentu.

Ada dua jenis akses yang ingin dilakukan terhadap sumber daya dalam masalah ini :

1.  Akses Pembaca (Reader) : Proses yang ingin membaca sumber daya. Akses pembaca dapat bersamaan tanpa mempengaruhi hasil bacaan.
2.  Akses Penulis (Writer) : Proses yang ingin menulis atau mengubah sumber daya. Hanya satu penulis yang diizinkan mengakses sumber daya pada satu waktu, dan saat penulis sedang menulis, tidak ada pembaca atau penulis lain yang diizinkan mengaksesnya.

Tantangannya adalah memastikan bahwa :

- Pembaca dapat membaca sumber daya secara bersamaan tanpa masalah konsistensi.
- Penulis memiliki akses eksklusif ke sumber daya untuk menghindari situasi di mana data dapat terbaca secara tidak konsisten oleh pembaca lain saat sedang diubah.

Strategi umum yang digunakan untuk menyelesaikan Reader-Writer Problem meliputi :

1.  Prioritas Pembaca : Memperbolehkan beberapa pembaca untuk membaca secara bersamaan selama tidak ada penulis yang sedang menulis. Ini memastikan ketersediaan sumber daya untuk pembaca sebanyak mungkin dan menghindari kelaparan pembaca.

2.  Prioritas Penulis : Memberikan prioritas kepada penulis sehingga jika ada penulis yang ingin menulis, tidak ada pembaca yang diizinkan membaca sampai penulisan selesai. Ini memastikan konsistensi data dan menghindari pembaca yang membaca data yang sedang berubah.

3.  Penutup Pencapaian Paralelisme : Menerapkan mekanisme yang membatasi jumlah akses bersama yang diizinkan ke sumber daya, baik pembaca maupun penulis, untuk menghindari persaingan berlebihan dan meningkatkan kinerja secara keseluruhan.

4.  Deteksi dan Pemulihan Deadlock : Mengidentifikasi dan menangani situasi deadlock yang mungkin terjadi, di mana penulis dan pembaca saling menunggu sumber daya yang dipegang oleh yang lain.

Dengan menerapkan strategi-strategi ini dengan bijaksana, Reader-Writer Problem dapat diatasi dengan memastikan bahwa akses bersama ke sumber daya dapat dilakukan secara aman dan efisien tanpa mengorbankan konsistensi data atau kinerja sistem. Masalah ini sering dihadapi dalam desain dan implementasi sistem yang mendukung operasi bersama dan terdistribusi.


