LAPORAN MINGGUAN JOB 5

Nama: Farel Farevi

NPM: 2410017514011

Prodi: TRKJ

Mata Kuliah: LAB IV Basic Analog Electronic

1. Tujuan Praktikum
Tujuan dari praktikum ini adalah untuk:

Mengetahui cara kerja sensor suhu LM35

Mengetahui cara kerja Arduino dengan sensor suhu LM35

Menguji keterkaitan dan komunikasi antara Arduino dan sensor LM35 melalui pengujian source code

2. Teori
Sensor suhu IC LM35 adalah komponen elektronika yang mengubah suhu menjadi sinyal tegangan analog. LM35 memiliki sensitivitas 10 mV setiap kenaikan 1°C. Sensor ini memiliki rentang kerja -55°C hingga +150°C dan outputnya dapat dibaca langsung oleh Arduino melalui pin analog.

Kelebihan LM35:

Rentang pengukuran yang lebar

Akurasi tinggi

Output linier

Tidak memerlukan kalibrasi

Formula dasar:
Vout = Suhu × 10 mV

3. Peralatan

Laptop

Board Arduino Uno

Kabel USB

Breadboard

Kabel jumper

Sensor LM35

LDR (opsional)

4. Rangkaian Praktikum
Konfigurasi sambungan sensor LM35:

VCC → 5V Arduino

Vout → A0 Arduino

GND → GND Arduino

5. Prosedur Praktikum

Menyiapkan seluruh peralatan

Membuka Arduino IDE

Menuliskan source code pembacaan LM35

Merangkai sensor LM35 ke Arduino

Mengupload program

Melihat hasil pembacaan suhu pada Serial Monitor

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
