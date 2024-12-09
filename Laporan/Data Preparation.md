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


