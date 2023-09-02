---
title: "3. Dependency (Package)"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "project", "dependency", "package", "library"]
---

Dependency atau jika di Flutter lebih dikenal dengan package adalah suatu source code (code) bundle yang dibuat untuk mempercepat maupun mempermudah melakukan sesuatu, dimana konteks saat ini dalam pengembangan Flutter.

Ada banyak package untuk Flutter yang mana secara umum dibedakan 2 jenis, pertama package untuk kebutuhan fitur baik itu ui, function, method, kedua package untuk kebutuhan development konfigurasi aplikasi seperti pengaturan icon aplikasi, id aplikasi, testing, dll. Package kebutuhan fitur dibedakan 2 tipe, ada package yang hanya berdasarkan resource framework flutter saja dan ada pula plugin (mengambil resource khusus ke platform tujuan).

Oleh karena ini, maka tidak semua package support untuk semua platform namun ada package yang support beberapa platform saja missal support untuk mobile sehingga hanya bisa dijalankan di device dengan os android dan ios.

Instalasi package atau pendaftaran package yang akan digunakan, disimpan maupun diinstall di `pubspec.yaml` pada bagian **dependencies**. Package fitur diletakkan di dependencies sedangkan package development konfigurasi pada bagian **dev_dependencies**. Flutter memiliki basis tempat download package yaitu di web [pub.dev](https://pub.dev/). di halaman home masing-masing package yang di publish di pub.dev terdapat cara instalasi dan contoh penggunaannya.

Pada gambar dibawah terdapat contoh package **cupertino_icons** untuk mengakses Icon dengan style guide cupertino dari ios (Apple). Dan **flutter_lints** kaitannya dengan file `analysis_options.yaml` untuk mendeteksi jika ada problem ataupun error pada syntax dart.

{{< image src="dependency.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
