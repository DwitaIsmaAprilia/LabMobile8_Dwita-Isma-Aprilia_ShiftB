## Halaman Tampilan Awal
![Lampiran Tampilan Awal](halaman_awal.png)

## Halaman Tampilan Tambah Mahasiswa
![Lampiran Tampilan Tambah](tambah_mahasiswa.png)
Fungsi tambahMahasiswa ini merupakan agian dari **operasi Create** dalam CRUD, yang mengirim data baru ke server untuk ditambahkan. Langkah-langkah utama yang dilakukan adalah:
1. Memvalidasi data input
2. Menyiapkan data mahasiswa dalam bentuk objek
3. Mengirim data ke server dengan metode POST
4. Menanggapi respons server untuk mengonfirmasi keberhasilan atau kegagalan penambahan data

Fungsi ini juga diintegrasikan dengan antarmuka pengguna untuk menutup modal dan memperbaharui daftar data mahasiswa setelah penambahan berhasil.

## Halaman Tampilan Setelah Tambah Mahasiswa
![Lampiran Tampilan Setelah Tambah](setelah_ditambah.png)

## Halaman Tampilan Edit Mahasiswa
![Lampiran Tampilan Edit](halaman_edit.png)
Fungsi editMahasiswa() ini digunakan untuk memperbarui data mahasiswa yang sudah ada dalam sistem. Fungsi ini merupakan bagian dari operasi Update dalam konsep CRUD. Berikut adalah penjelasan dari proses yang terjadi dalam fungsi ini:

Fungsi editMahasiswa()
1. Menyiapkan Data yang Akan Diperbarui
</br>Fungsi ini membuat objek data yang berisi properti id, nama, dan jurusan.
</br>id merupakan penanda unik untuk mahasiswa yang ingin diperbarui, sementara nama dan jurusan adalah informasi yang akan diubah.
2. Mengirim Data ke API
</br>Fungsi this.api.edit(data, 'edit.php') digunakan untuk mengirimkan data mahasiswa yang telah diperbarui ke endpoint API edit.php.
</br>this.api.edit() mengirim permintaan HTTP POST atau PUT ke server untuk melakukan pembaruan data mahasiswa di server.
Menangani Respons API

Jika pembaruan berhasil (respons sukses), blok next akan dipanggil:
Menampilkan hasil (hasil) yang diterima dari server ke console.
Memanggil resetModal() untuk mereset data input agar siap untuk penggunaan berikutnya.
Memanggil getMahasiswa() untuk memperbarui daftar mahasiswa yang ditampilkan di layar.
Menampilkan pesan 'berhasil edit Mahasiswa' di console.
Mengatur modalEdit menjadi false dan menutup modal dengan this.modal.dismiss().
Jika ada kesalahan dalam proses pembaruan, blok error akan dipanggil untuk menampilkan pesan 'gagal edit Mahasiswa' di console.
Rangkuman Proses
Fungsi editMahasiswa() melakukan langkah-langkah berikut:

Menyiapkan data mahasiswa yang akan diperbarui dengan memasukkan ID, nama, dan jurusan.
Mengirim data ke API untuk pembaruan menggunakan endpoint edit.php.
Menangani respons dari server untuk memastikan pembaruan berhasil atau gagal.
Memperbarui antarmuka pengguna dengan mengosongkan modal dan memperbarui daftar data mahasiswa.
Fungsi ini sangat penting untuk proses Update pada aplikasi, memastikan data mahasiswa yang ada dapat dimodifikasi sesuai kebutuhan.
## Halaman Tampilan Setelah Edit Mahasiswa
![Lampiran Tampilan Setelah Edit](setelah_diedit.png)

## Halaman Tampilan Hapus Mahasiswa
![Lampiran Tampilan Hapus](konfirmasi-hapus.png)
