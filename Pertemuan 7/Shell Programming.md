## TUGAS PENDAHULUAN:

## Jawablah pertanyaan-pertanyaan di bawah ini :

1. Apa yang dimaksud redirection?
Jawab : *Redirection* adalah teknik dalam sistem operasi, khususnya di shell Linux atau Unix, yang digunakan untuk mengalihkan input dan output dari perintah. Ini memungkinkan Anda untuk mengirim output dari satu perintah ke file atau perintah lain, atau mengambil input dari file bukan dari keyboard.
2. Apa yang dimaksud pipeline?
Jawab : *Pipeline*, dalam konteks sistem operasi seperti Unix dan Linux, adalah serangkaian proses yang dirantai bersama, di mana output dari satu proses (stdout) secara langsung menjadi input (stdin) untuk proses berikutnya. Ini memungkinkan untuk menggabungkan beberapa perintah sederhana untuk melakukan tugas yang lebih kompleks.
4. Apa yang dimaksud perintah di bawah ini :
    echo, cat, more, sort, grep, wc, cut, uniq
Jawab : 
- echo : Perintah yang digunakan untuk menampilkan string atau hasil dari perintah lain ke output standar (biasanya layar).
- cat : Perintah yang digunakan untuk membaca file dan menampilkan isinya di layar terminal.
 - sort : Perintah yang digunakan untuk mengurutkan baris teks dalam file teks.
 - grep : Perintah yang digunakan untuk mencari pola tertentu dalam file teks dan menampilkan baris yang cocok.
 - wc : Singkatan dari "word count", perintah yang digunakan untuk menghitung jumlah baris, kata, karakter, dan byte dalam file teks.
 - cut : Perintah yang digunakan untuk memotong bagian dari baris teks di file teks.
 - uniq : Perintah yang digunakan untuk menyaring atau melaporkan baris berulang dalam file teks

## PERCOBAAN:

1. Login sebagai user.
2. Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
3. Selesaikan soal-soal latihan.


## Percobaan 1 : File descriptor

1. Output ke layar (standar output), input dari system (kernel)
    ```
    $ ps
    ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/e64c3cd4-d1d2-4e92-9801-ddd85172d7b5)

Analisis : Perintah $ ps untuk menampilkan daftar proses yang sedang berjalan di sistem. Perintah ini digunakan untuk memberikan informasi tentang proses-proses yang sedang berjalan, seperti ID proses (PID), pengguna yang menjalankan proses, penggunaan CPU, dan status proses.

2. Output ke layar (standar output), input dari keyboard (standard input)
   ```
    $ cat
    hallo, apa khabar
    hallo, apa khabar
    exit dengan ^d
    exit dengan ^d
    [Ctrl-d]
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c254080a-a99f-485a-b784-df3a41745d8d)

Analisis : Perintah $ cat digunakan untuk menampilkan isi dari suatu file atau menggabungkan isi beberapa file dan mencetaknya ke layar. 

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
   ```
   $ mkdir mydir
   $ mkdir mydir **(Terdapat pesan error)**
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f9812e3e-6aec-4c95-80f5-aea329e43067)

Analisis : Pada perintah pertama, $ mkdir mydir, membuat direktori baru dengan nama "mydir" menggunakan perintah mkdir. Ini adalah perintah untuk membuat direktori baru di sistem file. Namun, pada perintah kedua, $ mkdir mydir (kemungkinan memiliki spasi ekstra), jika direktori dengan nama yang sama (mydir) sudah ada, maka perintah tersebut akan menghasilkan pesan error. Pesan error tersebut kemungkinan akan mencantumkan bahwa direktori tersebut sudah ada.

## Percobaan 2 : Pembelokan (redirection)
1. Pembelokan standar output
   ```
    $ cat 1> myfile.txt
    Ini adalah teks yang saya simpan ke file myfile.txt
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/12981e31-4e7c-4b0d-8995-59a93ad3abf6)

Analisis : Perintah $ cat 1> myfile.txt digunakan untuk membuat file baru dengan nama myfile.txt dan menunggu input dari pengguna. Apabila mengetikkan teks setelah menjalankan perintah ini, teks tersebut akan disimpan ke dalam file myfile.txt.

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
   ```
    $ cat 0< myfile.txt
    $ cat myfile.txt
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/95493074-77e3-421a-b564-c65811c50bbf)

Analisis : Perintah $ cat 0< myfile.txt dan $ cat myfile.txt digunakan untuk membaca isi dari file myfile.txt dan menampilkannya di layar terminal. 

3. Pembelokan standar error untuk disimpan di file
   ```
    $ mkdir mydir (Terdapat pesan error)
    $ mkdir mydir 2> myerror.txt
    $ cat myerror.txt
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/d77ed673-0f49-4119-aa63-e7015d466b5b)

Analisis : Pada perintah $ mkdir mydir pertama, membuat direktori baru bernama "mydir". Jika direktori dengan nama yang sama sudah ada, perintah tersebut akan menghasilkan pesan error. Namun, pada perintah kedua, $ mkdir mydir 2> myerror.txt, menggunakan operator pembelokan (2>) untuk membelokkan standard error (stderr) dari perintah mkdir ke dalam file yang disebut myerror.txt. Ini berarti pesan error yang dihasilkan oleh perintah akan disimpan dalam file tersebut dan tidak akan ditampilkan di layar.

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
   ```
    $ ls filebaru (Terdapat pesan error)
    $ ls filebaru 2> out.txt
    $ cat out.txt
    $ ls filebaru 2> out.txt 2>&
    $ cat out.txt
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/9ed27b08-8f91-4f11-9ac8-682cc3cf6f58)

Analisis : Perintah $ ls digunakan untuk menampilkan isi direktori. Jika filebaru tidak ada, akan muncul pesan error. Mengarahkan stderr (standard error) ke file out.txt dengan 2> akan menyimpan pesan error tersebut ke dalam file. Perintah cat out.txt akan menampilkan isi dari out.txt, termasuk pesan error yang disimpan. Sintaks 2>& tidak benar; jika ingin mengarahkan stdout dan stderr ke file yang sama, gunakan > out.txt 2>&1.

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
   ```
   $ echo “mencoba menulis file” 1> baru
   $ cat filebaru 2> baru 1>&
   $ cat baru
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8fd37155-c927-4de5-9a72-6e626e308834)

Analisis :  $ echo "mencoba menulis file" 1> baru untuk menulis teks ke dalam file "baru" menggunakan output standar (stdout). $ cat filebaru 2> baru 1>&2 untuk mencoba menampilkan isi dari file "filebaru." Jika ada pesan error, pesan tersebut akan disimpan di dalam file "baru" karena output standar error (stderr) dialihkan ke file "baru." $ cat baru untuk menampilkan isi dari file "baru," yang mungkin berisi output standar atau pesan error yang dihasilkan oleh perintah sebelumnya.

6. Notasi >> (append)
   ```
   $ echo “kata pertama” > surat
   $ echo “kata kedua” >> surat
   $ echo “kata ketiga” >> surat
   $ cat surat
   $ echo “kata keempat” > surat
   $ cat surat
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/a5d80502-4cec-48c9-aa01-84f9ca37f6f7)

Analisis : $ echo "kata pertama" > surat untuk membuat file "surat" dan menulis "kata pertama" ke dalamnya. $ echo "kata kedua" >> surat untuk menambahkan "kata kedua" ke dalam file "surat". $ echo "kata ketiga" >> surat untuk menambahkan "kata ketiga" ke dalam file "surat". $ cat surat untuk menampilkan isi "surat" (berisi "kata pertama", "kata kedua", dan "kata ketiga"). $ echo "kata keempat" > surat untuk membuat ulang file "surat" dan menulis "kata keempat" ke dalamnya, menggantikan isi sebelumnya. $ cat surat untuk menampilkan isi terbaru "surat" (berisi hanya "kata keempat").

7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
   ```
   $ cat <<++
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   ++
   $ cat <<%%%
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   %%%
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/b0db954f-59c8-4b0d-a0ac-756e2e3d352f)

Analisis :  Pada kedua perintah cat di atas, notasi here document (<<++ dan <<%%%) digunakan untuk memasukkan teks ke dalam perintah cat tanpa menggunakan file eksternal. Teks yang dimasukkan di antara ++ dan %%%' akan dianggap sebagai input untuk perintah cat`.

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
  ```
  $ cat myfile.txt – surat
  ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/bf137765-8485-4a24-9847-9126411dd70a)

Analisis :  Menggabungkan isi myfile.txt, input dari keyboard, dan isi file surat untuk ditampilkan oleh cat. Prosesnya sebagai berikut: menampilkan isi myfile.txt, menunggu input dari keyboard, dan menampilkan isi dari file surat. Jadi, outputnya akan mencakup konten myfile.txt, input dari keyboard, dan isi dari file surat.

## Percobaan 3 : Pipa (pipeline)

1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
   ```
   $ who
   $ who | sort
   $ who | sort –r
   $ who > tmp
   $ sort tmp
   $ rm tmp
   $ ls –l /etc | more
   $ ls –l /etc | sort | more
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/456228d5-c5e3-414a-a9ff-d09ece10a3cd)
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/8e96179c-68b6-4e5e-910b-43f9694ee60c)
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/f9c86185-1d47-4b52-86d9-aba04e72d443)

Analisis : Dua perintah pertama (who dan who | sort) digunakan untuk menampilkan dan mengurutkan daftar pengguna yang login. Dua perintah berikutnya (who | sort -r dan who > tmp) mengurutkan daftar pengguna secara terbalik dan menyimpannya dalam file sementara "tmp". Perintah selanjutnya (sort tmp) mengurutkan isi file "tmp" yang berisi daftar pengguna. Dua perintah terakhir (ls -l /etc | more dan ls -l /etc | sort | more) menampilkan isi direktori "/etc" dengan format panjang, dan hasilnya dapat diurutkan sebelum ditampilkan halaman per halaman.

2. Untuk membelokkan standart output ke file, digunakan operator ">"
   ```
   $ echo hello
   $ echo hello > output
   $ cat output
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/7902c72b-e103-4f78-92cf-b9cb39de94cf)

Analisis : Perintah pertama mencetak "hello" di terminal, perintah kedua menyimpan "hello" ke dalam file "output", dan perintah ketiga menampilkan isi dari file "output", yang berisi "hello".

3. Untuk menambahkan output ke file digunakan operator ">>"
   ```
   $ echo bye >> output
   $ cat output
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/d5c11fa3-f9f6-40b6-a65a-e5c2f4247b14)

Analisis : $ echo bye >> output untuk menambahkan teks "bye" ke dalam file bernama "output" tanpa menghapus isinya yang sudah ada sebelumnya. Jika file "output" belum ada, maka akan dibuat. $ cat output untuk menampilkan isi dari file "output". Outputnya akan mencakup "hello" (dari perintah sebelumnya) dan "bye" (dari perintah saat ini).
 
4. Untuk membelokkan standart input digunakan operator "<"
   ```
   $ cat < output
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/7108d537-a827-4ebb-8332-ec8065f11ab4)

Analisis : : $ cat < output untuk menggunakan operator < untuk mengalirkan isi dari file "output" ke perintah cat sebagai standar input. Ini akan menampilkan isi dari file "output" menggunakan perintah cat.

5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
   ```
   $ cat < output > out
   $ cat out
   $ cat < output >> out
   $ cat out
   $ cat < output > output
   $ cat output
   $ cat < out >> out (Proses tidak berhenti)
   [Ctrl-c]
   $ cat out
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/bb6cb7ba-2d2c-47fd-98fc-ed03e4a5f309)

Analisis : $ cat < output > out untuk membaca isi "output" dan menyimpannya di "out". $ cat < output >> out untuk membaca lagi isi "output" dan menambahkannya ke "out". $ cat < output > output untuk menggantikan isi "output" dengan dua baris dari "output" yang asli. $ cat < out >> out untuk mencoba menambahkan isi "out" ke "out" (proses tanpa akhir). Dihentikan dengan [Ctrl-c] dan $ cat out untuk menampilkan isi "out".

## Percobaan 4 : Filter
1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
   ```
    $ w –h | grep <user>
    $ grep <user> /etc/passwd
    $ ls /etc | wc
    $ ls /etc | wc –l
    $ cat > kelas1.txt
    Badu
    Zulkifli
    Yulizir
    Yudi
    Ade
    [Ctrl-d]
    $ cat > kelas2.txt
    Budi
    Gama
    Asep
    Muchlis
    [Ctrl-d]
    $ cat kelas1.txt kelas2.txt | sort
    $ cat kelas1.txt kelas2.txt > kelas.txt
    $ cat kelas.txt | sort | uniq
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/12f0292f-d01e-4df4-889d-6a46730b2bfa)
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/aa4dff4c-2cb8-4126-9fa9-02046d5103a0)

Analisis : Dua perintah pertama (w -h | grep <user> dan grep <user> /etc/passwd) mencari informasi tentang pengguna dengan nama "<user>" yang sedang login. Dua perintah berikutnya (ls /etc | wc dan ls /etc | wc -l) memberikan statistik tentang jumlah file dan direktori di "/etc". Dua perintah selanjutnya (cat > kelas1.txt ... dan cat > kelas2.txt ...) membuat file "kelas1.txt" dan "kelas2.txt" dengan daftar nama. Perintah berikutnya (cat kelas1.txt kelas2.txt | sort) menggabungkan dan mengurutkan daftar nama dari dua file tersebut. Dua perintah terakhir (cat kelas1.txt kelas2.txt > kelas.txt dan cat kelas.txt | sort | uniq) menggabungkan nama-nama dari dua file ke dalam satu file "kelas.txt", dan kemudian menampilkan nilai unik dari file tersebut setelah diurutkan.

## LATIHAN:

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output   ke file baru.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/9dd10d66-4952-4d96-9337-778620db9810)

Analisis : $ ls -l file.txt adalah perintah untuk menampilkan detail file file.txt, seperti pemiliknya, izin, ukuran, dan lain-lain. $ cat file.txt adalah perintah untuk menampilkan isi dari file file.txt.

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/4e60195c-f917-46b4-aa80-de7d4102ef0d)

Analisis : Perintah $ cat /etc/passwd >> file.txt digunakan untuk menyalin isi dari file /etc/passwd dan menambahkannya ke akhir file yang disebut file.txt. Jadi, itu tidak akan menampilkan isi apa pun pada layar, tetapi akan menambahkan isi file /etc/passwd ke dalam file file.txt. Setelah menjalankan perintah tersebut, jika Anda mencoba $ cat file.txt, itu akan menampilkan isi file file.txt, yang sekarang berisi konten dari /etc/passwd serta teks "digunakan untuk", yang mungkin sudah ada sebelumnya dalam file tersebut.

3. Urutkan file baru dengan cara membelokkan standard input.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/d7d0161b-89eb-467f-9eaf-06a17a8f3e47)

Analisis : Perintah $ sort < file.txt digunakan untuk mengurutkan baris-baris dalam file file.txt secara alfabetis dan kemudian menampilkannya. Jadi, itu akan mengurutkan teks dalam file file.txt dan menampilkan hasilnya di layar.

4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/ae56b0f0-7a86-4c48-879c-eb78e416ba19)

Analisis : Perintah $ cat file.txt > baru.urut digunakan untuk menyalin isi dari file.txt ke dalam file baru yang disebut baru.urut. Ini tidak akan menampilkan isi apa pun pada layar, tetapi akan membuat salinan isi file.txt ke dalam baru.urut. Ketika menjalankan $ cat baru.urut, itu akan menampilkan isi dari file baru.urut, yang merupakan salinan isi dari file.txt.

5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/b533d48e-b0d9-4dd9-973a-91ae817f81de)

Analisis : $ mkdir latihan2 untuk perintah pertama untuk membuat direktori "latihan2". 2> rmdirerror.txt untuk mengarahkan standard error dari perintah pertama ke file "rmdirerror.txt". && untuk operator logika "dan" yang menjalankan perintah berikutnya hanya jika perintah sebelumnya berhasil. mkdir latihan2 untuk perintah kedua untuk membuat direktori "latihan2" lagi. 2>> rmdirerror.txt untuk mengarahkan standard error dari perintah kedua ke file "rmdirerror.txt" tanpa menghapus isi sebelumnya.

6. Urutkan kalimat berikut :
   ```
   Jakarta
   Bandung
   Surabaya
   Padang
   Palembang
   Lampung
   ```
  Dengan menggunakan notasi **here document (<@@@ ...@@@)** . [HINT](https://www.geeksforgeeks.org/how-to-use-here-document-in-bash-programming/)
  
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/7ae9d8eb-2eef-43ba-9109-1a92f29c3c3c)

Analisis : Perintah $ sort <<@@@ digunakan untuk mengurutkan baris-baris teks yang diberikan sebagai input. Tanda @@@ digunakan sebagai delimiter atau penanda awal dan akhir dari blok teks yang akan diurutkan. Ini adalah salah satu cara untuk memberikan input kepada perintah sort, yang memungkinkan untuk mengurutkan baris-baris teks yang diberikan tanpa perlu menyimpannya dalam file terlebih dahulu.

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/c835c4c5-67f9-4bf2-a5fe-0aab2813d2e9)

Analisis : Perintah wc digunakan untuk menghitung jumlah kata, baris, dan byte dalam file atau teks yang diberikan. Dalam kasus ini, cat baru.urut digunakan untuk menampilkan isi file baru.urut, dan kemudian outputnya diarahkan ke perintah wc untuk dihitung. Berikut adalah analisis output untuk setiap perintah:
wc: Ini akan mengembalikan tiga angka, masing-masing mewakili jumlah baris, kata, dan byte dalam teks yang diberikan.
wc -l: Ini hanya akan menghitung jumlah baris dalam teks yang diberikan.
wc -c: Ini akan menghitung jumlah byte dalam teks yang diberikan.
wc -w: Ini akan menghitung jumlah kata dalam teks yang diberikan.

8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
   ```
    $ cat > hello.txt
    dog cat
    cat duck
    dog chicken
    chicken duck
    chicken cat
    dog duck
    [Ctrl-d]
    $ cat hello.txt | sort | uniq
    $ cat hello.txt | grep “dog” | grep –v “cat”
   ```
![image](https://github.com/divanadiaa/SysOP24-3123521026/assets/149218147/dc53d464-61f8-4821-bc44-501679c88581)

Analisis : Perintah pertama membuat file "hello.txt" dengan beberapa baris teks. Perintah kedua mengurutkan dan menghapus duplikat dari isi file "hello.txt". Perintah ketiga mencari baris yang mengandung kata "dog" dan menghindari baris yang mengandung kata "cat" dari isi file "hello.txt".

## Kesimpulan
Praktikum ini memberikan dasar yang kuat untuk memahami operasi input dan output di lingkungan Linux, yang merupakan keterampilan esensial untuk administrasi sistem dan pengelolaan file dalam sistem operasi Linux. Berikut adalah kesimpulan singkat dari praktikum ini :
- Input dan Output Standar: Perintah-perintah dasar seperti echo, cat, dan ls digunakan untuk menangani input dan output standar.
- Pembelokan Input dan Output: Operator < digunakan untuk membelokkan input dari file. Operator > digunakan untuk membelokkan output ke file. Operator >> digunakan untuk menambahkan output ke file tanpa menghapus isinya. Operator | (pipa) digunakan untuk mengalirkan output dari satu perintah ke perintah lainnya.
- Pembelokan Input dan Output Gabungan: Dapat mengkombinasikan pembelokan input dan output, tetapi harus hati-hati untuk menghindari penggunaan nama file yang sama.
- Notasi Here Document (<<): Digunakan untuk memberikan input langsung dalam script atau perintah.
- Perintah wc: Digunakan untuk menghitung jumlah baris, kata, dan karakter dari sebuah file.
- Perintah sort dan uniq: sort digunakan untuk mengurutkan baris-baris dalam file. uniq digunakan untuk menghapus baris duplikat.
- Perintah grep: Digunakan untuk mencari pola dalam teks. Opsi -v digunakan untuk mengecualikan pola tertentu.
- Penggunaan Piping: Operator pipa (|) digunakan untuk mengalirkan output dari satu perintah ke perintah lainnya.
