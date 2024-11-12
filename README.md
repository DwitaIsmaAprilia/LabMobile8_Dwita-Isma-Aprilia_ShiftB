## Halaman Tampilan Awal
![Lampiran Tampilan Awal](halaman_awal.png)

## Halaman Tampilan Tambah Mahasiswa
![Lampiran Tampilan Tambah](tambah_mahasiswa.png)
fungsi tambahMahasiswa() bertujuan untuk **menambahkan data** mahasiswa baru ke dalam sistem dengan konsep CRUD (Create, Read, Update, Delete) menggunakan framework Ionic. Berikut penjelasan prosesnya:

Fungsi tambahMahasiswa()
1. Validasi Data Input
</br>Fungsi ini dimulai dengan pengecekan apakah kedua variabel nama dan jurusan sudah diisi.
</br>Jika salah satu dari variabel tersebut kosong, maka proses dihentikan, dan pesan kesalahan ditampilkan di console dengan log 'gagal tambah mahasiswa karena masih ada data yg kosong'.
2. Menyiapkan Data untuk Ditambahkan
</br>Jika data sudah terisi, maka variabel data disiapkan dalam bentuk objek yang memuat properti nama dan jurusan.
</br>Objek data ini akan berisi informasi yang nantinya dikirimkan ke API untuk disimpan.
3. Mengirim Data ke API
</br>Fungsi this.api.tambah(data, 'tambah.php') dipanggil untuk mengirim data mahasiswa ke endpoint API tambah.php dengan metode HTTP POST.
</br>this.api.tambah() mengembalikan Observable yang digunakan untuk menangani respons API, baik untuk kasus sukses maupun gagal.
4. Menangani Respons API
</br>Jika permintaan berhasil (sukses), blok next akan dipanggil:
</br>Memanggil fungsi resetModal() untuk mengosongkan atau mereset data input.
</br>Menampilkan pesan 'berhasil tambah mahasiswa' di console.
</br>Memanggil fungsi getMahasiswa() untuk memperbarui daftar mahasiswa yang ditampilkan.
</br>Mengatur modalTambah menjadi false, menutup modal dengan this.modal.dismiss().
</br>Jika permintaan gagal, blok error akan dijalankan, menampilkan 'gagal tambah mahasiswa' di console.

Rangkuman Proses
Fungsi tambahMahasiswa ini merupakan bagian dari **operasi Create** dalam CRUD, yang mengirim data baru ke server untuk ditambahkan. Langkah-langkah utama yang dilakukan adalah:
1. Memvalidasi data input
2. Menyiapkan data mahasiswa dalam bentuk objek
3. Mengirim data ke server dengan metode POST
4. Menanggapi respons server untuk mengonfirmasi keberhasilan atau kegagalan penambahan data
</br>Fungsi ini juga diintegrasikan dengan antarmuka pengguna untuk menutup modal dan memperbaharui daftar data mahasiswa setelah penambahan berhasil.

## Halaman Tampilan Setelah Tambah Mahasiswa
![Lampiran Tampilan Setelah Tambah](setelah_ditambah.png)

## Halaman Tampilan Edit Mahasiswa
![Lampiran Tampilan Edit](halaman_edit.png)
Fungsi editMahasiswa() ini digunakan untuk memperbarui data mahasiswa yang sudah ada dalam sistem. Fungsi ini merupakan bagian dari **operasi Update** dalam konsep CRUD. Berikut adalah penjelasan dari proses yang terjadi dalam fungsi ini:

Fungsi editMahasiswa()
1. Menyiapkan Data yang Akan Diperbarui
</br>Fungsi ini membuat objek data yang berisi properti id, nama, dan jurusan.
</br>id merupakan penanda unik untuk mahasiswa yang ingin diperbarui, sementara nama dan jurusan adalah informasi yang akan diubah.
2. Mengirim Data ke API
</br>Fungsi this.api.edit(data, 'edit.php') digunakan untuk mengirimkan data mahasiswa yang telah diperbarui ke endpoint API edit.php.
</br>this.api.edit() mengirim permintaan HTTP POST atau PUT ke server untuk melakukan pembaruan data mahasiswa di server.
3. Menangani Respons API
</br>Jika pembaruan berhasil (respons sukses), blok next akan dipanggil:
</br>Menampilkan hasil (hasil) yang diterima dari server ke console.
</br>Memanggil resetModal() untuk mereset data input agar siap untuk penggunaan berikutnya.
</br>Memanggil getMahasiswa() untuk memperbarui daftar mahasiswa yang ditampilkan di layar.
</br>Menampilkan pesan 'berhasil edit Mahasiswa' di console.
</br>Mengatur modalEdit menjadi false dan menutup modal dengan this.modal.dismiss().
</br>Jika ada kesalahan dalam proses pembaruan, blok error akan dipanggil untuk menampilkan pesan 'gagal edit Mahasiswa' di console.

Rangkuman Proses
</br>Fungsi editMahasiswa() melakukan langkah-langkah berikut:
1. Menyiapkan data mahasiswa yang akan diperbarui dengan memasukkan ID, nama, dan jurusan.
2. Mengirim data ke API untuk pembaruan menggunakan endpoint edit.php.
3. Menangani respons dari server untuk memastikan pembaruan berhasil atau gagal.
4. Memperbarui antarmuka pengguna dengan mengosongkan modal dan memperbarui daftar data mahasiswa.
</br>Fungsi ini sangat penting untuk proses Update pada aplikasi, memastikan data mahasiswa yang ada dapat dimodifikasi sesuai kebutuhan.

## Halaman Tampilan Setelah Edit Mahasiswa
![Lampiran Tampilan Setelah Edit](setelah_diedit.png)

## Halaman Tampilan Hapus Mahasiswa
![Lampiran Tampilan Hapus](konfirmasi-hapus.png)
Fungsi hapusMahasiswa() ini bertujuan untuk menghapus data mahasiswa dari sistem. Fungsi ini merupakan bagian dari operasi Delete dalam konsep CRUD. Berikut adalah penjelasan proses yang terjadi dalam fungsi ini:

Fungsi hapusMahasiswa(id: any)
1. Mempersiapkan Data yang Akan Dihapus
</br>Fungsi ini menerima parameter id, yaitu ID mahasiswa yang ingin dihapus.
</br>ID ini akan digunakan sebagai penanda unik agar API dapat mengetahui data mahasiswa mana yang harus dihapus.
2. Mengirim Permintaan Hapus ke API
</br>Fungsi this.api.hapus(id, 'hapus.php?id=') digunakan untuk mengirim permintaan hapus ke endpoint API hapus.php.
</br>Endpoint hapus.php?id= diikuti oleh id akan membentuk URL lengkap untuk menentukan data mahasiswa mana yang akan dihapus.
</br>this.api.hapus() mengirim permintaan HTTP DELETE atau GET ke server untuk menghapus data yang sesuai.
3. Menangani Respons API
</br>Jika penghapusan berhasil (respons sukses), blok next akan dipanggil:
</br>Menampilkan pesan 'sukses' beserta respons (res) di console.
</br>Memanggil getMahasiswa() untuk memperbarui daftar mahasiswa di tampilan, sehingga data yang baru saja dihapus tidak lagi muncul.
</br>Menampilkan pesan 'berhasil hapus data' di console.
</br>Jika ada kesalahan dalam proses penghapusan, blok error akan dipanggil dan menampilkan pesan 'gagal' di console.

Rangkuman Proses
Fungsi hapusMahasiswa() melakukan langkah-langkah berikut:
1. Menerima ID mahasiswa yang akan dihapus.
2. Mengirim permintaan hapus ke API melalui endpoint hapus.php.
3. Menangani respons dari server untuk memastikan penghapusan berhasil atau gagal.
4. Memperbarui antarmuka pengguna dengan memperbarui daftar mahasiswa yang ditampilkan.
</br>Fungsi ini melengkapi operasi Delete dalam aplikasi, memungkinkan data mahasiswa yang tidak diperlukan lagi untuk dihapus dari sistem.









