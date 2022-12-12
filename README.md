# Praktikum-8

Nama : Syifa Aurellia Rahma

NIM : 312210009

Kelas : TI.22.A1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Praktikum 8|[Click Here](#Praktikum-8)|
|2|Diagram Class Praktikum 8|[Click Here](#Diagram-Class-Praktikum-8)|
|3|Flowchart Praktikum 8|[Click Here](#flowchart-praktikum-8)|

## Praktikum 8

### Rumus :
    class mahasiswa:
        def __init__(self, nim, nama, tugas, uts, uas):
            self.nim = nim
            self.nama = nama
            self.tugas = tugas
            self.uts = uts
            self.uas = uas

        def tambah(self,nim,nama,tugas,uts,uas):
            data.nim.append(nim)
            data.nama.append(nama)
            data.tugas.append(tugas)
            data.uts.append(uts)
            data.uas.append(uas)

        def lihat(self):
            for i in range(len(data.nama)):
                print("|", i+1, "  |", end="")
                print('{0:<25}'.format(self.nama[i]), end="")
                print("|", self.nim[i], end="")
                print(" |", self.tugas[i], end="")
                print("    |", self.uts[i], end="")
                print("  |", self.uas[i], " | ", end="")
                print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

        def ubah(self,nim,nama,tugas,uts,uas):
            self.nim[no] = nim
            self.nama[no] = nama
            self.tugas[no] = tugas
            self.uts[no] = uts
            self.uas[no] = uas

        def hapus(self):
            del self.nim[no]
            del self.nama[no]
            del self.tugas[no]
            del self.uts[no]
            del self.uas[no]

    data = mahasiswa([],[],[],[],[])

    while True:
        menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
        if menu == "t" or menu == "T":
           print("\nTambah Data")
           data.tambah(
               input("Masukkan NIM : "),
               input("Masukkan Nama : "),
               int(input("Nilai Tugas : ")),
               int(input("Nilai UTS : ")),
               int(input("Nilai UAS : "))
               )
           print("\nData berhasil ditambahkan")

        elif menu == "l" or menu == "L":
            print("\nDaftar Nilai")
            print("==========================================================================")
            print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
            print("==========================================================================")
            if len(data.nama) != 0:
                data.lihat()
            else:
                print("                         TIDAK ADA DATA                               ")
            print("==========================================================================")

        elif menu == "u" or menu == "U":
            print("\nUbah Data")
            ubah = input("Masukkan Nama : ")
            if ubah in data.nama:
               no = data.nama.index(ubah)
               print("Masukkan Data Yang Baru : ")
               data.ubah(
                   input("NIM : "),
                   input("Nama : "),
                   int(input("Nilai Tugas : ")),
                   int(input("Nilai UTS : ")),
                   int(input("Nilai UAS : "))
                   )
            else:
                print(ubah, "tidak ada di dalam data")

        elif menu == "h" or menu == "H":
            print("\nHapus Data")
            hapus = input("Masukkan Nama : ")
            if hapus in data.nama:
                no = data.nama.index(hapus)
                data.hapus()
                print("Data", hapus, "Berhasil dihapus")
            else:
                print(hapus, "tidak ada di dalam data")

        elif menu == "k" or menu == "K":
            print("\nTerimakasih\n")
            break

        else:
            print("\nPerintah yang dimasukkan salah!\n")
            
## Program :

![Screenshot (333)](https://user-images.githubusercontent.com/115867244/207099323-83638bdf-1c43-4080-b09f-89b93e41aafe.png)

![Screenshot (334)](https://user-images.githubusercontent.com/115867244/207099392-305bb303-e24a-45c1-8c71-98f9583925c1.png)

![Screenshot (335)](https://user-images.githubusercontent.com/115867244/207099514-6a26f8dd-0b61-42a8-998f-4387f1d0a9ef.png)

![Screenshot (337)](https://user-images.githubusercontent.com/115867244/207099702-a9452a90-3e61-4448-8c6f-c25bd24dd4d2.png)

![Screenshot (338)](https://user-images.githubusercontent.com/115867244/207099794-54699ffd-82a6-487a-9187-f0c58e736140.png)


## Hasil Run & Penjelasan Program :
- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP, kita harus menggunakan **def__init__ dan juga self.**

      class mahasiswa:
          def __init__(self, nim, nama, tugas, uts, uas):
              self.nim = nim
              self.nama = nama
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

      data = mahasiswa([],[],[],[],[])  

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nim,nama,tugas,uts,uas):
              data.nim.append(nim)
              data.nama.append(nama)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

- Ini tampilan jika kita menginput method : `Tambah()`

![Screenshot (344)](https://user-images.githubusercontent.com/115867244/207102699-51d49763-ebfb-43a6-a03c-48661b5492ee.png)

- Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan **TIDAK ADA DATA.**

      def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")
                  
- Ini tampilan jika kita menginput method : `Lihat()`

![Screenshot (345)](https://user-images.githubusercontent.com/115867244/207105956-d68a9e75-39df-45cd-9faf-c977b4cfe4fe.png)

- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nim,nama,tugas,uts,uas):
              self.nim[no] = nim
              self.nama[no] = nama
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas
              
- Ini tampilan jika kita menginput method : `Ubah()`

![Screenshot (346)](https://user-images.githubusercontent.com/115867244/207106942-53040157-0c18-4096-bdd9-50f966454fbb.png)

![Screenshot (347)](https://user-images.githubusercontent.com/115867244/207107063-70f06eb4-313f-4c54-9d71-18cd19b43917.png)

- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nim[no]
              del self.nama[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]
              
- Ini tampilan jika kita menginput method : `Hapus()`

![Screenshot (348)](https://user-images.githubusercontent.com/115867244/207107836-31039051-0e0c-436d-bcf6-6c9e88956311.png)


## Diagram Class Praktikum 8

![ss2](https://user-images.githubusercontent.com/115867244/207108605-1ff12848-fef7-422e-800f-c58a996206a0.png)

## Flowchart Praktikum 8

![206462353-41fd2d95-2329-4f92-9403-e679c5bc1784](https://user-images.githubusercontent.com/115867244/207111025-fea08892-8c22-4b7e-a0a8-733309aa3792.png)

## Sekian, Terima kasih
