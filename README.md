LAPORAN MINGGUAN JOB 5

Nama: Farel Farevi
NPM: 2410017514011
Prodi: TRKJ
Mata Kuliah: LAB IV Basic Analog Electronic

1. Tujuan Praktikum
Tujuan dari praktikum ini adalah untuk:

Mengetahui cara kerja sensor suhu LM35.

Mengetahui cara kerja Arduino dengan sensor suhu LM35.

Menguji keterkaitan dan komunikasi antara Arduino dan sensor LM35 melalui pengujian source code.

2. Teori
Sensor suhu IC LM35 adalah komponen elektronika yang mengubah suhu menjadi sinyal tegangan analog. LM35 memiliki sensitivitas sebesar 10 mV per 1°C, sehingga setiap kenaikan 1°C akan menambah tegangan sebesar 10 mV. Sensor ini bekerja pada rentang suhu -55°C hingga +150°C dan dapat dibaca langsung oleh Arduino melalui input analog.

Kelebihan LM35:

Rentang pengukuran yang lebar

Akurasi tinggi

Output linier

Tidak memerlukan kalibrasi tambahan

Formula dasar:
Vout = Suhu × 10 mV

3. Peralatan

Laptop

Board Arduino Uno

Konektor USB

Breadboard

Kabel jumper

Sensor suhu LM35

LDR (jika diperlukan)

4. Rangkaian Praktikum
Konfigurasi pin sensor LM35 pada Arduino:

Pin VCC dihubungkan ke 5V Arduino

Pin Vout dihubungkan ke A0 Arduino

Pin GND dihubungkan ke GND Arduino

5. Prosedur Praktikum

Menyiapkan seluruh peralatan praktikum.

Membuka Arduino IDE.

Menuliskan source code pembacaan sensor LM35.

Merangkai sensor LM35 pada Arduino.

Mengunggah program ke Arduino.

Melihat hasil pembacaan suhu menggunakan Serial Monitor.

6. Screenshot Prosedur Praktikum
(prosedur1)
(prosedur2)

7. Source Code Arduino

const int LM35Pin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(LM35Pin);
  float voltage = sensorValue * (5.0 / 1023.0);
  float temperature = voltage * 100;

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" C");

  delay(1000);
}
