# Sistem Deklarasi PUSKOP (VBA)

Version: 1.1

Ringkasan singkat proyek Excel + VBA untuk manajemen deklarasi dan klaim pada lingkungan koperasi (PUSKOP).

Fitur utama:
- Login berbasis peran (Corporate, Puskop, CU Primer) dengan pembatasan percobaan.
- Pencarian entri deklarasi berdasarkan nomor anggota/NAK dan pemuatan data ke UserForm klaim.
- Proteksi sheet dan visibilitas berdasarkan hak akses.

Struktur repo:
- `vba/` : Kode VBA (sebagai .txt untuk penyimpanan di repo)
- `docs/ALUR-SISTEM.md` : Penjelasan alur sistem
- `docs/STRUKTUR-DATABASE.md` : Struktur sheet/kolom yang digunakan
- `docs/screenshots/` : (kosong — tambahkan screenshot jika diperlukan)

Cara menggunakan
1. Buka file Excel target dan aktifkan Macro (save sebagai `.xlsm`).
2. Buka Visual Basic for Applications (Alt+F11) lalu tambahkan modul/UserForm sesuai nama yang ada pada kode.
3. Copy isi file `vba/Sistem-Login.txt` dan `vba/Sistem-Klaim.txt` ke modul/UserForm yang sesuai.
4. Pastikan ada sheet dengan nama yang dipakai di kode: `User Login`, `Deklarasi`, `DB CU`, `DB Sekunder`, `List TP`.
5. Sesuaikan proteksi/password bila diperlukan (default di kode: `PujilahTuhanselama-lamanya`).

Tips untuk publikasi ke GitHub
- Jangan sertakan file Excel yang berisi data sensitif.
- Sertakan screenshot di `docs/screenshots/` jika ingin menampilkan antarmuka.

Kontribusi
Jika ingin membantu perbaikan dokumentasi atau kode, silakan buka issue atau kirim pull request.

Lisensi
Proyek ini dilisensikan di bawah lisensi MIT — lihat file `LICENSE`.

Kontak
Pemilik/penulis: Mayer Simanjuntak
