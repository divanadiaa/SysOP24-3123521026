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


**FORK 1**

- Masuk ke compiler fork01.cpp
```sh
$ nano fork01.cpp
```
- Masukkan kode fork01.cpp
```sh
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>


/* getpid() adalah system call yg dideklarasikan pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t mypid;
	uid_t myuid;
	for (int i = 0; i < 3; i++) {
		mypid = getpid();
		cout << "I am process " << mypid << endl;
		cout << "My parent process ID is " << getppid() << endl;
		cout << "The owner of this process has uid " << getuid()
	<< endl;
/* sleep adalah system call atau fungsi library
yang menghentikan proses ini dalam detik
*/
	sleep(3);
	}
return 0;
}
```

![Screenshot 2024-04-30 002233](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/83f1290e-8810-457c-8524-6a9251c1a3c3)

- Simpan file (Ctrl + X), kemudian ubah .cpp menjadi .exe
```sh
$ g++ fork01.cpp -o fork01.exe
```

- Jalankan kodenya
```sh
$ ./fork01.exe
```

![Screenshot 2024-04-30 002830](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/bb2cdbee-600b-4ce5-851c-56a8c4164742)

**FORK 2**

- Perintahnya sama dengan menjalankan fork01.cpp
- Masuk ke compiler fork01.cpp
```sh
$ nano fork01.cpp
```

- Masukkan kode fork02.cpp
```sh
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	int x = 5;
	childpid = fork();

	while (1) {
		cout << "This is process ID" << getpid() << endl;
		cout << "In this process the value of x becomes " << x << endl;	
		sleep(2);
		x++;
	}
	return 0;
}
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/47d9abf7-4c3d-473f-a721-485851c61e0c)

- Simpan file (Ctrl + X), kemudian ubah .cpp menjadi .exe
```sh
$ g++ fork02.cpp -o fork02.exe
```

- Jalankan kodenya
```sh
$ ./fork02.exe
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/fa4fc856-4926-452d-bd00-76f7a076f510)

- Untuk menghentikan program menggunanakan (Ctrl + C)

**FORK 3**
- Perintahnya sama dengan menjalankan fork01.cpp dan fork02.cpp
- Masuk ke compiler fork01.cpp
```sh
$ nano fork01.cpp
```

- Masukkan kode fork02.cpp
```sh
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	int x = 5;
	childpid = fork();

	while (1) {
		cout << "This is process ID" << getpid() << endl;
		cout << "In this process the value of x becomes " << x << endl;	
		sleep(2);
		x++;
	}
	return 0;
}
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/429d5a07-c7ac-41b7-921d-58eb57741168)


- Simpan file (Ctrl + X), kemudian ubah .cpp menjadi .exe
```sh
$ g++ fork03.cpp -o fork03.exe
```

- Jalankan kodenya
```sh
$ ./fork03.exe
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/4870737e-2370-4969-9cfa-b392d4401235)

**ORPHAN**

- Masuk ke compiler orphan.c
```sh
$ nano orphan.c
```

- Masukkan kode orphan.c
```sh
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
	// fork() Create a child process

	int pid = fork();
	if (pid > 0)
	{
		//getpid() returns process id
		// while getppid() will return parent process id
		printf("Parent process\n");
		printf("ID : %d\n\n",getpid());
	}
	else if (pid == 0)
	{
		printf("Child process\n");
		// getpid() will return process id of child process
		printf("ID: %d\n",getpid());
		// getppid() will return parent process id of child process
		printf("Parent -ID: %d\n\n",getppid());

		sleep(10);

		// At this time parent process has finished.
		// So if u will check parent process id 
		// it will show different process id
		printf("\nChild process \n");
		printf("ID: %d\n",getpid());
		printf("Parent -ID: %d\n",getppid());
	}
	else
	{
		printf("Failed to create child process");
	}
	
	return 0;
}

/* https://www.includehelp.com/c-programs/orphan-process.aspx */
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/57326227-2f29-4e7d-86d3-6410d60f1e48)

- Simpan file (Ctrl + X), kemudian ubah .c menjadi .exe
```sh
$ g++ orphan.c -o orphan.exe
```

- Jalankan kodenya
```sh
$ ./orphan.exe
```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/098f9a34-32c5-4d68-8860-d3e171347192)


**ZOMBIE**
- Masuk ke compiler zombie.c
```sh
$ nano zombie.c
```

- Masukkan kode zombie.c
```sh
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>
int main ()
{
  pid_t child_pid;

   /* Create child*/
  child_pid = fork ();
  if (child_pid > 0) {

    /* Parent process */
    sleep (60);
  }
  else {

    /*Child process. Exit immediately. */
    exit (0);
  }
  return 0;
}

/*ps -e -o pid,ppid,stat,cmd */
```
* Lalu file 'c' menjadi 'exe'
```sh
$ g++ zombie.c -o zombie.exe
```
* Menjalankan Source codenya
```sh
$ ./zombie.exe
``` 

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8d85bff4-a57c-44cf-ac10-a9fe1fa87e12)

- Simpan file (Ctrl + X), kemudian ubah .c menjadi .exe
```sh
$ g++ zombie.c -o zombie.exe
```

- Jalankan kodenya
```sh
$ ./zombie.exe
```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/947896e9-ed90-4ef4-9ebd-02ae5f79b224)


### Producer Consumer Problem
- Procedur Consumer Problem dalam sistem operasi melibatkan dua jenis proses yaitu produsen yang menghasilkan data atau sumber daya, dan konsumen yang mengambil data dari produsen. Mereka berinteraksi melalui buffer bersama, dengan tujuan menyelaraskan produksi dan konsumsi agar tidak terjadi kondisi buffer penuh atau kosong.
- Solusinya melibatkan penggunaan teknik sinkronisasi seperti semafor atau mutex untuk mengontrol akses ke buffer, sambil memperhatikan efisiensi dan mencegah deadlock atau starvation. Masalah ini memiliki aplikasi luas dalam sistem operasi dan pemrograman paralel, di mana koordinasi antara proses-paroses paralel sangat penting untuk mencegah masalah kelebihan atau kekurangan sumber daya.
