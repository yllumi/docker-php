# Docker PHP

Contoh dockerized untuk php8.3-fpm, nginx dan mariadb. Disini saya membuat image dulu khusus untuk php-fpmnya dengan sudah menambahkan ekstensi php yang biasa saya gunakan. Repo docker imagenya bisa dilihat [disini](https://hub.docker.com/repository/docker/yllumi/php83/general).

Kalau mau membuat image php-fpm sendiri karena misalnya ada ekstensi yang mau ditambah, dsb, bisa modif file Dockerfile-php lalu jalankan perintah ini untuk membuat image baru:
```
docker build -t [namatag]:[versi] -f Dockerfile-php .
```

Setelah image php-fpm tersedia, jalankan perinah berikut untuk membuat container aplikasi yang dibutuhkan:
```
docker compose up -d
```

Untuk mengakses aplikasi, cek dulu IP dari container nginx:

```
docker container inspect [nama-container-nginx]
```
lalu cek bagian IP address. Nanti tinggal buka di browser dengan alamat http://[alamat_IP]
