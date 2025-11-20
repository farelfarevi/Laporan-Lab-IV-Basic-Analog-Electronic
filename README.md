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

Sensor suhu IC LM35 adalah komponen elektronik yang berfungsi mengubah suhu menjadi sinyal tegangan yang proporsional. LM35 memiliki sensitivitas 10 mV/°C, artinya untuk setiap perubahan suhu sebesar 1°C, output tegangan sensor akan berubah sebesar 10 mV. Sensor ini memerlukan tegangan operasi 5V dan bekerja pada rentang suhu -55°C hingga +150°C. Output sensor berupa tegangan yang langsung dapat dibaca oleh Arduino.

- **Kelebihan LM35**:
  - Rentang suhu yang lebar (-55°C hingga +150°C).
  - Akurasi tinggi dengan ketepatan ±0.5°C.
  - Tegangan output linier.
  - Tidak memerlukan kalibrasi tambahan.

Formula output sensor:
\[ V_{out} = Temperature \times 10 \, \text{mV} \]

### 3. Peralatan

- Laptop  
- Arduino Uno  
- Kabel USB  
- Breadboard  
- Kabel jumper  
- Sensor LM35  
- LDR (opsional)

### 4. Rangkaian Praktikum

Pin LM35:
- **VCC** → 5V  
- **Vout** → A0  
- **GND** → GND  

### 5. Prosedur Praktikum

1. Mempersiapkan seluruh peralatan.  
2. Membuka Arduino IDE.  
3. Menuliskan program untuk pembacaan sensor LM35.  
4. Merangkai LM35 ke Arduino sesuai diagram.  
5. Mengupload program ke Arduino.  
6. Melihat data suhu melalui Serial Monitor.  

### 6. Screenshot Prosedur Praktikum

![WhatsApp Image 2025-11-21 at 02 58 35_35aa8675](https://github.com/user-attachments/assets/ebf9f04f-5338-4647-8a03-870ade83c505)


### 7. Source Code Arduino

```cpp
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
  Serial.println(" °C");

  delay(1000);
}
```

