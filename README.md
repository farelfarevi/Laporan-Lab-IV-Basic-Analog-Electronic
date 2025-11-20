Nama: Farel Farevi
NPM: 2410017514011
Prodi: TRKJ
Mata Kuliah: LAB IV Basic Analog Electronic

1. Tujuan Praktikum

Tujuan dari praktikum ini adalah:

Mengetahui cara kerja sensor suhu LM35.

Memahami cara kerja Arduino dalam membaca sensor analog.

Menguji keterkiriman program ke Arduino.

Mengamati hasil pembacaan suhu melalui Serial Monitor.

2. Teori

LM35 adalah sensor suhu analog yang menghasilkan tegangan keluaran 10 mV untuk setiap 1°C.
Sensor ini sangat mudah digunakan dengan Arduino karena sifat outputnya linier.

Karakteristik LM35:

Sensitivitas: 10 mV/°C

Tegangan kerja: 4–30 V

Akurasi: ±0.5°C pada 25°C

Rentang suhu: −55°C sampai +150°C

Rumus dasar LM35:

Vout (mV) = Suhu (°C) × 10


Konversi pembacaan ke suhu pada Arduino:

voltage = (sensorValue × 5.0) / 1023
temperature = voltage × 100

3. Peralatan

Laptop

Arduino Uno

Kabel USB

Breadboard

Sensor LM35

Kabel jumper

4. Rangkaian Praktikum

Koneksi LM35:

Pin 1 → 5V Arduino  
Pin 2 → A0 Arduino  
Pin 3 → GND Arduino


Diagram simple:

LM35
[1]---5V
[2]---A0
[3]---GND

5. Prosedur Praktikum

Menyiapkan Arduino, LM35, dan breadboard.

Membuka Arduino IDE.

Menulis dan menyimpan program pembacaan suhu.

Merangkai LM35 sesuai diagram.

Mengupload program ke Arduino.

Membuka Serial Monitor untuk melihat hasil suhu.

6. Screenshot Praktikum

![WhatsApp Image 2025-11-21 at 02 58 35_dc851827](https://github.com/user-attachments/assets/a7e7c796-889a-46b3-92fc-fd3aa8ae3b92)

7. Source Code Arduino
```cpp
// Pin sensor LM35 dihubungkan ke A0
const int LM35Pin = A0;

void setup() {
  Serial.begin(9600); // Memulai komunikasi serial
}

void loop() {
  int sensorValue = analogRead(LM35Pin);

  float voltage = sensorValue * (5.0 / 1023.0); // Konversi ke tegangan
  float temperature = voltage * 100;            // LM35 = 10mV per °C

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");

  delay(1000);
}
```
