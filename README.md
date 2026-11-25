# MyTelkomsel: Prototipe Alur Beli Paket (PRD + UX Skill)

| | |
|---|---|
| **Mode** | PRD + UX Skill |
| **Versi** | 0.4.0 |
| **Pemilik** | Kurnia Nurhajijah (NIM 202310370311260) |
| **Mata kuliah** | Rekayasa Interaksi (UX) |
| **Status** | Prototipe untuk presentasi progres |

Repo ini berisi PRD (file ini), `CHANGELOG.md`, UX Skill lengkap, `agent.md`, dan source code prototipe. Prototipenya dibuat dari PRD **ditambah UX Skill**. PRD-nya sama dengan repo PRD Only, sehingga perbedaan hasil berasal dari UX Skill dan `agent.md`.

## 1. Ringkasan

Prototipe web untuk alur **Beli Paket** di aplikasi MyTelkomsel. Fokusnya satu masalah: pengguna sering tidak yakin bahwa verifikasi dan pembayaran paket data sudah berhasil. Dokumen ini adalah PRD kebutuhan UX yang disusun dari hasil riset Worksheet 1, 3, 5, 6, 7, 8, dan 9 pada mata kuliah Rekayasa Interaksi (UX).

Catatan: ini prototipe pembelajaran dengan data contoh, bukan aplikasi resmi Telkomsel.

## 2. Latar Belakang dan Masalah

Masalah utama: **kurangnya kepastian bahwa verifikasi dan pembayaran berhasil** (visibility of system status).

- Setelah membayar, status transaksi tidak selalu langsung terlihat, jadi pengguna mencari bukti sendiri lewat notifikasi atau riwayat transaksi (observasi U1, U3).
- Ketika diminta verifikasi ulang tanpa penjelasan, pengguna ragu apakah pembelian tadi sudah selesai (U2).
- Temuan Worksheet 1 (UX Detective): tidak ada konfirmasi setelah pembayaran, tampilan tidak diperbarui otomatis, ikon "Beli Paket" muncul berulang, dan aplikasi butuh internet saat kuota hampir habis.

Titik terberat (Moment of Truth) di User Journey: tahap **Memastikan transaksi berhasil**.

## 3. Pengguna Target

**Persona: Naira**, mahasiswa 22 tahun, pelanggan Telkomsel prabayar, memakai MyTelkomsel sekitar 2 sampai 4 tahun dan membeli paket 1 sampai 3 kali per bulan. Teliti membandingkan kuota dan harga, dan butuh kepastian bahwa transaksinya berhasil.

- **Tujuan:** membeli paket yang sesuai dengan cepat; memastikan verifikasi dan pembayaran berhasil tanpa ragu.
- **Pain point:** konfirmasi tidak langsung terlihat; verifikasi ulang membingungkan; harus membuka menu lain untuk memastikan hasil.
- **Kemampuan teknologi:** menengah.

Dasar data: observasi 3 responden mahasiswa prabayar (21 sampai 22 tahun). Belum mewakili pengguna pascabayar atau di luar mahasiswa.

## 4. Tujuan dan Non-Goals

**Tujuan**

1. Pengguna yakin transaksinya berhasil tanpa mencari bukti ke menu lain.
2. Pengguna paham apa yang sedang terjadi di setiap langkah (verifikasi, pembayaran, hasil).

**Non-goals**

- Integrasi sistem pembayaran atau jaringan Telkomsel yang asli.
- Fitur di luar alur Beli Paket (promo, poin, dan sebagainya).
- Desain visual detail atau branding resmi.

## 5. Kebutuhan UX

| ID | Kebutuhan (sudut pandang pengguna) | Prioritas | Kriteria penerimaan |
|---|---|---|---|
| UX-01 | Pengguna membutuhkan konfirmasi keberhasilan yang langsung terlihat setelah pembayaran agar yakin pembelian berhasil tanpa membuka menu lain. | High | Setelah bayar, halaman Konfirmasi Hasil muncul otomatis dengan status, nama paket, waktu, dan ID transaksi. Notifikasi keberhasilan ikut ditampilkan. |
| UX-02 | Pengguna membutuhkan tanda bahwa pembayaran sedang diproses atau sudah diterima agar tidak ragu dan tidak mengulang pembayaran. | High | Saat pembayaran berjalan tampil status "Pembayaran diproses" dengan indikator loading, dan hasilnya muncul tanpa tindakan tambahan. |
| UX-03 | Pengguna membutuhkan alasan dan langkah yang jelas saat diminta verifikasi ulang agar tahu pembelian tadi masih aman. | High | Layar verifikasi ulang menampilkan alasan, langkah berikutnya, dan keterangan bahwa pembelian belum diproses sampai verifikasi selesai. |
| UX-04 | Pengguna membutuhkan akses cepat ke riwayat transaksi agar bisa mengecek hasil pembelian tanpa mencari-cari. | Medium | Riwayat dapat dicapai maksimal 2 ketukan dari Konfirmasi Hasil atau Beranda. Riwayat punya filter status dan tanggal serta halaman detail. |
| UX-05 | Pengguna membutuhkan informasi kuota dan harga paket yang mudah dibandingkan agar bisa memilih paket yang pas. | Medium | Dua paket dapat dibandingkan (kuota, harga, masa aktif, harga per GB) dalam satu layar. |
| UX-06 | Pengguna membutuhkan cara membeli paket tetap lancar saat kuota hampir habis. | Medium (perlu validasi) | Tersedia Mode Hemat Data (di prototipe: tampilan ringan tanpa animasi sebagai simulasi). |
| UX-07 | Pengguna membutuhkan informasi kuota yang langsung diperbarui setelah pembayaran. | Medium | Sisa kuota di Beranda bertambah otomatis setelah transaksi berhasil, tanpa menyegarkan manual. |
| UX-08 | Pengguna membutuhkan satu jalur menu "Beli Paket" yang jelas agar tidak bingung memilih ikon. | Low | Hanya ada satu pintasan Beli Paket di Beranda dan satu menu utama Beli Paket. |

Prioritas ditentukan dari jumlah responden yang mengalami, tingkat dampak pada tujuan pengguna, keterkaitan dengan Moment of Truth, dan kekuatan bukti. UX-01 sampai UX-03 dikerjakan lebih dulu karena berakar pada masalah yang sama: kurangnya umpan balik status sistem.

## 6. Struktur Informasi (Sitemap)

```
[BERANDA / HOME]
│
├── [BERANDA]
│   ├── Info Sisa Kuota
│   ├── Beli Paket Cepat
│   └── Status Terakhir
│
├── [BELI PAKET]
│   ├── Mode Hemat Data (alternatif, perlu validasi)
│   ├── 1. Daftar Paket
│   ├── 2. Bandingkan Paket
│   ├── 3. Verifikasi Nomor (alasan verifikasi ulang)
│   ├── 4. Pembayaran (status diproses)
│   └── 5. Konfirmasi Hasil
│       ├── Lihat Riwayat -> Detail Transaksi
│       └── Jika gagal -> Pusat Bantuan
│
├── [RIWAYAT TRANSAKSI]
│   ├── Daftar Transaksi (filter tanggal dan status)
│   └── Detail Transaksi
│
└── [BANTUAN]
    └── Pusat Bantuan
```

## 7. Spesifikasi Halaman

| Halaman | Isi dan perilaku | Kebutuhan |
|---|---|---|
| Beranda | Sisa kuota (GB), tombol Beli Paket, kartu Status Terakhir (status, tombol Lihat detail), toggle Mode Hemat Data. | UX-01, 06, 07, 08 |
| Daftar Paket | 4 paket contoh (kuota, harga, masa aktif). Tombol Pilih dan Bandingkan; maksimal 2 paket untuk dibandingkan. | UX-05 |
| Bandingkan Paket | Tabel dua paket: kuota, harga, masa aktif, harga per GB. Tombol memilih salah satu. | UX-05 |
| Verifikasi Nomor | Nomor tersamar. Tombol Verifikasi lalu panel verifikasi ulang berisi alasan dan keterangan pembelian belum diproses. | UX-03 |
| Pembayaran | Ringkasan pesanan, metode (Pulsa, E-wallet, Transfer bank), tombol Bayar, pilihan demo "simulasikan transaksi gagal". Setelah Bayar tampil status diproses. | UX-02 |
| Konfirmasi Hasil | Status berhasil atau gagal, detail transaksi, tombol Lihat Riwayat dan Kembali ke Beranda. Jika gagal: pesan jelas dan tombol Bantuan. | UX-01, 04 |
| Riwayat Transaksi | Daftar transaksi terbaru di atas, filter status dan tanggal, tombol Lihat detail. | UX-04 |
| Detail Transaksi | Status, paket, harga, waktu, ID transaksi. | UX-04 |
| Bantuan | FAQ: transaksi gagal atau tertunda; kenapa diminta verifikasi ulang. | UX-01, 03 |

## 8. Navigasi

- Menu utama tetap di bawah layar: **Beranda, Beli Paket, Riwayat Transaksi, Bantuan** (empat menu).
- Alur Beli Paket berurutan (daftar, bandingkan, verifikasi, pembayaran, konfirmasi).
- Kedalaman maksimal tiga tingkat; tombol kembali tersedia di langkah alur.
- Pintasan: tombol Lihat Riwayat di Konfirmasi Hasil dan Status Terakhir di Beranda membuka Detail Transaksi.

## 9. Data dan Batasan Teknis

- Aplikasi web statis satu file (`index.html`), HTML, CSS, dan JavaScript murni tanpa build step.
- Data paket dan nomor adalah data contoh. Riwayat dan sisa kuota disimpan di `localStorage` browser.
- Tidak ada backend, pembayaran sungguhan, atau data pengguna nyata.
- Bahasa antarmuka: Bahasa Indonesia. Tampilan mobile first (lebar maksimal 430 px).

## UX Skill dan agent.md

- `agent.md`: instruksi untuk agent (urutan kerja, aturan, definisi selesai).
- `ux-skill/SKILL.md`: aturan UX utama (prinsip, aturan per tahap journey, komponen, microcopy, aksesibilitas, checklist, anti-pattern).
- `ux-skill/references/`: rujukan detail (`persona-journey.md`, `microcopy.md`, `checklist.md`).

Perbedaan dengan repo PRD Only: stepper "Langkah n dari 5", status dengan ikon dan teks, pengumuman status untuk pembaca layar (aria-live), fokus berpindah ke judul tiap layar, notifikasi (toast), tombol Kembali, status bertahap saat pembayaran, target sentuh 48 px, kontras lebih tinggi, dan layar gagal dengan tombol Coba bayar lagi.

## Struktur Repo

```
mytelkomsel-prd-ux-skill/
├── README.md              <- PRD (file ini)
├── CHANGELOG.md           <- riwayat perubahan
├── agent.md               <- instruksi agent
├── ux-skill/
│   ├── SKILL.md           <- UX Skill utama
│   └── references/
│       ├── persona-journey.md
│       ├── microcopy.md
│       └── checklist.md
└── index.html             <- source code prototipe (siap di-deploy)
```

## Pengujian dan Metrik

Diuji lewat usability test dengan 3 pengguna (mahasiswa prabayar) pada skenario: beli paket, verifikasi, bayar, lalu pastikan transaksi berhasil.

- UX-01: 3 dari 3 pengguna dapat memastikan transaksi berhasil hanya dari layar setelah pembayaran.
- UX-02: pengguna dapat menyebutkan status pembayaran saat proses berjalan tanpa mengulang pembayaran.
- UX-03: pengguna dapat menjelaskan alasan verifikasi ulang dan lanjut tanpa bertanya.
- UX-04: riwayat tercapai maksimal 2 ketukan.
- UX-05: dua paket dapat dibandingkan tanpa kembali ke halaman sebelumnya.
- UX-07: sisa kuota bertambah tanpa menyegarkan manual.

Angka di atas adalah target usulan dari Worksheet 8 dan belum diuji.

## Asumsi dan Risiko

- Struktur ini usulan perancangan, bukan struktur resmi MyTelkomsel.
- Card sorting dilakukan mandiri dan belum diuji dengan pengguna.
- Mode Hemat Data dan Pusat Bantuan adalah asumsi pendukung; Mode Hemat Data di prototipe hanya simulasi tampilan ringan.
- Data riset hanya dari 3 responden dalam satu sesi observasi.

## Menjalankan dan Deploy

Jalankan lokal: buka `index.html` di browser (tidak perlu instalasi).

Deploy dengan GitHub Pages: **Settings, Pages, Deploy from a branch, branch `main`, folder `/ (root)`**, lalu simpan. Setelah selesai, tulis tautannya di bawah.

- Demo: https://kurniaa13.github.io/mytelkomsel-prd-ux-skill/
## Sumber

Worksheet 1 (UX Detective), 3 (Know Your User), 5 (Observasi Pengguna), 6 (Empathy Map dan Persona), 7 (User Journey), 8 (UX Requirements), 9 (Information Architecture). Mata kuliah Rekayasa Interaksi (UX), Universitas Muhammadiyah Malang.
