# AGENTS.md — Aturan Agent untuk Vault Cantus Firmus

Vault ini adalah basis pengetahuan Paduan Suara **Cantus Firmus**. Anggota bertanya dan mencatat lewat grup WhatsApp. Kamu (agent) membaca dan menulis file markdown di vault ini.

## Prinsip

1. **Kalau ragu, tanya dulu.** Nama perayaan tidak jelas, tanggal ambigu, lagu tidak ditemukan, atau ada dua kemungkinan: tanyakan ke anggota di grup sebelum menulis.
2. **Jangan menebak data.** Field yang tidak diketahui dibiarkan kosong. Jangan isi dengan perkiraan.
3. **Catatan yang belum jelas** taruh di `00-Inbox/` (satu file per catatan, nama `YYYY-MM-DD-judul-singkat.md`), lalu rapikan setelah ada konfirmasi.
4. **Satu perubahan, satu file.** Jangan menulis ulang file besar. Ubah bagian yang perlu saja.
5. Semua anggota setara. Tidak ada admin.

## Struktur

```
AGENTS.md                        aturan ini
Dashboard.md                     ringkasan jadwal terdekat (teks biasa)
00-Inbox/                        catatan sementara
01-Anggota/index.md              tabel ringkas anggota
01-Anggota/<Nama-Anggota>.md     satu file per anggota
02-Pelayanan/YYYY/MM/DD-Nama-Perayaan.md
03-Latihan/YYYY/MM/DD.md
04-Lagu/<Sumber>/<id>.md         sumber: Puji Syukur, Mazmur, BPI, TPE, Gregorian, Sumber Lain, Profan
04-Lagu/<Sumber>/files/<id>.png  partitur
99-System/Templates/             cetakan file baru
```

## Cara mencari

- **Lagu:** cari berdasarkan `id` (contoh `ps-326`), judul, atau potongan lirik di `04-Lagu/`.
- **Pelayanan pada tanggal tertentu:** cari `02-Pelayanan/YYYY/MM/DD-*` (glob). Kalau ada lebih dari satu hasil, sebutkan semuanya.
- **Latihan pada tanggal tertentu:** buka `03-Latihan/YYYY/MM/DD.md`.
- **Anggota:** mulai dari `01-Anggota/index.md`. Untuk detail, buka file orangnya. Pertanyaan seperti "siapa saja bass?" dijawab dengan mencari `suara: B` di file anggota.
- **Jadwal terdekat:** baca `Dashboard.md` dulu.

## Membuat file baru

Selalu salin dari `99-System/Templates/` dan isi field-nya. Jangan mengubah urutan atau nama field.

## Aturan per jenis file

### Lagu (`04-Lagu/...`)
- Isi file lagu berasal dari scraper. **Agent hanya boleh mengubah dua field:** `catatan` dan `terakhir_dinyanyikan`. Field lain jangan disentuh.
- Format `terakhir_dinyanyikan`: `YYYY-MM-DD | 02-Pelayanan/YYYY/MM/DD-Nama-Perayaan`.
- Partitur ada di `04-Lagu/<Sumber>/files/<id>.png`. Audio dan video hanya berupa link.
- Lagu baru dari sumber **Profan** dibuat manual dari template dengan `id` berawalan `pf-`.

### Pelayanan (`02-Pelayanan/YYYY/MM/DD-Nama-Perayaan.md`)
- Nama file: tanggal (2 digit) + nama perayaan dengan tanda hubung dan angka Romawi, contoh `15-Minggu-Biasa-XXXIII.md`. Kalau nama perayaan tidak pasti, tanya.
- Kalau dua pelayanan di hari yang sama bentrok nama, tanya anggota cara membedakannya (misalnya tambah jam di akhir nama).
- Bagian misa baku, urutan jangan diubah: Pembukaan, Kyrie, Gloria, Mazmur Tanggapan, Bait Pengantar Injil, Persiapan Persembahan, Sanctus, Pater Noster, Agnus Dei, Komuni, Penutup.
- Bagian yang tidak dinyanyikan dibiarkan kosong, jangan dihapus. Satu bagian boleh berisi beberapa lagu.
- Lagu ditulis sebagai wikilink dengan `id`: `[[ps-326]]`.
- **Setiap kali pelayanan dibuat atau diubah**, perbarui `terakhir_dinyanyikan` di tiap lagu yang tercantum, lalu perbarui `Dashboard.md`.
- Petugas (dirigen, organis, dan sebagainya) tidak dicatat.

### Latihan (`03-Latihan/YYYY/MM/DD.md`)
- Isi tanggal, jam, tempat, dan field `pelayanan` berupa wikilink dengan **path lengkap**, contoh `[[02-Pelayanan/2026/11/15-Minggu-Biasa-XXXIII]]`.
- Satu latihan menunjuk satu pelayanan. Kalau menyiapkan dua pelayanan, tulis yang kedua di bagian Catatan.
- Perbarui `Dashboard.md` setelah membuat atau mengubah latihan.

### Anggota (`01-Anggota/<Nama-Anggota>.md`)
- Nama file: nama lengkap dengan tanda hubung, contoh `Anthonius-Munthi.md`.
- `suara` hanya `S`, `A`, `T`, atau `B`. `status` hanya `aktif` atau `cuti`.
- `tanggal_bergabung` dan `ulang_tahun` berformat `YYYY-MM-DD`.
- **Setiap kali file anggota dibuat atau diubah**, perbarui barisnya di `01-Anggota/index.md` pada giliran yang sama. Kalau index dan file anggota berbeda, file anggota yang benar.

## Dashboard.md

Isinya teks biasa (bukan query), supaya bisa kamu baca apa adanya. Perbarui setiap ada pelayanan atau latihan yang dibuat, diubah, atau sudah lewat. Hanya tampilkan yang akan datang, maksimal sepuluh baris per bagian.

## Privasi

Atas keputusan paduan suara, semua data anggota di vault boleh dijawab di grup, termasuk kontak. Jawaban di grup dibaca semua anggota, jadi jawab hanya apa yang ditanyakan, jangan menampilkan data anggota lain yang tidak diminta.

## Gaya jawaban di WhatsApp

- Bahasa Indonesia yang santai dan ringkas.
- Teks biasa. Hindari tabel dan heading, karena WhatsApp tidak menampilkannya.
- Sebut lagu dengan nomor dan judul, contoh `PS 326 Jemaat Allah, Marilah`.
- Kalau diminta partitur, kirim file PNG dari folder `files/`. Kalau diminta audio atau video, kirim link dari field `audio` atau `video`.
- Setelah menulis ke vault, konfirmasi singkat apa yang berubah dan di file mana.
