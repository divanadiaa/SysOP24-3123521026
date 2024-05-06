### Hubungan Antara Arsitektur CPU dengan Arsitektur Komputer
- Arsitektur CPU adalah bagian penting dari arsitektur komputer secara keseluruhan. Arsitektur komputer mencakup desain dan struktur dari seluruh sistem komputer, termasuk CPU, memori, bus data, bus kontrol, dan perangkat I/O. CPU adalah otak dari komputer yang bertanggung jawab atas eksekusi instruksi-instruksi yang diberikan oleh program, pengolahan data, dan koordinasi semua aktivitas yang terjadi dalam sistem.
- Arsitektur CPU mencakup elemen-elemen seperti unit kontrol, unit pemrosesan aritmetika dan logika (ALU), unit pemrosesan floating point (FPU), dan register. Desain arsitektur CPU memengaruhi kinerja dan kemampuan komputer secara keseluruhan. Misalnya, beberapa arsitektur CPU dapat mengeksekusi beberapa instruksi secara bersamaan (pipelining atau multithreading), yang dapat meningkatkan throughput dan kinerja sistem secara keseluruhan.
- Arsitektur CPU juga berhubungan erat dengan arsitektur memori komputer. CPU berkomunikasi dengan memori untuk mengambil instruksi dan data yang diperlukan untuk menjalankan program. Desain antarmuka antara CPU dan memori mempengaruhi kecepatan dan efisiensi sistem. Oleh karena itu, pemilihan arsitektur CPU dan konfigurasi memori harus saling mendukung untuk mencapai kinerja yang optimal dalam suatu sistem komputer.


### FORKING, ORPHAN dan ZOMBIE

- Melakukan clonning repository https://github.com/ferryastika/operatingsystem.git

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


### FORK 1

- Masuk ke directory operatingsystem
```sh
$ cd operatingsystem
```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/eb626cd6-b08d-4f70-8522-7e4a4e04f4d5)


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

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8ac4fcc2-b780-4278-a923-0269b40aacaf)


- Simpan file (Ctrl + X)
```sh
$ g++ fork01.cpp -o fork01
```

- Jalankan kodenya
```sh
$ ./fork01
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/24084072-314c-4fe4-91a1-c966ff0d69b7)

Analisis : 

- [ ]  Program fork01 menggunakan beberapa panggilan sistem (system calls) dari C/C++ dan header file untuk mengakses fungsi-fungsi ini.
- [ ]  Header file sys/types.h dan unistd.h digunakan untuk mendeklarasikan tipe data dan fungsi yang digunakan dalam program.
- [ ]  Fungsi getpid() digunakan untuk mengambil PID dari proses saat ini dan menyimpannya dalam variabel mypid.
- [ ]  Fungsi getppid() digunakan untuk mengambil PID dari parent proses dan mencetaknya.
- [ ]  Fungsi getuid() digunakan untuk mengambil UID dari pemilik proses dan mencetaknya.
- [ ]  Loop for digunakan untuk mencetak informasi proses sebanyak tiga kali dengan jeda waktu 3 detik menggunakan fungsi sleep(3).
- [ ]  Setelah proses mencetak informasi, program akan berhenti selama 3 detik sebelum mencetak informasi lagi.
- [ ]  Program kemudian mengembalikan nilai 0, menandakan bahwa program selesai berjalan tanpa masalah.

### FORK 2

- Perintahnya sama dengan menjalankan fork01.cpp
- Masuk ke compiler fork02.cpp
```sh
$ nano fork02.cpp
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

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f1adff06-a861-4358-b9cb-1ec8ba37887e)

- Simpan file (Ctrl + X)
```sh
$ g++ fork02.cpp -o fork02
```

- Jalankan kodenya
```sh
$ ./fork02
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/09835123-8d1f-4a5c-9ecc-7f2d907a5745)

- Untuk menghentikan program menggunanakan (Ctrl + C)
Analisis :
- [ ] Program fork02 menggunakan panggilan sistem fork() untuk membuat proses baru. Setelah pemanggilan fork(), dua proses child dan parent akan berjalan secara paralel.
- [ ] Variabel childpid digunakan untuk menyimpan nilai pengembalian dari pemanggilan fork(). Nilai 0 akan disimpan dalam childpid jika proses saat ini adalah proses child, sementara PID dari proses child akan disimpan dalam childpid jika proses saat ini adalah proses induk.
- [ ] Selanjutnya, program masuk ke dalam loop while(1) yang akan berjalan terus menerus.
- [ ] Di dalam loop, program mencetak PID dari proses saat ini dan nilai dari variabel x. Variabel x awalnya diinisialisasi dengan nilai 5 dan akan bertambah setiap kali melalui loop.
- [ ] Setelah mencetak informasi, program berhenti selama 2 detik menggunakan fungsi sleep(2) sebelum melanjutkan ke iterasi berikutnya.

### FORK 3
- Perintahnya sama dengan menjalankan fork01.cpp dan fork02.cpp
- Masuk ke compiler fork03.cpp
```sh
$ nano fork03.cpp
```

- Masukkan kode fork03.cpp
```sh
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
   pid_t childpid;
   childpid = fork();
   for (int i = 0; i < 5; i++) {
   	cout << "This is process " << getpid() << endl;
   	sleep(2);
   }
   return 0;
}
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/470be792-e091-47aa-b21f-4ff3deaa6850)


- Simpan file (Ctrl + X)
```sh
$ g++ fork03.cpp -o fork03
```

- Jalankan kodenya
```sh
$ ./fork03
```

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/44442284-eca6-4f9d-9171-05e352451b3a)

Analisis : 
- [ ] Program fork03 menggunakan panggilan sistem fork() untuk membuat proses baru.
- [ ] Setelah pemanggilan fork(), kedua proses child dan parent akan memiliki kode yang sama. Kedua proses akan mencetak pesan "This is process <PID>" di loop for.
- [ ] Loop for dijalankan lima kali, sehingga pesan akan dicetak lima kali oleh setiap proses.
- [ ] Setelah mencetak pesan, program berhenti selama 2 detik menggunakan fungsi sleep(2) sebelum melanjutkan ke iterasi berikutnya atau selesai jika sudah mencapai batas iterasi.
- [ ] Kedua proses akan berjalan secara bersamaan, dan pesan-pesan akan dicetak secara bergantian antara kedua proses.

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

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/04fdcb5c-63d4-4898-95b6-5e1175e3a3cc)

- Simpan file (Ctrl + X)
```sh
$ gcc orphan.c -o orphan
```

- Jalankan kodenya
```sh
$ ./orphan
```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/592fc64a-79b8-4beb-9732-4c59f58ca5da)

Analisis : 
- [ ] Program ini menggunakan panggilan sistem fork() untuk menciptakan proses child. Ketika fork() dipanggil, dua proses akan dibuat: satu adalah proses parent, dan satu lagi adalah proses child.
- [ ] Jika proses yang dihasilkan oleh fork() adalah proses parent, maka nilai pid akan positif. Dalam hal ini, proses ini akan mencetak pesan sebagai proses parent dan kemudian mengeluarkan informasi tentang ID proses saat ini (getpid()).
- [ ] Jika proses yang dihasilkan oleh fork() adalah proses child, maka nilai pid akan menjadi 0. Dalam hal ini, proses ini akan mencetak pesan sebagai proses child, dan kemudian mengeluarkan informasi tentang ID proses saat ini (getpid()) dan ID proses parent (getppid()).
- [ ] Setelah mencetak informasi, proses child akan berhenti selama 10 detik menggunakan fungsi sleep(10).
- [ ] Selama tidur, proses parent mungkin telah selesai dieksekusi, sehingga menjadi proses orphan. Proses anak masih berjalan, tetapi memiliki proses lain sebagai parentnya.
- [ ] Setelah berhenti selesai, proses child mencetak informasi tentang ID proses saat ini dan ID proses parent lagi.Program kemudian berakhir.

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

![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/5ef90740-0a54-4d9f-bd2f-caf732f18fb9)

- Simpan file (Ctrl + X)
```sh
$ gcc orphan.c -o orphan
```

- Jalankan kodenya
```sh
$ ./zombie
```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/041b1bf1-cb89-4c68-bdef-acdc10744039)

Analisis :
- [ ] Program zombie menggunakan panggilan sistem fork() untuk membuat proses baru.
- [ ] Jika pemanggilan fork() berhasil, maka akan ada dua proses: proses parent dan proses child.
- [ ] Proses parent akan sleep selama 60 detik menggunakan fungsi sleep(60).
- [ ] Proses child langsung keluar menggunakan fungsi exit(0), sehingga proses child akan segera berakhir setelah dibuat.
- [ ] Jika proses child berakhir sebelum proses parent, proses child akan menjadi "zombie", yaitu proses yang sudah selesai tetapi masih ada di tabel proses sistem karena proses parent belum membaca status akhirnya.
- [ ] Pada akhirnya, setelah berhenti selama 60 detik, proses parent akan selesai dieksekusi dan sistem akan membersihkan proses "zombie" yang sudah selesai.

### Producer Consumer Problem
- Procedur Consumer Problem dalam sistem operasi melibatkan dua jenis proses yaitu produsen yang menghasilkan data atau sumber daya, dan konsumen yang mengambil data dari produsen. Mereka berinteraksi melalui buffer bersama, dengan tujuan menyelaraskan produksi dan konsumsi agar tidak terjadi kondisi buffer penuh atau kosong.
- Solusinya melibatkan penggunaan teknik sinkronisasi seperti semafor atau mutex untuk mengontrol akses ke buffer, sambil memperhatikan efisiensi dan mencegah deadlock atau starvation. Masalah ini memiliki aplikasi luas dalam sistem operasi dan pemrograman paralel, di mana koordinasi antara proses-paroses paralel sangat penting untuk mencegah masalah kelebihan atau kekurangan sumber daya.
