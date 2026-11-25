# Changelog

Semua perubahan penting pada repo ini dicatat di sini. Format mengikuti [Keep a Changelog](https://keepachangelog.com/id-ID/1.1.0/) dan versi memakai [Semantic Versioning](https://semver.org/lang/id/).

## [0.4.0] - 2026-11-25

### Added
- `ux-skill/SKILL.md` dan `ux-skill/references/` (`persona-journey.md`, `microcopy.md`, `checklist.md`): UX Skill dari hasil Worksheet 1 sampai 9.
- `agent.md`: instruksi kerja agent (urutan, aturan, definisi selesai).
- `index.html`: prototipe web alur Beli Paket yang dibuat dari PRD **plus** UX Skill.

### UX improvements dibanding versi PRD Only
- Stepper "Langkah n dari 5" di alur Beli Paket.
- Status memakai ikon dan teks (Berhasil, Gagal, Diproses), tidak hanya warna.
- Status pembayaran bertahap ("Menghubungi penyedia pembayaran…", "Menunggu konfirmasi pembayaran…").
- Notifikasi (toast) setelah transaksi selesai; fokus pindah ke judul layar dan status diumumkan lewat `aria-live`.
- Layar gagal punya tombol Coba bayar lagi dan Buka Bantuan; tombol Kembali di tiap langkah.
- Perbandingan paket menandai harga per GB yang lebih hemat.
- Target sentuh minimal 48 px, indikator fokus keyboard, warna lebih kontras, dan dukungan `prefers-reduced-motion`.

### Notes
- Alur diuji otomatis (jalur berhasil dan gagal) dengan jsdom.

## [0.3.0] - 2026-11-25

### Changed
- Versi PRD disamakan dengan repo PRD Only (kebutuhan, sitemap, spesifikasi halaman) agar perbandingan hasil adil. Perbedaan hanya pada UX Skill dan `agent.md`.

## [0.2.0] - 2026-11-17

### Added
- PRD: struktur informasi (sitemap), spesifikasi halaman, dan navigasi dari Worksheet 9 (Information Architecture).

## [0.1.0] - 2026-11-13

### Added
- PRD awal: ringkasan masalah, persona Naira, tujuan, dan daftar kebutuhan UX-01 sampai UX-08 beserta prioritas dari Worksheet 8 (UX Requirements).
