# Cantus Firmus Vault

Obsidian vault Paduan Suara **Cantus Firmus**. Isinya jadwal latihan, jadwal pelayanan, repertoar lagu (dengan partitur), riwayat lagu, dan data anggota. Vault ini dibaca dan ditulis oleh AI agent yang melayani anggota lewat grup WhatsApp.

## Struktur

| Folder / file | Isi |
|---|---|
| `AGENTS.md` | Aturan untuk agent (baca dulu sebelum mengubah apa pun) |
| `Dashboard.md` | Ringkasan pelayanan dan latihan terdekat |
| `00-Inbox/` | Catatan sementara yang belum dirapikan |
| `01-Anggota/` | Satu file per anggota, plus `index.md` |
| `02-Pelayanan/YYYY/MM/` | Satu file per pelayanan: `DD-Nama-Perayaan.md` |
| `03-Latihan/YYYY/MM/` | Satu file per sesi latihan: `DD.md` |
| `04-Lagu/<Sumber>/` | Satu file per lagu, partitur di `files/` |
| `99-System/Templates/` | Template untuk file baru |
| `99-System/Kontrak-Scraper.md` | Field file lagu yang boleh ditulis scraper |

Sumber lagu: Puji Syukur, Mazmur, BPI, TPE, Gregorian, Sumber Lain, Profan.

## Prinsip singkat

- Semua anggota setara, tidak ada admin.
- Agent bertanya dulu kalau ragu dan tidak menebak data.
- File lagu berasal dari scraper. Agent hanya mengubah `catatan` dan `terakhir_dinyanyikan`.
- Audio dan video hanya berupa link, tidak disalin ke vault.

## Dibuka di Obsidian

Buka folder repo ini sebagai vault. File workspace Obsidian tidak ikut ke Git (lihat `.gitignore`).
