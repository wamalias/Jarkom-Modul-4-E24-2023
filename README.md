# Jarkom-Modul-4-E24-2023

## Anggota Kelompok :
1. Wardatul Amalia Safitri (5025211006) </br>
2. Daffa Zimraan Hasan (5025221223)

## Pembagian Subnet
Dalam praktikum ini kamu menggunakan topologi sebagai berikut. </br>
![Screenshot 2023-11-28 235649](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/assets/111508713/95540f8f-c35d-47b2-b561-ac8b5153f5a9)
Kami membagi topologi ini menjadi 21 subnet. Berikut adalah gambaran pembagian subnet beserta nama subnet yang kami buat. </br>
![Screenshot 2023-11-30 221926](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/assets/111508713/e16d0c56-cd10-4fe2-9fe3-ee2765151289)
Kemudian, di bawah ini terdapat tabel untuk memperjelas rute dari setiap subnet, kebutuhan IP tiap subnet, dan nilai netmask masing-masing subnet. Untuk menentukan nilai netmask, kami memperhatikan banyak host tiap subnet
![image](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/assets/111508713/af4a4582-9198-4de8-9798-582441b24dcf)

## CIDR
Pada teknik perhitungan CIDR(Classless Inter Domain Routing), hal pertama yang perlu dilakukan adalah melakukan penggabungan subnet untuk beberapa iterasi dimulai dari subnet yang paling jauh dari internet. Berikut hasil penggabungan subnet dari kelompok kami: </br>
Berdasarkan proses penggabungan tersebut, kami mendapat netmask `/14` untuk hasil penggabungan akhir. Langkah selanjutnya yang perlu dilakukan adalah membuat tree pembagian IP berdasarkan hasil penggabungan sebelumnya. Berikut tree CIDR dari kelompok kami: </br>
![cidrtree](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/cidrtree.jpg)

Berdasarkan tree diatas, berikut pembagian IP untuk masing-masing subnet:

Langkah selanjutnya adalah memasukkan IP yang sudah didapatkan sebelumnya ke masing-masing subnet pada CPT dan melakukan routing pada masing-masing router. </br>

Setelah memasukkan IP dan melakukan routing, langkah selanjutnya yaitu melakukan beberapa uji coba sebagai berikut:
- Router menuju Router </br>
![routertorouter](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/routertorouter.jpg)
- Router menuju Client </br>
![routertoclient](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/routertoclient.jpg)
- Router menuju Server </br>
![routertoserver](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/routertoserver.jpg)
- Server menuju Server </br>
![servertoserver](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/servertoserver.jpg)
- Client menuju Client </br>
![clienttoclient](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/clienttoclient.jpg)
- Client menuju Server </br>
![clienttoserver](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/blob/main/CIDR/clienttoserver.jpg)


## VLSM
Pada metode VLSM, tidak ada penggabungan subnet seperti metode CIDR. Pada metode ini, tree yang dibuat akan dimulai dari netmask total seperti pada tabel pembagian subnet. Kemudian, rentang ip yang ditampung oleh netmask awal ini akan dibagi 2 sama besar untuk membentuk node dengan netmask yang lebih kecil. </br>
</br>
Dalam kasus ini, netmask awal bernilai /19 dan nantinya hasil akhir dari tree ini akan membentuk node-node dengan nilai netmask sesuai dengan pembagian subnet. Jika dirinci, kebutuhan netmask dalam topologi ini adalah sebagai berikut. </br>
/21 : 1 </br>
/22 : 3 </br>
/23 : 1 </br>
/24 : 2 </br>
/26 : 1 </br>
/27 : 1 </br>
/29 : 2 </br>
/30 : 10 </br>

Sehingga ketika dibagi dalam bentuk tree, akan menghasilkan tree sebagai berikut.</br>
![image](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/assets/111508713/36d3015e-dfdb-41fd-aab9-88c55a36a059)

Nilai yang dituliskan dalam tree adalah IP awal dari subnet pada node tersebut. Nilai ini dapat disebut sebagai NID. Sedangkan nilai akhir dari rentang IP di suatu node akan menjadi IP Broadcast Address dari subnet di node tersebut. Jika dituliskan dalam tabel yang berisi nama subnet, NID, netmask, dan broadcast address, maka hasil dari pembagian ini adalah sebagai berikut. </br>
![image](https://github.com/wamalias/Jarkom-Modul-4-E24-2023/assets/111508713/5e450be2-9dee-4cd4-8d68-9635ff39f1dd) </br>
