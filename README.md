Nama: Farel Farevi
NPM: 2410017514011
Prodi: TRKJ
Mata Kuliah: LAB IV Basic Analog Electronic

1. Tujuan Praktikum

Tujuan praktikum ini adalah:

Mengetahui cara kerja sensor suhu LM35.

Mengetahui cara kerja Arduino dalam membaca nilai suhu.

Menguji apakah source code dapat terkirim dan bekerja dengan baik di Arduino.

Mengamati perubahan nilai suhu melalui Serial Monitor.

2. Teori

LM35 adalah sensor suhu analog yang mengubah temperatur menjadi tegangan listrik yang berbanding lurus (linier). Setiap 1°C menghasilkan 10 mV, sehingga mudah diolah menggunakan Arduino.

Karakteristik LM35:

Sensitivitas: 10 mV/°C

Tegangan kerja: 4–30 V

Akurasi: ±0.5°C pada 25°C

Rentang suhu: −55°C hingga +150°C

Output berupa tegangan analog yang dibaca melalui pin A0 Arduino.

Rumus dasar:

𝑉
𝑜
𝑢
𝑡
=
𝑆
𝑢
ℎ
𝑢
×
10
 
𝑚
𝑉
V
out
	​

=Suhu×10mV
3. Peralatan

Laptop

Arduino Uno

Kabel USB

Breadboard

Sensor Suhu LM35

Kabel jumper

4. Rangkaian Praktikum

Pin LM35:

VCC → 5V Arduino

Vout → A0 Arduino

GND → GND Arduino

Diagram sederhana:

      LM35
   [1] [2] [3]
    |   |   |
   5V  A0  GND

5. Prosedur Praktikum

Menyiapkan Arduino, LM35, breadboard, dan laptop.

Membuka Arduino IDE dan menulis program pembacaan suhu.

Merakit LM35 sesuai diagram.

Menghubungkan Arduino ke laptop.

Mengupload program ke Arduino.

Membuka Serial Monitor untuk melihat hasil pembacaan suhu.

6. Screenshot Prosedur Praktikum



WhatsApp Image 2025-11-21 at 02 58 36_a87aa0a2](https://github.com/user-attachments/assets/94b8711e-b955-47d0-840e-1c0fc9d3fcf0


7. Source Code Arduino
// Mendeklarasikan pin untuk sensor LM35
const int LM35Pin = A0;

void setup() {
  Serial.begin(9600); // Memulai komunikasi serial
}

void loop() {
  int sensorValue = analogRead(LM35Pin);

  float voltage = sensorValue * (5.0 / 1023.0); // Konversi ke tegangan
  float temperature = voltage * 100;            // 10 mV per °C → x100

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");

  delay(1000);
}
