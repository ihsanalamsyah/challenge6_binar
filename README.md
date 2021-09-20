# challenge6_binar


Dalam challenge ini saya membuat suatu database menggunakan postgreSQL dan localhost online.
Saya membuat tiga table bernama *User_Games*, *User_Game_Biodata*, dan *User_Game_History* dari setiap table itu terdapat column-column berisi data user.


Table *User_Games* terdapat column `id` dengan type data integer, `username`: string, `password`: string, dan `email`: string.
Table *User_Game_Biodata* terdapat column `id`: integer, `user_id`: integer, `name`: string, `umur`: string, dan `pekerjaan`: string.
Table *User_Game_History* terdapat tiga column `id`: integer, `user_id`: integer, dan `result`: string.


Setiap table terdapat primary key `id`.
Table *User_Game_Biodata*, dan *User_Game_History* terdapat column `user_id` dimana `user_id` menjadi foreign key dari `id` yang terdapat di-table *User_Games*.


Challenge ini dibuat menggunakan bahasa pemograman Javascript dan framework ExpressJs. ORM (Object Relation Mapping) yang digunakan pada challenge ini yaitu Sequelize.
Seuelize digunakan bertujuan untuk dapat membuat dan mengubah database menggunakan query. Dalam tujuan memindahkan data, kita melakukan migrasi pada sequelize
dengan cara `sequelize db:migrate` pada terminal sehingga data sudah masuk kedalam localhost.


Database saya terdapat beberapa table, pada table User_Games saya membuat fungsi CRUD (Create, Read, Update, Delete) untuk memanipulasi table User_Games. Fungsi CRUD
dibuat menggunakan API. Dalam challenge ini juga menggunakan middleware `app.use(express.static('public'));` untuk membaca file 'public' dan `app.set('view engine', 'ejs');`untuk membaca ejs (yang ada di direktori views) dan `app.use(express.json());` sehingga data dalam bentuk json dapat dijalankan. Selain itu saya membuat variable
*nama_table* dan dalam variable tersebut meng-import data dari direktori models sehingga data dapat dimanipulasi. Dan saya membuat middleware
`app.use( express.urlencoded ({ extended: false }) );` untuk membaca form yang ada di direktori views


Di dalam dashboard, kalian bisa memanipulasi setiap data dari table *User_Games* berupa membaca data, meng-update data dan meng-delete data.
