# BISpeak Dataset - Bahasa Isyarat Indonesia (BISINDO)

## 📌 Deskripsi

Repositori ini berisi dataset Bahasa Isyarat Indonesia (BISINDO) yang dikumpulkan secara mandiri oleh tim pengembang proyek **BISpeak**. Dataset ini digunakan untuk melatih model machine learning dalam mengenali gesture tangan dan menerjemahkannya menjadi teks sebagai bagian dari sistem penerjemah BISINDO.

Dataset mencakup:

- **46 kelas gesture**  
  - **26 kelas huruf** (A–Z)  
  - **20 kelas kosa kata umum** (misalnya: *makan*, *minum*, *ayah*, *ibu*, dll)
- Total lebih dari **23.000 gambar gesture**
- Jumlah gambar per kelas: ±500 hingga 1.000
- Semua data dikumpulkan melalui dokumentasi langsung dan pelabelan mandiri oleh tim

---

## 📂 Struktur Repositori

```bash
├── dataset_1_tangan/              # Gambar gesture satu tangan (format .jpg)
│   ├── 0/ ~ 9/                    # Huruf A-Z dalam indeks acak (lihat label di bawah)
│   ├── AYAH/
│   ├── BICARA/
│   ├── HALO/
│   ├── IBU/
│   ├── KAMU/
│   ├── MAAF/
│   ├── MAKAN/
│   ├── MELIHAT/
│   ├── MINUM/
│   ├── SAYA/
│   ├── SIAPA/
│   ├── SUKA/
│   └── TERIMA KASIH/

├── dataset_2_tangan/              # Gambar gesture dua tangan (format .jpg)
│   ├── 10/ ~ 25/                  # Huruf A-Z dalam indeks acak (lihat label di bawah)
│   ├── BERJALAN/
│   ├── BERMAIN/
│   ├── DUDUK/
│   ├── MEMBACA/
│   ├── NAMA/
│   ├── RUMAH/
│   └── SEHAT/

├── data_1_tangan.pickle           # Landmark tangan hasil ekstraksi MediaPipe (satu tangan)
├── data_2_tangan.pickle           # Landmark tangan hasil ekstraksi MediaPipe (dua tangan)
├── .gitattributes                 

```


---

## 🏷️ Label Kelas

### Huruf (kode label 0–25, tidak berurutan alfabet):

```python
labels_dict = {
    '0': 'C', '1': 'E', '2': 'I', '3': 'J', '4': 'L',
    '5': 'O', '6': 'R', '7': 'U', '8': 'V', '9': 'Z',
    '10': 'A', '11': 'B', '12': 'D', '13': 'F', '14': 'G',
    '15': 'H', '16': 'K', '17': 'M', '18': 'N', '19': 'P',
    '20': 'Q', '21': 'S', '22': 'T', '23': 'W', '24': 'X',
    '25': 'Y'
}
```
## 🖼️ Format dan Isi Dataset

- Format gambar: `.jpg`
- Setiap folder merepresentasikan satu kelas gesture, dengan format penamaan:
  - **Kode angka (0–25)** untuk huruf alfabet A–Z (tidak berurutan, lihat label pada bagian sebelumnya)
  - **Nama kata** untuk kosa kata umum seperti `MAKAN`, `MINUM`, `SAYA`, dll.
- Dataset terbagi menjadi dua jenis berdasarkan jumlah gesture tangan:
  - `dataset_1_tangan/` untuk gesture satu tangan
  - `dataset_2_tangan/` untuk gesture dua tangan

### 🧠 Ekstraksi Fitur

Dari setiap gambar dalam dataset, kami melakukan ekstraksi **21 titik koordinat (landmark) tangan** menggunakan **MediaPipe Hands**.
Hasil ekstraksi disimpan dalam dua file `.pickle`:

- `data_1_tangan.pickle` — berisi array landmark dari gambar satu tangan
- `data_2_tangan.pickle` — berisi array landmark dari gambar dua tangan

File `.pickle` ini digunakan sebagai **fitur input** utama untuk pelatihan model klasifikasi gesture BISINDO dalam proyek BISpeak.

---

## 💡 Tujuan Dataset

Dataset ini digunakan untuk:

- Pelatihan dan evaluasi **model klasifikasi gesture tangan BISINDO**
- Penerapan dalam proyek **BISpeak**: sistem penerjemah gesture ke teks 
- Eksperimen model berbasis **gambar mentah** maupun **fitur landmark tangan**

---





