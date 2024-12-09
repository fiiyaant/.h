## 3. Data Preparation

### 3.1 Sumber Data
Data diperoleh dari [Spotify Dataset](https://www.kaggle.com/datasets/). Dataset ini berisi informasi terkait karakteristik lagu-lagu populer di Spotify, seperti popularitas, durasi, energi, danceability, dan lain-lain.

### 3.2 Deskripsi Dataset Sumber
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

**Karakteristik khusus data:**
- **Nilai Hilang:** Dataset mencatat nilai hilang sebagai `NaN`.  
- **Format Waktu:** Kolom waktu rilis menggunakan format `YYYY-MM-DD`.  

### 3.3 Langkah-Langkah Pembersihan Data
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
#### 3.4 Ringkasan Dataset Setelah Pembersihan

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

### 3.5 Analisis Statistik Deskriptif
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
