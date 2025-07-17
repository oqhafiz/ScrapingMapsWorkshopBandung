# ScrapingMapsWorkshopBandung
# 🔧 Web Scraping Bengkel di Bandung dengan Python & SerpAPI

Proyek ini bertujuan untuk mengambil data **bengkel mobil** dan **bengkel motor** di kota **Bandung** secara otomatis menggunakan **Google Maps Search API (SerpAPI)**. Proses scraping dilakukan di Google Colab dan hasilnya disimpan dalam file Excel.

## 📌 Fitur

- Mengambil data lokasi bengkel dari Google Maps berdasarkan kata kunci
- Menyimpan informasi seperti:
  - Nama
  - Alamat
  - Nomor Telepon
  - Rating
  - Jumlah ulasan
  - Koordinat (Latitude, Longitude)
  - Kategori bisnis
- Hasil scraping disimpan ke file **Excel** dengan dua sheet: `Bengkel_Mobil` dan `Bengkel_Motor`
- Dapat dijalankan langsung di Google Colab

## 🛠️ Teknologi yang Digunakan

- Python
- Pandas
- Requests
- OpenPyXL
- SerpAPI (Google Maps API)
- Google Colab

## 📂 Struktur Output

File yang dihasilkan: `bandung_bengkel.xlsx`  
Berisi dua lembar kerja:
- `Bengkel_Mobil`
- `Bengkel_Motor`

## 🚀 Cara Menjalankan

1. **Clone repository** ini atau buka langsung notebook di Google Colab.
2. **Pasang API Key SerpAPI**:
   - Daftar dan dapatkan API key dari [https://serpapi.com/](https://serpapi.com/)
   - Tambahkan `API_KEY = "YOUR_API_KEY"` di awal notebook
3. Jalankan seluruh sel untuk melakukan scraping dan menyimpan data ke file Excel.

## 💡 Contoh Cuplikan Kode

```python
df_mobil = scrape_bengkel_bandung("bengkel mobil", pages=5)
df_motor = scrape_bengkel_bandung("bengkel motor", pages=5)
df_all   = pd.concat([df_mobil, df_motor], ignore_index=True)
df_all.to_excel("bandung_bengkel.xlsx", index=False)
