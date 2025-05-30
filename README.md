# BISINDO Image Classification Dataset

## Deskripsi Dataset
Dataset ini berisi gambar isyarat tangan dari Bahasa Isyarat Indonesia (BISINDO) yang terdiri dari 126 kelas, termasuk 26 alfabet dan 100 kelas kata-kata isyarat BISINDO lainnya. Dataset telah dibagi ke dalam tiga subset: `train`, `validation (val)`, dan `test`.

Untuk mengatasi ketidakseimbangan data, dilakukan augmentasi pada data pelatihan sehingga setiap kelas pada subset `train` memiliki jumlah data yang seragam, yaitu 300 gambar per kelas.

<!-- ## Link Dataset
Anda dapat mengunduh dataset lengkap melalui tautan Google Drive berikut:  
👉 [Google Drive - BISINDO Dataset](https://drive.google.com/file/d/1q59r6q-4YTB6e4psSmfWj5dEvLr_dLPF/view?usp=drive_link)

> _Gantilah link di atas dengan URL folder dataset Anda._
 -->
---

## Statistik Dataset

| Subset | Jumlah Kelas | Gambar per Kelas        | Total Gambar |
|--------|--------------|-------------------------|--------------|
| Train  | 126          | 300 (setelah augmentasi)| 37,800       |
| Val    | 126          | 7–21 gambar per kelas   | 2,062        |
| Test   | 126          | 7–21 gambar per kelas   | 2,062        |
| **Total** | —         | —                       | **41,924**   |

---

## Augmentasi Data

Augmentasi dilakukan pada data pelatihan (`train`) menggunakan berbagai teknik berikut:

- Rotasi acak (berlawanan/searah jarum jam: 90°, 180°, 270°)
- Flip vertikal (atas-bawah)
- Peningkatan kecerahan
- Gaussian blur
- Shearing (geser)
- Warp (melengkung)

Semua gambar diresize ke ukuran **224x224 piksel** sebelum proses augmentasi.

---


