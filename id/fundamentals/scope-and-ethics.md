# Lingkup, Otorisasi & Etika

Sebelum siapa pun menjalankan alat, penetration test memerlukan **persetujuan tertulis** dan kerangka etika. Artikel ini menjelaskan seperti apa otorisasi yang bertanggung jawab pada tingkat konseptual. Ini adalah materi edukatif, hanya untuk pengujian yang diotorisasi, tanpa perintah eksploitasi, payload, teknik penghindaran (evasion), atau instruksi untuk menyerang sistem yang bukan milik Anda.

> Sumber belajar independen dan tidak resmi: EC-Council, CEH, ECSA, dan LPT adalah merek dagang dari pemiliknya masing-masing. Situs ini tidak berafiliasi dengan EC-Council dan tidak memuat materi kursus atau ujian resmi. Sertifikat tidak pernah menggantikan izin.

## Yang sebaiknya dicakup persetujuan tertulis

| Butir | Mengapa penting |
|---|---|
| Target yang disebutkan nama dan pengecualian yang eksplisit | Mencegah pengujian tidak sengaja pada sistem yang tidak disetujui siapa pun |
| Batas lingkup dan jenis pengujian | Memisahkan pemeriksaan yang diizinkan dari teknik di luar batas |
| Jendela waktu uji yang disepakati | Mengurangi gangguan pada jam-jam kritis bisnis |
| Kontak darurat dan jalur eskalasi | Memberi tim pertahanan cara cepat untuk menghentikan atau mengalihkan pekerjaan |
| Aturan penanganan data | Menentukan bukti apa yang boleh dikumpulkan, disimpan, dan dibagikan |
| Kondisi penghentian | Menetapkan pemicu yang jelas untuk jeda jika muncul risiko |
| Pelaporan dan hasil yang diserahkan | Menjelaskan siapa yang menerima temuan dan kapan |
| Pertimbangan hukum dan yurisdiksi | Lokasi berbeda dapat memiliki aturan berbeda; mintalah nasihat setempat jika perlu |

Dokumen itu adalah titik awal, bukan tameng. Jika realitas berubah — layanan baru muncul, kepemilikan tidak jelas, atau pengujian menyentuh sistem yang tidak terduga — jedalah dan minta klarifikasi secara tertulis.

## Etika selama proyek berlangsung

Bekerjalah hanya dalam lingkup yang disepakati dan hormati pihak ketiga. Host bersama, tenant cloud, atau layanan pemasok mungkin menyimpan data milik orang-orang yang tidak pernah menyetujui pengujian ini. Kumpulkan data seminimal mungkin yang dibutuhkan untuk mendukung temuan, hindari membuka informasi pribadi, dan perlakukan bukti sesuai kesepakatan. Jangan menjalankan denial-of-service atau tindakan destruktif kecuali secara eksplisit disepakati, dan itupun perlakukan dengan sangat hati-hati.

Jujurlah tentang apa yang Anda amati. Jangan melebih-lebihkan keparahan untuk mengesankan klien, menyembunyikan kesalahan, atau mengklaim akses yang tidak Anda capai. Etika juga mencakup cara Anda berkomunikasi: temuan harus membantu tim pertahanan, bukan mempermalukan mereka.

## Bukti, penyimpanan, dan tindak lanjut

Simpan catatan yang akurat dan dapat direproduksi, tetapi simpan dengan aman dan hapus materi ketika kesepakatan tidak lagi mensyaratkannya. Laporkan temuan kepada kontak yang berotorisasi, dukung perbaikan dengan konteks praktis, dan uji ulang hanya dengan izin. Tindak lanjut di sisi pertahanan (defensive follow-up) adalah inti dari latihan ini.

## Perbedaan hukum dan tanggung jawab pribadi

Aturan berbeda menurut negara, wilayah, dan sektor, serta kebijakan organisasi bisa lebih ketat daripada hukum. Jika Anda ragu apakah suatu tindakan diizinkan, jangan lanjutkan — tanyalah kepada pemilik proyek atau profesional yang kompeten. Rasa ingin tahu pribadi tidak pernah menjadi otorisasi yang sah.

EC-Council secara berkala memperbarui versi ECSA dan format ujian; verifikasi detail terkini di [eccouncil.org](https://www.eccouncil.org/). Harapan terkait etika dan otorisasi juga berbeda menurut organisasi dan proyek.

## Lihat juga

- [Metodologi Penetration Testing](pentest-methodology.md)
- [Apa Itu ECSA](what-is-ecsa.md)
- [Membangun Portofolio yang Aman](../career/portfolio.md)
- [Skill, Rekrutmen & Realita Lapangan](../career/reality-check.md)
