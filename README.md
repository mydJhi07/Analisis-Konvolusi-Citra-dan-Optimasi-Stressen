<div align="center">

# 🖼️ Analisis Konvolusi Citra & Optimasi Algoritma Strassen
### Image Convolution & Strassen Algorithm Optimization

Studi kasus **C** tentang optimasi algoritma: **konvolusi citra (blur)** dan **perkalian matriks Strassen** dibandingkan metode standar.
<br/>
A **C** case study on algorithm optimization: **image convolution (blur)** and **Strassen matrix multiplication** versus the standard method.

![Language](https://img.shields.io/badge/Language-C-00599C?style=flat-square&logo=c&logoColor=white)
![Topic](https://img.shields.io/badge/Topic-Algorithms-blue?style=flat-square)
![Library](https://img.shields.io/badge/Library-stb__image-orange?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Performance-red?style=flat-square&logo=speedtest&logoColor=white)

🇮🇩 Bahasa Indonesia &nbsp;•&nbsp; 🇬🇧 English

</div>

---

## 📖 Tentang / About

**🇮🇩** Repositori ini berisi tiga modul C yang mengeksplorasi **kompleksitas dan optimasi algoritma**. Dua di antaranya membandingkan dua cara mengalikan matriks (standar O(n³) vs Strassen yang lebih cepat), dan satu modul menerapkan konsep konvolusi untuk memberi efek blur pada citra digital.

**🇬🇧** This repository contains three C modules exploring **algorithmic complexity and optimization**. Two of them compare two ways of multiplying matrices (standard O(n³) vs the faster Strassen algorithm), and one module applies the concept of convolution to blur a digital image.

---

## 🧩 Modul / Modules

### 1️⃣ Konvolusi Citra — `konvolusi.c`
**🇮🇩** Menerapkan **box blur** menggunakan operasi konvolusi dengan kernel berukuran *k×k* (default 5×5). Gambar dimuat dan disimpan memakai pustaka header tunggal **stb_image**, mendukung gambar multi-channel (RGB) dengan penanganan tepi (edge handling).
**🇬🇧** Applies a **box blur** using a convolution operation with a *k×k* kernel (default 5×5). Images are loaded and saved with the single-header **stb_image** library, supporting multi-channel (RGB) images with edge handling.

`input.jpg` ➜ 🌀 *convolution blur* ➜ `output_blur.png`

### 2️⃣ Perkalian Matriks Strassen — `strassen.c`
**🇮🇩** Implementasi algoritma **Strassen** (*divide and conquer*) yang menekan jumlah perkalian dari 8 menjadi 7 per pembagian, sehingga kompleksitasnya **O(n^2.807)**. Untuk submatriks kecil (n ≤ 64) program beralih ke metode standar demi efisiensi. Dilengkapi uji performa (timer) untuk N = 512 dan N = 1024.
**🇬🇧** Implementation of the **Strassen** algorithm (*divide and conquer*) which reduces the number of multiplications from 8 to 7 per split, giving a complexity of **O(n^2.807)**. For small submatrices (n ≤ 64) it falls back to the standard method for efficiency. Includes a performance test (timer) for N = 512 and N = 1024.

### 3️⃣ Perkalian Matriks Standar — `matriks_standar.c`
**🇮🇩** Perkalian matriks klasik dengan **tiga loop bersarang** berkompleksitas **O(n³)**, dipakai sebagai pembanding (baseline) untuk algoritma Strassen.
**🇬🇧** Classic matrix multiplication with **three nested loops** and **O(n³)** complexity, used as the baseline for comparison against Strassen.

---

## 📊 Analisis Kompleksitas / Complexity Analysis

| Metode / Method | Kompleksitas / Complexity | 🇮🇩 Catatan | 🇬🇧 Note |
|-----------------|---------------------------|-------------|----------|
| Standar / Standard | **O(n³)** | Sederhana, lambat untuk n besar | Simple, slow for large n |
| Strassen | **O(n^2.807)** | Lebih cepat untuk matriks besar | Faster for large matrices |

**🇮🇩** Semakin besar ukuran matriks, semakin terasa keunggulan Strassen — itulah inti yang diukur lewat uji performa.
**🇬🇧** The larger the matrix, the more Strassen's advantage shows — that is exactly what the performance test measures.

---

## 🛠️ Teknologi / Tech Stack

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![stb_image](https://img.shields.io/badge/stb__image-FF6F00?style=for-the-badge)

- **Bahasa / Language:** C (`stdio.h`, `stdlib.h`, `time.h`)
- **Pustaka / Library:** [stb_image](https://github.com/nothings/stb) (header-only image loader/writer)
- **Konsep / Concepts:** Divide and conquer, alokasi memori dinamis (heap), konvolusi citra, analisis kompleksitas

---

## ⚠️ Penting Sebelum Compile / Important Before Compiling

**🇮🇩** File di repo ini saat ini bernama `*.c.txt` dan `*.h.txt`. **Hapus akhiran `.txt`** (dan ganti spasi dengan `_`) agar bisa dikompilasi dan agar GitHub mengenalinya sebagai kode C:

**🇬🇧** Files in this repo are currently named `*.c.txt` and `*.h.txt`. **Remove the `.txt` suffix** (and replace spaces with `_`) so they compile and so GitHub recognizes them as C code:

```
konvolusi.c.txt          ➜  konvolusi.c
strassen.c.txt           ➜  strassen.c
matriks standar.c.txt    ➜  matriks_standar.c
stb_image.h.txt          ➜  stb_image.h
stb_image_write.h.txt    ➜  stb_image_write.h
```

---

## 🚀 Cara Menjalankan / Getting Started

**🌀 Konvolusi / Convolution**
```bash
# 🇮🇩 Letakkan gambar bernama input.jpg di folder yang sama
# 🇬🇧 Place an image named input.jpg in the same folder
gcc konvolusi.c -o konvolusi
./konvolusi
# ➜ output_blur.png
```

**⚡ Strassen**
```bash
gcc strassen.c -o strassen
./strassen
# 🇮🇩 Menampilkan waktu eksekusi untuk N=512 & N=1024
# 🇬🇧 Prints execution time for N=512 & N=1024
```

**🔢 Matriks Standar / Standard Matrix**
```bash
gcc matriks_standar.c -o matriks_standar
./matriks_standar
```

> 💡 **Windows:** ganti `./nama` menjadi `nama.exe` / replace `./name` with `name.exe`.

---

## 📁 Struktur Proyek / Project Structure

```
.
├── konvolusi.c            # 🇮🇩 Blur citra via konvolusi   | 🇬🇧 Image blur via convolution
├── strassen.c            # 🇮🇩 Perkalian matriks Strassen  | 🇬🇧 Strassen matrix multiplication
├── matriks_standar.c     # 🇮🇩 Perkalian matriks O(n³)     | 🇬🇧 O(n³) matrix multiplication
├── stb_image.h           # 🇮🇩 Pustaka pemuat gambar       | 🇬🇧 Image loader library
└── stb_image_write.h     # 🇮🇩 Pustaka penyimpan gambar    | 🇬🇧 Image writer library
```

---

## 🧠 Apa yang Dipelajari / Key Takeaways

**🇮🇩** Proyek ini menunjukkan bagaimana pemilihan algoritma memengaruhi performa nyata, melatih teknik *divide and conquer*, manajemen memori dinamis di C, serta penerapan konsep konvolusi pada pemrosesan citra.

**🇬🇧** This project demonstrates how algorithm choice affects real-world performance, practicing divide-and-conquer techniques, dynamic memory management in C, and applying the concept of convolution to image processing.

---

<div align="center">

### 👤 Author

**Yeurekaaa** — Teknik Informatika, Universitas Hasanuddin (UNHAS)

[![GitHub](https://img.shields.io/badge/GitHub-mydJhi07-181717?style=for-the-badge&logo=github)](https://github.com/mydJhi07)

⭐ *Star repo ini jika bermanfaat! / Star this repo if you find it useful!*

</div>
