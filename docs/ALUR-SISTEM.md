# Alur Sistem

Dokumen ini menjelaskan alur utama aplikasi VBA yang ada di repo.

1) Login
- Pengguna memasukkan username dan password pada UserForm login.
- Terdapat pembatasan percobaan (max 3 kali). Jika melewati, workbook akan ditutup.
- Setelah berhasil, sistem menentukan `role` berdasarkan baris pengguna di sheet `User Login` dan menyesuaikan visibilitas/proteksi sheet.

Role dan akses:
- Corporate: melihat dan mengedit semua sheet.
- Puskop: melihat beberapa sheet (mis. `DB Sekunder`, `Deklarasi`, `List TP`) dalam mode read-only.
- CU Primer: melihat `DB CU`, `Deklarasi`, dan `List TP` dengan akses terbatas; filter otomatis diterapkan untuk CU terkait.

2) Pencarian Deklarasi (Sistem Klaim)
- Pada UserForm klaim, user memasukkan `NAK`/nomor pencarian.
- Kode mencari nilai pada kolom E (range `E7:E400000`) pada sheet `Deklarasi`.
- Jika ditemukan, data dari baris tersebut dimuat ke label dan textbox pada UserForm (mis. nama, tanggal lahir, jenis kelamin, nilai numeric terformat, kolom cekbox diisi sesuai data).
- Jika ada nilai di kolom `AN`, maka field `LblADit` dan `LblADitket` akan ditampilkan.

3) Pengeditan & Simpan
- Setelah data dimuat, user dapat mengubah beberapa field dan memilih checkbox klaim.
- Tombol `CBSimpan` akan aktif setelah data berhasil dimuat; proses penyimpanan mengikuti aturan yang diimplementasikan pada macro (tidak semua prosedur simpan disertakan di repo ini - cek modul terkait jika ada).

4) Proteksi dan keamanan
- Workbook di-protect dengan password default `PujilahTuhanselama-lamanya` (ubah sebelum produksi).
- Jangan mengupload workbook yang berisi data sensitif ke GitHub.

Catatan
- Untuk melihat antarmuka, tambahkan screenshot ke folder `docs/screenshots/`.
- Nama sheet dan kolom sangat penting — sesuaikan struktur sheet jika Anda memindahkan kolom.
