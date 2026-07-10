# 🍎 AI Apple Price Predictor

Website prediksi harga produk Apple berbasis AI — dibangun sebagai project portofolio. Pengguna memilih produk (iPhone/iPad/MacBook), menentukan periode forecast, lalu mendapatkan prediksi harga instan lengkap dengan grafik tren historis vs prediksi.

**🔗 Live Demo:** _(akan aktif setelah GitHub Pages selesai di-deploy — lihat langkah di bawah)_
`https://<username-github-kamu>.github.io/ai-apple-price-predictor/`

## ✨ Fitur

- **Landing page** dengan hero section, stats overview, dan penjelasan sistem
- **Model comparison table** — perbandingan 5 model ML (XGBoost, Random Forest, LSTM, Prophet, ARIMA) berdasarkan metrik RMSE, MAE, MAPE, dan R²
- **Prediction tool** — pilih produk, tentukan period type (Daily/Weekly/Monthly/Yearly) dan jumlah periode
- **Hasil prediksi real-time**: predicted price, price change, current price, model yang dipakai, confidence score
- **Grafik interaktif** (SVG) yang menampilkan tren harga historis dan titik prediksi
- Fully responsive, dark theme, animasi halus

## 🛠️ Tech Stack

- HTML5, CSS3 (custom properties, tanpa framework)
- Vanilla JavaScript (ES6+)
- SVG untuk chart, tanpa library eksternal
- Font: [Inter](https://fonts.google.com/specimen/Inter) & [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono)

> Catatan: prediksi harga di project ini **disimulasikan** secara matematis di sisi client (bukan model ML sungguhan yang di-train), dibuat untuk tujuan demo/portofolio UI & UX. Tabel model comparison bersifat ilustratif.

## 🚀 Menjalankan secara lokal

Karena project ini murni HTML/CSS/JS statis, cukup buka filenya langsung:

```bash
git clone https://github.com/<username-github-kamu>/ai-apple-price-predictor.git
cd ai-apple-price-predictor
open index.html   # atau klik dua kali file index.html
```

Atau jalankan local server (opsional):

```bash
python3 -m http.server 8000
# lalu buka http://localhost:8000
```

## 📦 Struktur Project

```
ai-apple-price-predictor/
├── index.html      # seluruh aplikasi (markup, style, logic)
├── README.md
└── LICENSE
```

## 📄 License

Project ini dirilis di bawah [MIT License](LICENSE) — bebas dipakai, dimodifikasi, dan disebarluaskan.

---

Dibuat sebagai project portofolio pribadi.
