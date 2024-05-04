## Boot Process

![BootProcess drawio](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/a6157853-8e05-4f14-a0db-c928b00d1c4d)

Tahapan Boot Process :

- [ ] Power On/Initialization (Power On Self Test - POST): Saat komputer dinyalakan, proses inisialisasi dimulai dengan melakukan Power On Self Test (POST). POST memeriksa keberadaan dan kesehatan perangkat keras, termasuk RAM, prosesor, kartu grafis, dan perangkat penyimpanan.
- [ ] BIOS/UEFI Initialization: BIOS (Basic Input/Output System) atau UEFI (Unified Extensible Firmware Interface) akan diinisialisasi. BIOS/UEFI bertanggung jawab untuk mengonfigurasi dan memulai perangkat keras yang terhubung ke sistem.
- [ ] Boot Loader: Setelah BIOS/UEFI selesai, boot loader diaktifkan. Boot loader ini dapat berupa software seperti NTLDR (New Technology Loader) atau BOOTMGR (Boot Manager) untuk versi Windows yang lebih baru. Boot loader bertanggung jawab untuk memuat sistem operasi ke dalam memori.
- [ ] Kernel Loading: Boot loader memuat inti (kernel) dari sistem operasi ke dalam memori. Di Windows, kernel utama yang dimuat disebut "ntoskrnl.exe" (New Technology Operating System Kernel). Kernel ini bertanggung jawab atas manajemen sumber daya perangkat keras, manajemen proses, dan fungsi inti lainnya.
- [ ] Registry and Hardware Initialization: Setelah kernel dimuat, sistem operasi melakukan inisialisasi perangkat keras dan membaca konfigurasi dari Registry. Registry adalah database sentral yang menyimpan konfigurasi dan pengaturan sistem.
- [ ] Winlogon and User Session Initialization: Proses Winlogon dimulai untuk menangani proses otentikasi pengguna. User session dimulai, dan layar logon Windows muncul.
- [ ] Explorer.exe and User Interface Initialization: Setelah pengguna berhasil log masuk, proses "explorer.exe" dimulai. Explorer.exe bertanggung jawab untuk menginisialisasi antarmuka pengguna (Desktop) dan menjalankan berbagai proses dan layanan pengguna.
- [ ] Startup Programs and Services: Program dan layanan yang diatur untuk dimulai secara otomatis pada startup akan dijalankan.

## Identifikasi Laptop : HP 245 G8 5500U

![Screenshot 2024-03-03 144337](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/5633f99e-75d8-4a9c-b60a-8152a7e783fd)

Terdapat Processor, Clocks, Selection dan Cache di dalam CPU.

Processor : Menggunakan AMD Ryzen 5 Mobile 5500 with Radeon Graphics
Clocks : Memuat core speed untuk melihat kecepatan clock yaitu 1974.32 MHz
Cache : Menyimpan data yang digunakan, L1 data memiliki 6 x 32 KBytes 8-way, L1 Inst. memiliki 6 x 32KBytes 8-way, Level 2 memiliki 6 x 512 KBytes 8-way, dan Level 3 memiliki 2 x 4 MBytes
Selection : Memuat socket #1, cores 6 dan threads 12

![Screenshot 2024-03-03 144403](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/2fb9c3af-d909-4344-968e-7709d34a7602)

Terdapat Motherboard, BIOS dan Graphic Interface.

Motherboard : Memuat manufacturer yaitu HP dengan Model 8908, Bus Specs yaitu PCI-Express 3.0 (8.0 GT/s), Chipset AMD Ryzen SOC dan Southbridge AMD FCH
BIOS : Memuat Brand yaitu AMI, Version F.21 - AMD AGESA CezannePI-FP6 1.0.0.A
Graphic Interface : Memuat Bus PCI-Express 4.0, Current Link Width x16 dengan Max. Supported x16, Current Link Speed 8.0 GT/s dengan Max. Supported 16.0 GT/s

![Screenshot 2024-03-03 144436](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/3949b102-7ae6-4bbc-b708-b26483a24aae)

Terdapat  General dan Timings

General : Memuat Type yaitu DDR4 dengan Size 8GBtypes
Timings : Memuat DRAM Frequenzy yaitu 1594.8 MHz

![Screenshot 2024-03-03 144455](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/7bbe91d9-1887-49dc-a84c-1d1fc5866031)

Terdapat Memory Slot Selection dan Timings Table

Memory Slot Selection dan Timings Table: Memuat informasi memori slot selection terdapat 1 slot

![Screenshot 2024-03-03 144513](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/6e1c227d-8b44-4335-baee-f83c25556f18)

Terdapat Display Device Selection, GPU, Clocks dan Memory

Display Device Selection : Memiliki display AMD Radeon(TM) Graphics
GPU : Memuat Name, Board Manuf Hawlett-Packard
Clocks :  Terdapat GFX Core 400.0 MHz dan Memory 1200.0 MHz
Memory : Memuat size 512 MBytes

![Screenshot 2024-03-03 144533](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/91f93480-d1d8-49be-b7dc-18c0388313bf)

Terdapat CPU Single Thread, CPU Multi Thread, Benchmark Version 17.01.64, dan This Processor AMD Ryzen 5 7520U with Radeon Graphics

![Screenshot 2024-03-03 144552](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/7b962b83-28f1-4d51-8e0b-110d6cf0916b)

Terdapat About CPU-Z, Windows Version menggunakan Microsoft Windows 11 Home Single Language (x64) Version 22H2, Build 22621.3155, DirectX 12.0, dan Tools
