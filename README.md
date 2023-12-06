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
