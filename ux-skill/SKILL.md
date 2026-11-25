---
name: mytelkomsel-purchase-flow-ux
description: Aturan UX untuk merancang dan membangun alur Beli Paket MyTelkomsel agar pengguna yakin verifikasi dan pembayarannya berhasil. Gunakan setiap kali membuat atau mengubah layar, teks antarmuka, navigasi, atau status pada alur beli paket di repo ini.
---

# UX Skill: Alur Beli Paket MyTelkomsel

Skill ini merangkum hasil riset pengguna (Worksheet 1 sampai 9) menjadi aturan yang bisa langsung diterapkan. Detail pendukung ada di `references/`.

## Kapan dipakai

Pakai skill ini untuk setiap pekerjaan yang menyentuh alur Beli Paket: memilih dan membandingkan paket, verifikasi nomor, pembayaran, konfirmasi hasil, riwayat transaksi, dan bantuan.

## Konteks pengguna (ringkas)

- **Persona Naira:** mahasiswa 22 tahun, Telkomsel prabayar, beli paket 1 sampai 3 kali per bulan, teliti soal kuota dan harga, kemampuan teknologi menengah.
- **Masalah utama:** tidak yakin bahwa verifikasi dan pembayaran berhasil.
- **Moment of Truth:** saat memastikan transaksi berhasil (setelah pembayaran).
- Detail: `references/persona-journey.md`.

## Lima prinsip inti

1. **Status selalu terlihat.** Setiap proses punya status yang jelas: Diproses, Berhasil, atau Gagal. Tidak ada layar yang diam tanpa kabar.
2. **Tidak ada keraguan setelah aksi.** Setelah pengguna menekan Bayar, tampilkan hasil di layar yang sama alurnya, bukan di menu lain.
3. **Jelaskan alasan.** Kalau meminta sesuatu (misalnya verifikasi ulang), katakan kenapa, apa langkah berikutnya, dan apa yang belum terjadi.
4. **Satu jalur.** Satu pintasan dan satu menu untuk Beli Paket. Tidak ada ikon ganda.
5. **Bahasa sederhana.** Kalimat pendek, kosakata baku (lihat `references/microcopy.md`), tanpa istilah teknis.

## Aturan per tahap User Journey

| Tahap | Wajib | Hindari |
|---|---|---|
| 1. Menyadari kuota menipis | Sisa kuota terlihat di Beranda; pintasan Beli Paket jelas. Sediakan Mode Hemat Data (perlu validasi). | Menyembunyikan sisa kuota di menu lain. |
| 2. Memilih paket | Kuota, harga, dan masa aktif terlihat di daftar; bisa membandingkan 2 paket; tampilkan harga per GB. | Detail penting hanya muncul setelah paket dipilih. |
| 3. Verifikasi nomor | Beri alasan verifikasi ulang, langkah berikutnya, dan keterangan pembelian belum diproses. | Meminta verifikasi ulang tanpa penjelasan. |
| 4. Membayar | Ringkasan pesanan; status "Diproses" dengan indikator; pesan bertahap; jangan menyuruh mengulang. | Layar kosong atau tombol Bayar bisa ditekan dua kali tanpa tanda. |
| 5. Memastikan transaksi berhasil | Halaman konfirmasi otomatis: status, paket, harga, waktu, ID; notifikasi; tombol Lihat Riwayat. | Membiarkan pengguna mencari bukti sendiri. |
| 6. Mengecek kuota | Sisa kuota diperbarui otomatis dan disebut di konfirmasi. | Meminta pengguna menyegarkan halaman. |

## Aturan IA dan navigasi

- Empat menu utama tetap di bawah: Beranda, Beli Paket, Riwayat Transaksi, Bantuan.
- Kedalaman maksimal tiga tingkat. Penjelasan verifikasi dan status pembayaran adalah tampilan di dalam halaman, bukan halaman baru.
- Alur Beli Paket berurutan dan memakai penanda langkah "Langkah n dari 5: nama langkah".
- Setiap langkah alur punya tombol Kembali. Menu yang sedang aktif ditandai (`aria-current="page"`).
- Konfirmasi Hasil menghubungkan ke Detail Transaksi (Lihat Riwayat); jika gagal, ke Bantuan.
- Nama menu menjelaskan isinya. Pengguna harus bisa memperkirakan isi halaman sebelum membukanya.

## Aturan komponen

- **Chip status:** ikon + teks + warna (✓ Berhasil, ✕ Gagal, … Diproses). Warna saja tidak cukup.
- **Stepper:** teks "Langkah n dari 5: ..." dan bilah progres.
- **Tombol:** satu tombol utama per layar; tinggi minimal 48 px; label berupa kata kerja ("Bayar Rp65.000", bukan "OK").
- **Notifikasi (toast):** muncul setelah transaksi selesai, memakai `role="status"`, hilang otomatis dalam beberapa detik, dan informasinya tetap ada di layar konfirmasi.
- **Keadaan gagal:** jelaskan apa yang terjadi dan beri dua jalan: Coba bayar lagi dan Buka Bantuan.
- **Keadaan kosong:** jelaskan kenapa kosong dan apa yang bisa dilakukan.
- **Tabel perbandingan:** kolom per paket, tandai yang lebih hemat dengan teks, bukan hanya warna.

## Microcopy

- Kosakata status baku: **Diproses, Berhasil, Gagal**. Jangan campur dengan "Sukses", "Pending", atau "Error".
- Sapaan "kamu", nada ramah dan singkat.
- Jangan menjanjikan hal yang belum pasti. Tulis fakta yang diketahui sistem.
- Contoh benar dan salah: `references/microcopy.md`.

## Aksesibilitas dan performa ringan

- Fokus berpindah ke judul (`h1`) setiap pindah layar; perubahan status diumumkan lewat `aria-live`.
- Semua kontrol bisa dipakai dengan keyboard dan punya indikator fokus yang jelas.
- Kontras teks minimal 4,5:1.
- Hormati `prefers-reduced-motion`. Mode Hemat Data mematikan animasi dan dekorasi.

## Checklist penerimaan

Gunakan `references/checklist.md` sebelum menyatakan pekerjaan selesai. Ringkasnya:

- UX-01: konfirmasi hasil muncul otomatis setelah bayar, plus notifikasi.
- UX-02: status Diproses terlihat selama pembayaran berjalan.
- UX-03: verifikasi ulang punya alasan dan langkah berikutnya.
- UX-04: riwayat dicapai maksimal 2 ketukan; ada filter status dan tanggal.
- UX-05: dua paket bisa dibandingkan dalam satu layar.
- UX-06: Mode Hemat Data tersedia (simulasi).
- UX-07: sisa kuota diperbarui otomatis.
- UX-08: hanya satu pintasan dan satu menu Beli Paket.

## Anti-pattern

- Kalimat umum: "Terjadi kesalahan", "Aplikasi harus mudah digunakan".
- Status hanya dengan warna.
- Konfirmasi hanya lewat notifikasi sistem tanpa layar konfirmasi.
- Verifikasi ulang tanpa alasan.
- Dua jalur atau ikon berbeda untuk fungsi yang sama.
- Menambah fitur yang tidak ada di PRD.
