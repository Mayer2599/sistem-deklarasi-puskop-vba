# Struktur Database (Sheet & Kolom)

Dokumentasi ini menjelaskan nama sheet dan kolom yang direferensikan oleh kode VBA di repo.

Sheet yang digunakan (minimal):
- `User Login` : daftar username/password (kode mencari pada rentang A3:A50 dan B3:B50 untuk password).
- `Deklarasi` : sheet utama data deklarasi. Banyak kolom direferensikan dari kode klaim.
- `DB CU`, `DB Sekunder`, `List TP` : sheet tambahan yang dipakai untuk akses dan filter per role.

Kolom penting pada sheet `Deklarasi` (kolom menggunakan huruf seperti dalam kode):
- Kolom C: `CUP` (kode mengambil `.Cells(rowIndex, "C")` untuk LblCUPkey)
- Kolom D: `NTP` (`.Cells(rowIndex, "D")` untuk LblNTPkey)
- Kolom E: `NAK` atau nomor pencarian (pencarian dilakukan pada range `E7:E400000`)
- Kolom G: nama/atribut yang dipetakan ke `LblNAkey` (`.Cells(rowIndex, "G")`)
- Kolom H: `TL` (tanggal lahir atau sejenisnya, `.Cells(rowIndex, "H")`)
- Kolom I: `JK` (jenis kelamin, `.Cells(rowIndex, "I")`)
- Kolom J/K/L: nilai numeric (dipakai untuk `LblPin1key`, `LblSim1key`, `LblSol1key` dan diformat dengan pemisah ribuan)
- Kolom AN: data tambahan yang memengaruhi tampilan `LblADit` / `LblADitket` (jika ada isi di AN maka LblADit tampil)
- Kolom AO/A P/AQ: (AO -> `LblNAPket`, AP -> `LblNASket`, AQ -> `LblNASolket`)
- Kolom Q..U: diisi ke TextBox `LblTIket`, `LblTMket`, `LblTKket`, `LblTKdstjket`, `LblTKdbyrket` (Q=LblTIket, R=LblTMket, S=LblTKket, T=LblTKdstjket, U=LblTKdbyrket)
- Kolom V..AM: boolean/flag yang memetakan ke checkbox pada UserForm (V..AM -> CbxPeng1..CbxDbyr3)

Praktik terbaik
- Jangan mengubah urutan kolom tanpa memperbarui referensi di kode.
- Cadangkan file Excel sebelum menjalankan macro yang melakukan perubahan massal.

Contoh
Baris contoh pada `Deklarasi` (kolom singkat):
| C  | D  | E (NAK) | G (Nama) | H (TL) | I (JK) | J | K | L | AN | AO | AP | AQ | Q..U |

Jika Anda membutuhkan skema kolom yang lebih detail, buka sheet `Deklarasi` di workbook sumber dan bandingkan dengan referensi dalam `vba/*`.
