# Assets

Repository ini menyimpan aset frontend statis yang dipakai ulang oleh aplikasi atau tools internal. Isi repo berupa file CSS dan JavaScript vendor yang sudah siap dilayani langsung dari aplikasi, tanpa proses build atau package manager.

## Tujuan

- Menjadi lokasi terpusat untuk aset UI pihak ketiga yang dipakai oleh beberapa tools.
- Memudahkan aplikasi mengambil file vendor dari path yang konsisten.
- Menyimpan versi minified agar aset bisa langsung digunakan di halaman HTML.

## Struktur

```text
.
├── ckeditor/
├── datatables/
│   ├── License.txt
│   ├── css/
│   │   └── bootstrap.datatable.min.css
│   └── js/
│       ├── jquery.datatables.min.js
│       └── dataTables.bootstrap5.min.js
├── datepicker/
└── sweatalert/
    ├── css/
    │   └── sweetalert2.min.css
    └── js/
        └── sweetalert2.min.js
```

## Aset Tersedia

| Library | File | Keterangan |
| --- | --- | --- |
| DataTables 1.13.2 | `datatables/js/jquery.datatables.min.js` | Plugin tabel untuk jQuery. |
| DataTables Bootstrap 5 integration | `datatables/js/dataTables.bootstrap5.min.js` | Integrasi renderer DataTables untuk komponen Bootstrap 5. |
| DataTables Bootstrap 5 CSS | `datatables/css/bootstrap.datatable.min.css` | Styling DataTables untuk tampilan Bootstrap 5. |
| SweetAlert2 11.3.6 | `sweatalert/js/sweetalert2.min.js` | Dialog, alert, confirm, dan toast. |
| SweetAlert2 CSS | `sweatalert/css/sweetalert2.min.css` | Styling bawaan SweetAlert2. |

Direktori `ckeditor/` dan `datepicker/` saat ini masih kosong dan dapat dipakai untuk menaruh aset terkait jika dibutuhkan.

## Contoh Penggunaan

Tambahkan file CSS dan JavaScript sesuai kebutuhan aplikasi.

```html
<!-- DataTables -->
<link rel="stylesheet" href="/assets/datatables/css/bootstrap.datatable.min.css">
<script src="/assets/datatables/js/jquery.datatables.min.js"></script>
<script src="/assets/datatables/js/dataTables.bootstrap5.min.js"></script>

<!-- SweetAlert2 -->
<link rel="stylesheet" href="/assets/sweatalert/css/sweetalert2.min.css">
<script src="/assets/sweatalert/js/sweetalert2.min.js"></script>
```

Pastikan dependency eksternal seperti jQuery dan Bootstrap sudah dimuat oleh aplikasi sebelum mengaktifkan DataTables dengan integrasi Bootstrap. Untuk tampilan Bootstrap 5, muat file CSS dan JS integrasi Bootstrap setelah file utama DataTables.

## Catatan Maintenance

- Pertahankan struktur `library/css` dan `library/js` agar path aset tetap stabil.
- Saat mengganti versi library, update file minified dan sesuaikan bagian "Aset Tersedia" di README ini.
- Sertakan file lisensi vendor jika tersedia.
- Hindari mengubah nama file tanpa mengecek aplikasi yang sudah memakai path tersebut.

## Lisensi

Lisensi setiap aset mengikuti lisensi vendor masing-masing. DataTables menyertakan lisensi MIT di `datatables/License.txt`. Untuk aset lain, cek sumber resmi library sebelum redistribusi atau upgrade versi.
