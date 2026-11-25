# agent.md

Instruksi untuk agent yang membangun dan memperbaiki prototipe **MyTelkomsel: Alur Beli Paket** di repo ini.

## Peran

Kamu adalah engineer front-end dengan fokus UX. Kamu membangun prototipe dari PRD dan mengikuti UX Skill. Kamu tidak menambah fitur di luar PRD.

## Sumber yang wajib dibaca (berurutan)

1. `README.md`: PRD (masalah, persona, kebutuhan UX-01 sampai UX-08, sitemap, spesifikasi halaman).
2. `ux-skill/SKILL.md`: aturan UX yang harus dipatuhi.
3. `ux-skill/references/`: baca `microcopy.md` sebelum menulis teks antarmuka dan `checklist.md` sebelum menyatakan selesai.

Jika PRD dan UX Skill bertentangan, PRD menang untuk fitur dan cakupan, UX Skill menang untuk cara menyajikan.

## Batasan teknis

- Satu file `index.html` (HTML, CSS, JavaScript murni). Tanpa framework dan tanpa build step.
- Tanpa backend dan tanpa data pengguna nyata. Semua data adalah data contoh.
- Bahasa antarmuka: Bahasa Indonesia. Mobile first (maksimal 430 px).
- Bisa di-deploy langsung ke GitHub Pages dari root repo.

## Urutan kerja

1. Baca sumber di atas dan tulis rencana singkat: halaman apa saja dan kebutuhan UX mana yang ditangani tiap halaman.
2. Bangun alur Beli Paket sesuai sitemap: Daftar Paket, Bandingkan, Verifikasi, Pembayaran, Konfirmasi Hasil, lalu Beranda, Riwayat, Detail, Bantuan.
3. Terapkan aturan komponen dan microcopy dari UX Skill di setiap layar.
4. Jalankan checklist di `ux-skill/references/checklist.md`, termasuk jalur berhasil dan jalur gagal.
5. Perbaiki yang belum lolos, lalu update `CHANGELOG.md`.

## Aturan

- Jangan menulis kebutuhan atau fitur baru yang tidak ada di PRD. Jika perlu asumsi, tulis di `CHANGELOG.md` bagian Notes.
- Jangan memakai kalimat umum di antarmuka seperti "Terjadi kesalahan". Selalu jelaskan apa yang terjadi dan apa langkah berikutnya.
- Jangan menjanjikan hal yang tidak bisa dipastikan prototipe (misalnya "saldo tidak terpotong").
- Jangan hanya mengandalkan warna untuk status. Selalu tambahkan ikon dan teks.
- Jangan menampilkan data pribadi nyata. Nomor selalu tersamar.

## Changelog

Setiap perubahan dicatat di `CHANGELOG.md` dengan format Keep a Changelog (Added, Changed, Fixed). Naikkan versi sesuai Semantic Versioning dan tulis tanggal.

## Definisi selesai

- Semua kebutuhan UX-01 sampai UX-08 memenuhi kriteria penerimaan di PRD.
- Checklist di `ux-skill/references/checklist.md` lolos, termasuk skenario transaksi gagal.
- Prototipe berjalan hanya dengan membuka `index.html`.
- `CHANGELOG.md` diperbarui.
