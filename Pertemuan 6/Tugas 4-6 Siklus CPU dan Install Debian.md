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

![Siklus CPU 1](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/9423aa12-ffad-486a-acb2-e5b5da134364)

Analisis:

- [ ] LOAD [10]: Instruksi ini memuat nilai dari lokasi memori dengan alamat 10 ke dalam register.
- [ ] ADD [11]: Instruksi ini menambahkan nilai dari lokasi memori dengan alamat 11 ke dalam register.
- [ ] STORE [12]: Instruksi ini menyimpan hasil penjumlahan ke dalam lokasi memori dengan alamat 12.
- [ ] LOAD X: Instruksi ini memuat nilai dari variabel X ke dalam register.
- [ ] ADD Y: Instruksi ini menambahkan nilai dari variabel Y ke dalam register.
- [ ] STORE Z: Instruksi ini menyimpan hasil penjumlahan ke dalam variabel Z.

Jadi, rangkaian instruksi assembly tersebut melakukan operasi penjumlahan antara nilai X dan Y, lalu menyimpan hasilnya ke dalam variabel Z.


**Ilustrasi CPU**

![Siklus CPU 2](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/b4fbc7e6-c7dc-47b4-bbb3-f382606c3213)

 - CPU terbagi menjadi 3 yaitu Control Unit, Accumulator dan Arithmetic Logic Unit.
 - Registrasi Proses terdiri dari Program Counter, Current Instruction Register, Memory Address Register, dan Memory Data Register.

  **Langkah Langkah CPU**

 ![Siklus CPU 3](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c6087d26-a56f-4bd4-a08f-18186e84166d)
 ![Siklus CPU 4](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f7e128bc-8b68-48e1-bc5d-6f5772da2002)

  - Program Counter memegang informasi tentang alamat instruksi berikutnya yang akan dieksekusi.
 
 ![Siklus CPU 5](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/a36b413b-cfc5-465a-92ef-af8536d2bfb7)
 ![Siklus CPU 6](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/969315a0-eb9c-40fc-a3af-dc28e351d0b1)

  - Informasi alamat memori disimpan dalam MAR, data dari alamat memori diambil dan dimuat ke dalam MDR, sementara instruksi disimpan dalam CIR. Program Counter akan ditingkatkan sebanyak satu.

![Siklus CPU 7](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/855e1454-c510-4ebf-805f-4cfe58578756)
![Siklus CPU 8](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f23ad523-5da4-4950-99f3-dbd3714821d5)
![Siklus CPU 9](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/ea660f1a-db33-4f83-a4a9-d587c689d190)
![Siklus CPU 10](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/db87f8cd-4f93-4555-a6a6-92a7977fc12e)
![Siklus CPU 11](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c6df3660-6d17-4881-9561-0550b1ffdfce)

- Setelah instruksi LOAD 10 dieksekusi, CPU akan melanjutkan dengan mengambil data dari lokasi memori 10. Ini berarti Memory Address Register akan diperbarui dengan nilai 10. Selanjutnya, isi dari lokasi memori 10 akan diambil dan disimpan ke dalam Memory Data Register. Kemudian, data dari Memory Data Register akan disalin ke dalam Akumulator.

![Siklus CPU 12](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/e0aca54c-c4be-487b-a4c4-16db7198cf96)
![Siklus CPU 13](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/ba3fdbd0-9505-4d98-bf74-9468db281091)
![Siklus CPU 14](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/0e6391e8-6b26-475c-95b7-8a3c0af8f058)
![Siklus CPU 15](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/30df7d28-50e2-4384-90b8-9da2e7bf466a)

- Setelah Program Counter mengarahkan ke alamat memori yang baru, langkah selanjutnya adalah mengkopi alamat memori tersebut ke dalam Memory Address Register. Selanjutnya, konten dari alamat memori 101 akan diambil dan disimpan ke dalam Memory Data Register. Instruksi yang ada di alamat memori 101 juga akan disimpan di dalam Current Instruction Register. Setelah itu, Program Counter akan ditingkatkan sebesar 1 untuk menunjukkan instruksi selanjutnya.

![Siklus CPU 16](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/55fc1325-8144-4354-b62d-421ac0eb6fda)
![Siklus CPU 17](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/2418d3ae-0334-4715-912f-1ddc0ceb8ac5)
![Siklus CPU 18](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/31b09172-ea3a-47e9-8a2c-32cf43b7c113)
![Siklus CPU 19](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/0eba6634-5038-4281-afcc-a6dd2bda4bec)
![Siklus CPU 20](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/50b182a5-590c-47bd-9049-e071cef31449)
![Siklus CPU 21](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/86d78772-dc32-496e-bce5-ca35a52e896d)
![Siklus CPU 22](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/93fef39b-8084-40e2-8096-4367a4a0fb28)
![Siklus CPU 23](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/165a3830-aa23-4b26-bd82-349dc2196ebc)

- Setelah melakukan decode pada instruksi kedua dengan cara yang sama seperti instruksi pertama dan diteruskan ke Unit Kontrol, selanjutnya Unit Kontrol memahami bahwa instruksi ini adalah operasi penambahan (add), sehingga instruksi add diteruskan ke Unit Logika Aritmetika (ALU). Langkah selanjutnya, isi dari Akumulator akan disalin ke dalam ALU. Kemudian, alamat memori 11 akan disalin ke dalam Register Alamat Memori (MAR) karena akan diambil data dari alamat tersebut. Selanjutnya, isi dari alamat memori 11 akan disalin ke dalam Register Data Memori (MDR). Data dari MDR akan ditransfer ke dalam Akumulator. ALU akan menambahkan angka 3 dengan 2, dan hasilnya akan ditampilkan kembali ke Akumulator untuk menjaga total running.

![Siklus CPU 24](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/4fa853c4-5bd1-43ea-8811-be39c5ab8877)
![Siklus CPU 25](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c696c1a9-601a-4317-96e6-5f49575b4504)
![Siklus CPU 26](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/5cca9c4b-6e0e-4ae4-86c8-f4fcb395c8d4)
![Siklus CPU 27](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/6bd978a6-fe04-4e80-ab41-90511a855900)

- Alamat memori 102 akan disalin ke dalam Memory Address Register. Konten dari alamat memori 102 akan disalin ke dalam Memory Data Register. Instruksi tersebut akan dipindahkan ke dalam Current Instruction Register. Selanjutnya, Program Counter akan ditingkatkan sebesar 1 menjadi 103. Pada titik ini, biasanya akan ada instruksi halt atau stop yang menandakan akhir dari program.

![Siklus CPU 28](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/2d5bf834-c039-4283-b5e6-fb9059f3bbc1)
![Siklus CPU 29](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/85898a6a-5077-4673-a216-34d6d694218b)
![Siklus CPU 30](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/0bc44537-70bb-425e-aa14-0af56137dd88)
![Siklus CPU 31](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/a95ea35f-cb92-4e3e-baf0-f50f18ea0e91)

- Dekode instruksi ketiga dan simpan instruksi tersebut ke dalam Unit Kontrol. Karena instruksinya adalah untuk STORE, yang berarti menyimpan hasil ke alamat memori 12, maka lokasi memori 12 akan disimpan ke dalam Memory Address Register. Selanjutnya, hasil dari Akumulator akan dipindahkan ke dalam Memory Data Register, dan nilai dari Memory Data Register akan disalin ke lokasi memori 12. Dengan demikian, program ini selesai dieksekusi.

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
