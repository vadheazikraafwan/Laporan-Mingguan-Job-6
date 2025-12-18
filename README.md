# Laporan-Mingguan-Job-6

Nama: Vadhea Zikra Afwan

NPM: 2410017514015
Prodi: TRKJ

Mata Kuliah: LAB IV Basic Analog Electronic

1. Tujuan Praktikum
   
Tujuan dari praktikum ini adalah:
Mengetahui prinsip kerja seven segment display.

Memahami jenis seven segment (common anode dan common cathode).

Mengimplementasikan seven segment menggunakan Arduino.

Menampilkan angka 0–9 pada seven segment melalui pemrograman Arduino.

2. Teori
   
Seven Segment Display adalah komponen elektronika yang digunakan untuk menampilkan angka desimal dan beberapa karakter tertentu. Seven segment terdiri dari tujuh buah segmen LED yang disusun membentuk angka "8" dan satu titik desimal (dot). Setiap segmen dapat dikontrol secara ON atau OFF untuk membentuk angka tertentu. Seven segment banyak digunakan pada jam digital, kalkulator, penghitung digital, panel instrumen, dan alat ukur elektronik. Berdasarkan konfigurasi pin-nya, seven segment terbagi menjadi dua jenis:

A. Common Cathode
Semua kaki katoda segmen disatukan dan dihubungkan ke ground (GND). Segmen akan menyala jika diberi logika HIGH.

B. Common Anode
Semua kaki anoda segmen disatukan dan dihubungkan ke tegangan positif (+5V). Segmen akan menyala jika diberi logika LOW.

Pada praktikum ini digunakan seven segment LED yang dihubungkan langsung ke pin digital Arduino sehingga pola nyala segmen dikontrol menggunakan program.

3. Peralatan
Laptop
Board Arduino Uno
Kabel USB
Breadboard
Seven Segment Display
Resistor (220 Ω – 330 Ω)
Jumper wires

4. Rangkaian Praktikum
Rangkaian praktikum dilakukan dengan menghubungkan:

Pin segmen a–g seven segment ke pin digital Arduino (misalnya pin 2 sampai 8)

Pin common seven segment ke GND (untuk common cathode)

Setiap segmen diberi resistor sebagai pembatas arus

Rangkaian ini memungkinkan Arduino mengendalikan setiap segmen untuk menampilkan angka 0 sampai 9.

5. Prosedur Praktikum
a. Menyiapkan seluruh peralatan praktikum.

b. Menghubungkan Arduino ke laptop menggunakan kabel USB.

c. Merangkai seven segment pada breadboard sesuai dengan rangkaian praktikum.

d. Menghubungkan pin-pin seven segment ke pin digital Arduino.

e. Membuka aplikasi Arduino IDE.

f. Menuliskan source code untuk mengendalikan seven segment.

g. Mengecek kembali rangkaian dan program.

h. Melakukan compile dan upload program ke board Arduino.

i. Mengamati hasil percobaan berupa tampilan angka pada seven segment.

6. Screenshot Prosedur Praktikum
7. Source code arduino
   ## PRAKTIKUM VI

# SEVEN SEGMENT

## 1. Tujuan Praktikum

* Mengetahui prinsip kerja seven segment display.
* Memahami jenis seven segment (common anode dan common cathode).
* Mengimplementasikan seven segment menggunakan Arduino.
* Menampilkan angka 0–9 pada seven segment melalui pemrograman Arduino.

## 2. Teori

Seven Segment Display adalah komponen elektronika yang digunakan untuk menampilkan angka desimal dan beberapa karakter tertentu. Seven segment terdiri dari tujuh buah segmen LED yang disusun membentuk angka "8" dan satu titik desimal (dot). Setiap segmen dapat dikontrol secara ON atau OFF untuk membentuk angka tertentu.

Seven segment banyak digunakan pada jam digital, kalkulator, penghitung digital, panel instrumen, dan alat ukur elektronik.

Berdasarkan konfigurasi pin-nya, seven segment terbagi menjadi dua jenis:

1. **Common Cathode**
   Semua kaki katoda segmen disatukan dan dihubungkan ke ground (GND). Segmen akan menyala jika diberi logika HIGH.

2. **Common Anode**
   Semua kaki anoda segmen disatukan dan dihubungkan ke tegangan positif (+5V). Segmen akan menyala jika diberi logika LOW.

Pada praktikum ini digunakan seven segment LED yang dihubungkan langsung ke pin digital Arduino sehingga pola nyala segmen dikontrol menggunakan program.

## 3. Peralatan

* Laptop
* Board Arduino Uno
* Kabel USB
* Breadboard
* Seven Segment Display
* Resistor (220 Ω – 330 Ω)
* Jumper wires

## 4. Rangkaian Praktikum

Rangkaian praktikum dilakukan dengan menghubungkan:

* Pin segmen a–g seven segment ke pin digital Arduino (misalnya pin 2 sampai 8)
* Pin common seven segment ke GND (untuk common cathode)
* Setiap segmen diberi resistor sebagai pembatas arus

Rangkaian ini memungkinkan Arduino mengendalikan setiap segmen untuk menampilkan angka 0 sampai 9.

## 5. Prosedur Praktikum

1. Menyiapkan seluruh peralatan praktikum.
2. Menghubungkan Arduino ke laptop menggunakan kabel USB.
3. Merangkai seven segment pada breadboard sesuai dengan rangkaian praktikum.
4. Menghubungkan pin-pin seven segment ke pin digital Arduino.
5. Membuka aplikasi Arduino IDE.
6. Menuliskan source code untuk mengendalikan seven segment.
7. Mengecek kembali rangkaian dan program.
8. Melakukan compile dan upload program ke board Arduino.
9. Mengamati hasil percobaan berupa tampilan angka pada seven segment.

## 6. Foto Prosedur Praktikum 


![WhatsApp Image 2025-12-19 at 03 34 18](https://github.com/user-attachments/assets/76e9cd38-9b0d-4182-a758-808103cf30ca)





## 7. Source Code Arduino

```cpp
// Pin Arduino untuk segmen a–g
int segA = 2;
int segB = 3;
int segC = 4;
int segD = 5;
int segE = 6;
int segF = 7;
int segG = 8;

// Pola angka 0–9 (common cathode)
byte angka[10][7] = {
  {1,1,1,1,1,1,0}, // 0
  {0,1,1,0,0,0,0}, // 1
  {1,1,0,1,1,0,1}, // 2
  {1,1,1,1,0,0,1}, // 3
  {0,1,1,0,0,1,1}, // 4
  {1,0,1,1,0,1,1}, // 5
  {1,0,1,1,1,1,1}, // 6
  {1,1,1,0,0,0,0}, // 7
  {1,1,1,1,1,1,1}, // 8
  {1,1,1,1,0,1,1}  // 9
};

void setup() {
  pinMode(segA, OUTPUT);
  pinMode(segB, OUTPUT);
  pinMode(segC, OUTPUT);
  pinMode(segD, OUTPUT);
  pinMode(segE, OUTPUT);
  pinMode(segF, OUTPUT);
  pinMode(segG, OUTPUT);
}

void tampilAngka(int num) {
  digitalWrite(segA, angka[num][0]);
  digitalWrite(segB, angka[num][1]);
  digitalWrite(segC, angka[num][2]);
  digitalWrite(segD, angka[num][3]);
  digitalWrite(segE, angka[num][4]);
  digitalWrite(segF, angka[num][5]);
  digitalWrite(segG, angka[num][6]);
}

void loop() {
  for (int i = 0; i < 10; i++) {
    tampilAngka(i);
    delay(1000);
  }
}
```
