## Lisence Plate Detection dengan YOLOv11 dan EasyOCR

## Mohamad Ilham Ramadhani A11.2022.14587

### Ringkasan
Proyek ini bertujuan untuk mendeteksi kendaraan dan plat nomor dari sebuah gambar menggunakan model YOLO untuk mendeteksi kendaraan dan plat nomor, serta EasyOCR untuk membaca teks plat nomor. 
Implementasi dilakukan dengan menggunakan Jupyter Notebook dan Library OpenCV, EasyOCR, dan PyTorch.

#### Permasalahan:
Bagaimana cara mendeteksi kendaraan serta plat nomor secara akurat dari gambar yang diberikan, termasuk membaca informasi teks pada plat nomor?

#### Tujuan:
- Mendeteksi kendaraan dari gambar.
- Mendeteksi plat nomor dalam area kendaraan.
- Membaca teks dari plat nomor menggunakan OCR.

### Alur Penyelesaian
```
Input Image
    ↓
Vehicle Detection (YOLO)
    ↓
Extract Vehicle Bounding Boxes
    ↓
License Plate Detection (YOLO)
    ↓
Enhance License Plate Images
    ↓
Text Extraction (EasyOCR)
    ↓
Output: License Plate Numbers
```

### Datasets
dataset yang digunakan yaitu dataset plat nomor kendaraan hasil tangkapan dari cctv yang ada di daerah jembatan tiga yang berjumlah sebanyak 100 gambar dengan kondisi yang berbeda. 
di dataset terdapat beberapa object seperti motor, mobil dan juga truck

### Pengolahan Fitur

Deteksi Kendaraan:
Model YOLO dilatih untuk mendeteksi kendaraan seperti motor, mobil, dan juga truck.
Gambar diproses untuk mengekstraksi kotak pembatas kendaraan.

Deteksi Plat Nomor:
Gambar kendaraan yang telah dipotong diberikan ke model YOLO kedua untuk mendeteksi plat nomor.

Peningkatan Gambar:
Histogram equalization dan unsharp masking diterapkan untuk meningkatkan kejelasan plat nomor.
Area plat nomor diperbesar menggunakan interpolasi cubic.

### Proses Pembelajaran / Pemodelan
model yang digunakan yaitu YOLOv11 digunakan untuk mendeteksi kendaraan seperti motor, mobil, dan juga truck dan memberikan bounding box warna merah. model tersebut juga digunakan untuk mendeteksi plat nomor kendaraan yang dideteksi
dan memberikan bounding box berwarna hijau.

setelah didapatkan bounding box dari plat nomor, model EasyOCR digunakan untuk membaca plat nomor yang berhasil terdeteksi

### Performa Model
Proyek ini mengutamakan Kemampuan mendeteksi kendaraan dan juga Kemampuan mendeteksi dan membaca teks plat nomor.

### Hasil dan Kesimpulan

#### Hasil:
- Model YOLO mampu mendeteksi kendaraan dan plat nomor dengan baik pada sebagian besar gambar.
- Tantangan utama adalah gambar dengan resolusi rendah atau sudut pengambilan gambar yang sulit.
- EasyOCR bekerja cukup baik pada plat nomor yang jelas, namun terkendala pada plat nomor yang buram atau memiliki noise tinggi.

#### Kesimpulan:

Sistem ini berhasil mengintegrasikan YOLO dan EasyOCR untuk mendeteksi kendaraan dan membaca teks plat nomor.

Untuk peningkatan lebih lanjut, dapat digunakan model YOLO versi terbaru atau model OCR yang lebih canggih.

### Cara Run Code
- pastikan memiliki GPU yang di dukung oleh CUDA untuk menjalankan mesin
- buka code di Jupyter Notebook
- install library library yang digunakan dengan cara
 ```bash
  pip install ultralytics torch torchvision numpy opencv-python-headless matplotlib easyocr
 ```
- klik run all cells
- ubah pada bagian
  ```bash
  image_path = "datasets/B2102PBH_AUS_310313032101_20240619153114231_X1036Y640W38H21_Motorcycle_Audi_unknown_031_02_08614.jpg"
  ```
- dan ganti dengan path gambar yang anda inginkan
