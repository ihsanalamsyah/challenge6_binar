# Challenge 6 Binar Academy

Dalam project ini saya membuat suatu database menggunakan postgreSQL dan server online

Saya membuat tiga table bernama *User_Games*, *User_Game_Biodata*, dan *User_Game_History* dari setiap table itu terdapat column-column berisi data user

Table *User_Games* terdapat empat column `id` dengan type data integer, `username`: string, `password`: string, dan `email`: string

Table *User_Game_Biodata* terdapat lima column `id` type data integer, `user_id`: integer, `name`: string, `umur`: string, dan `pekerjaan`: string

Table *User_Game_History* terdapat tiga column `id` type data integer, `user_id`: integer, dan `result`: string.

Setiap table terdapat primary key `id`

Column `user_id` dari table *User_Game_Biodata*, dan *User_Game_History* dijadikan foreign key dan dihubungkan dengan `id` dari di-table *User_Games* sehingga setiap table terhubung

Project ini dibuat menggunakan bahasa pemograman Javascript dan framework ExpressJs

Project ini menggunakan ORM (Object Relation Mapping). ORM digunakan untuk menyambungkan applikasi dengan database dan adapter yang digunakan pada project ini adalah Sequelize

Karena ORM tidak bisa berjalan kalau tidak menginisialisasi adapter, kita perlu meng-inisialisasi adapter dapat dilakukan dengan cara:

```
npm install sequelize-cli
```

Sequelize digunakan berfungsi untuk mengubah dan membuat database menggunakan query. Dalam tujuan memindahkan data dari localhost ke server, kita melakukan migrasi pada sequelize dengan cara: 

```
sequelize db:migrate
```

Project ini terdapat beberapa table, pada table *User_Games* dibuat fungsi CRUD (Create, Read, Update, Delete) untuk memanipulasi data user. Fungsi CRUD dibuat menggunakan API

Dalam project ini juga menggunakan middleware: `app.use(express.static('public'));` untuk membaca file 'public' dan middleware: `app.set('view engine', 'ejs');` untuk membaca ejs (yang ada di direktori views) selain itu, middelware: `app.use(express.json());` digunakan untuk data dalam bentuk json dapat dijalankan

Lalu, perlu meng-import data dengan cara membuat variable nama_table dan dalam variable tersebut import data yang ada di direktori models

Bentuk query-nya seperti berikut: `const { User_Game, User_Game_Biodata, User_Game_History } = require('./models');`

Karena pengisian data dalam bentuk form middleware ini perlu dijalankan: `app.use( express.urlencoded ({ extended: false }) );` untuk membaca form yang ada di direktori views

Di dalam dashboard, kalian bisa memanipulasi setiap data dari table *User_Games* berupa membaca data, meng-update data dan meng-delete data. Sehingga pengguna dapat memanipulasi data dengan mudah
