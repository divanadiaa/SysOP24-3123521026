## 1. Presentasi langkah langkah tentang siklus CPU (fetch, decode, execute), peran dari Bahasa pemrograman dan Compiler, serta peran dari Sistem Operasi.

**1. Siklus CPU (Fetch, Decode, Execute) :** 

Fetch (Ambil) : 

- [ ] CPU mengambil instruksi dari lokasi memori tertentu (alamat memori instruksi).
- [ ]  Instruksi diambil dari memori utama dan disalin ke dalam register instruksi di dalam CPU.

Decode (Dekode) : 

- [ ] Decoder instruksi menafsirkan dan mengimplementasikan instruksi.
- [ ] Instruksi saat ini dipegang, sementara program counter (PC) memiliki alamat dalam memori dari instruksi berikutnya yang akan dieksekusi.

Execute (Eksekusi) : 

- [ ] CPU menjalankan instruksi dengan mengakses data dari memori utama.
- [ ] Hasil eksekusi disimpan kembali ke memori atau register.

**2.  Peran Bahasa Pemrograman dan Compiler :** 

Bahasa pemrograman adalah alat yang memungkinkan programmer mengekspresikan logika dan algoritma dalam bentuk yang dapat dimengerti oleh manusia. Bahasa pemrograman memungkinkan penulisan kode sumber dengan lebih mudah dan lebih terstruktur.

Compiler mengubah kode sumber dalam bahasa pemrograman menjadi kode objek atau bahasa mesin yang dimengerti oleh komputer. Tugas kompilator adalah menerjemahkan kode program menjadi bahasa mesin berbentuk kode biner (0 dan 1). Compiler adalah jembatan penghubung antara programmer dan komputer melalui perintah pemrograman.

**Peran Sistem Operasi :** 

Sistem operasi bertindak sebagai penghubung antara perangkat keras dan perangkat lunak. Ia mengelola sumber daya sistem, seperti memori dan proses, serta menyediakan antarmuka bagi pengguna untuk berinteraksi dengan sistem. Dalam konteks eksekusi program, sistem operasi bertanggung jawab untuk : 
- Memuat instruksi dan data ke dalam memori utama.
- Menginisialisasi perangkat I/O dan file.
- Menangani eksekusi program, termasuk penjadwalan proses dan pengalihan eksekusi antara program.

## 3. Menjalankan VM Debian

**Melakukan Clone** 

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/af313d37-dc14-4716-bce4-fe25fdb226cf)

**Build Binaries**
 ```sh
$ make
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/d6ce9579-a7b6-43bd-a86b-671a5ceded78)
Analisis : Perintah $ make digunakan untuk membangun (compile) program atau proyek perangkat lunak dari kode sumber.

**Cleaning Old Build**
```sh
$ make clean
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/3d1dcd83-01a6-4a41-b48c-310b873cad65)
Analisis : Perintah  $ make clean digunakan untuk membersihkan berkas-berkas sementara dan objek-objek yang dihasilkan selama proses kompilasi.

**Install Binaries**
```sh
$ sudo make install
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/ededa995-8cc6-49ee-873d-6aa837ef9198)
Analisis : Perintah $ sudo make install digunakan untuk menginstal program yang telah berhasil dikompilasi ke dalam sistem.

**Uninstall Binaries**
```sh
$ sudo make uninstall
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/94f829ad-5615-4cfa-830c-eb6fe2fdcbec)
Analisis : Perintah $ sudo make uninstall digunakan untuk menghapus program yang sebelumnya telah diinstal ke dalam sistem.

**Usage**

- Percobaan ke 1
```sh
$ iops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/536a7641-2943-4ded-b733-0f7a26e4cbd5)

```sh
$ flops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/d1126428-61a7-4cdd-975f-3341529f7823)

- Percobaan ke 2
```sh
$ iops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c51ffa08-28e3-43fc-b954-83ea7cba6219)

```sh
$ flops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f90525ff-4698-45d8-927a-16ae6190f9d0)

- Percobaan ke 3
```sh
$ iops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8170e030-1079-46fc-8e06-f5cd8f9cf305)

```sh
$ flops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/a9d269ae-4b6a-4daa-a2eb-c4738c10df8f)

- Percobaan ke 4
```sh
$ iops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/62c2a24f-bbfd-4b44-b2c4-1af5ce76610c)

```sh
$ flops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8b39d119-9931-46b7-88e2-c4e28e69cbde)

- Percobaan ke 5
```sh
$ iops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/3bf29185-fbdd-4e62-85c9-6edd63dce49a)

```sh
$ flops64 $(nproc)
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/68d36eb0-c87e-4971-acb1-6967760b2023)

Analisis : 

IOPS (Input/Output Operations Per Second) digunakan untuk mengukur seberapa cepat sebuah sistem dapat menyelesaikan operasi masukan/keluaran dalam satu detik. Ini sering digunakan untuk mengukur kinerja disk dan sistem penyimpanan.
FLOPS (Floating Point Operations Per Second) digunakan untuk mengukur seberapa cepat sebuah sistem dapat menyelesaikan operasi bilangan floating point dalam satu detik. Ini merupakan metrik umum untuk mengukur kinerja komputasi numerik dan penggunaan CPU secara umum.

**Perbandingan Hasil Percobaan Eksekusi**

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/deab76d6-7863-489e-9967-9fff7284e87e)

Kesimpulan : 

Jika nilai IOPS tinggi, berarti menunjukkan bahwa sistem memiliki kinerja yang baik dalam menangani operasi masukan/keluaran, yang mungkin merupakan indikator kecepatan sistem penyimpanan.
Jika nilai FLOPS tinggi, berarti menunjukkan bahwa sistem memiliki kinerja yang baik dalam menangani operasi bilangan floating point, yang mungkin merupakan indikator kemampuan komputasi numerik dan penggunaan CPU.
