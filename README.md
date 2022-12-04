Nama    : ZIDNA SOLEDA ZULFA

NIM     : 312210031

Kelas   : TI.22.B1

# Bahasa pemrograman Pertemuan ke-11 Praktikum "SUB RUTIN / FUNGSI"
                                        

# Latihan 1

1. Masukan coding sebagai berikut lalu run dengan mengetikan perintah berikut

![image](https://user-images.githubusercontent.com/115474076/205486926-fa1b3ae0-71bf-40f0-a7cc-89181d4cad05.png)

2. Hasil output

![image](https://user-images.githubusercontent.com/115474076/205486943-055b0325-fff7-4823-9ecf-feb2d5aee71f.png)


# Tugas Praktikum

![image](https://user-images.githubusercontent.com/115474076/205487968-6c24cc6f-9d94-40fb-a51b-c72342b886b9.png)

1. masukan codingan sebagai berikut lalu run dengan mengetikan perintah berikut diterminal python

                      # import tabulate
                      from tabulate import tabulate

                      # Zidna Soleda Zulfa
                      # TI22B1

                      dataMahasiswa = {
                               'No' : [],
                               'NIM' : [],
                               'Nama' :[],
                               'Tugas' : [],
                               'UTS' : [],
                               'UAS' : [],
                               'Nilai Akhir' : []
                      }
                      no = 0
                      # fungsi untuk menampilkan data


                      # fungsi untuk menambahkan data


                      def tambah(no):
                          # menginput data
                          nim = int(input("Masukkan NIM : "))
                          nama = input("Masukkan Nama : ")
                          tugas = int(input("Masukkan Nilai Tugas : "))
                          uts = int(input("Masukkan Nilai UTS : "))
                          uas = int(input("Masukkan Nilai UAS : "))
                          nilai_akhir = (tugas * 30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)
                          # menambahkan data
                          dataMahasiswa['No'].append(no)
                          dataMahasiswa['NIM'].append(nim)
                          dataMahasiswa['Nama'].append(nama)
                          dataMahasiswa['UTS'].append(uts)
                          dataMahasiswa['Tugas'].append(tugas)
                          dataMahasiswa['UAS'].append(uas)
                          dataMahasiswa['Nilai Akhir'].append(nilai_akhir)
                          print("Data berhasil di tambahkan.")
                          # print(tabulate(dataMahasiswa, headers=[
                          #       'NIM', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))
                      def tampilkan():
                          print("Berikut data yang ada")
                          print(tabulate(dataMahasiswa, headers=[
                              'No', 'NIM', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))   

                      # fungsi untuk mengedit data
                      def ubah(nama):

                          # cek jika ada nama tersebut di dataMahasiswa
                          if nama in dataMahasiswa['Nama']:
                              # cari posisi indexnya lalu di simpan di nimIndex
                              namaindex = dataMahasiswa['Nama'].index(nama)
                              print("Pilih data yang mau di edit")
                              # perulangan mengedit data dalam bentuk pilihan
                              while True:
                                  editApa = int(input(
                                      "(1) Nim, \n (2) Nama, \n (3) Nilai Tugas, \n (4) Nilai UTS, \n (5) Nilai UAS, \n (0) Save Perubahan & exit \n :"))
                                  print("")
                                  break
                                  if editApa == 1:
                                      # mengubah nim
                                      newNim = int(input("Masukkan NIM :"))
                                      dataMahasiswa['NIM'][namaindex] = newNim
                                  elif editApa == 2:
                                      # mengubah nama
                                      newNama = int(input("Masukkan Nama :"))
                                      dataMahasiswa['Nama'][namaindex] = newNama
                                  elif editApa == 3:
                                      # mengubah nilai tugas dan nilai akhir
                                      newTugas = int(input("Masukkan Nilai Tugas :"))
                                      nilai_akhir = (newTugas * 30 / 100) + (dataMahasiswa['UTS'][namaindex] * 35 / 100) + (
                                      dataMahasiswa['UAS'][namaindex] * 35 / 100)
                                      dataMahasiswa['Tugas'][namaindex] = newTugas
                                      dataMahasiswa['Nilai Akhir'][namaindex] = nilai_akhir
                                  elif editApa == 4:
                                      # mengubah nilai uts dan nilai akhir
                                      newUTS = int(input("Masukkan Nilai UTS :"))
                                      nilai_akhir = (dataMahasiswa['Tugas'][namaindex] * 30 / 100) + (newUTS * 35 / 100) + (
                                      dataMahasiswa['UAS'][namaindex] * 35 / 100)
                                      dataMahasiswa['UTS'][namaindex] = newUTS
                                      dataMahasiswa['Nilai Akhir'][namaindex] = nilai_akhir
                                  elif editApa == 5:
                                      # mengubah nilai uas dan nilai akhir
                                      newUAS = int(input("Masukkan Nilai UAS :"))
                                      nilai_akhir = (dataMahasiswa['Tugas'][namaindex] * 30 / 100) + (dataMahasiswa['UTS'][namaindex] * 35 / 100) * (newUAS * 35 / 100)
                                      ataMahasiswa['UAS'][namaindex] = nilai_akhir
                                  elif editApa == 0:
                                      print("Perubahan data berhasil di simpan")
                                      break
                          else:
                              print("Data tidak di temukan")


                      # fungsi untuk menghapus data
                      def hapus(nama):
                          if nama in dataMahasiswa['Nama']:
                              namaIndex = dataMahasiswa['Nama'].index(nama)
                              # menghapus data berdasarkan position index pada nama
                              del dataMahasiswa['No'][namaIndex]
                              del dataMahasiswa['NIM'][namaIndex]
                              del dataMahasiswa['Nama'][namaIndex]
                              del dataMahasiswa['Tugas'][namaIndex]
                              del dataMahasiswa['UTS'][namaIndex]
                              del dataMahasiswa['UAS'][namaIndex]
                              del dataMahasiswa['Nilai Akhir'][namaIndex]
                              print("Data berhasil di hapus. ")
                          else:
                              print("Data tidak di temukan")
                      # fungsi untuk mencari data

                      # melakukan perulangan menggunakan while sampai user menekan huruf Q perulangan akan berhenti
                      while True:
                      # opsi input pilihan C,R,U,D,Q
                          tanya = input (
                           "(C) Menambahkan data,\n (R) Melihat semua data,\n (U) Update data,\n (D) Menghapus data,\n (Q) Keluar Program :") 
                          if tanya == "C":
                              while True:
                                  no += 1
                                  # memanggil fungsi tambah data dan memparsing data no
                                  tambah(no)
                                  tambahDataLagi = input("Tambah data lagi ? (y/n) :")
                                  if tambahDataLagi == 'n':
                                      break
                          elif tanya == "R":
                                  # menampilkan data dalam bentuk table menggunakan package tabulate
                                  tampilkan()
                                  print("")
                          elif tanya == "U":
                                  print(tabulate(dataMahasiswa, headers=[
                                      'No', 'NIM', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))
                                  nama = input("Masukkan nama yang mau di edit : ")
                                  print("")
                                  ubah(nama)
                          elif tanya == "D":
                                  print(tabulate(dataMahasiswa, headers=['No', 'NIM', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_gird"))
                                  nama = input("Masukkan nama yang mau di di hapus : ")
                                  print("")
                                  hapus(nama)
                          elif tanya == 'Q':
                                  print("")
                                  print("Anda telah keluar dari program")
                                  break

2. Hasil output

A. menambahkan data = Ketik C

![image](https://user-images.githubusercontent.com/115474076/205488175-9a10689a-b87c-4c5b-ab01-6c7ed4cfafa7.png)

B. Melihat data = Ketik R

![image](https://user-images.githubusercontent.com/115474076/205488262-7de0b350-b63e-4927-bdb2-05a0a338d31a.png)

C. Mengupdate data = Ketik U

![image](https://user-images.githubusercontent.com/115474076/205488377-f453ee08-9b97-48f4-9a0a-7e2fe50b3a64.png)

D. Menghapus data = Ketik D

![image](https://user-images.githubusercontent.com/115474076/205488408-4a66d267-273c-4d37-8b59-f38609d0d392.png)

E. Keluar program = Ketik Q

![image](https://user-images.githubusercontent.com/115474076/205488442-95e4d91f-25a9-4930-8e00-87920a13f95f.png)

3. Flowchart

![image](https://user-images.githubusercontent.com/115474076/205488555-de484ff6-6aa5-40e1-81d2-031d6cb14e1f.png)


