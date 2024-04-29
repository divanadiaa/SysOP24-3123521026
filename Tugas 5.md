### Perbedaan RISC dan CISC

| RISC | CISC |
| :---: | :---: |
| RISC adalah singkatan dari Komputer Set Instruksi yang Dikurangi. | CISC adalah singkatan dari Kompleks Instruksi Set Komputer. |
| Prosesor RISC memiliki instruksi sederhana yang memakan waktu sekitar satu siklus clock. Siklus jam rata-rata per instruksi (CPI) adalah 1,5. | Prosesor CSIC memiliki instruksi rumit yang memerlukan banyak jam untuk dieksekusi. Rata-rata siklus jam per instruksi (CPI) berada pada kisaran 2 dan 15. |
| Kinerja dioptimalkan dengan lebih fokus pada perangkat lunak. | Performa dioptimalkan dengan lebih fokus pada perangkat keras. |
| Tidak memiliki unit memori dan menggunakan perangkat keras terpisah untuk mengimplementasikan instruksi. | Memiliki unit memori untuk mengimplementasikan instruksi yang kompleks. |
| Set instruksi dikurangi yaitu hanya memiliki beberapa instruksi dalam set instruksi. Banyak dari instruksi ini yang sangat primitif. | Set instruksi memiliki beragam instruksi berbeda yang dapat digunakan untuk operasi kompleks. |
| Set instruksi memiliki beragam instruksi berbeda yang dapat digunakan untuk operasi kompleks. | CISC memiliki banyak mode pengalamatan yang berbeda dan dengan demikian dapat digunakan untuk merepresentasikan pernyataan bahasa pemrograman tingkat tinggi dengan lebih efisien. |
| Kompleksitas RISC terletak pada compiler yang menjalankan program. | Kompleksitasnya terletak pada mikroprogram. |
| Tidak memerlukan memori eksternal untuk perhitungan. | Memerlukan memori eksternal untuk perhitungan. |
| Mikroprosesor RISC yang paling umum adalah Alpha, ARC, ARM, AVR, MIPS, PA-RISC, PIC, Power Architecture, dan SPARC. | Contoh prosesor CISC adalah System/360, VAX, PDP-11, keluarga Motorola 68000, AMD, dan CPU Intel x86. |
| Arsitektur RISC digunakan dalam aplikasi kelas atas seperti pemrosesan video, telekomunikasi, dan pemrosesan gambar. | Arsitektur CISC digunakan dalam aplikasi kelas bawah seperti sistem keamanan, otomatisasi rumah, dll. |

### Hubungan Antara Arsitektur CPU dengan Arsitektur Komputer
- Arsitektur CPU adalah bagian penting dari arsitektur komputer secara keseluruhan. Arsitektur komputer mencakup desain dan struktur dari seluruh sistem komputer, termasuk CPU, memori, bus data, bus kontrol, dan perangkat I/O. CPU adalah otak dari komputer yang bertanggung jawab atas eksekusi instruksi-instruksi yang diberikan oleh program, pengolahan data, dan koordinasi semua aktivitas yang terjadi dalam sistem.
- Arsitektur CPU mencakup elemen-elemen seperti unit kontrol, unit pemrosesan aritmetika dan logika (ALU), unit pemrosesan floating point (FPU), dan register. Desain arsitektur CPU memengaruhi kinerja dan kemampuan komputer secara keseluruhan. Misalnya, beberapa arsitektur CPU dapat mengeksekusi beberapa instruksi secara bersamaan (pipelining atau multithreading), yang dapat meningkatkan throughput dan kinerja sistem secara keseluruhan.
- Arsitektur CPU juga berhubungan erat dengan arsitektur memori komputer. CPU berkomunikasi dengan memori untuk mengambil instruksi dan data yang diperlukan untuk menjalankan program. Desain antarmuka antara CPU dan memori mempengaruhi kecepatan dan efisiensi sistem. Oleh karena itu, pemilihan arsitektur CPU dan konfigurasi memori harus saling mendukung untuk mencapai kinerja yang optimal dalam suatu sistem komputer.


### FORKING, ORPHAN dan ZOMBIE

Clonning repository https://github.com/ferryastika/operatingsystem.git

![Screenshot 2024-04-29 182341](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/240a32d4-c8ae-416d-858f-0deebcdddec7)


- Install g++ sebelum menjalankan fork, orphan dan zombie
```
    $ su root
    $ sudo apt update
    $ sudo apt upgrade
    $ sudo apt install g++
 ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c74a53a6-b34b-4199-891c-19163ae31513)

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/6ab87c59-e201-4002-8c61-aeed47cce305)

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/67fd91e6-9655-46e0-8d27-826b8c19ddb8)


- Login kembali ke dalam user
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/1fde79a9-8ed8-4b7c-b88f-0dff97b984ff)

FORK 1
- Masuk ke compiler fork 1




  


