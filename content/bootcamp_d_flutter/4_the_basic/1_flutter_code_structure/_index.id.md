---
title: "1. Flutter Code Structure"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "structure"]
---

Lingkup ngoding di Flutter ada beberapa tipe. Namun untuk memperjelas semuanya perlu latihan dan menyelesaikan materi sampai akhir.

| <div style="width: 30px">No</div> | <div style="width:80px">Warna</div> | Deskripsi                                                                                                                                                                                                                                           |
| :-------------------------------: | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                 1                 | Hijau                               | Jika penempatannya didalam class maka bisa diakses didalam class tersebut dan untuk diakses diluar class perlu persyaratan tertentu. Jika di luar class atau langsung dibuat di suatu file, maka akan menjadi global dan dapat diakses dimana saja. |
|                 2                 | Kuning                              | Lingkup function. Intruksi dart code pada umumnya bisa dibuat didalam function. Dimana setiap intruksi selalu diakhiri tanda semi-colon (;).                                                                                                        |
|                 3                 | Biru                                | Lingkup UI, dimana intruksi code ui yang sering disebut widget diterapkan. Biasanya diakhiri dengan coma (,).                                                                                                                                       |
|                 4                 | Merah                               | Jika membuat variable atau function, maka hanya dapat diakses didalam class tersebut saja. Untuk diakses diluar perlu ada persyaratannya. Namun jika diakses dari function build(), dapat langsung diakses karena satu lingkup yang sama.           |

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Struktur utama halaman di Flutter, menggunakan widget Scaffold:

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

**Red**, header halaman menggunakan widget AppBar. Untuk kasus lanjutannya bisa dicustom menggunakan widget lain.

**Blue**, tubuh halaman menggunakan layout tertentu untuk menyusun widget-widget.
2 bagian ini merupakan wilayah halaman utama secara default. Pada studi kasus tertentu untuk mempercantik tampilan, property appBar jarang digunakan dan diganti dengan custom ui.

<br>
