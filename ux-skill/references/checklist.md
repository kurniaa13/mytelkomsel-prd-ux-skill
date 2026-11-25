# Checklist Penerimaan dan Skrip Uji

## A. Checklist per kebutuhan UX

- [ ] **UX-01** Setelah menekan Bayar, halaman Konfirmasi Hasil muncul otomatis (status, paket, harga, waktu, ID). Notifikasi muncul. Pengguna tidak perlu membuka menu lain.
- [ ] **UX-02** Selama pembayaran berjalan ada status "Diproses" dengan indikator dan pesan bertahap. Tidak ada layar kosong.
- [ ] **UX-03** Layar verifikasi ulang memuat alasan, langkah berikutnya, dan keterangan pembelian belum diproses.
- [ ] **UX-04** Riwayat Transaksi dapat dicapai maksimal 2 ketukan dari Konfirmasi Hasil atau Beranda; ada filter status dan tanggal; ada Detail Transaksi.
- [ ] **UX-05** Dua paket dapat dibandingkan dalam satu layar (kuota, harga, masa aktif, harga per GB).
- [ ] **UX-06** Mode Hemat Data tersedia dan bekerja (simulasi tampilan ringan).
- [ ] **UX-07** Sisa kuota di Beranda bertambah otomatis setelah transaksi berhasil dan disebut di konfirmasi.
- [ ] **UX-08** Hanya ada satu pintasan Beli Paket di Beranda dan satu menu utama Beli Paket.

## B. Checklist umum

- [ ] Status memakai ikon + teks + warna.
- [ ] Setiap langkah alur punya "Langkah n dari 5" dan tombol Kembali.
- [ ] Fokus berpindah ke judul tiap pindah layar; status diumumkan lewat aria-live.
- [ ] Semua kontrol bisa dipakai dengan keyboard; indikator fokus terlihat.
- [ ] Target sentuh minimal 48 px; kontras teks minimal 4,5:1.
- [ ] Microcopy memakai kosakata baku (Diproses, Berhasil, Gagal) dan tidak menjanjikan hal yang tidak pasti.
- [ ] Nomor selalu tersamar; tidak ada data pribadi nyata.
- [ ] Berjalan hanya dengan membuka `index.html`.

## C. Jalur yang wajib diuji

1. **Berhasil:** Beranda, Beli Paket, pilih paket, verifikasi, verifikasi ulang, bayar, konfirmasi berhasil, Lihat Riwayat, kembali ke Beranda (kuota bertambah).
2. **Gagal:** sama sampai Pembayaran, centang "simulasikan transaksi gagal", bayar, layar gagal, Coba bayar lagi atau Buka Bantuan; kuota tidak berubah.
3. **Perbandingan:** pilih dua paket, buka perbandingan, pilih salah satu.
4. **Riwayat:** filter status dan tanggal; buka Detail Transaksi.

## D. Skrip usability test (3 pengguna)

Tugas: "Kuota kamu hampir habis. Belilah paket data yang menurutmu paling pas, lalu pastikan pembeliannya berhasil." Peneliti mengamati tanpa mengarahkan dan mencatat:

- Apakah pengguna bisa memastikan hasil hanya dari layar setelah bayar (UX-01)?
- Apakah pengguna bisa menyebutkan status saat pembayaran berjalan (UX-02)?
- Apakah pengguna paham alasan verifikasi ulang tanpa bertanya (UX-03)?
- Berapa ketukan untuk sampai ke riwayat (UX-04)?
- Apakah pengguna membandingkan dua paket tanpa kembali ke halaman sebelumnya (UX-05)?

Catat hasil per pengguna (U1 sampai U3) di `CHANGELOG.md` bagian Notes pada versi berikutnya.
