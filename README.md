# WordLayout Pro ⚡
> **MS Word Auto-Formatter & Layout Engine** — Otomasi format karya ilmiah, skripsi, buku cetak, dan novel sesuai pedoman baku dalam hitungan detik.

---

## 📌 Ringkasan Proyek

**WordLayout Pro** memformat naskah mentah (`.docx`) menjadi dokumen rapi siap cetak atau siap sidang tanpa perlu penataan margin, section break, penomoran halaman, tabel, dan spasi manual.

Tersedia dalam dua mode:
1. **Web App Standalone (`index.html`)**: Berjalan 100% di browser lokal (Client-Side OpenXML via JSZip, aman tanpa upload server).
2. **VBA Macro Module (`WordLayoutPro_Macro.bas`)**: Eksekusi 1-klik langsung di dalam Microsoft Word.

---

## 🎯 Fitur Utama

- **⚡ Otomasi Section & Page Breaks**:
  - **Section 1 (Cover/Sampul)**: `Different First Page` aktif, nomor halaman **kosong**.
  - **Section 2 (Bagian Awal)**: Nomor halaman **Romawi Kecil (`i, ii, iii`)**, posisi **Bottom Center** (Plain Number 2), mulai dari `1` (`i`).
  - **Section 3+ (Bagian Inti BAB I dst)**: Nomor halaman **Angka Biasa (`1, 2, 3`)**, posisi **Bottom Center**, *Start at* = `1` di BAB I, bersambung otomatis ke bab-bab berikutnya.
- **💬 Auto Intense Quote Detection**:
  - Mendeteksi kutipan bertanda petik dua (`"..."`, `“...”`, `«...»`) dengan panjang $\ge 70$ karakter (> 1 baris).
  - Otomatis mengubahnya menjadi style *Intense Quote* (border atas-bawah, margin kiri-kanan $1.27\text{ cm}$, teks miring/italic, justify).
- **📊 Auto-Format Tabel APA 7th Edition**:
  - Menghapus border vertikal.
  - Memasang 3 border horizontal standar (atas header, bawah header, dan bawah tabel).
  - Format teks header tebal (*bold*), 10pt, spasi tunggal (1.0).
- **🧹 Text Cleanup**:
  - Menghapus spasi ganda berlebih (*multiple spaces*).
  - Merapikan indentasi paragraf pertama (*first-line indent*).

---

## ⚙️ Preset Layout Tersedia

| Preset | Kertas | Margins (Kiri-Atas-Kanan-Bawah) | Font | Spasi | First-Line Indent | Nomor Halaman |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Karya Ilmiah Standar** | A4 | $4 - 3 - 3 - 3\text{ cm}$ | Arial 11pt | 1.5 | $1.27\text{ cm}$ | Bottom Center (Romawi / Arab) |
| **Buku Cetak Mirror** | B5 ($18.2 \times 25.7\text{ cm}$) | Inside $2.5$, Top $2.5$, Outside $2.0$, Bottom $2.0\text{ cm}$ | Book Antiqua 10.5pt | 1.15 | $0.68\text{ cm}$ | Bottom Center + Intense Quote |
| **Skripsi Nasional** | A4 | $4 - 4 - 3 - 3\text{ cm}$ | Times New Roman 12pt | 2.0 (Double) | $1.27\text{ cm}$ | Bottom Center (Romawi / Arab) |
| **Novel Cetak A5** | A5 ($14.8 \times 21.0\text{ cm}$) | Inside $2.0$, Top $2.0$, Outside $1.5$, Bottom $1.5\text{ cm}$ | Garamond 11pt | 1.15 | $0.68\text{ cm}$ | Bottom Center + Intense Quote |

---

## 🚀 Panduan Penggunaan

### 1. Menggunakan Web App (`index.html`)

1. Buka file [index.html](file:///c:/Users/WinproX11/Documents/TEMPLATE/index.html) di browser apa saja (Chrome, Edge, Firefox).
2. Pilih salah satu **Preset Layout** di panel kiri (atau sesuaikan parameter margin & font jika diperlukan).
3. Unggah file naskah berformat `.docx` ke area dropzone (atau klik tombol **🧪 Test Sample Dokumen** untuk mencoba draft bawaan).
4. Klik **⚡ Format Sekarang & Download**.
5. File hasil formatting akan langsung terunduh otomatis (`..._FORMATTED_...docx`).

### 2. Menggunakan Macro VBA di MS Word (`WordLayoutPro_Macro.bas`)

1. Buka dokumen Word Anda di Microsoft Word.
2. Tekan kombinasi tombol `Alt + F11` untuk membuka **VBA Editor**.
3. Pilih menu **File** > **Import File...**, lalu pilih file [WordLayoutPro_Macro.bas](file:///c:/Users/WinproX11/Documents/TEMPLATE/WordLayoutPro_Macro.bas).
4. Tutup VBA Editor (`Alt + Q`).
5. Jalankan Macro melalui menu **View** > **Macros** (`Alt + F8`):
   - `Format_Skripsi_Lengkap` untuk Karya Ilmiah Standar.
   - `Format_Buku_Cetak_Mirror` untuk Buku Cetak B5 Mirror.
   - `Format_Novel_Cetak_A5` untuk Novel A5 Mirror.

---



## 🛠️ Persyaratan Sistem

- **Web Formatter**: Browser modern dengan dukungan JavaScript ES6+ (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari).
- **VBA Macro**: Microsoft Word 2016 / 2019 / 2021 / Office 365 (Windows / macOS).
- **Format File**: `.docx` (Office OpenXML).
