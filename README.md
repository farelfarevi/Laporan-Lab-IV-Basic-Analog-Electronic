# Laporan Mingguan Job 5

**Nama**: Farel Farevi  
**NPM**: 2410017514011  
**Prodi**: TRKJ  
**Mata Kuliah**: LAB IV Basic Analog Electronic

### 1. Tujuan Praktikum

Tujuan dari praktikum ini adalah untuk:
- Mengetahui cara kerja sensor suhu LM35.
- Mengetahui cara kerja Arduino dengan sensor suhu LM35.
- Menguji keterkaitan dan komunikasi antara Arduino dan sensor LM35 melalui pengujian source code.

### 2. Teori

Sensor suhu IC **LM35** adalah komponen elektronik yang berfungsi mengubah suhu menjadi sinyal tegangan yang proporsional.  
LM35 memiliki sensitivitas **10 mV/°C**, artinya setiap kenaikan suhu 1°C akan meningkatkan output sebesar 10 mV.  
Sensor ini beroperasi pada **DC 5V** dan memiliki rentang kerja **-55°C hingga +150°C**.

Output LM35 berupa tegangan analog yang dapat dibaca oleh **ADC Arduino**, kemudian dikonversi menjadi nilai suhu.

### 3. Alat dan Bahan

- Arduino Uno  
- Sensor suhu LM35  
- Kabel jumper  
- Breadboard  
- Laptop yang sudah terinstal Arduino IDE  

### 4. Rangkaian

Pin LM35:
- VCC → 5V  
- OUT → A0 (analog input Arduino)  
- GND → GND  

### 5. Source Code

```cpp
const int lm35Pin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int analogValue = analogRead(lm35Pin);
  float voltage = analogValue * 5.0 / 1023.0;
  float temperature = voltage * 100;

  Serial.print("Suhu: ");
  Serial.print(temperature);
  Serial.println(" °C");

  delay(800);
}
```

### 6. Hasil dan Pembahasan

Sensor LM35 berhasil membaca suhu ruangan dengan stabil.  
Output pada Serial Monitor menampilkan perubahan suhu berdasarkan nilai tegangan dari pin analog A0.  
Semakin tinggi suhu, semakin besar nilai tegangan yang terbaca.

### 7. Kesimpulan

Dalam praktikum ini dapat disimpulkan bahwa:
- LM35 dapat digunakan sebagai sensor suhu analog dengan sensitivitas tinggi.
- Arduino dapat membaca dan mengolah sinyal dari LM35 dengan baik.
- Hubungan antara LM35 dan Arduino dapat menghasilkan data suhu real-time yang akurat.
