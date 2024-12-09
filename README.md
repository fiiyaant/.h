# Uncovering the Secrets Behind Music Popularity 🎶

![Spotify Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/2/26/Spotify_logo_with_text.svg/1024px-Spotify_logo_with_text.svg.png)


## Table Of Contents
- [About](#About)
- [Dataset](#dataset)
- [Analisis dan code](#analisis-dan-code)
- [Storyboard](#storyboard)
- [Dependencies](#dependencies)
- [Tutorial](#Tutorial)
- [Hasil](#hasiL)
- [Anggota Kelompok](#anggota-kelompok)
- [Lisensi](#lisensi)

---


## About
<details>
  
### **1.1 Musik: Lebih dari Sekadar Hiburan**

Musik lebih dari sekadar hiburan; ia memiliki dampak besar pada **suasana hati**, **produktivitas**, dan bahkan **membentuk tren sosial** yang memengaruhi kehidupan sehari-hari. 

Di tengah persaingan ketat di industri musik, **memahami apa yang membuat sebuah lagu bisa viral atau populer** adalah kunci sukses. Dengan perkembangan teknologi, terutama lewat platform seperti **Spotify**, tren musik bergerak sangat cepat, dan preferensi audiens pun berubah seiring waktu.

Oleh karena itu, penting untuk menganalisis:
- **Faktor-faktor yang memengaruhi popularitas lagu**,
- **Karakteristik musik yang cocok untuk aktivitas tertentu**, serta
- **Tren yang muncul berdasarkan waktu rilis**.

Pemahaman ini bisa membantu **artis**, **produser**, dan **label musik** menciptakan karya yang lebih relevan, menarik, dan berpotensi sukses. 
Mari bersama-sama mengeksplorasi apa yang sebenarnya membuat musik bisa menghubungkan banyak orang!


### **1.2 Penjelasan Singkat Tentang Rencana dalam Mengatasi Pernyataan Masalah**

Kami menggunakan dataset yang berisi **32,833 lagu** dengan **23 fitur utama** seperti popularitas, genre, danceability, tempo, energi, valence, durasi, dan tahun rilis. Data ini mencakup informasi terperinci yang relevan untuk menganalisis tren musik, memahami karakteristik yang memengaruhi popularitas lagu, dan memberikan insight kepada artis serta produser musik.  

Pendekatan kami terdiri dari:
1. **Analisis Tren Musik**: Mengidentifikasi faktor-faktor yang memengaruhi popularitas lagu dan potensinya untuk menjadi viral berdasarkan genre dan fitur musik.
2. **Karakteristik Lagu untuk Aktivitas Tertentu**: Mengelompokkan lagu berdasarkan fitur seperti energi, tempo, dan valence untuk berbagai aktivitas seperti workout, relaksasi, atau bekerja.
3. **Tren Berdasarkan Waktu**: Menelusuri evolusi fitur musik seperti durasi, danceability, dan valence untuk menemukan perubahan pola preferensi audiens.
4. **Memberikan Insight Strategis**: Menyediakan panduan bagi artis dan industri musik untuk menciptakan karya yang relevan dengan audiens modern.

### **1.3 Pendekatan dan Teknik Analisis**

Kami menggunakan berbagai teknik analisis data untuk memahami dan menjawab permasalahan:
1. **Eksplorasi Data**: Melihat distribusi dan pola fitur musikal, seperti danceability dan popularitas.
2. **Korelasi Fitur**: Mengukur hubungan antara elemen musikal seperti energi, valence, dan danceability dengan tingkat popularitas.
3. **Clustering**: Mengelompokkan lagu menggunakan teknik seperti *K-Means* untuk menentukan kelompok lagu berdasarkan karakteristik tertentu, seperti workout atau relaksasi.
4. **Analisis Tren Historis**: Mengamati perubahan durasi, valence, dan danceability lagu berdasarkan tahun rilis untuk memahami evolusi tren musik.
5. **Visualisasi Data**: Menggunakan grafik untuk memetakan tren seperti dominasi genre setiap tahun, perubahan durasi lagu, dan evolusi energi serta valence.
6. **Rekomendasi Berbasis Data**: Menyusun daftar lagu dan insight untuk genre atau aktivitas tertentu berdasarkan hasil analisis.

Pendekatan ini bertujuan untuk memberikan solusi komprehensif yang relevan dengan dinamika industri musik modern.

### **1.4 Manfaat Analisis untuk Konsumen dan Industri Musik**

**Bagi Artis dan Produser**:
- Insight tentang genre dan fitur musik yang cenderung populer, seperti danceability tinggi atau valence positif, membantu menciptakan lagu dengan peluang besar untuk viralitas.
- Rekomendasi tentang durasi lagu, kombinasi fitur seperti energi dan tempo, serta genre dominan dapat menjadi panduan dalam proses kreatif.

**Bagi Industri Musik**:
- Tren berdasarkan waktu membantu industri memahami evolusi musik dan menyesuaikan strategi pemasaran.
- Insight tentang fitur musikal memungkinkan label untuk lebih tepat memasarkan lagu sesuai target audiens, baik untuk platform digital seperti Spotify maupun media sosial seperti TikTok.

**Bagi Audiens**:
- Playlist yang relevan dengan kebutuhan, seperti lagu workout dengan energi tinggi atau lagu relaksasi dengan suasana positif.
- Meningkatkan pengalaman mendengarkan yang lebih personal, membantu audiens menikmati musik yang sesuai dengan aktivitas dan preferensi mereka.

Analisis kami dilakukan diharapkan memberikan manfaat nyata untuk semua pemangku kepentingan dalam industri musik, mulai dari menciptakan musik yang relevan hingga memperkuat pengalaman mendengarkan audiens.
</details>


---

## Dataset

### Sumber Data
Data diperoleh dari [Spotify Dataset](https://www.kaggle.com/datasets/). Dataset ini berisi informasi terkait karakteristik lagu-lagu populer di Spotify, seperti popularitas, durasi, energi, danceability, dan lain-lain.

### Deskripsi Dataset Sumber
Dataset ini berisi **<jumlah data>** entri dengan **<jumlah variabel>** variabel. Tujuan utama dataset ini adalah menganalisis faktor-faktor yang memengaruhi popularitas lagu di Spotify.  

**Detail variabel utama dalam dataset:**
- `id`: Identitas unik setiap lagu.
- `name`: Judul lagu.
- `artists`: Nama artis yang membawakan lagu.
- `popularity`: Popularitas lagu dalam skala 0–100.
- `danceability`: Kemampuan lagu untuk digunakan dalam aktivitas menari.
- `energy`: Tingkat energi lagu.
- `tempo`: Tempo lagu dalam BPM (beats per minute).
- `duration_ms`: Durasi lagu dalam milidetik.
- **dan variabel lainnya.**  

<details>

**Karakteristik khusus data:**
- **Nilai Hilang:** Dataset mencatat nilai hilang sebagai `NaN`.  
- **Format Waktu:** Kolom waktu rilis menggunakan format `YYYY-MM-DD`.  

### Langkah-Langkah Pembersihan Data
#### **Langkah 1: Impor Data**
Data diimpor menggunakan pustaka `pandas` dengan format `.csv`. Berikut adalah langkah untuk mengimpor data:  
```python
import pandas as pd

# Membaca dataset 
df = pd.read_csv("spotify_dataset.csv")

# Menampilkan beberapa baris awal
df.head()
```

#### **Langkah 2: Pemeriksaan Nilai Hilang**
Kolom dengan nilai yang hilang diperiksa dan ditangani sesuai konteks:

```
# Menangani nilai hilang
df['popularity'].fillna(df['popularity'].mean(), inplace=True)  # Imputasi dengan rata-rata
df.dropna(subset=['artists', 'name'], inplace=True)  # Hapus baris dengan artis/nama hilang
```
#### **Langkah 3: Pemeriksaan dan Perbaikan Tipe Data**
Setelah data bersih, tipe data diperiksa dan diperbaiki jika ditemukan ketidaksesuaian.
```
# Mengecek tipe data
df.dtypes

# Mengubah tipe data 'duration_ms' menjadi tipe integer
df['duration_ms'] = df['duration_ms'].astype(int)
```
#### Ringkasan Dataset Setelah Pembersihan

**Sebelum Pembersihan:**
| Variabel              | Nilai Hilang |
|-----------------------|--------------|
| track_artist          | 5            |
| track_album_name      | 5            |
| track_name            | 5            |
| track_id              | 0            |
| key                   | 0            |
| tempo                 | 0            |
| valence               | 0            |
| liveness              | 0            |
| instrumentalness      | 0            |
| acousticsness         | 0            |
| speechiness           | 0            |
| mode                  | 0            |
| loudness              | 0            |
| danceability          | 0            |
| energy                | 0            |

**Sesudah Pembersihan:**
| Variabel              | Nilai Hilang |
|-----------------------|--------------|
| track_id              | 0            |
| energy                | 0            |
| tempo                 | 0            |
| valence               | 0            |
| liveness              | 0            |
| instrumentalness      | 0            |
| acousticsness         | 0            |
| speechiness           | 0            |
| mode                  | 0            |
| loudness              | 0            |
| key                   | 0            |
| danceability          | 0            |
| track_name            | 0            |
| playlist_subgenre     | 0            |
| playlist_genre        | 0            |
| playlist_id           | 0            |
| playlist_name         | 0            |
| track_album_release_date | 0         |


### Analisis Statistik Deskriptif


#### Tujuan
Analisis statistik deskriptif dilakukan untuk memberikan gambaran umum tentang data yang telah dibersihkan. Hal ini meliputi informasi seperti rata-rata, standar deviasi, nilai minimum, nilai maksimum, serta kuartil dari setiap variabel numerik dalam dataset.

#### Statistik Deskriptif Variabel Numerik
Berikut adalah hasil analisis statistik deskriptif untuk variabel numerik dalam dataset:

| Variabel            | Count    | Mean       | Std Dev    | Min       | 25%       | 50%       | 75%       | Max       |
|---------------------|----------|------------|------------|-----------|-----------|-----------|-----------|-----------|
| `track_popularity`  | 32833    | 42.48      | 24.98      | 0.00      | 24.00     | 45.00     | 62.00     | 100.00    |
| `danceability`      | 32833    | 0.65       | 0.14       | 0.00      | 0.56      | 0.67      | 0.76      | 0.98      |
| `energy`            | 32833    | 0.69       | 0.18       | 0.00      | 0.58      | 0.72      | 0.84      | 1.00      |
| `key`               | 32833    | 5.37       | 3.61       | 0.00      | 2.00      | 6.00      | 9.00      | 11.00     |
| `loudness`          | 32833    | -6.71      | 2.99       | -46.44    | -8.17     | -6.16     | -4.64     | 1.28      |
| `mode`              | 32833    | 0.56       | 0.49       | 0.00      | 0.00      | 1.00      | 1.00      | 1.00      |
| `speechiness`       | 32833    | 0.10       | 0.10       | 0.00      | 0.04      | 0.06      | 0.13      | 0.91      |
| `acousticness`      | 32833    | 0.17       | 0.21       | 0.00      | 0.01      | 0.08      | 0.25      | 0.99      |
| `instrumentalness`  | 32833    | 0.08       | 0.22       | 0.00      | 0.00      | 0.00      | 0.00      | 0.99      |
| `liveness`          | 32833    | 0.19       | 0.15       | 0.00      | 0.09      | 0.12      | 0.24      | 0.99      |
| `valence`           | 32833    | 0.51       | 0.23       | 0.00      | 0.33      | 0.51      | 0.69      | 0.99      |
| `tempo`             | 32833    | 120.88     | 26.90      | 0.00      | 99.96     | 121.98    | 133.92    | 239.44    |
| `duration_ms`       | 32833    | 225799.81  | 59834.00   | 4000.00   | 187819.00 | 216000.00 | 253585.00 | 517810.00 |

**Kesimpulan Awal**
1. **Populeritas Lagu (track_popularity)**: Nilai rata-rata adalah 42.48, menunjukkan sebagian besar lagu tidak sepenuhnya populer.
2. **Danceability dan Energy**: Sebagian besar lagu memiliki nilai danceability dan energy tinggi, yang menunjukkan karakteristik musik yang sering digunakan untuk aktivitas tarian atau hiburan.
3. **Tempo**: Tempo rata-rata adalah sekitar 120 BPM, konsisten dengan genre musik pop dan dance.

  
---
## Analisis dan code
- [File ipynb](https://colab.research.google.com/drive/1IT7PGdNXmqVbZYcVfQr2KW413MFy3L2V?usp=sharing) tersedia untuk dieksekusi langsung melalui Google Colab.
- Notebook ini adalah bagian dari [repository GitHub Analisis Big Data](https://github.com/fiiyaant/Analisis-Big-data/tree/main/Notebook).

---
## Storyboard
Storyboard dari proyek ini memberikan gambaran visual dari alur analisis dan tujuan utama proyek. File storyboard dapat diakses melalui link berikut:
- [Storyboard (PDF)](storyboard/storyboard.pdf)
- [Storyboard di Canva](https://www.canva.com/design/DAGYmD00Jps/ZUJwMcNluhOYKbGw4kTA7w/edit)

---
## Dependencies
---
## Tutorial
---
## Hasil
---

## Anggota Kelompok

- [Nur Fitri Yanti](https://github.com/fiiyaant) - 202110370311088
- [Indri Reghina Putri](https://github.com/nanajem1) - 202110370311096

---

## Lisensi
---
