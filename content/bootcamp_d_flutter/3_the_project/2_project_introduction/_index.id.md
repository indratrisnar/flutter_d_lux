---
title: "2. Project Introduction"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "introduction"]
---

Sebelum lanjut ke intri materi, kita kenalan dulu dengan project flutter. Ada apa saja disana, namun gambaran umumnya. Untuk spesifik ke detail masing-masing bagian ada penjelasannya tergantung materi yang berkaitan.

{{< image src="project_structure.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

| <div style="width: 40px">No</div> | <div style="width:200px">Nama</div> | Deskripsi                                                                                                                                                                                                               |
| :-------------------------------: | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                 1                 | .dart_tool                          | Tool sdk dart untuk kebutuhan programming, versinya tergantung dari sdk yang diinstall.                                                                                                                                 |
|                 2                 | .idea                               | Secara umum, berisi settingan visual studio code di computer yang digunakan. Komputer yang lain dapat berbeda settingannya.                                                                                             |
|                 3                 | android                             | Source code untuk implementasi ke platform android. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus android.                                           |
|                 4                 | ios                                 | Source code untuk implementasi ke platform ios. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus ios.                                                   |
|                 5                 | lib                                 | Tempat semua source dart code disimpan, baik itu code ui, function, class, widgets dan lain-lain. Termasuk implementasi clean architecture juga dibuat di dalam folder lib ini.                                         |
|                 6                 | linux                               | Source code untuk implementasi ke platform linux. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus linux.                                               |
|                 7                 | macos                               | Source code untuk implementasi ke platform macos. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus macos.                                               |
|                 8                 | test                                | Sama seperti lib, namun khusus untuk testing. Seperti integration test dan unit test.                                                                                                                                   |
|                 9                 | web                                 | Source code untuk implementasi ke platform web. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus web.                                                   |
|                10                 | windows                             | Source code untuk implementasi ke platform windows. Ada beberapa fitur ataupun package yang mesti disetting khusus pada bagian platform tertentu saja semisal khusus windows.                                           |
|                11                 | .gitignore                          | Settingan untuk menangani source yang akan dikaitkan atau pun tidak dengan git.                                                                                                                                         |
|                12                 | .metadata                           | Informasi terkait project, selengkapnya ada informasi tambahan di dalam file tersebut.                                                                                                                                  |
|                13                 | analysis_options.yaml               | Mengkonfigurasikan analyzer untuk mendeteksi error, warning dan lainnya saat ngoding di workspace.                                                                                                                      |
|                14                 | pubspec.lock                        | Berisi library/package bawaan flutter dan external. File ini tidak boleh diedit manual akan berdampak ke project tidak berjalan dengan semestinya atau bahkan tidak bisa dijalankan sama sekali.                        |
|                15                 | pubspec.yaml                        | Berisi ringkasan informasi project. Tempat pendaftaran package external. Dan pendaftaran asset-asset yang akan digunakan didalam project. Package external yang ditambahkan disini akan masuk otomatis ke pubspec.lock. |
|                16                 | README.md                           | Informasi dan dokumentasi project. Akan tampil pada home page git yang di publish.                                                                                                                                      |
|                17                 | <project_name>.iml                  | Informasi module.                                                                                                                                                                                                       |
|                18                 | build                               | Folder yang berisi source executable hasil export, signing app, dll. Akan muncul jika sudah pernah merunning aplikasi.                                                                                                  |

<br>

Yang boleh kita modifikasi diantaranya platforms folder, lib, test, pubspec.yaml, dan README. .gitignore opsional jika ada beberapa settingan pada saat ingin push source ke git.

Jika ingin mengupload atau membagikan project secara manual tanpa git, bisa menselect semua folder dan file kecuali **.dart_tool**, **.idea**, **build** kemudian menjadikan archive .zip, .rar, atau sejenisnya. Atau bisa juga melakukan `flutter clean` terlebih dahulu di terminal untuk menghapus resource package diluar asset project, kemudian dibuat archive.

<br>
