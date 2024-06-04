**THREAD**

**Practice Exercises**

4.1 Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi single-threaded.

Jawab:

A. Server Web yang melayani setiap permintaan dalam thread terpisah.

B. Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian-bagian matriks yang berbeda dapat dikerjakan secara paralel.

C. Sebuah program GUI interaktif seperti debugger dimana thread digunakan untuk memonitor input pengguna, thread lain mewakili aplikasi yang sedang berjalan, dan thread ketiga memonitor kinerja.


4.2 Apa dua perbedaan antara thread tingkat pengguna (user-level threads) dan thread tingkat kernel (kernel-level threads)? Di bawah keadaan apa satu jenis lebih baik dari yang lain? 

Jawab:
A. Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui thread tingkat kernel.

B. Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh pustaka thread dan kernel menjadwalkan thread kernel.

C. Thread kernel tidak perlu terkait dengan suatu proses sedangkan setiap thread pengguna milik suatu proses. Thread kernel umumnya lebih mahal untuk dipelihara daripada thread pengguna karena harus direpresentasikan dengan struktur data kernel.


4.3 Jelaskan tindakan yang dilakukan oleh kernel untuk melakukan konteks-switch antara thread tingkat kernel.

Jawab:

Penukaran konteks antara thread kernel umumnya memerlukan penyimpanan nilai register CPU dari thread yang sedang dialihkan keluar dan mengembalikan register CPU dari thread baru yang dijadwalkan.


4.4 Sumber daya apa yang digunakan saat sebuah thread dibuat? Bagaimana perbedaannya dengan yang digunakan saat proses dibuat?

Jawab:

Karena sebuah thread lebih kecil dari sebuah proses, pembuatan thread biasanya menggunakan sumber daya yang lebih sedikit daripada pembuatan proses. Membuat sebuah proses memerlukan alokasi blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file terbuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya adalah aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan alokasi struktur data kecil untuk menyimpan set register, tumpukan, dan prioritas.


4.5 Asumsikan bahwa sebuah sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model banyak-ke-banyak (many-to-many) dan bahwa pemetaan dilakukan melalui LWPs. Selain itu, sistem memungkinkan pengembang untuk membuat thread real-time untuk digunakan dalam sistem real-time. Apakah perlu untuk mengikat sebuah thread real-time ke LWP? Jelaskan.

Jawab:

Ya. Waktu sangat penting untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak terikat ke LWP, thread tersebut mungkin harus menunggu untuk dilampirkan ke LWP sebelum berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terlampir ke LWP) dan kemudian harus memblokir (misalnya harus melakukan I/O, telah dipreempt oleh thread real-time prioritas yang lebih tinggi, menunggu kunci eksklusi bersama, dll.) Saat thread real-time diblokir, LWP yang terlampir kepadanya telah ditugaskan ke thread lain. Ketika thread real-time tersebut dijadwalkan untuk berjalan lagi, ia harus menunggu untuk dilampirkan ke LWP. Dengan mengikat sebuah LWP ke thread real-time, Anda memastikan thread tersebut akan dapat berjalan dengan penundaan minimal setelah dijadwalkan.
