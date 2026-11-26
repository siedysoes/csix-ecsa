# Lingkup, Otorisasi & Etika

> **Sumber belajar independen dan tidak resmi.** EC-Council, CEH, ECSA, LPT, dan
> nama kredensial lainnya adalah merek dagang dari pemiliknya. Situs ini tidak
> berafiliasi atau didukung oleh EC-Council, tidak memuat materi kursus resmi,
> kunci ujian, atau materi berhak cipta. Setelah kegiatan yang dibahas di sini
> mengandaikan lab yang Anda miliki atau sistem yang tercakup dalam **izin
> tertulis eksplisit**. Artikel ini membahas **proses, pertimbangan, bukti, dan
> pertahanan** — tanpa perintah, payload, langkah eksploitasi, atau petunjuk
> penghindaran deteksi — serta merupakan **pendidikan, bukan nasihat hukum**.

## Tujuan pembelajaran

Setelah membaca dan mengerjatkan latihan dalam artikel ini, Anda seharusnya mampu:

1. Membedakan permintaan, izin, kewenangan, dan kemampuan teknis, serta
   menjelaskan mengapa keempatnya harus selaras sebelum pekerjaan dimulai.
2. Menyusun pernyataan lingkup yang menyebut aset secara eksak, pengecualian,
   pemilik, dan bukti persetujuan.
3. Mengenali sistem pihak ketiga, infrastruktur bersama, dan kumpulan data
   tersembunyi sebelum berubah menjadi pelanggaran lingkup.
4. Menyusun *rules of engagement* (RoE) yang memuat jendela waktu, batas teknik,
   kontak, aturan data, kondisi berhenti, dan pengendalian perubahan.
5. Menerapkan gerbang keputusan lingkup pada setiap petunjuk baru, termasuk
   keputusan untuk berhenti dan eskalasi.
6. Menangani bukti dengan prinsip minimalisasi data, rantai penjagaan
   (*chain of custody*), dan rencana penghancuran yang disepakati.
7. Menjelaskan bagaimana privasi, etika, dan hukum setempat membentuk batas
   kerja penguji, serta kapan harus meminta nasihat profesional.
8. Melatih keputusan etis di bawah tekanan menggunakan skenario dan templat yang
   disediakan.

Jika poin 2, 4, dan 5 belum bisa Anda lakukan, yang Anda miliki adalah
keterampilan teknis yang masih mencari target — bukan keterampilan menjalankan
pengujian yang aman. Tiga poin itulah yang membedakan "bisa menguji" dari "boleh
menguji".

---

## Otorisasi adalah kontrol keamanan pertama

Uji penetrasi adalah pengecualian yang disengaja dari aturan normal. Tindakan
yang di luar konteks bisa disebut penyalahgunaan menjadi sah untuk **tujuan
tertentu**, dilakukan oleh **orang tertentu**, terhadap **sistem tertentu**,
dalam **jangka waktu tertentu**. Dokumen yang membuat pengecualian itu bukan
birokrasi yang mengganggu pekerjaan; dialah kontrol yang mencegah pengecualian
berubah menjadi insiden.

Empat gagasan berikut sering tertukar, padahal konsekuensinya sangat berbeda:

| Gagasan | Arti | Akibat jika tertukar |
|---|---|---|
| **Permintaan** | Seseorang meminta pengujian dilakukan | Keinginan dianggap sebagai lampu hijau |
| **Izin** | Seseorang mengatakan "ya" | Diandaikan si pengiyah sah mengikat organisasi |
| **Kewenangan** | Orang itu memang berhak menyetujui sistem dan data bersangkutan | Persetujuan diterima dari peminta yang tidak punya mandat |
| **Kemampuan teknis** | Anda memang bisa menjangkau sistem tersebut | Kemampuan dipakai sebagai pengganti izin |

Keempatnya harus hadir bersamaan. Seorang peminta bisa tulus dan tetap tidak
memiliki kewenangan. Seorang penandatangan bisa menguasai aplikasi tetapi tidak
menguasai platform bersama di bawahnya. Memiliki kredensial istimewa tidak
berarti Anda diberi hak memakainya untuk pengujian. Bila ragu, jawabannya
belum", bukan "sepertinya tidak apa-apa".

Otorisasi bersifat **spesifik, berbatas waktu, dan dapat dicabut**. Spesifik
berarti aset disebut satu per satu, bukan "semua milik kami". Berbatas waktu
berarti ada tanggal, jam, dan zona waktu, bukan "sampai selesai". Dapat dicabut
berarti klien boleh menghentikan pekerjaan dan kondisi berhenti boleh
menjedakannya tanpa debat kusir. Persetujuan tahun lalu tidak menaungi
lingkungan baru tahun ini.

Perlu dibedakan pula empat dokumen yang sering dianggap sama:

- **Pernyataan lingkup** menjawab *apa* yang boleh disentuh.
- **RoE** menjawab *bagaimana, kapan, dan dengan batas apa* pekerjaan dilakukan.
- **Kontrak** memuat ketentuan hukum dan komersial, termasuk tanggung jawab dan
  pemberitahuan.
- **Kebijakan internal** bisa lebih ketat dari ketiga-tiganya, misalnya soal
  akses karyawan atau penyimpanan data.

Bila ada pertentangan, aturan paling ketat yang berlaku yang menang, dan
pertentangan itu dilaporkan secara tertulis kepada kontak yang ditunjuk. Penguji
tidak berhak "memilih yang paling enak" dan diam-diam menyelesaikan konflik
sendiri.

---

## Gerbang keputusan lingkup

Setiap petunjuk baru — sebuah nama host yang muncul, pesan "tolong cek ini juga",
atau hasil yang menarik — melewati gerbang yang sama. Gerbang yang gagal
berarti **STOP**, bukan jalan memutar di sekitar pertanyaan.

```
                 PERMINTAAN atau PETUNJUK BARU
                              |
                              v
             +----------------------------------+
             | Peminta dan pemilik diketahui?   |
             +-------+--------------------+-----+
                     | TIDAK              | YA
                     v                    v
        [ STOP: identifikasi dulu,   +------------------------------+
          jangan sentuh sistem ]     | Otorisasi tertulis dari pihak|
                                     | berwenang tersedia?          |
                                     +-------+----------------+-----+
                                             | TIDAK         | YA
                                             v               v
                              [ STOP: minta tanda tangan ]  +------------------+
                                                           | Aset, environment|
                                                           | & status jelas?  |
                                                           +---+----------+---+
                                                               | TIDAK    | YA
                                                               v          v
                                                   [ STOP: lengkapi ]  +-------------+
                                                                       | Pihak ketiga|
                                                                       | terlibat?   |
                                                                       +--+------+--+
                                                                          | YA   | TIDAK
                                                                          v      v
                                              [ STOP: kecualikan /   +---------------+
                                                minta izin terpisah]| Jendela, teknik,|
                                                                   | kontak, data,  |
                                                                   | stop lengkap? |
                                                                   +---+--------+---+
                                                                       | TIDAK | YA
                                                                       v       v
                                                          [ STOP: RoE belum siap ]  |
                                                                                 v
                                                              +--------------------------------+
                                                              | KERJA hanya di dalam lingkup   |
                                                              | dan jendela yang disepakati    |
                                                              +---------------+----------------+
                                                                              |
                                                                              v
                                                              +--------------------------------+
                                                              | Stop event / perubahan ruang?  |
                                                              +---+------------------------+---+
                                                                  | YA                     | TIDAK
                                                                  v                        v
                                              [ PAUSE: hentikan, catat, kabari,       Bukti ->
                                               tunggu persetujuan tertulis ]        lapor ->
                                                                                  tinjau ->
                                                                                  retest ->
                                                                                  tutup
```

Diagram ini adalah alat bantu keputusan, bukan prosedur teknis. Sifat pentingnya
sederhana: **tidak ada satu pun cabang yang berkata "lanjutkan saja diam-diam"**.
Setiap gerbang yang gagal menghasilkan dua hal — pertanyaan kepada kontak yang
ditunjuk dan entri dalam log kegiatan. Ungkapan "cuma sekali ini" adalah jalan
yang mengubah penyimpangan kecil menjadi laporan insiden.

---

## Unsur lingkup yang wajib ditulis

Pernyataan lingkup baru berguna apabila dua orang membacanya dan menarik batas
yang sama. Ambiguitas bukan kelenturan; ia adalah risiko yang belum dialokasikan
ke siapa pun.

| Unsur lingkup | Yang wajib ditulis | Mengapa penting |
|---|---|---|
| Badan hukum dan pemilik | Entitas hukum, unit bisnis, penanggung jawab | Menentukan siapa yang menanggung risiko |
| Penandatangan | Nama, jabatan, bukti kewenangan, tanggal tanda tangan | Membuktikan otorisasi, bukan sekadar pesan |
| Aset dalam lingkup | Host, rentang alamat, aplikasi, environment, lokasi, ID tenant secara eksak | Menghilangkan tebakan di lapangan |
| Pengecualian eksplisit | Portal mitra, alamat bersama, vendor, data produksi, anak usaha | Membuat batas terlihat, bukan tersirat |
| Peta kepemilikan | Pemilik tiap aset, termasuk pemilik platform dan pemilik data | Mengungkap pihak ketiga yang tersembunyi |
| Status environment | Produksi, staging, lab, atau salinan — dan apakah salinan memuat data nyata | "Staging" tidak otomatis aman |
| Jendela pengujian | Tanggal, jam, zona waktu, hari jeda, durasi maksimum | Membuat izin benar-benar berbatas waktu |
| Kelas teknik | Kategori yang diizinkan, dibatasi, dan dilarang: perubahan state, gangguan layanan, ekspor data, rekayasa sosial, kerja fisik dan nirkabel | Menetapkan plafon intensitas |
| Aturan sumber | Sumber publik yang disepakati, bahan dari klien, data yang dikecualikan | Menjaga hipotesis tetap dapat ditelusuri |
| Syarat pihak ketiga | Penyedia, tenant, pemroses, dan siapa yang harus memberikan persetujuan | Mencegah kerugian pada pihak yang tidak menyetujui |
| Aturan data | Jenis bukti, minimalisasi, penyimpanan, akses, retensi, penghancuran, transfer | Melindungi orang, bukan hanya berkas |
| Kontak | Utama, teknis, darurat, privasi/hukum, eskalasi | Memungkinkan penghentian seketika |
| Kondisi berhenti | Pemicu, siapa yang menyatakan berhenti, cara melanjutkan | Menghilangkan improvisasi saat krisis |
| Komunikasi | Jadwal *check-in*, kanal status, penerima laporan | Mencegah kejutan di akhir pekerjaan |
| Hasil dan retest | Draf, laporan akhir, kriteria retest, catatan penutupan | Menutup siklus, bukan sekadar selesai |
| Pengendalian perubahan | Cara perubahan diajukan, disetujui, diberi tanggal, dan dicatat | Memblokir perluasan lewat percakapan lisan |

Uji sederhana: berikan dokumen ini kepada rekan kerja dan tanyakan aset mana
yang akan ia sentuh. Bila daftarnya berbeda, lingkup belum selesai.

---

## Siapa boleh mengotorisasi apa

Kewenangan itu didelegasikan, dibatasi, dan didokumentasikan. Tabel berikut
adalah **pola umum**, bukan aturan hukum universal; piagam organisasi, undang-
undang, dan kontrak dapat mengubah jawabannya.

| Peran atau pihak | Dapat mengotorisasi | Tidak boleh diasumsikan | Bukti yang disimpan |
|---|---|---|---|
| Pemilik sistem atau bisnis dengan delegasi | Pengujian atas sistem dan data yang dikuasainya | Platform bersama, sistem vendor, unit lain | Catatan delegasi |
| CISO atau pimpinan keamanan | Program kerja dalam mandat yang disetujui | Mengabaikan hukum atau ketentuan penyedia | RoE tertandatangani, rujukan kebijakan |
| Manajer operasi TI | Jendela pemeliharaan, akses lab, penjadwalan | Risiko hukum, target pihak ketiga | Persetujuan jendela, tiket internal |
| Pemilik aplikasi | Aplikasinya dan salinan nonproduksi | Infrastruktur bersama di bawahnya; data pelanggan nyata | Entri inventaris |
| Pengadaan dan hukum | Klausul kontrak, lintas batas, kewajiban pemberitahuan | Izin teknis untuk menyentuh sistem | Kontrak atau memo tertandatangani |
| Penyedia cloud/platform | Pemakaian platform sesuai ketentuan mereka | Persetujuan atas tenant lain | Kebijakan penyedia terbaru |
| Tenant lain | Hanya tenant miliknya | Menghapus hak tenant di sekitarnya | Persetujuan terpisah atau pengecualian |
| Perusahaan induk | Sistem grup yang memang berada di bawah kendalinya | Mengikat anak usaha atau akuisisi baru | Persetujuan korporat, daftar aset |
| Karyawan atau pengembang | Lab pribadi yang ia miliki dan isolasi | Sistem apa pun yang dikendalikan perusahaan | Catatan lab pribadi |
| Regulator atau auditor yang ditunjuk | Kerja dalam mandat yang dinyatakan | Akses tanpa batas; menghapus kewajiban menjaga | Surat penugasan |
| Kontak darurat | Menghentikan atau menjeda pekerjaan berjalan | Memperluas lingkup saat insiden | Catatan penghentian |
| Penguji | Hanya lab miliknya sendiri | Sistem klien, betapapun mudahnya dijangkau | Inventaris lab |

Dua aturan muncul dari tabel ini. Pertama, persetujuan dari satu pemilik
**tidak menular** ke aset milik pihak lain. Kedua, kekuasaan untuk
**menghentikan** lebih luas daripada kekuasaan untuk **memperluas**: hampir
siapa pun dalam daftar kontak boleh menghentikan pekerjaan, tetapi hanya
penandatangan berwenang melalui pengendalian perubahan yang boleh menambahnya.

---

## Kepemilikan pihak ketiga: batas yang bergerak

Kegagalan lingkup yang paling merugikan jarang bersifat spektakuler. Biasanya
seorang penguji mengikuti petunjuk biasa dan tanpa sengaja masuk ke
infrastruktur milik orang yang tidak pernah menyetujui pengujian.

- **Alamat bersama dan CDN.** Sebuah nama host dapat mengarah ke alamat yang
  dipakai banyak pelanggan. Catatan DNS membuktikan penamaan, bukan kepemilikan;
  pemeriksaan aktif bisa menyentuh sistem orang asing.
- **SaaS dan layanan kelolaan.** Aplikasi bisa milik klien, platform milik
  penyedia, dan data milik pelanggan klien. Ketentuan penyedia sering melarang
  pengujian aktif sama sekali.
- **Pemroses dan pengendali data.** Klien menentukan tujuan pemrosesan, sementara
  vendor menjalankan sistemnya; bukti yang terkumpul bisa memuat catatan
  organisasi lain.
- **Anak usaha dan akuisisi.** Sebuah merek tampak menyatu, sementara badan hukum,
  kontrak, dan rantai persetujuan masih terpisah.
- **Manusia.** Nama staf, catatan pelanggan, tiket, dan log percakapan dalam
  bukti adalah data pribadi orang yang tidak menyetujui pengujian kita.
- **Aset yang tidak dikenal.** Host aneh dalam inventaris adalah pertanyaan,
  bukan undangan. Eskalasikan; jangan "mengintip" untuk mencari tahu.

Pola amannya tetap sama: **identifikasi → catat → kecualikan atau minta
persetujuan tertulis terpisah**. Bila keduanya tidak memungkinkan, laporkan
keterbatasannya: *teramati, tidak diuji, terhalang oleh kepemilikan pihak ketiga*.
Itu adalah hasil profesional. Melanjutkan tanpa catatan bukanlah hasil.

---

## Rules of engagement: buku aturan operasional

RoE mengubah lingkup menjadi instruksi yang bisa diikuti oleh penguji **dan**
tim pertahanan ketika tekanan tinggi. RoE cukup pendek untuk dibaca saat insiden
dan cukup tegas untuk menyelesaikan perdebatan sebelum perdebatan itu muncul.

1. **Jendela dan intensitas.** Tanggal, jam setempat, masa jeda, dan plafon
   seberapa keras pemeriksaan boleh dilakukan. Sebuah teknik yang secara
   prinsip diizinkan tetap bisa salah dalam jendela produksi.
2. **Aturan environment.** Environment mana yang dipakai untuk kegiatan apa, dan
   kapan salinan lab lebih diutamakan atau diwajibkan.
3. **Kategori teknik.** Daftar izinkan, batasi, dan larang secara eksplisit.
   Diam bukan persetujuan: bila suatu kategori tidak tercantum, tanya dulu.
4. **Batasan sumber.** Sumber publik yang disepakati dan bahan yang diberikan
   klien; data yang diperoleh dari pihak luar dikecualikan.
5. **Komunikasi.** *Check-in* harian, tangga eskalasi, telepon darurat, dan satu
   kanal status. "Tidak ada perubahan" adalah laporan yang sah.
6. **Kondisi berhenti.** Pemicu yang disebut nama, siapa yang menyatakan berhenti,
   dan siapa yang boleh melanjutkan.
7. **Aturan data.** Apa yang boleh direkam, di mana disimpan, siapa yang boleh
   mengakses, dan kapan dihancurkan.
8. **Pengendalian perubahan.** Perubahan aset, waktu, teknik, atau kontak harus
   berupa amandemen tertulis yang diberi tanggal.
9. **Penutupan.** Tinjauan draf, laporan akhir, kriteria retest, penghancuran
   bukti, dan penutupan tertulis dari kedua belah pihak.

RoE yang baik melindungi tim pertahanan juga: operasi dapat membedakan aktivitas
yang sah dari aktivitas penyusup dan tahu kepada siapa mereka harus menelepon
bila ada yang tampak aneh.

---

## Kondisi berhenti dan apa yang terjadi saat dipicu

Kondisi berhenti adalah kejadian yang telah disepakati dan mengharuskan kerja
di jeda. Ia bukan tanda kegagalan; ia adalah kontrol yang sedang bekerja.

| Kategori | Contoh pemicu | Tindakan pertama |
|---|---|---|
| Teknis | Layanan menjadi tidak stabil atau melambat | Jeda, kabari kontak teknis, catat waktu |
| Lingkup | Sistem di luar lingkup atau sistem tak dikenal tersentuh | Hentikan aktivitas, catat aset, minta keputusan |
| Data | Data pribadi atau data pihak ketiga tak terduga muncul | Hentikan pengumpulan, amankan yang sudah ada, kabari kontak privasi |
| Otorisasi | Persetujuan dicabut atau jendela berakhir | Berhenti, konfirmasi tertulis, tanpa kelanjutan informal |
| Keselamatan | Ada tekanan melewati batas atau kontak tidak dapat dihubungi | Jeda, eskalasi ke pimpinan yang ditunjuk, dokumentasikan permintaan |

Urutannya selalu **berhenti → catat fakta → kabari kontak yang ditunjuk →
tunggu instruksi tertulis → lanjut hanya jika diizinkan**. Jangan menghapus bukti
agar peristiwa seolah tak pernah terjadi, jangan "menyelesaikan dulu" sebelum
memberi tahu siapa pun, dan jangan menganggap kontak yang tak terjangkau sebagai
izin. Kesalahan pun masuk ke catatan yang sama: bila Anda menyentuh aset yang
salah, tuliskan apa yang terjadi, kapan, apa yang teramati, dan siapa yang
diberitahu. Pengungkapan cepat adalah bagian dari kompetensi profesional.

---

## Bukti dan penanganan data

Bukti bukan koleksi trofi. Setiap butir harus menjawab pertanyaan tertentu,
memuat data paling sedikit yang cukup untuk menjawabnya, dan memiliki akhir
hayat yang jelas.

| Jenis bukti | Aturan minimalisasi | Penyimpanan dan akses | Retensi dan penghancuran | Jebakan umum |
|---|---|---|---|---|
| Tangkapan layar | Pangkas atau sensor identitas | Repositori terenkripsi yang disepakati, daftar akses bernama | Selama temuan terbuka, lalu hancurkan | Layar penuh memuat data pelanggan |
| Log dan cap waktu | Ambil hanya rentang yang relevan | Penyimpanan hanya-baca, catatan penjagaan | masa tinjau, lalu hapus | Menyalin seluruh kumpulan log |
| Catatan konfigurasi | Ekspor hanya pengaturan yang bersangkutan | Folder dengan kontrol akses | Terkait temuan; hapus saat penutupan | Ikut terbawa kata sandi atau token |
| Inventaris aset | Hanya penanda yang diperlukan untuk pemetaan lingkup | Dibagikan kepada kontak yang ditunjuk | Diperbarui saat penutupan, lalu diarsipkan atau dihancurkan | Aset tak dikenal tanpa penanda |
| Data pribadi | Hindari; sensor nama dan nomor identitas | Akses sangat terbatas, dasar pemrosesan didokumentasikan | Hapus pada titik paling awal yang diizinkan | Menganggap data staf "tidak berbahaya" |
| Kredensial atau rahasia | Jangan kumpulkan; catat saja fakta keterpaparannya | Tidak disimpan dalam paket bukti | Tidak berlaku — jangan menyimpan | "Membuktikan" dengan rahasia yang masih aktif |
| Data pihak ketiga | Kecualikan atau minta persetujuan terpisah | Penyimpanan terpisah bila disetujui | Ikuti aturan paling ketat | Mengira izin klien menutupi vendor |
| Catatan kerja | Fakta dulu, kesimpulan dipisahkan | Kontrol sama dengan bukti akhir | Diubah menjadi laporan atau dihapus | Catatan mentah di penyimpanan pribadi |
| Draf dan laporan | Beri label draf dan asumsi | Daftar distribusi terkontrol | Sesuai kontrak dan kebijakan | Dikirim ke milis yang tidak disetujui |
| Salinan dan cadangan | Ikut dihitung sebagai bukti | Inventarisasi dan kontrol akses | Dihancurkan bersama berkas utama | Lupa salinan di laptop |

Tiga kebiasaan membuat semua ini operasional: selenggara **rantai penjagaan**
(siapa memegang butir, kapan, dan untuk apa), terapkan **minimalisasi data**
sebelum merekam, dan sepakati retensi serta penghancuran sejak awal — lalu
konfirmasi saat penutupan, termasuk salinan dan cadangan.

---

## Etika, privasi, dan kode etik

Kode etik adalah sekumpulan janji yang tetap berlaku ketika tidak ada yang
mengawasi. Badan profesional menerbitkan kode masing-masing; bacalah teks mutakhir
yang berlaku bagi Anda, jangan menganggap daftar di bawah sebagai otoritas
tunggal.

1. **Tujuan yang sah saja.** Akses atau data yang diperoleh tidak dipakai untuk
   rasa penasaran, keuntungan pribadi, atau pekerjaan berikutnya.
2. **Kompetensi dan kejujuran.** Jangan mengklaim keahlian, temuan, atau akses
   yang tidak Anda miliki; beri label asumsi dan berhenti bila pekerjaan
   melampaui kemampuan Anda.
3. **Kerugian seminimal mungkin.** Pilih tindakan terkecil yang menjawab
   pertanyaan; utamakan salinan lab dan pengamatan tanpa perubahan state.
4. **Hormati pihak ketiga.** Orang yang sistem atau datanya Anda temui tetap
   punya hak meskipun mereka bukan klien Anda.
5. **Privasi sebagai keadaan awal.** Kumpulkan paling sedikit, sensor identitas,
   dan perlakukan data pribadi sebagai tanggung jawab, bukan bahan riset.
6. **Kerahasiaan.** Bagikan temuan hanya kepada penerima yang berwenang; jangan
   pernah memposting bukti atau detail pelanggan di kanal publik.
7. **Integritas pelaporan.** Jangan membesar-besarkan keparahan, meremehkan
   risiko nyata, atau menyembunyikan kesalahan.
8. **Kelola benturan kepentingan.** Ungkapkan kepentingan bersaing, hadiah, atau
   tekanan yang dapat memengaruhi penilaian; tolak pekerjaan yang tidak bisa
   Anda jalankan secara etis.
9. **Akuntabilitas.** Catat keputusan, akui kesalahan, dan eskalasi cepat ketika
   batas dilanggar.
10. **Komunikasi yang bertanggung jawab.** Pakai kanal yang disepakati dan
    pengungkapan terkoordinasi; jangan menerbitkan detail yang belum terverifikasi
    atau materi teknis berbahaya.

Privasi perlu penekanan khusus. Sebuah pengujian dapat membuka jauh lebih banyak
informasi pribadi daripada yang dibutuhkan tujuannya: nama dalam tiket, alamat
email pelanggan dalam log, data lokasi dalam ekspor. Sebelum menyimpan sesuatu,
tanyakan: *Apakah ini diperlukan untuk temuan? Apakah ada versi yang lebih
anonim? Apakah rencana data mencakupnya?* Bila satu jawaban saja kabur, jangan
simpan. Pemantauan karyawan, perekaman percakapan, dan akses ke perangkat
pekerja juga dapat diatur oleh aturan ketenagakerjaan dan perjanjian tempat
kerja yang lebih ketat daripada kontrak pengujian.

Etika juga mengatur tekanan. Klien yang berkata "kami membayar untuk menemukan
temuan kritis" sebenarnya meminta laporan yang dibengkokkan. Ulangi model
pembuktian Anda, tunjukkan penalaran, dan tawarkan pilihan yang sah: perbaiki,
terima risiko dengan penanggung jawab, atau uji hipotesis yang lebih dalam dalam
jendela baru yang disetujui.

---

## Variasi hukum dan batas artikel ini

Hukum bersifat teritorial dan spesifik per sektor. Aturan tentang akses tanpa
izin, penyadapan, pemantauan di tempat kerja, privasi, transfer data, dan
kewajiban lapor ke regulator berbeda antarnegara, kadang antarnegara bagian atau
provinsi. Kebiasaan yang lazim di satu yurisdiksi bisa melanggar hukum di
yurisdiksi lain. Kebijakan organisasi, kode profesi, ketentuan penyedia, dan
perjanjian bersama buruh dapat lebih ketat lagi.

Tentukan yurisdiksi yang berlaku bagi penguji, badan hukum klien, lokasi fisik
sistem, dan orang-orang yang datanya terlibat. Periksa pembatasan penyimpanan
bukti lintas batas, aturan sektor kesehatan, keuangan, telekomunikasi,
pendidikan, atau sistem publik, serta apakah pekerjaan memerlukan klausul
kontrak khusus, konsultasi dewan pekerja, atau pemberitahuan regulator. Bila
ragu, tanyakan kontak hukum atau privasi klien dan, seperlunya, profesional
berkualifikasi di yurisdiksi terkait.

Artikel ini bersifat pendidikan dan **bukan nasihat hukum, keuangan, pajak, atau
regulasi**. Artikel ini tidak dapat menentukan apakah sebuah tindakan sah di
tempat Anda tinggal atau bekerja. Otorisasi dalam dokumen tidak mengesampingkan
hukum, dan hukum tidak menggantikan otorisasi tertulis: keduanya harus terpenuhi.

Konteks kredensial: ECSA **tidak tercantum dalam katalog sertifikasi mutakhir
EC-Council saat diperiksa pada 26 Nov 2026**. Di sini ECSA diperlakukan sebagai
**jalur VAPT historis**, bukan program aktif dengan versi atau format ujian yang
tetap. Verifikasi informasi terkini di
[eccouncil.org](https://www.eccouncil.org/) dan
[cert.eccouncil.org](https://cert.eccouncil.org/), serta baca materi kode etik
resmi langsung dari sumbernya, bukan dari halaman ini.

---

## Tiga studi kasus fiktif

Ketiga kisah di bawah seluruhnya fiktif dan sengaja tidak memuat prosedur teknis.
Fokusnya adalah titik keputusan tempat pertimbangan jauh lebih penting daripada
alat.

### Kasus 1 — Lampu hijau hanya lewat telepon

**Latar.** Seorang manajer TI internal berkata kepada konsultan, "Silakan uji
portal pelanggan malam ini, kami percaya pada Anda." Portal itu dihoskan mitra;
perusahaan hanya memiliki kontrak dukungan, bukan kepemilikan. Tidak ada
dokumen, jendela waktu, maupun kontak darurat.

**Batasan.** Konsultan boleh menguji aplikasi milik perusahaan sendiri. Mitra
belum memberikan persetujuan, persetujuan dari penyedia kecil kemungkinannya,
dan manajer tersebut tersinggung oleh keraguan.

**Keputusan.** Konsultan menolak kegiatan aktif pada portal, menanyakan siapa
pemilik platform dan siapa yang sah menandatangani untuk aplikasi perusahaan,
serta menawarkan latihan terbatas pada salinan milik perusahaan sambil menunggu
administrasi. Permintaan lisan dicatat dalam pelacak kegiatan. Keesokan harinya
CISO menerbitkan lingkup tertandatangani untuk aplikasi milik perusahaan dengan
portal mitra sebagai pengecualian eksplisit.

**Yang diajarkan.** Izin, kewenangan, dan kepemilikan adalah tiga hal berbeda.
Bersikap sopan di bawah tekanan adalah cara menjaga batas. Menunda sehari jauh
lebih murah daripada berinteraksi tanpa izin dengan sistem produksi mitra.

### Kasus 2 — Satu tenant di antara banyak tenant

**Latar.** Klien meminta penilaian sebuah aplikasi web. Inventaris awal
menunjukkan nama publiknya mengarah ke alamat yang dipakai bersama pelanggan
lain, sementara antarmuka depan dijalankan vendor. Klien hanya memiliki satu
tenant dan datanya — bukan yang lain.

**Batasan.** Ketentuan platform membatasi pengujian aktif; tenant lain tidak
memberi persetujuan. Klien menginginkan keyakinan sebelum peluncuran dan
menyarankan "beberapa pemeriksaan cepat" pada alamat bersama itu.

**Keputusan.** Penguji mencatat alamat bersama, menandai aset sebagai
*milik pihak ketiga — tidak diuji*, dan menjeda kegiatan aktif di sana. Ia
menawarkan environment staging khusus, kesepakatan yang disetujui penyedia, atau
tinjauan konfigurasi hanya dari bahan yang diberikan klien. Tidak ada data
tenant lain yang dikumpulkan. Laporan menyatakan keterbatasan dan apa yang tetap
tidak terverifikasi.

**Yang diajarkan.** Nama host bukan kepemilikan. Pengujian yang tidak lengkap
dengan batasan yang jujur lebih baik daripada pengujian yang tampak lengkap
tetapi merugikan orang asing. Kewajiban kita juga berlaku terhadap tenant lain.

### Kasus 3 — Dua puluh menit melewati jendela

**Latar.** Jendela berakhir pukul 00.00. Pukul 23.50 muncul petunjuk menarik;
pukul 23.55 manajer piket berkata, "Tetap lanjut, kami butuh jawabannya"; pukul
23.58 aplikasi terasa lebih lambat.

**Batasan.** RoE berakhir tengah malam dan melarang perubahan state. Manajer itu
senior, tetapi pengendalian perubahan menunjuk CISO untuk perpanjangan. Petunjuk
tersebut bisa mengarah ke layanan yang dikecualikan.

**Keputusan.** Penguji berhenti tepat pukul 00.00, mencatat petunjuk sebagai
hipotesis yang belum terverifikasi, memberi tahu kontak teknis soal perlambatan,
dan mengirim catatan status: jendela ditutup, petunjuk didokumentasikan, tidak
ada perpanjangan yang disetujui. Perpanjangan lisan ditolak dan jendela baru
diminta secara tertulis. Belakangan klien mengonfirmasi petunjuk itu memang
menyangkut layanan yang dikecualikan.

**Yang diajarkan.** Batas waktu adalah kontrol keselamatan, bukan saran. Tekanan
untuk memperpanjang justru sinyal untuk memperlambat. Petunjuk yang belum selesai
dan tercatat dengan benar adalah keberhasilan; petunjuk yang tidak dicatat dan
besoknya menjadi "pemeriksaan cepat" bukanlah keberhasilan.

---

## Latihan per bagian

Jawab dengan suara keras sebelum membuka kunci. Tujuannya adalah melatih
keputusan, bukan menghafal definisi.

### Kewenangan dan lingkup

**Q1.** Seorang rekan berkata, "Direktur saya bilang tidak apa-apa — coba lihat
server itu." Apa langkah Anda?

**Q2.** Seorang CISO menyetujui "semua sistem perusahaan" lewat email. Apa yang
Anda tanyakan?

**Q3.** Sebuah domain dalam lingkup ternyata menampung portal pelanggan mitra.
Ambil keputusan Anda.

**Q4.** Apa bedanya penolakan terhadap permintaan dan penolakan terhadap orang
yang meminta?

<details>
<summary><strong>Kunci jawaban</strong></summary>

**A1.** Tidak ada kegiatan aktif. Tanyakan siapa yang berwenang menyetujui server
itu, minta persetujuan tertulis bertanggal yang menyebutnya, dan tawarkan
alternatif lab. Kalimat yang diteruskan dari orang lain bukan kewenangan.

**A2.** Mintalah aset eksak, environment, pengecualian, jendela, batas teknik,
serta kontak. "Semua sistem" bukan pernyataan lingkup.

**A3.** Catat portal sebagai pengecualian beserta pemilik dan alasannya; jangan
berinteraksi dengannya. Pengujiannya memerlukan persetujuan terpisah dari pemilik
atau penyedia platformnya.

**A4.** Anda menolak **tindakan** yang belum diotorisasi, bukan menolak
**orangnya**. Tetap sambung komunikasi, jelaskan alasan, dan tawarkan jalur yang
sah. Sikap ini menjaga hubungan tanpa melemahkan batas.

</details>

### Perubahan, jendela, dan penghentian

**Q5.** Di tengah pekerjaan seorang manajer menambah subnet secara lisan. Apa yang
Anda katakan?

**Q6.** Tersisa sepuluh menit dan petunjuk menjanjikan muncul. Putuskan.

**Q7.** Sebuah layanan melambat saat pemeriksaan. Sebutkan tiga tindakan pertama.

**Q8.** Kontak darurat tidak merespons, sementara rekan Anda menyarankan
"lanjut saja dulu". Putuskan.

<details>
<summary><strong>Kunci jawaban</strong></summary>

**A5.** "Dengan senang hati kami sertakan setelah perubahan tertulis tersedia,
lengkap dengan jendela, pemilik, dan kontak baru." Sebelum itu subnet tetap di
luar; permintaan dicatat.

**A6.** Berhenti saat jendela tutup, catat petunjuk sebagai belum terverifikasi,
dan minta jendela baru yang disetujui. Tidak ada "cuma satu lagi".

**A7.** Hentikan, kabari kontak teknis yang ditunjuk segera, dan catat waktu serta
pengamatan. Lanjutkan hanya dengan izin eksplisit.

**A8.** Jeda pekerjaan. Kontak yang tidak dapat dihubungi bukan persetujuan;
eskalasi melalui tangga yang telah disepakati dan dokumentasikan saran tersebut.

</details>

### Pihak ketiga dan data

**Q9.** Nama host dalam lingkup mengarah ke alamat bersama. Lanjutkan?

**Q10.** Tangkapan layar memuat nama dan email pelanggan. Apa yang Anda lakukan
sebelum menyimpannya?

**Q11.** Klien ingin semua bukti disimpan selamanya. Tanggapi.

**Q12.** Seorang teman menawarkan berkas data bocor "untuk membantu penentuan
lingkup". Pakai atau tidak?

<details>
<summary><strong>Kunci jawaban</strong></summary>

**A9.** Tidak ada pemeriksaan aktif. Catat pengamatan, tandai aset sebagai milik
pihak ketiga, dan minta environment khusus, persetujuan terpisah, atau tinjauan
konfigurasi saja.

**A10.** Pangkas atau sensor bila temuan tetap terbukti; bila tidak, cari bentuk
yang lebih anonim. Simpan versi minimal di repositori yang disepakati.

**A11.** Kutip rencana retensi yang disepakati dan risiko menyimpan data pribadi
tanpa batas; tawarkan masa tinjau dengan pemilik bernama. Pengecualian memerlukan
keputusan tertulis dari pemilik data dan kontak hukum/privasi.

**A12.** Tidak. Data curi atau data pribadi dari luar berada di luar aturan sumber
yang disepakati serta menimbulkan masalah hukum dan etika. Tolak dan catat
penawaran itu.

</details>

### Etika, hukum, dan pelaporan

**Q13.** Klien bersikeras sebuah temuan diberi label *informasional* karena
"hanya tiga orang yang memakainya". Tangani.

**Q14.** Penasihat di yurisdiksi lain mengatakan aturan pemberitahuan setempat
berlaku bagi bukti Anda. Apa yang berubah?

**Q15.** Anda menyadari telah menyentuh host di luar lingkup. Apa sekarang?

**Q16.** Anda menemukan kontrol yang berhasil menghentikan Anda. Apakah itu
layak masuk laporan?

<details>
<summary><strong>Kunci jawaban</strong></summary>

**A13.** Buka kembali bukti dan model keparahan: keterjangkauan, prasyarat,
dampak, dan kontrol kompensasi. Perbaiki laporan bila Anda keliru; bila tidak,
catat posisi klien beserta penalaran Anda. Jangan mengganti label secara diam-
diam.

**A14.** Terapkan aturan paling ketat untuk penyimpanan, transfer, akses, atau
pemberitahuan bersama kontak hukum/privasi; amandemen RoE sebelum melanjutkan
dan minta nasihat lokal yang berkualifikasi.

**A15.** Berhenti, buat catatan faktual tentang aset dan waktunya, kabari kontak
yang ditunjuk sesegera mungkin, dan minta instruksi. Jangan hapus catatan.

**A16.** Ya — itu temuan positif. Ia membuktikan kontrol bekerja dan membantu
klien memutuskan investasi berikutnya. Laporan tidak boleh hanya berisi daftar
kegagalan.

</details>

---

## Kesalahan umum yang perlu dihafal

- **"Cuma mau cek."** Rasa penasaran atau "iya" lisan dianggap otorisasi.
- **Berburu penandatangan.** Bertanya terus sampai ada yang setuju tanpa
  memeriksa kewenangannya atas aset itu.
- **Subnet dan subdomain implisit.** Mengira sebuah nama otomatis mencakup
  segala sesuatu di sekitarnya.
- **Buta alamat bersama.** Lupa tenant lain berdiri di balik satu alamat.
- **Mitologi staging.** Mengira salinan uji tidak memuat data nyata.
- **Perluasan diam-diam.** Mengikuti petunjuk menarik tanpa amandemen tertulis.
- **Penyimpangan jendela.** "Lima menit lagi" sampai batas waktu kehilangan
  makna.
- **Penimbunan bukti.** Log penuh, layar penuh, atau rahasia aktif demi
  "membuktikan" sesuatu.
- **Kontak kabur.** Tidak tahu siapa yang harus ditelepon saat penghentian
  diperlukan.
- **Retensi amnesia.** Lupa salinan dan cadangan saat bukti dihancurkan.
- **Teater keparahan.** Membesar-besarkan temuan untuk terlihat berharga.
- **Asumsi hukum seragam.** Menganggap aturan di satu negara berlaku identik di
  negara lain.

---

## Templat yang bisa dipakai ulang

Salin struktur ini ke catatan Anda. Ini kerangka, bukan pekerjaan yang sudah
jadi; nilainya muncul saat diisi secara jujur sebelum pengujian dimulai.

### Checklist RoE lengkap

```
IDENTITAS
[ ] ID / nama kegiatan; badan hukum dan unit klien; penguji & subkontraktor tercantum
[ ] Versi, tanggal, dan riwayat perubahan dicatat

KEWENANGAN
[ ] Penandatangan bernama, jabatan, bukti kewenangan, tanggal tanda tangan
[ ] Perjanjian / RoE tertandatangani menjadi rujukan
[ ] Delegasi didokumentasikan bila penandatangan bukan pemilik
[ ] Kewenangan dikonfirmasi untuk tiap aset yang dikuasai

LINGKUP
[ ] Aset eksak: host, rentang, aplikasi, environment, lokasi, tenant
[ ] Pengecualian ditulis eksplisit
[ ] Peta kepemilikan per aset, termasuk pemilik platform dan data
[ ] Status produksi / staging / lab / salinan tercatat
[ ] Keberadaan data nyata dalam salinan nonproduksi diperiksa
[ ] Pihak ketiga dikecualikan atau memiliki persetujuan terpisah

JENDELA DAN BATAS TEKNIK
[ ] Tanggal, jam, zona waktu, hari jeda, durasi maksimum
[ ] Kategori teknik yang diizinkan
[ ] Kategori dibatasi dan rute persetujuannya
[ ] Kategori dilarang dinyatakan eksplisit
[ ] Sumber informasi yang disepakati tercantum

KOMUNIKASI
[ ] Kontak utama, teknis, darurat, privasi/hukum
[ ] Tangga eskalasi dan rute di luar jam kerja
[ ] Frekuensi check-in dan kanal status
[ ] Penerima laporan serta proses tinjauan draf

KONDISI BERHENTI
[ ] Pemicu ketidakstabilan / perlambatan
[ ] Pemicu kontak dengan aset luar lingkup
[ ] Pemicu data sensitif atau data pihak ketiga
[ ] Pemicu pencabutan, berakhirnya jendela, dan keselamatan
[ ] Siapa yang menyatakan berhenti dan siapa yang boleh melanjutkan

PENANGANAN DATA
[ ] Jenis bukti yang diizinkan; aturan minimalisasi dan sensor
[ ] Lokasi penyimpanan, ekspektasi enkripsi, daftar akses bernama
[ ] Pembatasan transfer / lintas batas diperiksa
[ ] Masa retensi dan tanggal penghancuran disepakati
[ ] Salinan dan cadangan masuk dalam rencana penghancuran
[ ] Metode rantai penjagaan disepakati

PERUBAHAN DAN PENUTUPAN
[ ] Amandemen tertulis wajib untuk perubahan lingkup/waktu/teknik
[ ] Draf, laporan akhir, kriteria retest didefinisikan
[ ] Konfirmasi penghancuran bukti direncanakan
[ ] Penutupan tertulis dari kedua belah pihak direncanakan
[ ] Tanda tangan: klien ............ penguji ............
```

### Permintaan perubahan lingkup — kirim, jangan sekadar ucapkan

```
Kegiatan: [ID] | Pengaju: [nama, jabatan] | Waktu: [..]
Perubahan: [aset / waktu / teknik eksak] | Alasan: [satu baris]
Pemilik aset baru: [nama] | Bukti kewenangan: [rujukan]
Jendela baru diperlukan: [ya/tidak] | Pihak ketiga terlibat: [ya/tidak]
Keputusan: [setuju / tolak / tinjau] | Disetujui oleh: [..]
Entri riwayat perubahan: [versi, tanggal]
```

### Catatan peristiwa penghentian

```
Kegiatan: [ID] | Waktu berhenti dan zona waktu: [..]
Pemicu: [teknis / lingkup / data / otorisasi / keselamatan]
Fakta saja: [apa yang terjadi] | Aset atau data terlibat: [..]
Tindakan segera: [hentikan / kabari / amankan]
Kontak diberitahu dan waktunya: [..] | Instruksi: [..]
Dilanjutkan dengan izin tertulis? [ya/tidak — rujukan]
```

### Baris register bukti

| ID | Yang dibuktikan | Sumber dan waktu | Bentuk minimal | Penjaga | Retensi | Dihancurkan / tanggal |
|---|---|---|---|---|---|---|
| E-01 | | | | | | |

---

## Glosarium

| Istilah | Arti dengan bahasa sederhana |
|---|---|
| **Otorisasi** | Izin yang sah dan terdokumentasi untuk pekerjaan tertentu pada sistem tertentu |
| **Kewenangan** | Hak sah untuk memberikan izin tersebut |
| **Lingkup** | Daftar pasti aset, environment, dan kegiatan yang diizinkan |
| **RoE** | *Rules of Engagement*: bagaimana, kapan, dan dengan batas apa pekerjaan dijalankan |
| **Jendela pengujian** | Tanggal dan jam yang disepakati untuk kegiatan aktif |
| **Kondisi berhenti** | Kejadian yang telah disepakati dan memaksa pekerjaan dijeda |
| **Eskalasi** | Mengarahkan keputusan kepada orang bernama yang berhak menyelesaikannya |
| **Pengendalian perubahan** | Proses tertulis untuk mengubah lingkup, waktu, atau teknik |
| **Pihak ketiga** | Pihak yang sistem atau datanya terlibat, tetapi bukan klien |
| **Tanggung jawab bersama** | Klien, penyedia, dan tenant masing-masing menguasai bagian berbeda dari sebuah layanan |
| **Minimalisasi data** | Menyimpan hanya data paling sedikit yang cukup untuk sebuah temuan |
| **Data pribadi** | Informasi tentang orang yang dapat diidentifikasi, termasuk di log teknis |
| **Rantai penjagaan** | Catatan siapa memegang bukti, kapan, dan untuk apa |
| **Retensi** | Berapa lama bukti disimpan sebelum dihancurkan sesuai kesepakatan |
| **Benturan kepentingan** | Kepentingan lain yang dapat memengaruhi penilaian Anda |
| **Pengecualian** | Aset yang dinyatakan di luar lingkup, bukan sekadar tidak disebut |

---

## Referensi dan verifikasi

- Informasi program dan katalog EC-Council:
  [eccouncil.org](https://www.eccouncil.org/) dan
  [cert.eccouncil.org](https://cert.eccouncil.org/). Periksa katalog aktif,
  status program, dan teks kode etik di sana. ECSA tidak tercantum saat diperiksa
  pada 26 Nov 2026; perlakukan klaim tentang versi atau format ujian mutakhir
  dengan hati-hati.
- PTES — metodologi komunitas yang mencakup interaksi pra-kegiatan dan RoE;
  periksa versi terbitan terbaru sebelum menjadikannya rujukan.
- NIST SP 800-115, *Technical Guide to Information Security Testing and
  Assessment* — panduan umum; konfirmasi status mutakhir dan dokumen penggantinya.
- ISO/IEC 27001 dan 27002 — rujukan tata kelola dan kontrol; verifikasi edisi
  terbaru melalui badan standar.
- Dokumentasi OWASP — konteks keamanan aplikasi, bukan aturan otorisasi; cek
  rilis terkini.
- Otoritas perlindungan data, regulator sektor, aturan ketenagakerjaan,
  ketentuan penyedia, dan dokumen kegiatan yang ditandatangani di yurisdiksi
  Anda **mengalahkan** arti umum mana pun, termasuk halaman ini.
- Halaman pendamping CSIX (memakai placeholder — ganti dengan pemilik situs
  saat diterbitkan):
  [Metodologi Penetration Testing](https://siedysoes.github.io/csix-ecsa/id/fundamentals/pentest-methodology.md),
  [Apa Itu ECSA](https://siedysoes.github.io/csix-ecsa/id/fundamentals/what-is-ecsa.md),
  [Membangun Portofolio yang Aman](https://siedysoes.github.io/csix-ecsa/id/career/portfolio.md),
  dan [ECSA vs CEH & Sertifikasi Lain](https://siedysoes.github.io/csix-ecsa/id/fundamentals/ecsa-vs-ceh.md).

Halaman ini adalah bantuan belajar mandiri, bukan nasihat hukum, bukan materi
kursus resmi, dan bukan pengganti perjanjian kegiatan yang diotorisasi maupun
pertimbangan profesional berkualifikasi di yurisdiksi Anda.

## Lihat juga

- [Metodologi Penetration Testing](pentest-methodology.md)
- [Apa Itu ECSA](what-is-ecsa.md)
- [ECSA vs CEH & Sertifikasi Lain](ecsa-vs-ceh.md)
- [Rencana Belajar Praktis](../exam/study-plan.md)
- [Membangun Portofolio yang Aman](../career/portfolio.md)
