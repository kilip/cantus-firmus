# Kontrak Scraper dan Daftar Template

Dokumen ini menjelaskan field yang boleh ditulis scraper di file lagu, serta daftar template di `99-System/Templates/`.

Semua file baru di vault disalin dari template di folder `Templates/`. Nilai dan komentar `#` di template hanyalah contoh dan petunjuk; hapus komentar dan ganti nilainya saat membuat file asli.

| Template | Dipakai untuk | Lokasi file hasil |
|---|---|---|
| `lagu.md` | satu lagu | `04-Lagu/<Sumber>/<id>.md` |
| `pelayanan.md` | satu pelayanan | `02-Pelayanan/YYYY/MM/DD-Nama-Perayaan.md` |
| `latihan.md` | satu sesi latihan | `03-Latihan/YYYY/MM/DD.md` |
| `anggota.md` | satu anggota | `01-Anggota/Nama-Lengkap.md` |
| `index-anggota.md` | ringkasan anggota | `01-Anggota/index.md` |
| `dashboard.md` | ringkasan jadwal | `Dashboard.md` |
| `inbox.md` | catatan sementara | `00-Inbox/YYYY-MM-DD-judul.md` |

## Kontrak untuk scraper (file lagu)

Scraper hanya boleh menulis field berikut. Dua field terakhir **milik agent**: kalau file sudah ada, scraper tidak boleh mengubahnya.

| Field | Tipe | Wajib | Pemilik |
|---|---|---|---|
| `id` | string unik, sama dengan nama file | ya | scraper |
| `judul` | string | ya | scraper |
| `sumber` | Puji Syukur / Mazmur / BPI / TPE / Gregorian / Sumber Lain / Profan | ya | scraper |
| `nomor` | angka | tidak | scraper |
| `kategori` | string | tidak | scraper |
| `nada_dasar` | string (`do=f`) | tidak | scraper |
| `birama` | string (`4/4`) | tidak | scraper |
| `tempo` | angka | tidak | scraper |
| `not_awal` | string | tidak | scraper |
| `url_halaman` | URL | ya | scraper |
| `partitur` | path relatif dari `04-Lagu/` | tidak | scraper |
| `audio` | map suara ke URL; hilangkan key yang tidak ada | tidak | scraper |
| `video` | daftar URL | tidak | scraper |
| `tags` | daftar string | tidak | scraper |
| `catatan` | string | tidak | **agent** |
| `terakhir_dinyanyikan` | `YYYY-MM-DD \| path pelayanan` | tidak | **agent** |

Aturan umum:
- Field yang tidak ada di sumber **dihilangkan**, bukan dikosongkan, kecuali `catatan` dan `terakhir_dinyanyikan` yang selalu ada (boleh kosong).
- Lirik ada di badan file, setelah frontmatter.
- Partitur disimpan sebagai `04-Lagu/<Sumber>/files/<id>.png`. Audio dan video hanya link.
- Satu file per lagu, nama file sama dengan `id`.
- Kalau file sudah ada, update hanya field milik scraper dan lirik; jangan sentuh `catatan` dan `terakhir_dinyanyikan`.
