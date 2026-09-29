# Brand Voice & Terminology

> **Applies to**: UI labels, buttons, dialog titles, notification toasts, and error alerts across Achilles, OnlinePajak, Credor, and Covia.

---

## 1. Core Tone Principles

- **Calm & Confident**: Financial and tax software handles sensitive, high-stakes data. Keep the tone steady, reassuring, and professional.
- **Direct & Action-Oriented**: Tell the user exactly what will happen before they click. Use concrete verbs (*"Lapor SPT"*, *"Ajukan Pembiayaan"*, *"Simpan Perubahan"*).
- **Adult & Respectful**: Helpful without being overly colloquial or chatty. No informal slang or exclamation-mark-heavy filler.
- **Bilingual Consistency**: Follow standard Indonesian financial/tax terminology, with clean English equivalents for enterprise multi-language modes.

---

## 2. Universal Action Verbs

| Gunakan (Approved) | Hindari (Forbidden) | Konteks |
| :--- | :--- | :--- |
| **Lanjutkan** / *Continue* | Selanjutnya / *Next* (kecuali stepper) | Aksi forward utama wizard |
| **Simpan perubahan** / *Save changes* | Perbarui / Update / Simpan saja | Menyimpan edit data |
| **Tinjau** / *Review* | Cek / Double check | Langkah konfirmasi sebelum submit |
| **Rincian** / *Details* | Info / Keterangan | Menampilkan breakdown data |
| **Unduh** / *Download* | Ambil / Sedot | Mengambil file dokumen |
| **Batal** / *Cancel* | Keluar / Stop | Menutup dialog tanpa aksi |

---

## 3. Product-Specific Terminology Matrix

| Produk / Pilar | Gunakan (Approved) | Hindari (Forbidden) |
| :--- | :--- | :--- |
| **OnlinePajak** | • e-Faktur, e-Bupot, ID Billing, NTPN<br>• Lawan Transaksi<br>• Masa Pajak, Tahun Pajak<br>• Lapor SPT | • Invoice Pajak<br>• Customer / Klien<br>• Bulan Pajak<br>• Kirim Pajak / Submit |
| **Credor** | • Pembiayaan Modal Kerja / *Invoice Financing*<br>• Skor Risiko Bisnis<br>• Limit Tersedia, Jatuh Tempo<br>• Pencairan Dana, Pelunasan | • Pinjaman Cepat / Utang<br>• Rating / Bintang<br>• Sisa Plafon<br>• Transfer Duit |
| **Covia** | • Indeks Harga (*Price Index*)<br>• Disparitas Harga Regional<br>• Rerata Nasional<br>• Fluktuasi / Tren Komoditas | • Daftar Harga Murah<br>• Selisih Untung<br>• Rata-rata Biasa<br>• Naik Turun |
| **Document Hub** | • Tanda Tangan Elektronik (*e-Signature*)<br>• Meterai Elektronik (*e-Meterai*)<br>• Dokumen Sah Terverifikasi PSrE | • Tanda Tangan Biasa<br>• Cap Materai<br>• Dokumen Aman |

---

## 4. Error Message Writing Rules

1. **Never Blame the User**:
   - ❌ *"Anda salah memasukkan NPWP."*
   - ✅ *"Format NPWP harus terdiri dari 16 digit angka valid."*
2. **Always Provide a Recovery Path**:
   - ❌ *"Gagal memproses faktur."*
   - ✅ *"Server DJP sedang sibuk. Faktur tersimpan sebagai Draft; Anda dapat mencoba mengirim ulang dalam beberapa menit."*
3. **No Internal System Jargon**:
   - ❌ *"Error 500: NullPointerException in BillingGatewayService."*
   - ✅ *"Koneksi pembayaran terputus. Silakan muat ulang halaman atau hubungi tim bantuan."*
