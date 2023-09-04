---
title: "1. API"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api"]
---

API atau singkatan dari Application Programming Interface. Bagaimana car akita berinteraksi antar platform yang berbeda, misal Android dengan web, android dengan desktop ataupun sebaliknya. API adalah jembatan diantara keduanya maupun antar platform yang lain. API disebut juga sebagai web service yang melayani sebuah request ke server, oleh karenanya API berada di web namun bisa di server yang sama maupun di server yang berbeda.

Data yang dikirim maupun diterima dari API memiliki tipe tertentu, saat ini pertukaran data via API yang digunakan berformat JSON atau XML. Format data yang sering digunakan yaitu JSON atau Javascript Object Notation.

Untuk mengakses API perlu beberapa hal yang perlu di set dan disiapkan, diantaranya:

1. Endpoint/URL

Endpoint/url ini adalah lokasi dimana API tersebut berada. Contoh:\
[https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)

2. Method

Metode yang diperlukan atau dibolehkan untuk mengakses API berdasarkan URL yang disediakan. Method yang umum digunakan diantaranya.

- **GET** untuk meminta data
- **POST** untuk input/create data
- **PUT** untuk update data keseluruhan
- **PATCH** untuk update data Sebagian
- **DELETE** untuk menghapus data

Disisi lain, method POST juga bisa digunakan untuk mengakses API update, delete, dan lainnya. Yang paling utama, ikuti saja rule akses API yang dibuat oleh backend developernya.

3. Authentication

Auth ini opsional, jika API nya public maka boleh tanpa menggunakan Authentication. Authentication dibuat atau disimpan pada bagian request header. Namun Kembali lagi ke rule API yang dibuat, apakah wajib ditambahakan Auth atau tidak.

4. Request Header

Schema cara akses API, misal dijelaskan bahwa url yang ingin diakses perlu data di request body yang bertipe ini itu, atau dan juga harus ada auth nya.

5. Request Body

Jika ingin mengirim data ke API untuk keperluan input update delete data, bisa dikirim melalui body pada request API. Data yang dikirim di body request, di hide dan tidak Nampak pada URL.

6. Parameter

Kegunaannya sama seperti data di request body namun sifatnya publik, parameter akan tampil di URL yang mau diakses karena penempatanya wajib di URL/endpoint. Biasa digunakan pada saat meminta data dengan method GET namun dengan beberapa filter atau lainnya, dimana data yang menjadi filter dikirim dari client yang me request.

<br>

Penamaan jenis API yang banyak diperbincangkan developer saat ini dibagi 2, Rest API dan RestFull API. Rest API atau API biasa disebut untuk API yang endpoint nya hanya digunakan untuk kebutuhan 1 action/API tersebut saja. Sedangkan RestFull API, 1 endpoint yang sama bisa digunakan untuk beberapa API, dengan method apa yang digunakan sebagai pembeda antar API.

Contoh Rest API biasa:

https://domain-name/api/note/create.php

endpoint tersebut hanya digunakan untuk 1 API, yaitu membuat data note baru dengan menggunakan method POST.

Contoh RestFull API:

https://domain-name/api/note/

endpoint tersebut bisa digunakan untuk beberapa API.

- GET: mengambil data list note
- POST: menambahkan data note baru
- PUT: mengupdate data note tertentu
- DELETE: menghapus data note tertentu

Setelah request client sampai ke servernya, client akan mendapatkan response. Responsenya bermacam-macam, bisa berhasil, gagal dan lainnya. Yang paling umum dan disarankan untuk mengecek request client apakah berhasil, gagal dan lain sebagainya, menggunakan response status code. Salah satu referensi bisa cek ke sini: [List of HTTP status codes - Wikipedia](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

Data yang dikembalikan dari API berada pada response body, dengan format JSON. Jika request API gagal, response body bisa berformat lain misal html.

Berikut gambaran bagaimana client berinteraksi dengan server menggunakan API/Web Service.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Implementasi API tidak selamanya mengakses endpoint/url, namun ada juga yang sudah dibuat schema tertentu. Misal API Firebase, dari sisi Flutter tinggal menggunakan class dan method yang disediakan. Namun rule nya tetap ada, perlu ikuti rule dari firebase tersebut.

<br>
