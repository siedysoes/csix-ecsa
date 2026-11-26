# Membangun Portofolio yang Aman

Portofolio adalah sekumpulan artefak pendek dan jujur yang menunjukkan cara Anda berpikir. Ini bukan kumpulan exploit. Bagi pemula, dua atau tiga laporan lab yang dibuat dengan cermat lebih berguna daripada segulung skrip hasil salinan. Situs ini adalah **sumber belajar independen, bukan resmi**, tidak berafiliasi dengan EC-Council; EC-Council, CEH, ECSA dan LPT adalah merek dagang dari pemiliknya.

## Aturan emas: izin tertulis atau lab yang Anda miliki

Setiap artefak yang Anda publikasikan harus berasal dari:

- sistem yang Anda miliki dan kendalikan, seperti mesin virtual lokal;
- range latihan yang ketentunya telah Anda baca dan ikuti; atau
- sistem di mana Anda memiliki **izin tertulis eksplisit** yang mencakup pengujian maupun publikasi.

Jangan pernah mempublikasikan temuan tentang organisasi nyata, perangkat pribadi, atau akun orang lain. Jangan sertakan data pribadi, kredensial asli, token, cookie, atau informasi pelanggan. Jika ragu, jangan sertakan. Lihat [Lingkup, Otorisasi & Etika](../fundamentals/scope-and-ethics.md).

## Struktur laporan yang bisa dipakai ulang

| Bagian | Apa yang ditulis |
|---|---|
| Judul + tanggal | Nama latihan yang singkat dan netral |
| Pernyataan lingkup | Sistem mana tepatnya dan jendela waktu pengujian apa yang termasuk dalam lingkup |
| Catatan otorisasi | Siapa yang menyetujui dan dari mana izin berasal (diparafrosakan, tanpa detail pribadi) |
| Ringkasan metodologi | Beberapa baris tentang fase, alat secara garis besar, dan batasan |
| Temuan | Satu per masalah: kondisi, dampak, dan tingkat keparahan secara konseptual beserta alasannya |
| Bukti | Screenshot atau diagram yang sudah disanitasi dengan nama dan data dihapus |
| Perbaikan | Saran praktis dan defensif yang bisa diterapkan oleh tim pertahanan |
| Pembelajaran | Apa yang Anda salah, apa yang akan Anda ulangi, apa yang harus dipelajari berikutnya |

Jaga tingkat keparahan tetap **konseptual**: jelaskan penalaran Anda alih-alih mengklaim skor formal. Laporan dua halaman yang mudah dibaca lebih baik daripada tumpukan seratus halaman. Untuk fase-fase di balik laporan, lihat [Metodologi Penetration Testing](../fundamentals/pentest-methodology.md).

## Writeup CTF: periksa aturan terlebih dahulu

Writeup CTF boleh **hanya jika aturan acara mengizinkan publikasi**, dan biasanya hanya setelah acara berakhir. Beberapa kompetisi membatasi pembagian flag atau solusi. Baca aturannya, tunggu bila diperlukan, dan jangan pernah menautkan writeup ke target yang masih aktif. Jika aturannya tidak jelas, tanyakan kepada penyelenggara atau cukup jangan publikasikan.

## Tata letak GitHub sederhana

```
portfolio/
├── README.md              # indeks: satu baris per proyek + tautan
├── lab-01-web-app/
│   ├── report.md          # laporan terstruktur di atas
│   ├── scope-and-authorization.md
│   └── evidence/          # hanya gambar yang sudah disanitasi
├── lab-02-network/
│   └── report.md
└── notes/
    └── what-i-learned.md
```

`README.md` adalah indeks: tabel singkat berisi proyek, tanggal, keterampilan yang ditunjukkan, dan tautan. Jaga kode tetap minimal dan bersifat penjelasan — ini portofolio, bukan repositori exploit. Jangan publikasikan payload atau langkah-langkah yang bisa membantu seseorang menyerang sistem yang bukan miliknya.

## Sebelum menekan publish

- [ ] Izin dan kepemilikan lab sudah jelas.
- [ ] Screenshot tidak memuat data pribadi atau identifier asli.
- [ ] Temuan ditulis sehingga orang bukan spesialis pun bisa mengikutinya.
- [ ] Saran perbaikan tersedia dan bersifat defensif.
- [ ] Aturan CTF mengizinkan writeup.

## Lihat juga

- [Metodologi Penetration Testing](../fundamentals/pentest-methodology.md)
- [Pelatihan, Lab & Range Latihan](../exam/training-and-labs.md)
- [Karier Setelah ECSA](ecsa-careers.md)
- [Sertifikasi & Skill Berikutnya](next-steps.md)
- [Skill, Rekrutmen & Realita Lapangan](reality-check.md)
