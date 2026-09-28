# Business Context: OnlinePajak

> **Unit**: Perpajakan & Kepatuhan (Tax & Compliance)  
> **Parent Platform**: Achilles ([achilles.id](https://achilles.id))  
> **Official Designation**: Penyedia Jasa Aplikasi Perpajakan (PJAP) Resmi Mitra DJP, terdaftar & diawasi oleh Bank Indonesia.  
> **Target Audience**: Tax Specialists, Accountants, Finance Managers, Corporate Tax Consultants, Business Owners.

---

## 1. Product Purpose & Value Proposition
OnlinePajak adalah platform kepatuhan perpajakan digital terintegrasi yang menyederhanakan perhitungan, pembuatan bukti transaksi pajak (e-Faktur & e-Bupot), pembayaran (billing DJP), hingga pelaporan SPT (Masa & Tahunan) dalam satu alur kerja terotomatisasi.

---

## 2. Core Personas

| Persona | Primary Goal | Critical Constraints |
| :--- | :--- | :--- |
| **Corporate Tax Specialist** | Mengelola ribuan e-Faktur & e-Bupot setiap bulan secara massal dan akurat | Batas waktu pelaporan bulanan DJP (akhir bulan berikutnya), validasi NPWP/NIK ketat. |
| **Finance & Accounting Manager** | Rekonsiliasi antara invoice komersial dan faktur pajak tanpa selisih (*zero-discrepancy*) | Membutuhkan approval flow berjenjang (maker-checker), audit trail lengkap. |
| **SME Business Owner** | Menyelesaikan kewajiban pajak dengan cepat tanpa keahlian akuntansi mendalam | Butuh bahasa sederhana, alur kalkulasi otomatis, dan panduan kode billing. |

---

## 3. Core Flows

```mermaid
flowchart LR
    Invoice[Commercial Invoice] --> Faktur[Generate e-Faktur / e-Bupot]
    Faktur --> DJP[Validasi & Approval DJP]
    DJP --> Bayar[Generate ID Billing & Bayar Pajak]
    Bayar --> Lapor[Pelaporan SPT & Cetak BPE]
```

1. **Pembuatan & Validasi e-Faktur / e-Bupot**:
   - Pembuatan faktur tunggal atau massal (via file CSV/Excel atau API ERP).
   - Validasi kelengkapan data lawan transaksi (NPWP 16 digit, NIK, Nama, Alamat).
   - Pengiriman ke sistem DJP dan penerimaan status approval/QR code resmi.

2. **Pembayaran Pajak Terintegrasi**:
   - Pembuatan Kode Billing resmi negara otomatis.
   - Pembayaran langsung melalui channel perbankan / Bank Indonesia dengan konfirmasi NTPN instan.

3. **Pelaporan SPT & Tanda Terima Elektronik**:
   - Kompilasi SPT Masa (PPN 1111, PPh 21, PPh 23, PPh Final) atau SPT Tahunan Badan/Pribadi.
   - Penerimaan Bukti Penerimaan Elektronik (BPE) dan Nomor Tanda Terima Elektronik (NTTE) sah.

---

## 4. UI Copy, Terminology & Action Verbs

| Gunakan (Approved) | Jangan Gunakan (Forbidden) | Konteks |
| :--- | :--- | :--- |
| **Lapor SPT** | Kirim SPT / Submit Pajak | Tombol pelaporan resmi ke DJP |
| **Buat e-Faktur** | Bikin Faktur / Input Pajak | Pembuatan faktur pajak elektronik |
| **Unduh BPE** | Download Tanda Terima | Bukti Penerimaan Elektronik resmi |
| **ID Billing** | Nomor Bayar | Kode pembayaran pajak DJP |
| **NTPN** | Resi Bayar | Nomor Transaksi Penerimaan Negara |
| **Lawan Transaksi** | Customer / Klien | Pihak pembeli/penjual dalam faktur |
| **Masa Pajak** | Bulan Pajak | Periode pelaporan pajak |

---

## 5. Compliance & Legal Guardrails

- **Status Resmi DJP**: Wajib selalu mencantumkan disclaimer resmi: *"OnlinePajak merupakan PJAP resmi mitra DJP serta terdaftar dan diawasi oleh Bank Indonesia."*
- **Tidak Memberikan Konsultasi Hukum**: UI copy dilarang memberikan saran hukum/pajak khusus (misal: *"Sebaiknya gunakan tarif ini untuk hemat"*). Berikan formulasi dan opsi sesuai UU perpajakan yang berlaku.
- **Status Validasi Eksplisit**: Status faktur hanya boleh bernilai baku: `Draft`, `Menunggu DJP`, `Disetujui (Approved)`, `Ditolak (Rejected)`, `Dibatalkan (Cancelled)`.
- **Penanganan Error DJP**: Tampilkan pesan error resmi dari DJP beserta solusi konkret (contoh: *"NPWP lawan transaksi tidak aktif. Silakan hubungi lawan transaksi untuk verifikasi data"*).
