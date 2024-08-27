# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. Suatu cara yang memudahkan kolaborasi tim untuk membuat sesuatu sehingga lebih cepat dan efisien  
2. Biasanya disebut juga Infrastructure as Code, yaitu infrastruktur seperti server, jaringan, database, dan yang lainnya di program sehingga bisa dijalankan otomatis. 
3. Server biasanya digunakan untuk menyimpan data sesuatu, contohnya yaitu aplikasi toko online menyimpan informasi pelanggan, produk, juga pesanan yang dilakukan. Saat pengguna mencari produk, server akan merespons dengan mengirimkan data produk yang dicari pengguna.
4. Peran server sangat penting dalam setiap tahap development suatu software, mulai dari awal pembuatan hingga tahap pemeliharaan. 
5. Virtualisasi biasanya digunakan untuk menjalankan beberapa OS di satu device. Sedangkan, Container membantu memastikan aplikasi yang dijalankan bisa jalan di mana saja dengan cara yang lebih efisien dan mudah.
6. Karena teknologi container memberikan banyak keuntungan sperti portabilitas, teknologi ini juga efisen sumber daya dan mudah digunakan, dan soal biaya juga lebih hemat.
7. Teknologi yang memudahkan pengelolaan, mengotomatisasikan penyebaran, dan pengoperasian container dalam jumlah besar di dalam lingkungan yang kompleks.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

