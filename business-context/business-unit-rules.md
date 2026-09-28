# Business Unit Compliance Rules

> **Applies to**: All UI copy, interactive forms, error messages, and onboarding screens across the Achilles platform.

---

## 1. Unit-Specific Guardrails

| Business Unit | Mandatory Inclusion | Prohibited Wording / Claims | Key Regulatory Body |
| :--- | :--- | :--- | :--- |
| **OnlinePajak** | PJAP resmi mitra DJP & pengawasan Bank Indonesia. Nomor izin & audit trail pelaporan. | Dilarang menjamin kelolosan audit pajak atau memberikan nasihat legal/pajak spesifik. | Direktorat Jenderal Pajak (DJP), Bank Indonesia (BI) |
| **Credor** | Transparansi suku bunga, tenor, biaya provisi, dan jadwal jatuh tempo sebelum konfirmasi. | Dilarang mengklaim pinjaman instan 100% cair tanpa syarat atau tanpa bunga. | Otoritas Jasa Keuangan (OJK) via mitra pendanaan berizin |
| **Covia** | Timestamp keterbaruan data (*data freshness*) dan disclaimer data sebagai referensi pasar. | Dilarang memanipulasi sumbu grafik untuk mendistorsi volatilitas harga komoditas. | Kementerian Perdagangan / Bappebti / Asosiasi Komoditas |
| **Document Hub** | PSrE resmi tersertifikasi Peruri & terdaftar PSE Komdigi. Validasi meterai elektronik sah. | Dilarang mengklaim tanda tangan digital sah tanpa melalui verifikasi identitas resmi. | Peruri, Komdigi |

---

## 2. Universal Data & Consent Rules

1. **Consent Checkboxes**: Checkbox untuk syarat & ketentuan (T&C), kebijakan privasi, atau penarikan data finansial **TIDAK PERNAH boleh pre-checked secara default**.
2. **Kerahasiaan Data Pajak & Finansial**: Informasi faktur pajak, laba rugi, dan rekening bank berstatus rahasia tinggi (*confidential*). Selalu sediakan tombol masker data (*eye toggle* untuk menyembunyikan nominal sensitif jika dibutuhkan).
3. **Penyimpanan Audit Trail**: Seluruh tindakan persetujuan (*approval*), penandatanganan dokumen, dan pengiriman SPT wajib mencatat identitas akun, stempel waktu (WIB), dan alamat IP.
4. **Penanganan Error Terbimbing**: Pesan error dari server perbankan atau DJP wajib disertai rekomendasi pemulihan konkret (misal: *"Kode Billing kedaluwarsa. Klik 'Buat Ulang Kode Billing' untuk melanjutkan pembayaran"*).
