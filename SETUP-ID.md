# Cara memasang profil Pramanaa

Paket ini berisi README profil bertema merah dengan layout ringkas sesuai referensi: gambar kiriman, About Me, Tech Stack dengan ikon rata tengah, kemudian Contributions paling bawah. Detail stack bisa dibuka pada satu panel. Gambar kiriman disertakan utuh tanpa perubahan resolusi atau kompresi ulang. Banner SVG lama tetap disertakan sebagai aset opsional, tetapi tidak ditampilkan pada layout ini.

## Hasil pemeriksaan

Pada 21 September 2026, API publik GitHub menampilkan akun `Pramanaa` dengan nama **Pramana Putra**, jumlah repositori publik **0**, dan daftar repositori publik kosong. Karena itu, kode, dependency, dan frekuensi penggunaan stack belum dapat diperiksa. Ini tidak berarti kamu tidak memiliki proyek; proyek privat dan proyek di akun/organisasi lain tidak terwakili oleh daftar tersebut.

Tech stack dan versinya pada README sekarang mengikuti daftar yang kamu berikan secara langsung: frontend, backend, database/cache/queue, serta DevOps. Teknologi utama ditampilkan sebagai ikon merah rata tengah, sedangkan versi, arsitektur, package, dan tooling tersedia pada bagian **Explore my full tech stack** yang dapat dibuka. Daftar ini merupakan informasi yang kamu konfirmasi, bukan hasil verifikasi dependency repositori.

## 1. Buat repositori profil

1. Masuk ke akun **Pramanaa** di GitHub.
2. Buat repositori bernama persis **Pramanaa**, sehingga alamatnya `https://github.com/Pramanaa/Pramanaa`.
3. Pilih **Public** dan aktifkan **Add README**. Jika repositori tersebut sudah ada, edit repositori yang sama.
4. Gunakan branch default `main`. Jika branch default bernama `master`, workflow juga mendukungnya. Untuk nama lain, sesuaikan bagian `push.branches` di workflow.

GitHub menampilkan README profil jika repositori publik memiliki nama yang sama dengan username dan `README.md` berada di root.

## 2. Pasang file pada lokasi yang tepat

Ekstrak ZIP terlebih dahulu. Jangan unggah ZIP-nya langsung dan jangan letakkan semua file di dalam folder tambahan.

| File dalam paket | Lokasi di repositori |
| --- | --- |
| `README.md` | `README.md` |
| `assets/header.svg` | Opsional; banner dari layout sebelumnya |
| `assets/red-coding.jpg` | `assets/red-coding.jpg` |
| `.github/workflows/snake.yml` | `.github/workflows/snake.yml` |
| `SETUP-ID.md` | Opsional; panduan ini tidak perlu dipasang |

Melalui browser GitHub, edit README lalu ganti isinya dengan file yang disediakan. Unggah folder `assets` menggunakan **Add file → Upload files**. Untuk workflow, gunakan **Add file → Create new file**, ketik `.github/workflows/snake.yml` sebagai nama file, lalu salin isi `snake.yml` dari paket dan commit. Cara ini juga membantu jika folder `.github` tidak terlihat di pengelola file.

Jika versi merah sebelumnya sudah dipasang, cukup ganti `README.md` untuk pembaruan layout ini. Gambar dan workflow animasi tetap sama. Jika kamu masih memakai versi biru, ganti seluruh aset dan workflow dari paket, tambahkan `assets/red-coding.jpg`, lalu jalankan workflow kembali agar SVG di branch `output` berubah merah.

## 3. Jalankan animasi kontribusi

1. Buka tab **Actions** di repositori `Pramanaa/Pramanaa`.
2. Jika GitHub meminta pengaktifan Actions, aktifkan untuk repositori ini.
3. Pilih workflow **Generate contribution snake**.
4. Pilih **Run workflow**, gunakan branch default, lalu jalankan.
5. Tunggu proses selesai dengan tanda hijau. Branch `output` akan berisi `github-snake.svg` dan `github-snake-dark.svg`.
6. Buka profil `https://github.com/Pramanaa` dan muat ulang halaman. Gambar kadang memerlukan waktu tambahan karena cache GitHub.

Animasi dibuat dari kalender kontribusi akun pemilik repositori. Jadwal otomatis berjalan setiap hari sekitar **08.17 WITA** / **00.17 UTC**, dan dapat terlambat karena antrean GitHub. Workflow juga berjalan ketika file workflow diubah pada `main` atau `master`.

Workflow menggunakan `GITHUB_TOKEN` bawaan GitHub dan permission `contents: write` untuk menyimpan hasil di branch `output`. Kamu tidak perlu membuat Personal Access Token. Tidak perlu mengaktifkan GitHub Pages.

Versi terang dan gelap dipilih otomatis sesuai tema. Ini menambahkan gambar animasi ke README, bukan mengubah grafik kontribusi bawaan GitHub di bawah profil.

## Jika animasi belum muncul

- Pastikan workflow sudah selesai dengan sukses. Tautan SVG baru tersedia setelah proses pertama berhasil.
- Jika muncul error permission saat menyimpan, periksa **Settings → Actions → General → Workflow permissions**, kebijakan organisasi, dan aturan branch `output`. Workflow sudah meminta izin tulis; kebijakan repositori/organisasi masih dapat membatasinya.
- Jika workflow tidak terlihat, pastikan file benar-benar berada di `.github/workflows/snake.yml` pada branch default, bukan `snake.yml.txt` atau folder tambahan.
- Jika tidak ada kotak kontribusi yang berwarna, grafik mungkin kosong atau kontribusi tersebut tidak terlihat oleh token bawaan. Jangan menambahkan token privat hanya demi tampilan.
- Ikon tech stack dimuat dari CDN Simple Icons. Jika layanan tersebut gagal dimuat, nama teknologi tetap tersedia pada teks alternatif dan tabel detail. Gambar anime disimpan di repositori sendiri.
- Pada repositori publik yang lama tidak aktif, jadwal Actions dapat dinonaktifkan GitHub. Periksa tab Actions dan aktifkan kembali bila perlu.

## Status paket

Struktur file, sintaks YAML, referensi gambar, dan SVG diperiksa secara lokal. Workflow belum dijalankan di akunmu; animasi kalender yang sebenarnya akan dibuat pada run pertama. Belum ada perubahan yang dipublikasikan ke akun GitHub.

## Referensi

- [API profil publik](https://api.github.com/users/Pramanaa)
- [API repositori publik](https://api.github.com/users/Pramanaa/repos?per_page=100)
- [Panduan README profil GitHub](https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme)
- [Platane/snk: generator animasi kontribusi](https://github.com/Platane/snk)
- [Action publikasi hasil ke branch](https://github.com/crazy-max/ghaction-github-pages)
